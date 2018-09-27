From `November 17, 2018` we increased `Emission Supply` by 2.5% to support self-sustainability. This was scheduled and described in [POA Whitepaper](https://github.com/poanetwork/wiki/wiki/POA-Network-Whitepaper#economy), [POA Token Supply](https://github.com/poanetwork/wiki/wiki/POA-Token-Supply#after-the-core-launch), and [RFC issue #14](https://github.com/poanetwork/RFC/issues/14).

Therefore, starting from `November 17, 2018` every block produces **2 POA** instead of **1 POA**: 1 POA is still for validator's reward and a remaining 1 POA is accrued to `EmissionFunds` smart contract which permanently accumulates these funds.

The `EmissionFunds` contract allows to perform the following actions on its balance: `burn` funds, `hold` funds, or `send` them to a specified address. Any of those actions can only be performed as a result of validators' voting with `VotingToManageEmissionFunds` smart contract which interacts with `Governance DApp`.

In order to create a new ballot, a validator should launch `Governance DApp`, open `New Ballot` page, and select the `Emission Funds Ballot` tab.

![](https://raw.githubusercontent.com/poanetwork/wiki/master/assets/imgs/manage-emission-funds/new-ballot.png)

On that page, a validator should enter a ballot description and paste an address of funds receiver which the funds will be sent to if `Send` action obtains the majority of votes.

The field `Current amount of funds` is not editable and just shows the current balance of `EmissionFunds` contract.

Above the `Add Ballot` button we see the note with two dates:

1) The date from which a new ballot can be created (in local time). E.g., as in the screenshot above, it is `December 1, 2018 10:00 AM`. That is, a new ballot can be created not earlier than this date.

2) The date when a ballot will end (in local time). E.g., as on the screen above, the end date is `December 8, 2018 10:00 AM`. This end date is **7 days** in the future relative to the first date mentioned above. `7 days` is so-called `distribution threshold`. The end date doesn't depend on the actual date of the beginning of voting. For example on the screen above, the voting can be started on `3rd December` but it will still have the end date of `December 8, 2018 at 10:00 AM`. Read `Time limitations` section below for more info.

As a result of creating a ballot, its card will appear in a ballot card list. For example (the screenshot of test ballot's card in Sokol network):

![](https://raw.githubusercontent.com/poanetwork/wiki/master/assets/imgs/manage-emission-funds/ballot-card.png)

## Time limitations

Validators can create a ballot of this type every `3 months`. This period of time is called `emission release threshold`.

Validators also have `distribution threshold` of 7 days max when they can make a decision about distribution.

E.g. validator started a ballot 2 days after `emission release threshold` then ballot may have 5 days or less `distribution threshold`.

A validator who created a ballot can cancel the ballot within 15 minutes right after its creation:

![](https://raw.githubusercontent.com/poanetwork/wiki/master/assets/imgs/manage-emission-funds/cancel-ballot.png)

### Example

For example on the first screen above, `emission release threshold` is equal to `December 1, 2018 10:00 AM`. So, we add 7 days (`distribution threshold`) and get `December 8, 10:00 AM` as an end date of the ballot.

Let's assume that a validator created a new ballot on `December 3 at 10:00 AM`. So, validators will have 5 days to give their votes. After `December 8, 10:00 AM` the ballot can be finalized.

After that validators will be able to create the next ballot from `March 1, 2019 10:00 AM` and it will have an end date of `March 8, 2019 10:00 AM`. And so on.

## Notes
- Note that only **one** ballot of this type can be created at a time. Validators cannot create a few ballots of this type in parallel: to be able to create a new ballot, the previous ballot must be finalized.
- In `Sokol` network we have reduced values of `emission release threshold` and `distribution threshold` (for testing purposes):
    * `emission release threshold` is equal to `7 days`
    * `distribution threshold` is equal to `3 days`
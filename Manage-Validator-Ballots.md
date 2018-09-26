## Introduction:

The Manage Validator Ballot Types are used for the following use cases:

* ### Adding a Validator key -- This Ballot should be used for the following use cases:

  * **Use Case 1**:  Add a new Validator via Governance -- To add a new fully qualified Validator (3) Ballots need to be created.
    * Add Key Ballot for mining key -- For this Ballot both the "Affected Key" and "Mining Key" field should be populated with the new Validator's mining key ( _**NOTE:**_ as mining key not part of system yet, will need to add manually in "Mining Key" field )
    * Add Key Ballot for voting key -- For this Ballot the "Affected Key" should be the new Validator's voting key and the "Mining Key" field should be populated with the new Validator's mining key
    * Add Key Ballot for payout key -- For this Ballot the "Affected Key" should be the new Validator's payout key and the "Mining Key" field should be populated with the new Validator's mining key

  * **Use Case 2**:  Adding a missing payout or voting key -- Occasionally, a Validator may get into a state where their mining key is active but they need to add either/both of their voting or payout key.  
    * Add Key Ballot for voting key -- For this Ballot the "Affected Key" should be the new Validator's voting key and the "Mining Key" field should be populated with the Validator's mining key ( _**NOTE:**_ mining key will be available in the "Mining Key" dropdown )
    * Add Key Ballot for payout key -- For this Ballot the "Affected Key" should be the new Validator's payout key and the "Mining Key" field should be populated with the Validator's mining key ( _**NOTE:**_ mining key will be available in the "Mining Key" dropdown )

    Finally, the "Description" field should be populated with:
    * Validator's full name
    * Network being added to, i.e. Sokol or Core
    * Link to profile on Forum
    * Reason text
        
* ### Removing a Validator key

    To remove a Validator, `Remove Key` and `Mining Key` buttons should be clicked on the page `New Ballot` of Governance DApp. Then Mining Key of the removable Validator should be selected in the corresponding drop-down list and this Mining Key should be duplicated in `Affected Key` text field.

    The `Description of the ballot` text field should be populated with:
    * Validator's full name
    * Network being removed from, i.e. Sokol or Core
    * Reason text

* ### Swapping key(s) for an Existing Validator


### Ballot Finalization Order:

- Add Validator: Mining first, voting/payout later
- Swap/Remove Keys: Voting/Payout first, then mining
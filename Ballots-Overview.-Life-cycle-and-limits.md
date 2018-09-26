# Table of Contents
* [Overview](#overview)
* [Types](#types)
* [Lifecycle](#lifecycle)
* [Limits](#limits)

## Overview

A Ballot is a proposal that changes the current state of the network.  

Here are the properties of a given Ballot:
* Ballot Type -- These have been reviewed in the previous section.  Each Ballot Type will have different fields that need to be supplied.
* Ballot End Time -- This defines the time window in which the Ballot is open for voting. Currently, this must be a date/time in the future that allows a reasonable time for other Validators to consider, research and discuss the ballot.  The format is mm/dd/yyyy, hh:mm AM/PM  for example 02/22/2022, 10:00 PM.  <question: which time zone?  Consideration is being given to converting this to an 'hours+minute+seconds from ballot start' format to eliminate possible time zone concerns.>
* Consensus Threshold -- This defines the minimum number of votes for a Ballot to succeed.  Once a ballot has been created this value is immutable.


## Types

* Ballot for keys -- this is the voting to add, remove or swap any type of validator's key: mining, voting, payout.

[//]: # "http://sequencediagram.org/index.html#initialData=C4S2BsFMAIAUHkCC0ByBRAKgdXgJQNLQDi8AamrioigMJoBc0y+aAmtAEKIAy38G0GrjSIMASXgoAUFICGAY2AB7AE7RSPMQBFReKQAdZK0PJCGAdsGJkKVWmmg7YsKQBNZwWQCNZAZxik-GIoRBjwNAAS1ERoLKwAyoKSGLiINBhuHt5+MFy8-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-Cy5wMggA"
![](https://github.com/poanetwork/wiki/raw/master/assets/imgs/dapps-schemes/governance_keys_ballot_creation_scheme.png)


* Ballot to change minimum threshold -- this is the voting to change Consensus threshold

[//]: # "http://sequencediagram.org/index.html#initialData=C4S2BsFMAIAUHkCC0ByBRAKgdXgJQNLQDi8AamrioigMJoBc0yAsgJIrQYASuaAyl3gAZACLQAQoiFD4GaDV6IMreCgBQagIYBjYAHsATtFKbwIACab9BtQAdNB0NpD2AdsGJ6AbpAOvNrtowIpq2tmqWwJoARpoAzjCkeqCuAOYYejQAFgGpzCCuGFkGkHFZeuDm8nruBjrAEVYx8TDipuDJcXzWmqkwNDXAdbqNUbEJ0PiQAJ5xzAG9vtW19aPNE7AGegAe092Gi8tDq2oG0TvQ3ksmZpGGjKyucVHg4HHQzJBR83EA1gA6rlYAFtbIZgO8vMkCqloL8ZoCMHUngAzXzvOJ6YEwBDIFFbYHQApgECmOEzNQ3CxWQzQAC0AD5PD4-AEgtAQmFGPBbJAntBYq9ktBtCUrCAatB7H0tLoQF4rDAiFdWYFgqFwlS7kYADx0unM3z+NUcjWMNpC4AAcneosg4slKMMhJA73Mrts4E000g5kppmp1npTOVLON7M5tkY2T0egS7wtHQ8+hFOTSMGBBWgwGKpXKlTUrmSMCgKI8ehRhtVEbNADEQK93jmYJFNICDbYtmCElUFeAAK6QdsC9rJG3QPlVUDYtSho1s9VhYNJFLpTJpvIFIolMoVKoDFa6RgAKmPdsVieSGWyuUg27ze9P0AAFIDoO-388HMAMCBsQAaN8P3fSdfwAoDgM7PRu19G5B0BABKWVQAVYBEmhNJrw3fJClzXdKiOYYGiLNDoAMEBUiyctKxXGEsNyHD73w-dBiI+hskgbRfjiehh2BOJUgAOgSVxzCWV1oD7CxJIw2F4WmY9h0nbM-xgJkv0cFTsWHDTk1U6AmW0fsDBKdwtKHVwDVcSAAHcR0tIl3hssAsizMxMw8XkjCk7V-kUxTLKlLs41g0xBwMgBeaAAGZhygmDzDgmAAEIoqMky+WAJK-JygKO2CnskugHUoqg3YmPzcxctyylZPotJGLwyrCPqRlNh2PYej6Fqj2gU8+mAKZZnmfw+gMZ8EP-aABsvCF9jqPoJtPZD5UVOAtl2ebDgPY4Rnazauv6VjWoZWjMPXBityavceuAeh5LmBYxqmwUky27rtGO3R3k0cxzB3eMIntOVUJxDbOoObqdqI2rV3qzdcJ3ZroZOobHtGpYUaPU8-NdM7UkQEHIGfKFVyGhDlvqVbSLRkbFiMLGGlpp7Ma+4BGXx+HGqRm7GcYCTSZhclpmgKmfEuIwSNhuiLoaq6eYIxnGWZjGGbZ+h+q+HCYXEaZ8aG59+KEkSxIMCnjzUFX6dujm6tlhGKt59XoEzVwhfky5K2JUAaRsMSxbWq2xtu6XzpvOXEYfRW2cZWaukO26T38vyZtHYAhD-MBYF8LVfaWi2A9IuP3qOw8Gk5+3uajliy71YuE75kVjNMjx3LAKUlh833oAiwEACYAAYB+gAB6bNkjJVx+2BaIlgrSSA21OJQ7XcOHeu6Oy9jtP48h0vdruvrk-81PLUdyp85Xrn5er26653kvE6bjKzNe4UcwVv0K7XqvmJthl657yfjjY+Kcvj7WmOfcwl9v7YRvn-Rm99LS7wWvvNiz8W5BQ6tmDeVRe6uGfPoF40Ap4zznpWLu1h3hjz7ghaAABqaAABGIGhdWgPwbmzK+ld4HIxjgyOc1ZFxRmgHwfs2gghxHeDuMETxICsJBmtWBl1I4IK4YI8MwjgzGEXr7aMYo0JVDfh4DU9oDDvElM2aAZhngKJQmtDRC5TRhA0EAA"
![](https://github.com/poanetwork/wiki/raw/master/assets/imgs/dapps-schemes/governance_min_threshold_ballot_creation_scheme.png)


* Ballot to change proxy contract -- this is the voting to change addresses of proxy smart-contracts# 

[//]: # "http://sequencediagram.org/index.html#initialData=C4S2BsFMAIAUHkCC0ByBRAKgdXgJQNLQDi8AamrioigMJoBc0ysu8AGgJrQBCiAMn3gZoNXGkQYAkvBQAoWQEMAxsAD2AJ2ikF4EABMFa9bIAOC9aCUgzAO2DFVAN0jqbCm0pgARBSZOyDYAUAIwUAZxhSVVAbAHMMVRoAC3dY2HVVAA8ATxFVO3VlYADDEPCYbh1waLCAZSMFWJgafOBClRKg0IjofEhssIBZd0aXPIKizrKe9Kzs+o1R8bbJ2XVgrOgnMe1dQI1GSRswoPBwMOhByCDhsIBrAB0bSQBbEw1gC8dokDjoO-6TwwhWOADMXBcwqoXjAEMhQRkXtBfmAQDp-v1ZLt9IYNNAALQAPgczlc7k80B8fkY8BMkGO0FCZ2i0CU6kghhA+WgZiaihUIEchhgRG2ZI83l8-mx+00AB58fiSS43BLKVLGJVmcAAOQXNkc0Dc0EaJEgC56c0mcAKbKQPRYnQ4owE4mi0mqilUkyMZKqVQRC5a6r2NSslJxGAmDI5WQ2aIwKCg+yqUHK8VejUAMRAZwuwCSMECCieSujqneET00AUej07LCYVLrNa7VD2TpzaZIb10Hp1dAMNk7pV5MlfldURi8USEbSMdyLQmKkYACpVwbhcHoglkqlILMcuvoAAKJ7QC8Xk7mYAYEAwgA058vF-7d8fz5f5cr9sQdYbYRPjYL4XkorZFBgHaQE8ACU-KgEKwCRD8cS7nOh6LuBHTxkh0DqCAsRJCmaZTr8M57nEGHLG29DJJASh3GE9DNi8YSxAAdBENh6GM5rQEKez8ShsQYtkq7Nv20CDjAxLXhYUn3tBNhKnJoaKdAxJKAAruo7J2ApMLNjYkAAO6MlULJ8SZYBJL80C6C8YA8mMAnOhoDzieJyk8hkP56H+9aQI2yIXDhfZvMA2RYsJaGpFRS4rCoRIYQshRNNRRRrquTTAH0AzDG4TTqCeMEPtAOXbp8qWjCV67wYKwpwAu1XpQlbayClDStVhwBEqRqGznFC4ZSuAL5SMRVld20QtTAYHLp8Nb-kFgYBByAqIbCzVdc0PXRdOsWUcNbVFESeVDBNYwnSu64eea-WxIgG2QCe3zTnlMF1UUDW4edBWjJo13FH9l2Az1fUxYNR1zCNwCMHxb1kaJNbPVsmg4ftZGHfOMNA2d-QXYVV09fQ645YMKJxNw2QPXlJ6sRxXE8eon2rrIINE2DC0QwdUM4zksOMI5NhI2NWxpiioC4sYPHfZtvQE-9RWw5jA0UfzmHc4SlV1DtgvQLdnkVRZwB8PeYCwC4MrS7VbNy41OuzSrD3Y-FPUKo7etA4w2m6fS9gOU5dKaK5srQAAvE8ABMAAMMfQAA9FJ0TojYWkvMEYypvxTqymEqvkehx3g9rJu64s3ULVlOUYRgSQNkkqjgHotsF67xcLR7ZdO97rI6Xp9jlgLBYN031aRzYJ5qKc0BpxnWdpqH0sXEnUcwdAADU0AAIxrfbuGexXu0LW3fNu1rI4ZuOPrQLUWlKJ4wUNu8xyQHvG2NS7Z8d4lxSX5619XRaFztLX07JhTVmmvYKUHJ1AXG5AWRM5piiyw-rhf+Y51R+HkEAA"
![](https://github.com/poanetwork/wiki/raw/master/assets/imgs/dapps-schemes/governance_proxy_ballot_creation_scheme.png)

## Lifecycle

Here are the states of a Ballot:
* Created -- This is the process of creating a new Ballot
* Open -- This is the time window where the Ballot will accept votes.  NOTE: A Validator can only vote once per ballot, and the MoC does not possess any voting rights except on Ballots impacting Consensus contracts where MoC participates in consensus
* Closed awaiting Finalization -- When the Ballot End Time expires the Ballot will no longer accept any new votes and the Ballot has not yet been committed to the network.
* Finalized -- After a ballot has expired the ballot must be Finalized, i.e. proposer or other active Validator for associated network must click the "Finalize" button on the ballot.  This commits the result of the Ballot to the network, and if the Ballot was accepted the changes to the network will be applied.

Here is the ballot's voting and finalization lifecycle, for example, for the ballot for validator key:

![](https://github.com/poanetwork/wiki/raw/master/assets/imgs/dapps-schemes/governance_voting_and_finalizing_ballot_for_mining_keys_scheme.png)

## Limits
To prevent Validators from spamming the network with nonsense Ballots, there exist limits on each Ballot type.
At the time of this writing, current limits are as follows:
*  Validator Management Ballot: 9 active ballots at one time
*  Consensus Threshold Ballot: 9 active ballots at one time
*  Modify Proxy Contract Ballot: 9 active ballots at one time
   * *NOTE* For allowed active votes per validator, we currently use the following formula: [200/N] where N= NumberOfActiveValidators (excluding Master of Ceremony).  Example with 21 TotalActiveValidators:  200 / 21 = 9 (as an integer) - this is the maximum active ballots allowed to one Validator.  As a number of Validators increases, this number reduces.

_**NOTE:**_ Ballots need to be thoughtful and should only be proposed by a Validator if they can defend the Ballot and explain the Ballot's benefit to the network.  Inappropriate use or abuse of balloting privileges, or failure of a Validator to participate in offered ballots can be cited in future balloting procedures.
# Table of Contents
* [Overview](#overview)
* [Types](#types)
* [Lifecycle](#lifecycle)
* [Limits](#limits)

## Overview

A Ballot is a proposal that changes the current state of the network.  

Here are the properties of a given Ballot:
* Ballot Type -- These have been reviewed in the previous section.  Each Ballot Type will have different fields that need to be supplied.
* Ballot End Time -- This defines the time window in which the Ballot is open for voting. Currently, this must be a date/time in the future that allows a reasonable time for other Validators to consider, research, and discuss the ballot.  The format is `mm/dd/yyyy, hh:mm AM/PM` (local time), for example, `02/22/2022, 10:00 PM`.  <question: which time zone?  Consideration is being given to converting this to an 'hours+minute+seconds from ballot start' format to eliminate possible time zone concerns.>
* Consensus Threshold -- This defines the minimum number of votes for a Ballot to succeed.  Once a ballot has been created this value is immutable.


## Types

* Ballot for keys -- this is the voting to add, remove, or swap any type of validator's key: mining, voting, payout.

[//]: # "http://sequencediagram.org/index.html#initialData=C4S2BsFMAIAUHkCC0ByBRAKgdXgJQNLQDi8AamrioigMJoBc0y+aAmtAEKIAy38G0GrjSIMASXgoAUFICGAY2AB7AE7RSPMQBFReKQAdZK0PJCGAdsGJkKVWmmg7YsKQBNZwWQCNZAZxik-GIoRBjwNAAS1ERoLKwAyoKSGLiINBhuHt5+MFy8-PHxYakxSSgpaRnunj7+0HHxALLUiDG4ZRXpmTU5cLjwABoJxa0ONMmpXVKQlioAnr6GpuYA5tAADAB0ABxSKl5KAB7QSgBukGoa3Nq6uPQA1Pdi5r6e4OC+0I2Qno1+ANYAHXMYgAtvpVMBPqclKBVtB-pA5sCMCpZC8AGYXT6+JSgmAIZAYlR46AgcxgECycAIpGPKRXG7FaAAWgAfNZyJRqHRHIhnA97vB9DNPj53rDoPIVJAPCAlOZoIYVpB6QpQKcPDASFy7LynC5GTpmQAeFkszm2HkOA2CjjU8CwgDkn2lstACugGNUoLJn1cIEW4Fkc0grnpRturI5Oqt9j5AseNAAFkolP5PvaJVZlFLk+iVbSFvTzLCYFAMVYlBjLdz47bHgAxEDvT7AZMwaqyYEW4BzEUnGuIuaMUHk8krAD0MLhU8McyUAFdgD3oH2B9XoOr5eZGLJXK5JzLQWdIJPfAB3WT6VeyDFYxRhourscU+HD1fix3AF3QGauNcQHxelYzrfV+VgaNAnEEIwkiaJYjYRJxnKSYMEFAAqDC3S1LNvyw6AAApgWgUjSNeIxgAwIDIAAGhIsi-3MVxqPxejFUYr9YQwfs6IYsi7wfYAw3wJEeJFdjGOgfET0kxjBMgR9XFEuY5LI18JxU4EAEo1UUEBNWE9Qglg8IohCRCEg6NCpFLIyVBAFZkyrGtoOCUIzIQhprMqQUU0U-5fHoF9fBWTZ-GYi4-WgTVwBAACZwnIsMNXf9WJgDkKOMdLVyyqiaOgDl5EXFQZUsQD8U-B1JVcEq5U9DlX2gWq0Q9cwquzZq6ra6ATQAXmk2Rjha+r2vMC1zEgC9oC4qxA2gC8wGTcloDiscrBFS5NGNPBARSlLxq3e9FOE5SkWiuy-3BPsOu-cSYHm2L4tvY6lJU+7oqe1xVxAGt9wA1RoEva9pPHVYVPY+QO3kf413zKxJumjT33OybzjULxIBmLcDzDPb8YOi1fugY8zmpQci1o0G3zWebt3OAnGcO4nSdiinEtWSd5yXKxhyphS3vOgBCAbkZWLTmZrVnycB4H9Cp9sPCOoSRPOun9IZ8x0QAsBoplcmObWQHueXZ99sZjCIxMjz4Is7yUM6DB2VgfohiKPBRh89JMIwgB9FVgBU3w-i1lUVEI7Sqf9n48NhXx4mUNEVQjrC9I1LU+kGYYPdKB2bJdrP3ZKMYJkqdk3NM22Ynt0vvceYdg-RWQw6p2aE9UZuYHkBVgDRRRPn+mVfAzelXFlDWM4Lt2Rlz2uMgrm3zOrpCvadtkGmaKg2lXn29sDUhYQnRANcgQjDZU7TU-uOQJ6MjeWm3vPKike+t4oVfy+tuCl8s5C58FR6h8UZzC3CfE4ag7JWxgovLyK8n7pHZK-UY7R4HoUeFhAOjQwbiyRBwOYB9ZyEVBKFcK-4LiX0ttfJBj856f2gd-WBVlUGCjFkWCm45QAeFUFA9yDC7ZwNoevJCm9kE73QebfamDsEqQiIGROcwiHSKRBQ+k1D36oLobwzy-CmH-0eKw4cFMBanXUNtKMxJSTLVeKoOYPDK4-xrqhMuQiEgiJoU4uu9wsIWz3sHbBx8NSnzFhfK+L9hEP3UYIhefDl66I8Wg+480DHnU3MYp8kZmT0xgIDSB19onaNiX-eJiDwlvxQXorxEiLb7yASsAJBlT7n2UVTQMsAQw83qecRRNMQmULCa4iJ5TilsnyVXX+O9oqPENlzdpptDGpNeiYjJeBQGBPAdAXJMgx70wzmooZjsGRfwKeMjRbI8h8AwIUGeJd4m70kTHaqwBuBATALAC4pBqTxS4eHFR18dlGXOQUIuntUGHPoccxxjszSAsucC2etzHjFVKjMKwa1dabVMdcHa7Q+rAgAEzrHWNASca5YTk3MIuUEmM1CbmWbgXwdiYE6KKY7dkMKrk5xuY7H2AdY5UWTEPVM4BXCEVmvdX5YKtFjMhWhaFPALkcuLmI+4SKypWCau2QVShhVekBoY2aa5eKj3HunAF8qgXXNXpK+xjCWVoXZKBPUNoIKCniIueQ8hIDDxJl6iELxVTX22bfAIRzpUCPiVIR11oEyQXZJipkeA-L6xMQa68IojCfE9O2cscjjX-O1DYMCzrnAyCAA"
    [![](https://github.com/poanetwork/wiki/raw/master/assets/imgs/dapps-schemes/governance_keys_ballot_creation_scheme.png)](https://github.com/poanetwork/wiki/raw/master/assets/imgs/dapps-schemes/governance_keys_ballot_creation_scheme.png)


* Ballot to change minimum threshold -- this is the voting to change Consensus threshold for `Validator Management Ballot` and `Consensus Threshold Ballot`.

[//]: # "http://sequencediagram.org/index.html#initialData=C4S2BsFMAIAUHkCC0ByBRAKgdXgJQNLQDi8AamrioigMJoBc0yAsgJIrQYASuaAyl3gAZACLQAQoiFD4GaDV6IMreCgBQagIYBjYAHsATtFKbwIACab9BtQAdNB0NpD2AdsGJ6AbpAOvNrtowIpq2tmqWwJoARpoAzjCkeqCuAOYYejQAFgGpzCCuGFkGkHFZeuDm8nruBjrAEVYx8TDipuDJcXzWmqkwNDXAdbqNUbEJ0PiQAJ5xzAG9vtW19aPNE7AGegAe092Gi8tDq2oG0TvQ3ksmZpGGjKyucVHg4HHQzJBR83EA1gA6rlYAFtbIZgO8vMkCqloL8ZoCMHUngAzXzvOJ6YEwBDIFFbYHQApgECmOEzNQ3CxWQzQAC0AD5PD4-AEgtAQmFGPBbJAntBYq9ktBtCUrCAatB7H0tLoQF4rDAiFdWYFgqFwlS7kYADx0unM3z+NUcjWMNpC4AAcneosg4slKMMhJA73Mrts4E000g5kppmp1npTOVLON7M5tkY2T0egS7wtHQ8+hFOTSMGBBWgwGKpXKlTUrmSMCgKI8ehRhtVEbNADEQK93jmYJFNICDbYtmCElUFeAAK6QdsC9rJG3QPlVUDYtSho1s9VhYNJFLpTJpvIFIolMoVKoDFa6RgAKmPdsVieSGWyuUg27ze9P0AAFIDoO-388HMAMCBsQAaN8P3fSdfwAoDgM7PRu19G5B0BABKWVQAVYBEmhNJrw3fJClzXdKiOYYGiLNDoAMEBUiyctKxXGEsNyHD73w-dBiI+hskgbRfjiehh2BOJUgAOgSVxzCWV1oD7CxJIw2F4WmY9h0nbM-xgJkv0cFTsWHDTk1U6AmW0fsDBKdwtKHVwDVcSAAHcR0tIl3hssAsizMxMw8XkjCk7V-kUxTLKlLs41g0xBwMgBeaAAGZhygmDzDgmAAEIoqMky+WAJK-JygKO2CnskugHUoqg3YmPzcxctyylZPotJGLwyrCPqRlNh2PYej6Fqj2gU8+mAKZZnmfw+gMZ8EP-aABsvCF9jqPoJtPZD5UVOAtl2ebDgPY4Rnazauv6VjWoZWjMPXBityavceuAeh5LmBYxqmwUky27rtGO3R3k0cxzB3eMIntOVUJxDbOoObqdqI2rV3qzdcJ3ZroZOobHtGpYUaPU8-NdM7UkQEHIGfKFVyGhDlvqVbSLRkbFiMLGGlpp7Ma+4BGXx+HGqRm7GcYCTSZhclpmgKmfEuIwSNhuiLoaq6eYIxnGWZjGGbZ+h+q+HCYXEaZ8aG59+KEkSxIMCnjzUFX6dujm6tlhGKt59XoEzVwhfky5K2JUAaRsMSxbWq2xtu6XzpvOXEYfRW2cZWaukO26T38vyZtHYAhD-MBYF8LVfaWi2A9IuP3qOw8Gk5+3uajliy71YuE75kVjNMjx3LAKUlh833oAiwEACYAAYB+gAB6bNkjJVx+2BaIlgrSSA21OJQ7XcOHeu6Oy9jtP48h0vdruvrk-81PLUdyp85Xrn5er26653kvE6bjKzNe4UcwVv0K7XqvmJthl657yfjjY+Kcvj7WmOfcwl9v7YRvn-Rm99LS7wWvvNiz8W5BQ6tmDeVRe6uGfPoF40Ap4zznpWLu1h3hjz7ghaAABqaAABGIGhdWgPwbmzK+ld4HIxjgyOc1ZFxRmgHwfs2gghxHeDuMETxICsJBmtWBl1I4IK4YI8MwjgzGEXr7aMYo0JVDfh4DU9oDDvElM2aAZhngKJQmtDRC5TRhA0EAA"
    [![](https://github.com/poanetwork/wiki/raw/master/assets/imgs/dapps-schemes/governance_min_threshold_ballot_creation_scheme.png)](https://github.com/poanetwork/wiki/raw/master/assets/imgs/dapps-schemes/governance_min_threshold_ballot_creation_scheme.png)


* Ballot to change proxy contract -- this is the voting to change the addresses of smart contracts' implementations.

[//]: # "http://sequencediagram.org/index.html#initialData=C4S2BsFMAIAUHkCC0ByBRAKgdXgJQNLQDi8AamrioigMJoBc0ysu8AGgJrQBCiAMn3gZoNXGkQYAkvBQAoWQEMAxsAD2AJ2ikF4EABMFa9bIAOC9aCUgzAO2DFVAN0jqbCm0pgARBSZOyDYAUAIwUAZxhSVVAbAHMMVRoAC3dY2HVVAA8ATxFVO3VlYADDEPCYbh1waLCAZSMFWJgafOBClRKg0IjofEhssIBZd0aXPIKizrKe9Kzs+o1R8bbJ2XVgrOgnMe1dQI1GSRswoPBwMOhByCDhsIBrAB0bSQBbEw1gC8dokDjoO-6TwwhWOADMXBcwqoXjAEMhQRkXtBfmAQDp-v1ZLt9IYNNAALQAPgczlc7k80B8fkY8BMkGO0FCZ2i0CU6kghhA+WgZiaihUIEchhgRG2ZI83l8-mx+00AB58fiSS43BLKVLGJVmcAAOQXNkc0Dc0EaJEgC56c0mcAKbKQPRYnQ4owE4mi0mqilUkyMZKqVQRC5a6r2NSslJxGAmDI5WQ2aIwKCg+yqUHK8VejUAMRAZwuwCSMECCieSujqneET00AUej07LCYVLrNa7VD2TpzaZIb10Hp1dAMNk7pV5MlfldURi8USEbSMdyLQmKkYACpVwbhcHoglkqlILMcuvoAAKJ7QC8Xk7mYAYEAwgA058vF-7d8fz5f5cr9sQdYbYRPjYL4XkorZFBgHaQE8ACU-KgEKwCRD8cS7nOh6LuBHTxkh0DqCAsRJCmaZTr8M57nEGHLG29DJJASh3GE9DNi8YSxAAdBENh6GM5rQEKez8ShsQYtkq7Nv20CDjAxLXhYUn3tBNhKnJoaKdAxJKAAruo7J2ApMLNjYkAAO6MlULJ8SZYBJL80C6C8YA8mMAnOhoDzieJyk8hkP56H+9aQI2yIXDhfZvMA2RYsJaGpFRS4rCoRIYQshRNNRRRrquTTAH0AzDG4TTqCeMEPtAOXbp8qWjCV67wYKwpwAu1XpQlbayClDStVhwBEqRqGznFC4ZSuAL5SMRVld20QtTAYHLp8Nb-kFgYBByAqIbCzVdc0PXRdOsWUcNbVFESeVDBNYwnSu64eea-WxIgG2QCe3zTnlMF1UUDW4edBWjJo13FH9l2Az1fUxYNR1zCNwCMHxb1kaJNbPVsmg4ftZGHfOMNA2d-QXYVV09fQ645YMKJxNw2QPXlJ6sRxXE8eon2rrIINE2DC0QwdUM4zksOMI5NhI2NWxpiioC4sYPHfZtvQE-9RWw5jA0UfzmHc4SlV1DtgvQLdnkVRZwB8PeYCwC4MrS7VbNy41OuzSrD3Y-FPUKo7etA4w2m6fS9gOU5dKaK5srQAAvE8ABMAAMMfQAA9FJ0TojYWkvMEYypvxTqymEqvkehx3g9rJu64s3ULVlOUYRgSQNkkqjgHotsF67xcLR7ZdO97rI6Xp9jlgLBYN031aRzYJ5qKc0BpxnWdpqH0sXEnUcwdAADU0AAIxrfbuGexXu0LW3fNu1rI4ZuOPrQLUWlKJ4wUNu8xyQHvG2NS7Z8d4lxSX5619XRaFztLX07JhTVmmvYKUHJ1AXG5AWRM5piiyw-rhf+Y51R+HkEAA"
    [![](https://github.com/poanetwork/wiki/raw/master/assets/imgs/dapps-schemes/governance_proxy_ballot_creation_scheme.png)](https://github.com/poanetwork/wiki/raw/master/assets/imgs/dapps-schemes/governance_proxy_ballot_creation_scheme.png)

## Lifecycle

Here are the states of a Ballot:
* Created -- This is the process of creating a new Ballot.
* Open -- This is the time window where the Ballot will accept votes.  NOTE: A Validator can only vote once per ballot, and the MoC does not possess any voting rights.
* Closed awaiting Finalization -- When the Ballot End Time expires the Ballot will no longer accept any new votes and the Ballot has not yet been committed to the network.
* Finalized -- After a ballot has expired the ballot must be Finalized, i.e. proposer or other active Validator for associated network must click the "Finalize" button on the ballot.  This commits the result of the Ballot to the network, and if the Ballot was accepted the changes to the network will be applied.

Here is the ballot's voting and finalization lifecycle, for example, for the ballot for validator key:

[![](https://github.com/poanetwork/wiki/raw/master/assets/imgs/dapps-schemes/governance_voting_and_finalizing_ballot_for_mining_keys_scheme.png)](https://github.com/poanetwork/wiki/raw/master/assets/imgs/dapps-schemes/governance_voting_and_finalizing_ballot_for_mining_keys_scheme.png)

## Limits
To prevent Validators from spamming the network with nonsense Ballots, there exist limits on each Ballot type.
At the time of this writing, current limits are as follows:
*  Validator Management Ballot: 9 active ballots at one time
*  Consensus Threshold Ballot: 9 active ballots at one time
*  Modify Proxy Contract Ballot: 9 active ballots at one time
   * *NOTE* For allowed active votes per validator, we currently use the following formula: [200/N] where N= NumberOfActiveValidators (excluding Master of Ceremony).  Example with 21 TotalActiveValidators:  200 / 21 = 9 (as an integer) - this is the maximum active ballots allowed to one Validator.  As a number of Validators increases, this number reduces.

_**NOTE:**_ Ballots need to be thoughtful and should only be proposed by a Validator if they can defend the Ballot and explain the Ballot's benefit to the network.  Inappropriate use or abuse of balloting privileges, or failure of a Validator to participate in offered ballots can be cited in future balloting procedures.
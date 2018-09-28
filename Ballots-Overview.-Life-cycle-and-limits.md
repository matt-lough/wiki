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

[//]: # "http://sequencediagram.org/index.html#initialData=C4S2BsFMAIAUHkCC0ByBRAKgdXgJQNLQDi8AamrioigMJoBc0y+aAmtAEKIAy38G0GrjSIMASXgoAUFICGAY2AB7AE7RSs8CAAms5SqkAHWStDyQxgHbBiSgG6QVl2ZfkwAIokOGpu4LIAjWQBnGFIlUEsAcwwlGgALFyjIfEgAT2DBJWsVBWBfPUCQmA5NcAjggGV9WWSsnLyC-yDQ6FSMgFkXWsd64FzFJqLW2BUlAA806tUevoH8qUgcjONzaOgABgA6AA4pFQCJ6HtejS0-VXoAaiuxS2D-cHBMjsh-LuCAawAdSzEAW0MqmAmTsERA60+6V+GFy9wAZo5MsElP8YAhkPCxv9oBCwCBNNAoWkblIzjo9KpoABaAB8tgcThcbmgnm81yu8EMS0yQSeEWg8hUkD0IGy0GMyVJeRAdj0MCIJyZrg8Xh85IuagAPNTqQzHM4Vay1RzSvzgAByTJCkWgcXw1Q4kCZbTOwzgWRpSDaUkaylqOn65UstmGDkJJRKUKZM3lGzKQWJaIwYnBUmWCIwKDwmxKeFBw0hk03ABiICemWA8Rgflkvz12kgwSFFjtlnr0GAaW5x3zxMY-zx0QA9GDIlFh8Y0koAK7ADtdnt56Ay7KMWTabTD4X-E7D4IAd1khg7snhiMU3qJ0MsesHlghUWvaQ7fLjVugS20nZAaNJisZQtVW8GlaXCcdYgSJIUnSTIaGyfo8g5AAqZCbXlWMIlQ6AAApfmgAiCIeExgAwX9IAAGnwwjP0sbQyLRKjLBo6A3wiDBu0o6jCLPC9gG9doOO5JiWLRXcRJo3jIEvbR2gkwj70fdpfgASmlRRZXldRwWiSCk2Sdo4IQ+YpAzfjoBUEAoniXN83Ax89Ogwy5iQm4Emkz5gnoDt-mCKItlCOjemdaA5XOUKdKfYlkI7L8GJgeliNMeKOyS0jyOgel5BnFRhWsH80VfMoBW0HLRXFel72gUrcjbIrzWqsq22gLUAF5oH+WRxka2qxXbW9oEsSAD1Y4qbBCg8wHiCFoC0QcbG5NQ-X0b4YpigapJk9pcUyMzP0BLt6rjISYBCsKdFPc9pP42T0hOnbQs0C6BpAfMN2-KlD2PDqhyiOTfnkat5E+TtEhsIaRsUyF0kGyBGVYyAlhXTdvVWtH1r1V6LMgXcwt7Z8KJ+h91hCmUHHRimXvzHd7EJZcx0fSdPVnGxiUJzabu2gBCdqob+m9MepnHafAY41C+wxCarPQVyuraYdJjTycNb8wAe4VCQZ9YqSnFnnwptbVt9SLHOTZz4IaRQ6VGCYphqOoLcQxQUOQ5JgEMrpnGSFQcJUwm3cwkFplyZJfdQ9TQDlcybcmYPZkdkyY7tmYHeMvI6Xs3S4n0mCMhc52blTT2ehUQm2OAOO6nkNPFEyd7hWCaNSUbMmtKTyuYATxpM5ibOnNg-PgDpD3um9weXdW50e8QJXIBwrX+bSFTw6uOQla0kevd6LvBk3kvB4zk2+7Nged+ADkzsi58V1nsXBoiY2IOPgzT5rofaT3sez5dt2Ol+9oOBpB7jhXy-lAqNhUMvZCpJP7bzfofJ+UET552-jcPm19lx4lAP6R+Dln65yMpbd+sC1CoKuKhA2v9-7pAABLOn0GkEB1Cl4rykCQg+YEj5IJfigt+HJ0HEnxhzK8y0qRYlRNAaaDxVAklXj3U2PDCFO2IbBYuX8+E3AoYbNazo-7EyiDPSOc8+btCgTA1Ro84FEIQXg7hBDx43BCgImGy5hHflEWoMmMAqRmVwVnOx5t4EfwsVvUhGjyHaINlPSKhjZRzwXqYwmzpYDMznLEhwTD9GmNYews+Nj-E50CUQxgIUbgLyZtOOcGC3pyxuuoJ6mob5GLvr41evgRTr3Mrkt+ZIuGFNftY2kgcqj207uErRq0A5jW4L+MAsBHAeLDtA1erdzLDI7oPXpiD+m8KITqdZoyHFXGyrlJYNg5pq0WvU84-poCtV+AAJg2BsaAw5OwREJJYGc-wAi9GXKQHgYhPAYDwGmORfT+67OUXSA5KcxnFM0a7N4gcMDxAbvEJQ4BtA4XLidMx4LtmQqUfMfZY0RlwqOScvKNgqpVnRZi78Do1CCPLp2TizcOmRy0rCkO8LlFbNsTs4l6daQAQNMyYCYYbiVBnPINwjdsbBCBPcSAHLVlhAhcg4VgwxXBklaBa5FJ9Dhg1nU1lx5uQmEyOKKsWZ6Fqs6QqJUQFjTeBkEAA"
    [![](https://github.com/poanetwork/wiki/raw/master/assets/imgs/dapps-schemes/governance_keys_ballot_creation_scheme.png)](https://github.com/poanetwork/wiki/raw/master/assets/imgs/dapps-schemes/governance_keys_ballot_creation_scheme.png)


* Ballot to change minimum threshold -- this is the voting to change Consensus threshold for `Validator Management Ballot` and `Consensus Threshold Ballot`.

[//]: # "http://sequencediagram.org/index.html#initialData=C4S2BsFMAIAUHkCC0ByBRAKgdXgJQNLQDi8AamrioigMJoBc0yAsgJIrQYASuaAyl3gAZACLQAQoiFD4GaDV6IMreCgBQagIYBjYAHsATtFKbwIACab9BtQAdNB0NpD2AdsGJ6AbpAOvNrtowIoi2tmqWwJoARpoAzjCkeqCuAOYYejQAFgGpkMwgrhhZBpBxWXrg5vJ67gY6wBFWMfEw4qbgyXF81pp5NXUNTVGxCdD4kACeccwBfb4DwPW6wy1jsAZ6AB6TPYbzi8uNagbR29DeCyZmkYaMrK5xUeDgcdDMkFGzcQDWADquVgAW1shmAby8yUKqWgPymAIw9UeADNfG84nogTAEMhkZsgdBCmAQKZYVM1NcLFZDNAALQAPk8Pj8ASC0BCYUY8FskEe0FiL2S0G0pSsIFq0HseS0uhAXisMCIlxZgWCoXClNuRgAPLTaUzfP5Vez1Yx2oLgAByN4iyBiiXIwwEkBvcwu2zgTSTSDmCmmKnWOmMpXMo1sjm2ejZPR6BJvGi1BKPACub2KpXKlWq5s6jVcyRgUGRHj0yINKvDpoAYiAXm9gFkYJFNAD9eYyiKXKBaq3JZtQQlqvLwMnIL2BbnrdBedVQFi1CHDay1WEg0kUulMjk0vlCumyhUqocGvQAFSn20KnPJc-QAAUAOgT+fTwcwAwICxABpH8+nzOP2-X8-1sftYx9a5Rx-Vw-yfLEgT0AEAEoZVAeVgESKE0gybJcl3IoSgPLNjxWfMMOgAwQFSLISzLddoRw7c8gKAiM0PaoE0GXQo0bbQfjieheyBOJUgAOiTdsjBdaBhwsGSsJhOFJlPXsZ2gOcYEZV9HHUz8x1cfVtI8DToEZbRkwMUp3F0rFxw6IVzAs+0YMZIFCmgRz6m7Vw7ItDynO86BtQAXmgIFNC2fyvPFHyDOgVxIAAd35eyPGkxKwCydyzDcjweSMWStT+FSVLi0C9AHCDTFHUzQoAZl7crKvMSCYAAQlC8zLN5Dxh1HYqBtK-UmvAlrqpgEK+22SZ1MIzMqkGwaKQUxi8JY-d5o42olgaBkNmmvZ6n6Tidu4888mACZplmfw8gMO8kK-aALuvcFDvmB7z1QuUFTgTYdne47tqONR9oB3oga44AGXo7CtzWvc5vYkjgHoJSZjmO6nonZJAZgbRgYaN5NHMcwMzjCI7VldDsX+3YIZgE6QdhzdcJ3dakeIpndvpK6MduhZubOkqXRZxBqcgO9IQ3K6kK+hofvIvmbvmIwhcaZXMcFwndBhlb4fZxG2K5nXUcJCEFLJGaFZ8C4jDI5aN1Ww3WKIo91YZTWBbV02z1PC6WOhK7xEmFm72EsSJN8OXTzUL3VZRvWnYN5ijbdraocYNzXGhK2LjLIlQGpGx2xt3747ulHHYYlP8I25GPfpV7ugZlG-cGl7UqET8wFgXxNWLz7Y7L8jm7xquWed1PXc2lHdTH1v1cYLqrI8HKwElBZCuL6BgoBAAmAAGQ-oAAenU5JSVcZMgWiBZSxk-0tTiau4bZ6f65NqGGQX-ZIdO1G55Fr+0+K9T+VQ7w43fJMHkMdX6syYnXTm7tTbz1Si3P+jNfbCgsqvFKfkGzGyqPAqeSCiEZwAT-dB48l7QCASVDunwwaTHAeYIeJDa4c3IXPWkv8jpYMzjg7q1lyo7Fmtwverg7z6GePFG+d8jAP23tYN45995IWgAAamgAARkpiPNo1DF6mw4e-Mh6dE70kXBWFckZoB8GTNoIIcQ3gZlBI8SA+jqa-UnpwtOs91YLmVGGWxQZjBP2LowGgooMLVCgdATQYQ7QGDeBKBshYXSNFLt48i1iQkmjCBoIAA"
    [![](https://github.com/poanetwork/wiki/raw/master/assets/imgs/dapps-schemes/governance_min_threshold_ballot_creation_scheme.png)](https://github.com/poanetwork/wiki/raw/master/assets/imgs/dapps-schemes/governance_min_threshold_ballot_creation_scheme.png)


* Ballot to change proxy contract -- this is the voting to change the addresses of smart contracts' implementations.

[//]: # "http://sequencediagram.org/index.html#initialData=C4S2BsFMAIAUHkCC0ByBRAKgdXgJQNLQDi8AamrioigMJoBc0ysu8AGgJrQBCiAMn3gZoNXGkQYAkvBQAoWQEMAxsAD2AJ2ikF4EABMFa9bIAOC9aCUgzAO2DFVAN0jqbCm0pgARRCZOyDYAUAIwUAZxhSVVAbAHMMVRoAC3dYyFh1VQAPAE9EPT11SDCwkVU7dWVgAMMQ8JhuHXBosIBlIwU0soqqmqDQiOh8SBywgFl3Tpdu4EqVPrrBjOyc9o0pmbnq2XVg7Ognae1dQI1GSRswoPBwUrHIIImwgGsAHRtJAFsTDWBSx2iIDi0GeI3eGEqlwAZi5SmFVJ8YAhkFDMp9oECwCAdCCRrJjvpDBpoABaAB8DmcrncnmgPj8jHgJkgl2goRu0WgSiKhhA5WgZjSihUIEchhgREO1I83l8-gJp00AB4SSTKS43DK6XLGI0OcAAOSlbmQXn8qEadEgUp6a0mcAKHKQPT4nSEoykimSqma2n0kz0ZKqVQRO6qW1QnJwTK5TZVHhNaKyGzRGBQKH2VRQ9XSv06gBiIBupWASRggQU7zVemK3OsoHKVYFmR+ET00AUBSKJSbSnKs3jwByzKb7OahtKLPboERsm9Gppsr8nqiMXiiRScXSMbyXeKpRo-a29AAVCeTeK9eOz9AABTvaCPp9XczADAgREAGgfT8fU-fX4-r+fY9CoGDDpA342L+j6Ip8qhQTBzaqK2zr5IU+7vAAlMKoBisAkSAnECTJKk24rOh3YHkevQpgR0DqCAsRJJm2arkC66kVuyy5JR+5xiogZlkozxhPQTafGEsQAHQRDYNaaNa0BiicylEbEuI5CeTb-h+MAUi+FgAZATaGW+enQBSSgAK7qEUdjQDOJk2GqY6cnotlmtBFKfEC0AeZUDY2KOib2AFXnQEqAC80CfAoWT+Z5QVNjYkAAO5sqFGKlGlYBJH5ui+fYzKaCp7oaK82naS5yGoXofElNl0B0dAkDfEO+LqSRm5pDxu4YY1h6gcA5J9WslRdENA6CWeaTAMMowTG4aTqLeWGftAc1Xi041TGtZ64aK4rRisu2TTR8xjR053DeS7HERuZF9Q11HDfQoKLZMK0bW5wBnTAIHTX8HZ7iUxQBKaIr4UiO7-QJ1T3ZxPXkbxoOvUD5ILeMX3TFNx5npV1qI4gUOQLeAJrgtWEHVUR30VjS1TJoeO9AzOPMxdI1koj3VPTuL3w4wSkUxxmkdqTByaHRnVrrz3H82j8OYyM2PLbjnOniec1jJicQLdwOSI7ekkyXJCnUyeshs2rHO3dzXWPfLFGKyzgmxbrGkfQc2aYqARLGDWtPQ0MKuMyt8Myxxcu9QrA3o1s5LbX8cOu8AjAE1VW2hXwH5gLALgKv7+2W0Hx1J2010wKnkcPVxMfO3H8MquXKca1ytn2fYhVgAK0xlYq0BRe8ABMAAMo-QAA9I50Q4jY1mfME0xZspbqKmENdI3zDdUUrZIt5XgvQLNDx9RgSTdkkqjgHoxeb9HKP9bvqfN6FFfrDdQOMDZdkssVO6OQvsUK+N9B7vFvGoa4zUF5L00Cvfu-tSjT2HlhaAABqaAABGCGpd6IHw-lXTm99Hb11Ro3VO5J5y5iXAGaArRrJKE8I1bsPxLiQBwVDY6PMSGPwFtXKhvoaGei0Gvf2jAaA8gIu2X6HY-CmnUKUfkpY0zWmqIHTh9EBGLm1H4eQQA"
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
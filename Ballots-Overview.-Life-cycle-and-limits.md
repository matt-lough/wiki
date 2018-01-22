## Overview

A Ballot is a proposal that changes the current state of the network.  

Here are the properties of a given Ballot:
* Ballot Type -- These have been reviewed in the previous section.  Each Ballot Type will have different fields that need to be supplied.
* Ballot End Type -- This defines the time window in which the Ballot is open for voting.  Currently this must be a date/time in the future that allows a reasonable time for other Validators to consider, research and discuss the ballot.  The format is mm/dd/yyyy, hh:mm AM/PM  for example 02/22/2022, 10:00 PM.  <question: which time zone?  Consideration is being given to converting this to an 'hours+minute+seconds from ballot start' format to eliminate possible time zone concerns.>
* Consensus Threshold -- This defines the minimum number of "Yes" votes for a Ballot to succeed.  Once a ballot has been created this value is immutable.

## Life cycle

Here are the states of a Ballot:
* Created -- This is the process of creating a new Ballot
* Open -- This is the time window where the Ballot will accept votes.  NOTE: A Validator can only vote once per ballot, and the MoC does not possess any voting rights except on Ballots impacting Consensus contracts where MoC participates in consensus
* Closed awaiting Finalization -- When the Ballot End Time expires the Ballot will not longer accept any new votes and the Ballot has not yet been committed to the network.
* Finalized -- After a ballot has expired the ballot must be Finalized, i.e. proposer or other active Validator for associated network must click the "Finalize" button on the ballot.  This commits the result of the Ballot to the network, and if the Ballot was accepted the changes to the network will be applied.

## Limits
To prevent Validators from spamming the network with nonsense Ballots, there exists limits on each Ballot type.
Current limits are as follows:
*  Validator Management Ballot: 9 active ballots at one time
*  Consensus Threshold Ballot: 9 active ballots at one time
*  Modify Proxy Contract Ballot: 9 active ballots at one time
 *NOTE* For allowed active votes per validator, we currently use the following formula: [200/((N/2) +1)] where N= NumberOfActiveValidators.  Example with 20 TotalActiveValidators:  200 / ((20/2)+1) = 200/11 = 18 (rounded) - this is the maximum active ballots allowed to one Validator.  As number of Validators increases, this number reduces.

_**NOTE:**_ Ballots need to be thoughtful and should only be proposed by a Validator if they can defend the Ballot and explain the Ballot's benefit to the network.  Inappropriate use or abuse of balloting privileges, or failure of a Validator to participate in offered ballots can be cited in future balloting procedures.
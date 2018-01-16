## Overview

A Ballot is a proposal that changes the current state of the network.  

Here are the properties of a given Ballot:
* Ballot Type -- These have been review in the previous section.  Each Ballot Type will have different fields that need to be supplied.
* Ballot End Type -- This defines the time window in which the Ballot is open for voting.  This must be a date/time in the future that gives a reasonable time for other Validator to consider, research and discuss the a ballot.  The format is mm/dd/yyyy, hh:mm AM/PM  for example 02/22/2022, 10:00 PM.  <question what time zone?>
* Consensus Threshold -- This defines the minimum number of "Yes" votes for a Ballot to succeed.  Once a ballot has been created this value is immutable.

## Life cycle

Here are the states of a Ballot:
* Created -- This is the process of creating a new Ballot
* Open -- This is the time window where the Ballot will accept votes.  NOTE: A Validator can only vote once per ballot and the MoC does not possess any voting rights except on Ballots impacting Consensus contracts at MoC participates in consensus
* Closed awaiting Finalization -- When the Ballot End Time expires the Ballot will not longer accept any new votes however the Ballot has not been committed to the network.
* Finalized -- After a ballot has expired the ballot must be Finalized, i.e. proposer must click Finalize on the ballot.  This commits the result of the Ballot to the network and if the Ballot was accepted the changes to the network will be applied.

## Limits
To prevent Validators from spamming the network with nonsense Ballots, there exists limits on each Ballot type.
The limits are as follows:
*  Validator Management Ballot: 9
*  Consensus Threshold Ballot: 9
*  Modify Proxy Contract Ballot: 9

_**NOTE:**_ Ballots need to be thoughtful and should only be proposed by a Validator if they can defend the Ballot and explain the Ballot's benefit to the network.
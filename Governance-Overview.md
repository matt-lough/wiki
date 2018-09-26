## Introduction

Governance is the process whereby Validators manage themselves and the underlying on-chain contracts related to Consensus to ensure the network's security and performance.  Security of the network is a function of the number of Validators on the network, i.e. the greater number of Validators, the more distributed the network and thus more secure.  That said too many Validators would impact the performance of the network.  The goal of POA Network is to maximize the number and distribution of Validators to secure the network and preserve the performance attributes of the network.

_**NOTE:**_  It is essential for all Validators existing or prospective to review and understand the POA Governance model, the Ballot types and prepare themselves to ask challenging questions of the Ballot proposer and themselves as well as exercising due diligence regarding all ramifications when participating in a Ballot.

To participate fully on the network a Validator needs to possess 3 keys:

* Mining key
     * This key is required to participate in consensus and validate transactions and blocks on the network.  This key must never be compromised and it is duty of the Validator to keep secure at all times.
* Voting key
     * This key is required to participate in Governance and Balloting
* Payout key
    * This key is not strictly required. It is the recipient of mining rewards on a periodic based to reduce the incentive for hacking the mining key.

There are (2) ways for a proposed Validator to receive these key:
1. Initial Ceremony -- 
This is the process to bootstrap a trusted setup by the Master of Ceremony (MoC) of the network.  The MoC invites a set of trusted entities to participate in the network by sending an initial key known to the network via a tamper proof secure channel.  Once the invitee has possession of the initial key, there is a process called the Initial Ceremony implemented as DApp whereby the invitee converts their initial key into the (3) keys mentioned above.  At this point the invitee is able to install a Validator node on the network at which point they will be participating in the Consensus, validating blocks and ensuring the network is secure.

2. Governance -- 
This process involves an existing Validator on the network proposes to add a new Validator via the Ballot.  There are two main reasons to add a Validator:
    * To increase the Validator set to increase the security of the network
    * To replace a Validator removed from the network via Remove Validator Ballot, for malicious behavior or acted in any that impacts the performance or security of the network.  Once the invitee has been identified the proposing Validator requests the invitee to generate the (3) above keys.  The invitee can use this convenient generate keys DApp ( [here](https://ceremony.poa.network/#just-generate-keys) ).

Goverance is implemented as a DApp and currently supports the following Ballots types:

* Validator Management Ballot --
This is the Ballot type used to manage the Validator set and their keys.
   * Add a Validator keys --
     This ballot is used to add a proposed Validator to the network.  The Ballot proposer will need the (3) keys mentioned above, invitee's notary license and address. 
   * Remove Validator keys --
     This ballot is used to remove a Validator.
   * Swap Validator keys --
     This ballot is used only for existing Validators to replace an existing key for a new one, for example if a key is lost or suspected of being compromised.
   
* Consensus Threshold Ballot --
  This ballot is used to increase or decrease the number of "Yes" votes for a Ballot to be approved.

* Modify Proxy Contract Ballot --
  This ballot is used to manage the underlying contracts that control the Consensus mechanisms on chain.  This functionality adds flexibility to the network but also adds complexity and nuance to the Validators role.  For these ballots the Validator must have sophisticated knowledge ( or access to a third-party with such knowledge ) of the existing contracts as well as the impact the new contract will have on the network.


Here is the current landing page of the current "Add Ballot" landing page 

<img src="https://github.com/poanetwork/wiki/blob/master/assets/imgs/governance-add-ballot-page.png" />

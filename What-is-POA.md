# What is POA?

POA is both the name of the Network and the underlying token and refers to Proof of Authority (PoA) Consensus  algorithm used by POA Networks.  In general, PoA is a consensus mechanism where a list of trusted authorities represented as accounts or nodes on the network are responsible for validating transactions and blocks.  In POA Network, Proof of Authority (PoA) is functionally a modified form of Proof of Stake (PoS) where instead of stake with the monetary value, a validator’s identity performs the role of stake. 

Staking identity means voluntarily disclosing who you are in exchange for the right to validate the blocks. This means that the benefits you derive from it are public and so are the nefarious actions you might undertake. Identity placed at stake can serve as a great equalizer, understood and valued the same by all actors. Individuals whose identity (and reputation by extension) is at stake for the securing of a network are incentivized to preserve the network.

The three main conditions that must be fulfilled for a Validator to be established are:

* Identity must be formally verified on-chain, with a possibility to cross-check the information in a publicly available domain
* Eligibility must be difficult to obtain, earned and valued. (Example: potential validators are required to obtain public notary license)
* There must be complete uniformity in the checks and procedures for establishing an Validator.

The final layer in POA Networks is Governance, a collection of DApps where ballots are proposed and voted on by Validators to manage the network. This includes:
* Adding new Validators
* Removing Validators, i.e. for compromising security of network, malicious behavior, non-participation in Governance
* Updating/swapping of one of more Validator keys
* Changing the Approve Ballot Threshold
* Changing Consensus Proxy Contract


Summary of POA Network Features/Benefits:

* Radical Simplification of consensus ( Easy to understand )
* More Reliable Block Generation ( ~5s/block )
* Higher Transaction Throughput
* Energy efficient compared with PoW, i.e. no mining
* Cheaper more efficient network, i.e. lower transactions costs
* Consensus algorithm is PoA also has features of PoS where the stake equal, i.e. the Identity/Reputation of Validators
* Validators have duty to service the network by maintaining their nodes, participation in governance and servicing the needs of network users
* Validators NOT immutable can change by governance, i.e. can be removed by vote for either node unavailability, lack of participation in governance, malicious behavior or any other activity deemed harmful to network
* Maintenance of network, reputation, independence, desire to serve community and reward for creating new blocks incentives for Validators.


For a deeper look into existing consensus algorithms and how they compare with PoA please see below.

# POA compared to Proof of Work ( PoW ).

Proof of Work requires that a certain amount of computational work to be done to solve an arbitrarily difficult mathematical cryptographic puzzle.  This effort is called mining and the probability that one mines a block is proportional to hashing power. In turn hashing power is a function of hardware, network access and energy. In its current state PoW is not only computationally expensive but also grossly inefficient with respect to energy consumption ( see: [PoW PowerCompare Report](https://powercompare.co.uk/bitcoin/) ).  These factors incentivize miners to centralize hashing power rather than creating a truly decentralized network where anyone can participate.  In fact, miners have consolidated into small set of large mining farms or large mining pools and act as defacto authorities on the network.

In addition, to the energy consumption, current PoW networks don't scale well, have low transaction throughput and variable block generation times.


# POA compared to Proof of State/Delegated Proof of Stake  ( PoS/dPoS )

Proof of Stake eliminates the need to spend a huge amount of electric power to validate the blocks. Instead, blockchain participants with the most stake in it are selected by algorithm for the right to validate the blocks. The assumption behind Proof of Stake is the following: those who hold a stake in a network are incentivized to act in its interests. All else equal, the more stake one has, the higher should be his or her interest in preserving the system.  One vulnerability, is the fact that the same size stake may be valued differently by different actors.  This implies there are fundamental inequities among stake holders and thus differing motives for network behavior. This results whole new set of vulnerabilities that don't exist in PoW as high staked entities are incentivized to act in their own interests and not the interests of the network.  Lower stake entities are also higher at risk to malicious behavior such as bribery or coercion via the "nothing at stake" problem.


List of references:
<TBD>


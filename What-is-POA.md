# What is POA?

POA Network is an open, public, permissioned blockchain based on Ethereum protocol. To reach consensus on a global state, it uses a Proof of Authority consensus algorithm. PoA consensus is a straightforward and efficient form of Proof of Stake with known Validators and governance-based penalty system. A list of validators is managed by a smart contract with governance by Validators. During an initial ceremony, master of ceremony distributes keys to 12 independent Validators. They add 12 plus one more to reach initial requirements for the consensus. To be Validators on the network, a master of ceremony asks them to have an active notary public license within the United States. A concerned third party can cross-validate Validators’ identities using open data sources and ensure that each Validator is a good actor with no criminal records. In the proposed network, identity of individual Validator and trust to independent and non-affiliated participants will secure the consensus.

The network is fully compatible with Ethereum protocol. The network supports only Parity client version 1.7 and later. The network supports trusted setup, on-chain governance, and a variety of “proof of identity” oracles. We believe that Oracles Network will close a gap between private and public networks, and will become a model for open networks based on PoA consensus.

### Summary of POA Network Features/Benefits:

* Radical Simplification of Consensus ( Easy to understand, drives adoption )
* More Reliable Block Generation ( ~5s/block )
* Higher Transaction Throughput
* No specialized hardware required ( lower barrier of entry )
* Energy efficient compared with PoW ( no mining )
* Cheaper more efficient network ( lower transactions costs )
* Consensus as a Service
* Horizontal Scaling

For a deeper look into existing consensus algorithms and how they compare with PoA please see below.

### POA compared to Proof of Work ( PoW ).

Proof of Work requires that a certain amount of computational work to be done to solve an arbitrarily difficult mathematical cryptographic puzzle.  This effort is called mining and the probability that one mines a block is proportional to hashing power. In turn hashing power is a function of hardware, network access and energy. In its current state PoW is not only computationally expensive but also grossly inefficient with respect to energy consumption ( see: [PoW PowerCompare Report](https://powercompare.co.uk/bitcoin/) ).  These factors incentivize miners to centralize hashing power rather than creating a truly decentralized network where anyone can participate.  In fact, miners have consolidated into small set of large mining farms or large mining pools and act as defacto authorities on the network.

In addition, to the energy consumption, current PoW networks:
* Don't scale well 
* Have low transaction throughput
* Variable block generation times


### POA compared to Proof of Stake/Delegated Proof of Stake  ( PoS/dPoS )

Proof of Stake eliminates the need to spend a huge amount of electric power to validate the blocks. Instead, blockchain participants with the most stake in it are selected by algorithm for the right to validate the blocks. The assumption behind Proof of Stake is the following: those who hold a stake in a network are incentivized to act in its interests. All else equal, the more stake one has, the higher should be his or her interest in preserving the system.  One vulnerability, is the fact that the same size stake may be valued differently by different actors.  This implies there are fundamental inequities among stake holders and thus differing motives for network behavior. This results whole new set of vulnerabilities that don't exist in PoW as high staked entities are incentivized to act in their own interests and not the interests of the network.  Lower stake entities are also higher at risk to malicious behavior such as bribery or coercion via the "nothing at stake" problem.
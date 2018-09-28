# POA Network

# Abstract

In this paper we propose an open permissioned network based on Ethereum protocol with Proof of Authority consensus by independent validators. 

Keywords: Ethereum, Proof of Authority, Consensus, Validators, Public Notary
Authors: Igor Barinov, Viktor Baranov, Pavel Khahulin


# Introduction

POA Network is an open, public, permissioned blockchain based on Ethereum[^fn1] protocol. To reach consensus on a global state, it uses a Proof of Authority consensus algorithm. PoA consensus is a straightforward and efficient form of Proof of Stake with known validators and governance-based penalty system. A list of validators is managed by a smart contract with governance by validators. During an initial ceremony, master of ceremony distributes keys to 12 independent validators. They add 12 plus one more to reach initial requirements for the consensus. To be validators on the network, a master of ceremony asks them to have an active notary public license within the United States. A concerned third party can cross-validate validators' identities using open data sources and ensure that each validator is a good actor with no criminal records. In the proposed network, identity of individual validator and trust to independent and non-affiliated participants will secure the consensus. 

The network is fully compatible with Ethereum protocol. The network supports only Parity client version 1.7 and later. The network supports trusted setup, on-chain governance, and a variety of "proof of identity" oracles. We believe that POA Network will close a gap between private and public networks, and will become a model for open networks based on PoA consensus.


# Proof of Authority

## AuthorityRound (AuRa)

Aura is one of the Blockchain consensus algorithms available in Parity. It is capable of tolerating up to 50% of malicious nodes with chain reorganizations possible up to a limited depth, dependent on the number of validators, after which finality is guaranteed. This consensus requires a set of validators to be specified, which determines the list of blockchain addresses which participate in the consensus at each height. Sealing a block is the act of collecting transactions and attaching a header to produce a block.[^fn11]

At each step the primary node is chosen that is entitled to seal and broadcast a block, specifically `step modulo #_of_validators`the validator is chosen from the set. Blocks should be always sealed on top of the latest known block in the canonical chain. The block's header includes the step and the primary's signature of the block hash.[^fn11]

Block can be verified by checking that the signature belongs to the correct primary for the given step. Finality of the chain can be achieved within at most `2 x #_of_validator` steps, after more than 50% of the nodes are signed on a chain and then they are signed again on those signatures. [^fn11]

## History of POA

On March 6, 2017, a group of blockchain companies announced[^fn2] new blockchain based on Ethereum protocol with Proof of Authority consensus [^fn3]. Spam attack on the Ropsten testnet was the reason to create a new public test network[^fn4]. This network was named Kovan, for a metro station in Singapore, where companies who founded the network are located. It is a common name convention for Ethereum test networks, for example, Morden, Ropsten, and Rinkeby are names of metro stations.

## Adoption of Kovan blockchain

In the table below we show stats for Main (Homestead) and Test (Kovan) Ethereum networks.


| Network | Type|Blocks mined | Tx created | Contract created | Accounts created |
| -------- | -------- | -------- | -------- | -------- | -------- |
| Kovan    |Testnet | 3,417,527     | 2,859,549     | 54,384     | 18,082     | Text     |
| Homestead    |Mainnet| 4,203,319      | 50,374,359     | 1,488,072     | 4,957,479    | Text     |

Large numbers of transactions, smart contracts, and accounts on the test network show adoption from the community and proven utility benefit. 

# POA Network

## Validators

Independent U.S. public notaries with active commission license will be the first validators in POA Network. For the initial ceremony, 12 initial keys will be created by a master of ceremony. He will distribute those keys to individual validators. Each validator will change a key to a new subset of keys using a client-side DApp. After the initial distribution of licenses, an additional validator can be added through the voting process on the built-in Governance DApp. A majority of votes will be needed from validators to be accepted into the smart contract with a list of validators. 

## Economy

Crowdsale will take place before the launch of the main network.
Purchased coins will be included in the genesis block and will create initial liquidity for the network.
 
Validators will start to create blocks and generate a reward for the network security. For each generated block, a validator who created it will get one coin and all fees for transactions. Each validator has equal rights to create a block. 

The network will start with 12 validators. With 12 validators active, each validator will create one block every 12 blocks. For each block one coin will be created as a reward for validators and one coin for self sustaining of the network.

A block will be generated with an average time of 5 seconds. During the first year of the network, validators will create 31,536,000 sec/5 sec per block = 6,307,200 blocks.

The emission rate for validators is 2.5% for the first year of the network. The network will use disinflation model, and emission will decrease every year. An additional 2.5% will be added to support sustainability of the network.

Therefore, 2.5% of the network supply will be generated as a reward for validators to secure the network. And 2.5% of total supply will be distributed to support sustainability. Validators will be able to propose areas of spending:
- burn coins
- hold coins
- spend on R&D Foundation
 
Sustainability emission will be governed by decentralized apps.

Emission rate. 
X-axis - %, Y-axis - Years
![](https://github.com/poanetwork/wiki/blob/master/assets/imgs/poa/papers/whitepaper/emission-rate.png)


## Use Cases

### Inexpensive Network

POA Network provides inexpensive consensus to secure the network. Users can run Ethereum programs on POA Network and spend less money on transaction fees. Overall cost of the network's security will  also be cheaper due to lower market cap.

#### Problem

Though the issuance of ETH is in a fixed amount each year, the rate of growth of the monetary base (monetary inflation) is not constant. This monetary inflation rate decreases every year, making ETH a disinflationary currency (in terms of monetary base). Disinflation is a special case of inflation in which the amount of inflation shrinks over time.[^fn9]

In 2017 the issuance rate of Ether is 14.75%.[^fn10] Roughly five Ethers per block are issued. Because Ethereum rewards Uncles it means that there may be more or less than five Ethers.[^fn10]

By 9/7/2017 miners generated 21,335,541.72 ETH as Mining Block Reward and 1,181,201.88 Mining Uncle Reward. For securing the network, they received a total of 22,516,743.6 ETH. Using the 9/7/2017 price of $303.86, security of the network costs 22516743.6 ETH * $303.86 = $6,841,937,710.296. 

There are 56,048,767 transactions on the network. Security of a transaction in the main Ethereum network costs are about $122.07 at the current rate.

#### Solution

In POA Network the issuance rate is 2.5% with future disinflation. There is no Mining Uncle Reward in the network, because consensus is not based on Proof of Work.


### Validators with known identity

Each validator of the network will prove his/her identity using "proof of identity" DApps. Each block will be attributed with the identity of a validator. If a miner breaks the rules of the open network, e.g. will not accept a transaction to a specific address, participants of the network will have legal instruments to resolve that problem. 

### Fast network

Validators in POA Network create blocks every five seconds. This rate is tested on Kovan testnet and usable in the long-term. A faster network allows for building new types of applications where response rate from the distributed consensus is important.

### Legally recognizable hard forks

Hard fork is a change of the software. After applying this software, old clients will not be able to work on the new network.
All validators on the network are residents of the U.S. Therefore, they are all located in the same legal system. Hard fork decisions will be signed as legal documents and will be recognizable in a court system. This will bring protections to participants of the network and will open new possibilities to decide how to deal with ongoing changes. 

### Model for experiments

The network is built to iterate fast. In the future many open and independent networks based on Ethereum protocol will operate and have interface for interoperability.


## Security Risks

###  Key compromise

During the initial ceremony, validators will be required to replace their initial keys with a set of three keys. Mining keys are located on a mining node. If a node is compromised, validators will create a ballot using Governance DApp and propose replacement of the mining key. If a voting key is compromised, a validator will ask another validator to create a ballot to replace his/her voting key. If a payout key is compromised, a validator will create a ballot to replace his/her payout key. Because payout is not required, a validator can specify a new payout key on a mining node without proposing ballots.

### Censoring signer 

Censoring signing is an attack vector in which a signer or a group of signers attempts to censor out blocks that vote on removing them from the validators list. To work around this, we restrict the allowed minting frequency of signers to 1 out of N. This ensures that malicious signers need to control at least 51% of signing accounts, at which case it's game over anyway. 

### Regulatory risks

All validators are required to have an active notary commission. Doing block validation under the name of a notary public may be considered as false advertising and a regulator may revoke the notary commission from the validator. The network will mitigate the risk by providing additional identity checks for a validator. Eventually, those unbiased checks will replace the need for a validator to have an active notary commission. 

### Collusion of validators

Validators may become an affiliated group even though we require them to be independent. Before distribution of initial keys, the master of ceremony will require validators to sign a non-affiliation agreement between them and the network. All validators are in the same jurisdiction, where the general public may enforce that agreement.

## Deployment

We provide a deployment script for cloud installation of mining, boot, and general purpose nodes. 
For a validator, setting up a node is a one-button solution. For a mining node, a validator will provide
- Mining Address. The address of the mining key received at the initial ceremony.
- Mining Keyfile. File with the private key of the mining key.
- Mining Keypass. The password to unlock the private key of the mining key. 
- Admin Username. Username of admin user of the virtual machine, e.g. `root`.
- Admin SSH public key. Content of admin's SSH public key. We do not allow use of passwords for the VMs.
- Netstats Server. Network statistics, e.g. number of Active Nodes, Last Block, Avg Block Time, Best Block, Gas Spending, Gas Limit, List of validators with parameters. 
- Netstats Secret. Password to the netstat server.

# Decentralized apps 
The term decentralized app or DApp stands for an application which works with a smart contract and can be deployed on any host and redeployed in case of attack or censorship without any harm to its functions. POA Network provides sets of supported DApps for identity verification, governance, and network administration.

## Initial ceremony DApp
During the initial ceremony a master of ceremony creates a set of keys for each validator. He/She distributes them to validators one by one. Before each distribution of keys, he/she sends a transaction to a smart contract with a list of validators. That smart contract is used by consensus algorithm to determine if a validator has rights to participate in consensus and create blocks. The validator's smart contracts are used by other DApps, e.g. Governance DApp and Payout DApp.

A validator generates three keys in the Initial Ceremony DApp:
* mining key, required to participate in consensus and create blocks.
* voting key, required to create ballots and vote on ballots.
* payout key, not required. Used in Payout DApp to send daily mined coins from the mining key to the payout key. If a mining node should be compromised, an attacker will get daily earnings or less.

All keys are generated on the client side and not transmitted over the Internet without a validator's permission and willingness. When keys are generated, the validator stores them on secure local storage, e.g. saves them to a hardware wallet and the password to a password manager. The validator signs a transaction to the validator's contract with the initial key, provided by the master of ceremony.

Initial ceremony is a required procedure to start a new network based on POA Network's ideas of independent validators.

![](https://github.com/poanetwork/wiki/blob/master/assets/imgs/poa/papers/whitepaper/initial-ceremony.png)

[](http://sequencediagram.org/index.html?initialData=FAQwxgLg9gTgBAWRAZwgU3lAZnAwhtAWygDsBPUSWOANRABsBLAExGnmFYhACMU04AGUao42WgxZtYyYBEYR6AgJIkFjBnDAFi5YMCSoMYnPhhFSZALQA+Q+kymdlgFwBxNCQxsBAdwZKEHAgzMzmyMhoyAA0ADokAA4wjABuPnAA1mhkMSAkzHAJKMi+sMzIcFiw8QCMAExwaUxcMgYoDiZ4zuS2wqLidM3SMMguAMqeBRAAHnC+CgAWcwFoQSFhURXiII2SLTCU8mnoQiJBA3vDsiRQJ8kA5gvnOH3PEkPso7gLaGAZcBAFmw4CQAK6EHjGcTxJpST5wAA8cHqbSMji65l0ZARVlenUGcJkLlwpCwjBghABQKCsP2ywq6zQzE4aHAR3SeIuH1a9ihTkxllsBP240mhWSxwEWTIwXyhWKpRgzOYrMgqQ5Z3xl0+wGFwyF2tg7k83hO-nogWi4vVJ2lVqKEUVzHiVXghEYahI93tIDIUFBECtKVuHvumWyyAAdLrDTBepquYSRqK5TM4MhGPcvAV5oC4B71JppQCoHBzAl6OA0PEC-Ii9k5os4PcTTAfAVpRVDjaBJycHqdX33knkAbuTAXHhSeTKYDgZ25gRgqEmSy2T3Tv1+7HkEA)


## Proof of Identity DApps

In POA Network, identity of individual validators plays a major role for selected consensus. We propose a requirement for the initial validators to have an active notary commission within one of the states of the United States, although notary commission is not an object a validator can control solely. A regulator, e.g. a Secretary of State, may revoke notarial license from a validator, and we propose additional checks of identity, performed in a decentralized way. 

Proof of Identity DApps is a series of decentralized applications focused on connecting a user's identity to his/her wallet. Applications can be run on any Ethereum-compatible network.

### Proof of Physical Address (PoPA) DApp

Using Proof of Physical Address, a user can confirm his/her physical address. It can be used to prove residency.
#### Typical workflow for Identity DApps on PoPA example

![](https://github.com/poanetwork/wiki/blob/master/assets/imgs/poa/papers/whitepaper/proof-of-address.png)


[](http://sequencediagram.org/index.html#initialData=C4S2BsFMAIAUCcD2iBm1VwBYE8DOIBjAQ3GgEEATC+SXXAKHqIOEXmgFVdJ56AHIvFAEQAgHbBoAETJ8+0AO6QARv0HDRRCdNnzu8AG496FIsCLKi3aAGUeR9lIBCaoYU3aAwognxmkslgASRMzCysYb19-W1Y-AHNIVw1xSVhEXEl9A0Ik+mVEAA90B059AC5oILFMknBcaABZSHNGqwBrei4eaABaAD4ZOUUVcvoh+SVlAYnobJ5KmwBXZQBbMGgiKho6aBQ2VYAaAB0xFsxN7doGAuLEUtn5+HKANRIQU2AYADJoMQP3gAvGAgMR8JbAfJFEo9R72BbQADikDOfi+0AIPhQIHgqzMIB8GMQFBgAAoCAQAJTjXRzeHwAZ2QywpyVbh0AliaDtSDYaCk3DtSmnADUGIIoug50u1GuTBYIAMZhgTIeLluMMctKeixA8S5Aj8qxaPAYcOZDMGtKmiwAEmQAMzkqmSwWuvViMxLGiS-64oGQCjQUHgyH+RXKnTDKY06MqAZRYB+FjkYKVAAqAA1Kp46tAaPEQJkeAB9Layuik8s7XDUjX3HqJ5MBNPQN7gD6R-D6r00KF3UpNmKBII5zCQAjtGU1qWFIvABhDlMjhM+JMxGxxIiJRZEIzT66Smz2p0U4ViMXS6uHi-QZTgRCTv5LVbKYzhpXopeSTdsbdJb9UyCGZrVGaBgEKEsPljSZ4ytYYdXAyCPldToSQ-SNZhjc0HEZelpFZOZOlVFkQIQ+lKgpSUryuOh+01KM9Ao6BPHHSdTgggA6FAkFWaAAF5+KlYALmvOgOMKTjWAEoTMWiFNEAUVEYLpC1V3kltR2gAAxUEgzEhoC3nHhA1OAABJDOPvR92gAORfN9eEAld4KYi1KkoCsGk+IgVKeAZ0kyVScgISBKJoZUSz4DJgGIeAgyrWjcEOcVqXQhVPxVfDnHoQKsnsXIBm6Z5pEgDtSmizI4ooLp9DI2DlDGLC4JwhZ6IbLVyPc2wPWgQ0iGNL54DNbV6XqkZGrmD1eySZrpn6ZzWyzHM8yVDtPkgEs5Oxf1QB8LbiUgZ0Uu7T1gG9SA62hDqWLXZsgMqXSxH0pLTgUMALjxWLMFBeJxXoRbgIWu6Ny3HdbrEHiQFWRh6CAA)

User fills out a form in DApp and submits it to the server.

Server consists of a web app and a parity node connected to the blockchain. The node is run under the ethereum account that was used to deploy the PoPA contract (contract's `owner`), and this account needs to be unlocked. It shouldn't have any ether on it though, as it doesn't send any more transactions.

Server validates and normalizes the user's input: removes trailing spaces, converts letters to lower case.
Then it generates a random confirmation code (alphanumeric sequence) and computes its SHA-3 (strictly speaking, keccak256[^fn6]) hash. Also, it generates a random session code (see below), that it stores in memory/database along with the user's eth address and plain text confirmation code.
Then the server combines input data, namely `str2sign = (user's eth address + user's name + all parts of physical address + confirmation code's hash`) into a string that is hashed and signed with the `owner`'s private key. (This is why the `owner`'s account needs to be unlocked. In the next release of web3js it will probably become possible to sign using a private key without unlocking.)

Signature, the confirmation code's hash, the user's normalized input, and the session code are sent back to the client. User then confirms the transaction in MetaMask and invokes the contract's method. The contract combines input data in the same order as the server did, hashes it, and then uses the built-in function `ecrecover` to validate that the signature belongs to the `owner`. If it doesn't, the contract rejects the transaction, otherwise it adds some metadata, most importantly the current block's number, and saves it in the blockchain.

When the transaction is mined, `tx_id` is returned to the client and then via the client to the server, along with the session code. Server queries memory by the session code and validates the user's eth address. Then it fetches the transaction from the blockchain by `tx_id`. It verifies that `tx.to` is equal to `owner` and `tx.from` is equal to the user's eth address. Then, using `tx.blockNumber` the server uses the contract's method to find the physical address added at that blockNumber. User should be limited to registering at most one address per eth block. Since block generation time is less than a minute, it shouldn't be too restrictive on the user.

Having fetched the address from the contract, the server calls postoffice's api (lob.com) to create a postcard. Server uses the session code to get plain text confirmation code from memory and print it on the postcard. Then the server removes this session code from memory to prevent reuse.

When the postcard arrives, the user enters the confirmation code in DApp, DApps gets signature from the server and invokes the contract's method. Contract verifies signature, computes the confirmation code's hash and loops over the user's addresses to find the matching one.

Possible cheating:
1. _user can generate his/her own confirmation code, compute all hashes and submit it to the contract, and then confirm it_
This can't be done because the user doesn't know the `owner`'s private key and therefore can't compute a valid signature. 
2. _user can reuse someone else's confirmation code, or his/her own confirmation code from one of the previously confirmed addresses_
This is prevented by hashing all essential pieces of data together before signing (user's eth address, full physical address, confirmation code) and by checking the address for duplicates in the contract.
3. _user can submit the form, but doesn't sign the transaction_
For this reason the postcard is sent after the address is added to the blockchain and `tx_id` is presented to the server.
4. _user can submit the form and sign the transaction, but sends another address to the server to send postcard to_
After the first transaction is mined, the server sees for itself what address was added and fetches it from the contract instead of trusting the client. Session code is then used to retrieve the corresponding confirmation code. To simpify things, we can limit the user to only submitting a single address per block. In this case, the contract just needs to find the first record with matching `creation_block`.
5. _user can resubmit the same tx_id to the server multiple times_
This is prevented by removing the session code from memory after the first postcard is sent.

### Proof of Bank Account DApp
![](https://github.com/poanetwork/wiki/blob/master/assets/imgs/poa/papers/whitepaper/proof-of-bank.png)
[](http://sequencediagram.org/index.html?initialData=C4S2BsFMAIAUCcD2iBm1XQEIEMB2BraAQQGMTEBXXYAKBuxOEXmgFUBnSeGgB23lAkQfatAAiRHj2gB3SACNe-QcLzBxk6Z3gA3LjQAm2YNnnZO0AMpc9LMZiUCQQkeoDCiavAbqisAJKGxqbmMB5ePlZM3gDmkI4qrlh4hH6BNPKIAB7otmzaAFzQ-rjsJuDg7NAAspAm1eb4NBxc0AC0AHwSUrIKRSTwkAaQ1CDYlTTd0nLynTgExAFF2BTAABYjgsYwFNo086kBnVO98stkkOxVTPgjk5qnxw-atuckl9eIt7gAOrgA1NAGOQqOpcBQALbyLh-QF1NZAgwGQZXDLZXKtE4vLhFABq4xARmAMAAZNBcMwIQSAF4wEC4Hire49bHwOYpRb+IoAMTqJARwMoonBUK4VXkAE8gRcrtAbncDpyniybDjiGQhWDIdD4Ow0TlEHksar4EU3BsSIRgR85YhpSDhdr9JkDUbniaigiALxWAASRAAzAAKeGI5EfWHQMwLEU6yOC0Hkp3wACU+oxdndujVlhAMVw0ARzK0JvaHQ0PRmRXYedwxgog3jGsTsZhAKjHLrEPiJxmZeg4WA3kYnKKABUABpm8bgaCDGIgMpcAD6Ceoy9b3BdGYHniHkTSeIJRJgNfz9cG6cNrUHw98SwHFqtzcdopYkCyi9ot4PRw6P5HSxomwOJq2wPRoFDbAkRRdhI2jQgu0gJsHS1N8aCAA)

In contrast to other identity DApps, PoBA is (from the contract's point of view) a one-step verification process.

DApp client and server are integrated with bank accounting API service (plaid.com).

Client side uses the service's widget (Plaid Link) to authenticate the user, and as a result of successful authentication, access_token is returned from Plaid to the client. User then fills out a form with his/her bank account number and submits it to the server alongside Plaid's access token.

Server consists of a web app and a parity node connected to the blockchain. The node is run under the ethereum account that was used to deploy the PoP contract (contract's `owner`). This account needs to be unlocked.

Server validates and normalizes the user's account number by removing trailing spaces. Then the server fetches the bank account numbers from Plaid using access_token. It checks that the account number submitted by the user is present in the list returned by Plaid.

Server then combines `user's eth address + bank's name + account number` into a single string and hashes it with SHA-3 function. The hash is then signed with `owner`'s private key (this is why `owner` account needs to be unlocked).

Signature, normalized account number, and bank name are returned to the client. User then signs the transaction in MetaMask and invokes the contract's method.

Contract checks that the account number for this bank for this eth address doesn't already exist. If it does, the contract rejects the transaction. Otherwise, it combines parameters in the same order as the server did and computes `sha3` hash of them. Then it uses the built-in `ecrecover` function to validate that the signature belongs to the `owner`. If it doesn't, the contract rejects the transaction, otherwise, it saves the information to the blockchain.

Possible cheating:
1. _user can generate his/her own confirmation code, compute all hashes, and submit it to the contract, and then confirm it_
This can't be done because the user doesn't know the `owner`'s private key and hence can't compute a valid signature. 
2. _user can use someone else's access_token returned by Plaid and thus verify the account he/she has no real access to_
This is equivalent to either hacking someone else's computer or the account's owner deliberately providing the user with his/her access_token. Since all communications with Plaid are via HTTPS protocol, there is no way for the user to intercept access_token sent to someone else.

### Proof of Social Network DApp

![](https://github.com/poanetwork/wiki/blob/master/assets/imgs/poa/papers/whitepaper/proof-of-social.png)

[](http://sequencediagram.org/index.html?initialData=C4S2BsFMAIAUCcD2iBm1XQMqIMYgIbjQBykwA7ovANYBQt+OwV0AqgM6Ty0AO+8oPHwB2waABEAgjx7RykAEa9+gkCLFSZ0TvABuXWgBN8wfAvycsXffAkAhZQJBD8o6AGFEo+IzGTYAJJGJmYWMJ7evljMPgDmkI6q6li4BETCZJQ09AqIAB7oNmw6AFzQAcLspuDg7NAAsmT49RZ0HFzQALQAfJqy8gpltH1yij0jOjZlmACuCgC2YNqphNAZFFTU0DxIKCBQ0AAU7MI8AJTQ4CDCdLkFiEUT1lxlAGqEIMbAMABka1TzD4ALxg1x4M2AtDuhQ6Tz0L2gAHFIBkfN9oDgvHt4IDQF4MYhDDBDjgcGdhtJZJMuD1MM9bOI7GVOOx2CB8dRIABPI7sahnAA6wgA1BicELRWQABbQfCGQzwSCshhMEC6EwwOnwhkOaEPWGU7T06YgWLCbb8fDzMhcdgUrTU+DjQ0DaYACUkAGYSWSJdpqH62WaTDNFX7hADgZBDNAwRCVaB1eiRgN7f0xt0IsAfExoP4AmUACoADTK7kIREVsRAVS4AH0dqh9pBjqdyXqilmc35Am8Pl8YEHhCHFVD8jDbF2ovmy1LIDgtidZJA8jXgHap7n8z1N2JMDF8PFpvh9NpTn7MB7vaTBSLoNLZfLFay-QpwLgtsIZvMFAZfGqNQ8LxsyifcqEPBJdzzQJnS0V1oGAPI60+NNRgUWCqWNBCkM+QM6CJf8kxgFNFFQx1aXpexmToLVHjsDCjW1MpST9B85QVJU7QI1UiKsbV7DHe5HkNR1Z3nANRDyAA6FAkHmaAAF4FPvYAZXY592CFRCpOYRTlMxSJc0QchUTI+kd2A7toILaAADFrhjJdoCrNcuGjIUAAFsKkt8P2Ib9f24KDt16ESsMwYhYGgL58EEicJDCpjoAAdR8WRSVjUREAJYRsVxdlzR4KUfEsElzjM7UGPgnAeFQgYenaeAhka2kVnSTJNjKFpOW2OYrhwbZECqOQwBlGraBa0K4MUMoEAeT4YCuG4EOy1SYB4IaxHIUaMVqkj0KmzCktmBYljWy5rlucd9QZRKpiwHA0pgc6luoAAaaB1SuAc1g6mhoD+Uk4puhKHXC01zSBuEbCqmbtAhkdID9KGXQzYLe2gEsywrT7+w1OsDLykwCoJwkWxvYHO0s6cMfeb7AKHRHKY6dGbPs4RHPPYRttU6BcRwKVrliMVaFZizDL3A8jyA3L4BAeZ6FoIA)

User fills out a form in DApp providing the link to his/her social network profile and submits it to the server.

Server consists of a web app and a parity node connected to the blockchain. The node is run under the ethereum account that was used to deploy the PoSN contract (contract's `owner`). This account needs to be unlocked.

Server validates and normalizes the user's profile link: removes trailing spaces, converts protocol to HTTPS if applicable, domain name to lowercase, and removes extra URL parameters.

Then it generates a random confirmation code (alphanumeric sequence) and computes its SHA-3 (strictly speaking, keccak256[^fn6]) hash. Also, it generates a random session code (see below), that it stores in memory/database along with the user's eth address and plain text confirmation code.
Then server combines input data, namely `str2sign = (user's eth address + user's profile link + confirmation code's hash`) into a string that is hashed and signed with `owner`'s private key (this is why `owner`'s account needs to be unlocked).

Signature, the confirmation code's hash, the user's normalized profile link, and the session code are sent back to the client. User then confirms the transaction in MetaMask and invokes the contract's method. The contract combines input data in the same order as the server did, hashes it, and then uses the built-in function `ecrecover` to validate that the signature belongs to the `owner`. If it doesn't, the contract rejects the transaction, otherwise it adds some metadata, most importantly the current block's number, and saves it in the blockchain.

When the transaction is mined, `tx_id` is returned to the client and then via the client to the server along with the session code. Server queries memory by the session code and validates the user's eth address. Then it fetches the transaction from the blockchain by `tx_id`. It verifies that `tx.to` is equal to `owner` and `tx.from` is equal to the user's eth address. Then, using `tx.blockNumber` the server uses the contract's method to find the profile link added at that blockNumber. User should be limited to registering at most one profile link per eth block.

Then the server uses the session code to get plain text confirmation code from memory and enclose it into a predefined meaningful text, e.g.:
```
My POA identity confirmation code is <confirmation code>
```
(As a side note, it'd be funny if the confirmation code was a random quote from a random book.) Then the server sends this confirmation phrase back to the client and removes the session code from memory to prevent reuse.

User must create a publicly available post where the confirmation phrase would appear alone, on a separate line (there may be other text in this post, on other lines).

Then the user returns to the DApp and submits the link to his/her post. Server needs to scrape this post, find a line starting with the predefined text and extract the confirmation code from it. Server then calculates SHA-3 of the confirmation code and signs it with the `owner`'s private key. Hash of the confirmation code and signature is returned to the client.

User then confirms the transaction in MetaMask, which invokes the contract's method. Contract first of all uses `ecrecover` to verify that the signature belongs to the `owner`. If it doesn't, the contract rejects the transaction, otherwise it computes the confirmation code's hash and loops through the user's profile links to find a matching one. Server must also double-check that post is on the same network that is in the profile link in the contract's data.

Possible cheating:
1. _user can generate his/her own confirmation code, compute all hashes, and submit it to the contract, and then confirm it_
This can't be done because the user doesn't know the `owner`'s private key and therefore can't compute a valid signature. 
2. _user can reuse someone else's confirmation code, or his/her own confirmation code from one of the previously confirmed profile links_
This is prevented by hashing all essential pieces of data together before signing (user's eth address, profile link, confirmation code) and by checking the profile link for duplicates in the contract.
3. _user can submit the form, but doesn't sign the transaction_
For this reason confirmation phrase is sent to the client after the profile link is added to the blockchain and `tx_id` presented to the server.
4. _since user knows confirmation code right from the start (cf. PoPA DApp), he/she can avoid posting the confirmation phrase and just call the contract's method directly_
Link to the post should be presented to the server, which scrapes it, extracts the confirmation code, and then signs it with the `owner`'s private key.
5. _user can post the confirmation phrase on some other social network or website_
Server should double-check that the post is on the same network as the profile link from the contract's data. 
6. _user can resubmit the same tx_id to the server multiple times_
This is prevented by removing the session code from memory after the first postcard is sent.


### Proof of Phone Number DApp

![](https://github.com/poanetwork/wiki/blob/master/assets/imgs/poa/papers/whitepaper/proof-of-phone.png)


[](http://sequencediagram.org/index.html?initialData=C4S2BsFMAIAUCcD2iBm1XQLKIEYinABaIB2kAUOQIYDGwi80AqgM6TzkAOV8oNI3EsGgARAIKdO0AO6QcXHnwFUhoiVLbwAbu3IATKsCo4qbaAGV2OxiIBCC3iH6DhAYVLB4tYWNgBJfUNjUxh3IS86C3ovAHMKbkdnFWFzTHNoXwDyHEQAD3RrZk0ALmg-EhYjcHAWLEgjTFMAa3JWdmgAWgA+cUkZOWLyXqlZHG7h6E1rUvMAVxwAWzBoTmIyaBJZhZx2ABoAHTJgQmgqPT14SBYWbLyC9omp9mKANSpwEANgGAAyDYYFu8QAAvGAgEicWbAW75RCFR5WZ7QADikDIXm+0BopBQIHggNApCxiD0MAAFDQaABKIbqSaI+DdSzaB62Upsa4gIlNSAAT2gZJYTSphwA1FiaGLoPUTmcLlcbt4QFpDDBmfD7DlYfC6U94DMQDESCseFQFvV2DcESzGT06aMZgAJMQAZgp1KlQs9hpIhlmlylJABQNBemg4Mh0KVKsxE1GtL6o26YU83gy-lKABUABqlVzvcDQS4xECVdgAfVWpEgZKrZBpWvujBTER8Gegbw+XxgLB9fsuMKb0BbacyecIkBoTRWaxgkFypeANxHkUyyY8raiDCocRmVB0M+rUvMzrdlJFJHFMtO50u1ylOHAiCnGy2Ow40dVw43afM0R3FArm2fjjPaAzQMAuTlp8CYjHIoF9HqpSQdBeiei0pKfrGYHyNa1hMgyohspMLTqqyCEaAypSUlK15yneNyNnCDy6lRw4TlOhyQQAdCgSALNAAC8gnSscN7yveQi5Nx9BCSJ2LhGmiDSOisH0ja66Kau7YAGLgmGdYwMWi7sJAaEkAAAhB0mPs+TQAHJvroQHpiBdqIWxYi3gq0BfFQal6kyaSueyaJ6OWLALLUtazrsEo0phdDKl+ZE2PYqTpGuXRtPqoiQB8hQZa0mgUf0OCDHG8FdC5Y7QDmeYFtAKpdqq5YKbi+KGFyJBtSSNbnoOzHNj+2l+KUekkAZs6HNIYAnASNCEOCMQSuQNX+JpqaRH+267t+JB8SACzkEAA)

User fills out a form in DApp providing his/her phone number and submits it to the server.

Server consists of a web app and a parity node connected to the blockchain. The node is run under the ethereum account that was used to deploy the PoP contract (contract's `owner`). This account needs to be unlocked.

Server validates and normalizes the user's phone number: removes trailing spaces, converts it to international format.

Then it generates a random confirmation code (alphanumeric sequence) and computes its SHA-3 (strictly speaking, keccak256[^fn6]) hash. Also, it generates a random session code (see below) that it stores in memory/database along with the user's eth address and plain text confirmation code.
Then the server combines input data, namely `str2sign = (user's eth address + user's phone number + confirmation code's hash`) into a string that is hashed and signed with the `owner`'s private key (this is why `owner`'s account needs to be unlocked).

Signature, the confirmation code's hash, the user's normalized phone number, and the session code are sent back to the client. User then confirms the transaction in MetaMask and invokes the contract's method. The contract combines input data in the same order as the server did, hashes it, and then uses the built-in function `ecrecover` to validate that the signature belongs to the `owner`. If it doesn't, the contract rejects the transaction, otherwise it adds some metadata, most importantly the current block's number, and saves it in the blockchain.

When the transaction is mined, `tx_id` is returned to the client and then via the client to the server along with session code. Server queries memory by the session code and validates the user's eth address. Then it fetches the transaction from the blockchain by `tx_id`. It verifies that `tx.to` is equal to `owner` and `tx.from` is equal to the user's eth address. Then, using `tx.blockNumber` the server uses the contract's method to find the phone number added at that blockNumber. User should be limited to registering at most one phone number per eth block.

Then the server uses the session code to get plain text confirmation code from memory and send it via SMS service (twilio.com) to the user's phone number. Then the server removes the session code from memory to prevent reuse.

Having received SMS with verification code, the user returns to the DApp and confirms the transaction in MetaMask, which sends confirmation code to the contract's method directly, without calling the server. There doesn't seem to be any need for signing this transaction with the `owner`'s private key. Contract computes the confirmation code's hash and loops over the user's phone numbers to find a matching one.

Possible cheating:
1. _user can generate his/her own confirmation code, compute all hashes and submit it to the contract, and then confirm it_
This can't be done because the user doesn't know the `owner`'s private key and therefore can't compute a valid signature. 
2. _user can reuse someone else's confirmation code, or his/her own confirmation code from one of the previously confirmed phone numbers_
This is prevented by hashing all essential pieces of data together before signing (user's eth address, phone number, confirmation code) and by checking the phone number for duplicates in the contract.
3. _user can submit the form, but doesn't sign the transaction_
For this reason, SMS is sent after the phone number is added to the blockchain and `tx_id` is presented to the server.
4. _user can submit the form and sign the transaction, but sends another phone number to the server to send SMS to_
After the first transaction is mined, the server sees for itself what phone number was added and fetches it from the contract instead of trusting the client. Session code is then used to retrieve the corresponding confirmation code. To simpify things, we can limit the user to only submitting a single phone number per block. In this case the contract just needs to find the first record with matching `creation_block`.
5. _user can resubmit the same tx_id to the server multiple times_
This is prevented by removing the session code from memory after the first postcard was sent.


## Governance DApp
This client-side DApp provides the list of existing ballots with the ability of filtering by active, unanswered, and expired ballots, and gives the opportunity to create new ballots and to vote for or against notaries.

The governance is available only with a valid voting key that should be selected in the MetaMask Google Chrome plugin.
### Creating a new ballot
[![](https://raw.githubusercontent.com/poanetwork/wiki/master/assets/imgs/poa/papers/whitepaper/new-ballot.png)](https://raw.githubusercontent.com/poanetwork/wiki/master/assets/imgs/poa/papers/whitepaper/new-ballot.png)

[](http://sequencediagram.org/index.html#initialData=C4S2BsFMAIHEHsBukBOA7AhmgxpAXNAEYbjjzDTYqQajxoBQDG2w8K0AqgM6oMAOGFKGwhBaCgBEAgv37QA7pEIChIsVgoBhesBQsK0gAoBJBgBNaGYr2g6J+1tG5t9Ac0hMUheAA9oSKhcvCgEIGguJODc0ACykMAYsRjcANYMPEEAtAB80DJyisoE8PyQEURR5JTUtCD00IIezKwgiLQwBfJKKpkcADxZWfmy3cWVpOQA5DFUNHRo0ABm7AC20CAx5pv84BgAnpDmGSHQuSOFPQRLIKQxxJPAMxtoKwA0lOAg2KkxgDgEACoAfZQGgAK6QIGAXAIGGhyDAUCA3AALCjwJYXMaEMIYsAbGJwxIofbPVbhcJuaCpSD7fHQDBLJaQVhHD4AHVea2W7GWty+aEphKEJJiZRQ3HoJGglkSdIwcho1GOfWgg2GXSK2OgQuJzzFEsw4GlVm5KHWKw4N1IFLp224uwORxO2TyGquvLu2vIwr1qANUplGAYbuUZxyIMchlMBGwUVmukj0FWCWR8HM0DY9PM6Y5aEgCgmZAo4Uz2ATBmcrgwzQMbQ6dnLTmMZhVaojFebBHiiWSaXpUGEtp2e0O6YUYGRGf0EVrDXCK2dHFy7ab0co9BuZpiwGRMD0WG4s8YhIRSNRAQxK6jJhju5+3A+IAx7S+6cQ5Bt1P2DCv0GbYYbBwKxcdhq3wQtqk2ZwMGQdNwkA-dWBaUB2mAGBfxA9xPBIYsMQZJkWXTL98TQQBMAgoHURSTckBSpGlg1GTVVSGDCqw8AgtFqND0weIs5QVIQjheDNd2gL4XAYSBok8ENCDDVjQPYyg43XICnGTHc0wzeAs3MAB6MF+BlGBc29YlSNFP1JSNQMXlLRsKEwsDF2YrJf07OIEiSFJUn7VBiy2YdHTHCcpwPI8XgXFVlwcv81zLV4QC3ES92nQ9WnoH9Yv-c4FKwghKIsxorMNY1ZSgw9YOEq8GMuUM21ipylM4+YhN4yCYnlMpBLgxYdxgcTgEktBjnMGhWlQzpGJ6CxxpQ+t3NMWba0mhDEyazwGCAA)
Valid notary of the POA Network fills out a form in DApp providing:
- *mining key* - mining key of a new or existing notary, which will be voted on
- *affected key type* - key type (mining, payout, or voting key) of a new or existing notary, which will be voted on
- *memo* - brief information about notary, which will be voted on
- *action* - add affected key to the network or remove it from the network

If the affected key type is mining key, the user will be asked to provide personal data of the notary (owner of this mining key) such as full name, physical address, U.S. state name, zip code, notary license ID, and notary license expiration date.

At the final step, one transaction to create a new ballot in POA contract will be pushed to the blockchain to add a new ballot after the user presses "Continue" button. It should be noted, that in case of a mining key, it will be two consistent transactions: to add personal data of a notary and a new ballot to contract. User will see MetaMask popups equal to the number of transactions. After the confirmation and successful mining of the transaction by existing validators, the user will see the created ballot in the list and be able to vote on it.

### Voting on a ballot
[![](https://raw.githubusercontent.com/poanetwork/wiki/master/assets/imgs/poa/papers/whitepaper/ballot-voting.png)](https://raw.githubusercontent.com/poanetwork/wiki/master/assets/imgs/poa/papers/whitepaper/ballot-voting.png)

[](http://sequencediagram.org/index.html#initialData=C4S2BsFMAIHEHsBukBOA7AhmgxpAXNIvKGgOYBQ5G2w8K0AqgM6rkAOGKo2IHaw0ACIBBNm2gB3SACN2nbrywCAwvH4pqA4QAUAkuQAmGYBmkYW0Ves3QmtDaUiUU0+AA9oSVIxYoCINDsMcHAmaABZSBNw8wBrcmZvAFoAPiFRcSlpAmxwEGxYsIAqIoBXTECpFEgDEugAMxBwYFZNEERjGBExSRkE32gAHiSk9J6sggAVAAsYPLtPeuhyrCYqmugzEOIwkDCDPbZwDABPGv7ktO7MmRy8grCAIhKANWIYNHgJEsfN0uBaGhPECtuBiAByMLYTgGaABaDAWbQebAC70Yaja69bKbYJg4CQ6AcRxwsLwNiQNDnRL0VJjG443L5QrQZ5FN4tBp0H6eehsjkwDCkDABOw86T-QHkLFZaCpKzADQ0aA6XQ5PFQtSKmwAWyi03gsIAOvx4NBqNh4OUBKVfIBMAjCRHyTjaHU5CqVWj0aKGIw9NlVBEi0Ti5qgXFJ0AOTCOpw2EjA0wRGkCbTUcLQ9XgPvlWs9Kr0OTUjRQOrCiJg2tTNBAanIn05KBApGmAngS39ysD0GwsweABo4UsOnlYUQSKRoLFICd6+9oE2W22O3mA4We33CoOQEtQcRI66nJ2vbo5Wlj7Z7EL8LjtsAHYRiAFJ0FQHZ8mETXtlmwjC1YfCx5UDWbowBedh0Ne0oZNivpJOBV6OAQABCeL7t+0YYGIkCcBs9QoPAOrLBUayoHhTQtCgg7js+l7GHs3C7GEpS-p0sJZvQYCGDhIGdPS2Lca6fEXqqgm8e6q7KhBDiQEAA)
The user can see all his/her unanswered ballots by clicking on the self-titled button on the filtering panel.
The list of unanswered ballots will be displayed after filtering, and the "Vote now" button will be enabled for any item in the list. After clicking on this button, a preview of the ballot will be opened with the notary's personal data, statistics of voting, and time to ballot's ending. Two buttons will be enabled here: "Vote for" and "Vote against". After clicking on any of them, the transaction to account the user's voice will be generated, and a MetaMask popup will be shown with the transaction information. After the confirmation and successful mining of the transaction by existing validators, the user will see the updated statistics with his/her voice, and the ballot will disappear from the unanswered ballots filter.

Possible cheating:
1. _user can create ballot or vote with his/her own dummy key_ 
It is impossible, because only a valid payout key can govern. It is checked on the contract side.
2. _same user can vote for or against a notary twice_
It is restricted at the contract side.
3. _user can vote after ballot's time has ended_
It is restricted at the contract side.
4. _notary with counterfeit license can become a member of the network_
It is impossible in practice, because any of the voters can check public information about every notary before voting.
5. _user can govern other notaries alone_
It is impossible, because the minimal amount of voices for a ballot is equal to 3.
6. _user can manage the time of a ballot_
Duration of a ballot is constant and equal to 48 hours. It is set in the contract.

# Summary

We believe that such networks with Proof of Authority consensus algorithms will be a trend in public blockchains in the coming years. On-demand systems with trusted validators will play a major role in creating specialized open networks based on Ethereum's protocol. Our goal is to be a model for the generation of networks connected by inter-ledger protocols, such as Polkadot[^fn5] and Cosmos.

# Acknowledgments

We would like to express our gratitude to our mentors, advisors and to the many people in the Ethereum community that have been so welcoming and generous with their knowledge. 

We would also like to thank the organizers and community members that we’ve met at the Silicon Valley and SF Ethereum Meetups including Roman Storm, Joseph Chow, Martin Koppelmann, Grant Hummer, Tom Ding, Chris Peel, Jeff Flowers, and many others.

# Appendix A. Code samples.

## Ballots manager

```
pragma solidity ^0.4.14;

import "./Utility.sol";
import "./ValidatorsManager.sol";

contract BallotsManager is ValidatorsManager {
    /**
    @notice Adds new Ballot
    @param ballotID Ballot unique ID
    @param owner Voting key of notary, who creates ballot
    @param miningKey Mining key of notary, which is proposed to add or remove
    @param affectedKey Mining/payout/voting key of notary, which is proposed to add or remove
    @param affectedKeyType Type of affectedKey: 0 = mining key, 1 = voting key, 2 = payout key
    @param addAction Flag: adding is true, removing is false
    @param memo Ballot's memo
    */
    function addBallot(
        uint ballotID,
        address owner,
        address miningKey,
        address affectedKey,
        uint affectedKeyType,
        bool addAction,
        string memo
    ) {
        assert(checkVotingKeyValidity(msg.sender));
        assert(!(licensesIssued == licensesLimit && addAction));
        assert(ballotsMapping[ballotID].createdAt <= 0);
        if (affectedKeyType == 0) {//mining key
            bool validatorIsAdded = false;
            for (uint i = 0; i < validators.length; i++) {
                assert(!(validators[i] == affectedKey && addAction)); //validator is already added before
                if (validators[i] == affectedKey) {
                    validatorIsAdded = true;
                    break;
                }
            }
            for (uint j = 0; j < disabledValidators.length; j++) {
                assert(disabledValidators[j] != affectedKey); //validator is already removed before
            }
            assert(!(!validatorIsAdded && !addAction)); // no such validator in validators array to remove it
        } else if (affectedKeyType == 1) {//voting key
            assert(!(checkVotingKeyValidity(affectedKey) && addAction)); //voting key is already added before
            assert(!(!checkVotingKeyValidity(affectedKey) && !addAction)); //no such voting key to remove it
        } else if (affectedKeyType == 2) {//payout key
            assert(!(checkPayoutKeyValidity(affectedKey) && addAction)); //payout key is already added before
            assert(!(!checkPayoutKeyValidity(affectedKey) && !addAction)); //no such payout key to remove it
        }
        uint votingStart = now;
        ballotsMapping[ballotID] = Ballot({
            owner: owner,
            miningKey: miningKey,
            affectedKey: affectedKey,
            memo: memo, 
            affectedKeyType: affectedKeyType,
            createdAt: now,
            votingStart: votingStart,
            votingDeadline: votingStart + 48 * 60 minutes,
            votesAmmount: 0,
            result: 0,
            addAction: addAction,
            active: true
        });
        ballots.push(ballotID);
        checkBallotsActivity();
    }
    
    /**
    @notice Gets active ballots' ids
    @return { "value" : "Array of active ballots ids" }
    */
    function getBallots() constant returns (uint[] value) {
        return ballots;
    }
    
    /**
    @notice Gets ballot's memo
    @param ballotID Ballot unique ID
    @return { "value" : "Ballot's memo" }
    */
    function getBallotMemo(uint ballotID) constant returns (string value) {
        return ballotsMapping[ballotID].memo;
    }
    
    /**
    @notice Gets ballot's action
    @param ballotID Ballot unique ID
    @return { "value" : "Ballot's action: adding is true, removing is false" }
    */
    function getBallotAction(uint ballotID) constant returns (bool value) {
        return ballotsMapping[ballotID].addAction;
    }
    
    /**
    @notice Gets mining key of notary
    @param ballotID Ballot unique ID
    @return { "value" : "Notary's mining key" }
    */
    function getBallotMiningKey(uint ballotID) constant returns (address value) {
        return ballotsMapping[ballotID].miningKey;
    }

    /**
    @notice Gets affected key of ballot
    @param ballotID Ballot unique ID
    @return { "value" : "Ballot's affected key" }
    */
    function getBallotAffectedKey(uint ballotID) constant returns (address value) {
        return ballotsMapping[ballotID].affectedKey;
    }

    /**
    @notice Gets affected key type of ballot
    @param ballotID Ballot unique ID
    @return { "value" : "Ballot's affected key type" }
    */
    function getBallotAffectedKeyType(uint ballotID) constant returns (uint value) {
        return ballotsMapping[ballotID].affectedKeyType;
    }

    function toString(address x) internal returns (string) {
        bytes memory b = new bytes(20);
        for (uint i = 0; i < 20; i++)
            b[i] = byte(uint8(uint(x) / (2**(8*(19 - i)))));
        return string(b);
    }

    /**
    @notice Gets ballot's owner full name
    @param ballotID Ballot unique ID
    @return { "value" : "Ballot's owner full name" }
    */
    function getBallotOwner(uint ballotID) constant returns (string value) {
        address ballotOwnerVotingKey = ballotsMapping[ballotID].owner;
        address ballotOwnerMiningKey = votingMiningKeysPair[ballotOwnerVotingKey];
        string storage validatorFullName = validator[ballotOwnerMiningKey].fullName;
        bytes memory ownerName = bytes(validatorFullName);
        if (ownerName.length == 0)
            return toString(ballotOwnerMiningKey);
        else
            return validatorFullName;
    }
    
    /**
    @notice Gets ballot's creation time
    @param ballotID Ballot unique ID
    @return { "value" : "Ballot's creation time" }
    */
    function ballotCreatedAt(uint ballotID) constant returns (uint value) {
        return ballotsMapping[ballotID].createdAt;
    }
    
    /**
    @notice Gets ballot's voting start date
    @param ballotID Ballot unique ID
    @return { "value" : "Ballot's voting start date" }
    */
    function getBallotVotingStart(uint ballotID) constant returns (uint value) {
        return ballotsMapping[ballotID].votingStart;
    }
    
    /**
    @notice Gets ballot's voting end date
    @param ballotID Ballot unique ID
    @return { "value" : "Ballot's voting end date" }
    */
    function getBallotVotingEnd(uint ballotID) constant returns (uint value) {
        return ballotsMapping[ballotID].votingDeadline;
    }
    
    /**
    @notice Gets ballot's amount of votes for
    @param ballotID Ballot unique ID
    @return { "value" : "Ballot's amount of votes for" }
    */
    function getVotesFor(uint ballotID) constant returns (int value) {
        return (ballotsMapping[ballotID].votesAmmount + ballotsMapping[ballotID].result)/2;
    }
    
    /**
    @notice Gets ballot's amount of votes against
    @param ballotID Ballot unique ID
    @return { "value" : "Ballot's amount of votes against" }
    */
    function getVotesAgainst(uint ballotID) constant returns (int value) {
        return (ballotsMapping[ballotID].votesAmmount - ballotsMapping[ballotID].result)/2;
    }
    
    /**
    @notice Checks, if ballot is active
    @param ballotID Ballot unique ID
    @return { "value" : "Ballot's activity: active or not" }
    */
    function ballotIsActive(uint ballotID) constant returns (bool value) {
        return ballotsMapping[ballotID].active;
    }

    /**
    @notice Checks, if ballot is already voted by signer of current transaction
    @param ballotID Ballot unique ID
    @return { "value" : "Ballot is already voted by signer of current transaction: yes or no" }
    */
    function ballotIsVoted(uint ballotID) constant returns (bool value) {
        return ballotsMapping[ballotID].voted[msg.sender];
    }
    
    /**
    @notice Votes
    @param ballotID Ballot unique ID
    @param accept Vote for is true, vote against is false
    */
    function vote(uint ballotID, bool accept) {
        assert(checkVotingKeyValidity(msg.sender));
        Ballot storage v =  ballotsMapping[ballotID];
        assert(v.votingDeadline >= now);
        assert(!v.voted[msg.sender]);
        v.voted[msg.sender] = true;
        v.votesAmmount++;
        if (accept) v.result++;
        else v.result--;
        checkBallotsActivity();
    }

    /**
    @notice Removes element by index from validators array and shift elements in array
    @param index Element's index to remove
    @return { "value" : "Updated validators array with removed element at index" }
    */
    function removeValidator(uint index) internal returns(address[]) {
        if (index >= validators.length) return;

        for (uint i = index; i<validators.length-1; i++){
            validators[i] = validators[i+1];
        }
        delete validators[validators.length-1];
        validators.length--;
    }
    
    /**
    @notice Checks ballots' activity
    @dev Deactivate ballots, if ballot's time is finished and implement action: add or remove notary, if votes for are greater votes against, and total votes are greater than 3
    */
    function checkBallotsActivity() internal {
        for (uint ijk = 0; ijk < ballots.length; ijk++) {
            Ballot storage b = ballotsMapping[ballots[ijk]];
            if (b.votingDeadline < now && b.active) {
                if ((int(b.votesAmmount) >= int(votingLowerLimit)) && b.result > 0) {
                    if (b.addAction) { //add key
                        if (b.affectedKeyType == 0) {//mining key
                            if (licensesIssued < licensesLimit) {
                                licensesIssued++;
                                validators.push(b.affectedKey);
                                InitiateChange(Utility.getLastBlockHash(), validators);
                            }
                        } else if (b.affectedKeyType == 1) {//voting key
                            votingKeys[b.affectedKey] = VotingKey({isActive: true});
                            votingMiningKeysPair[b.affectedKey] = b.miningKey;
                        } else if (b.affectedKeyType == 2) {//payout key
                            payoutKeys[b.affectedKey] = PayoutKey({isActive: true});
                            miningPayoutKeysPair[b.miningKey] = b.affectedKey;
                        }
                    } else { //invalidate key
                        if (b.affectedKeyType == 0) {//mining key
                            for (uint jj = 0; jj < validators.length; jj++) {
                                if (validators[jj] == b.affectedKey) {
                                    removeValidator(jj); 
                                    return;
                                }
                            }
                            disabledValidators.push(b.affectedKey);
                            validator[b.affectedKey].disablingDate = now;
                        } else if (b.affectedKeyType == 1) {//voting key
                            votingKeys[b.affectedKey] = VotingKey({isActive: false});
                        } else if (b.affectedKeyType == 2) {//payout key
                            payoutKeys[b.affectedKey] = PayoutKey({isActive: false});
                        }
                    }
                }
                b.active = false;
            }
        }
    }
}
```

## Validators manager

```
pragma solidity ^0.4.14;

import "oracles-contract-validator/ValidatorClass.sol";
import "./KeysManager.sol";

contract ValidatorsManager is ValidatorClass, KeysManager {
    
    /**
    @notice Adds new notary
    @param miningKey Notary's mining key
    @param zip Notary's zip code
    @param licenseID Notary's license ID
    @param licenseExpiredAt Notary's expiration date
    @param fullName Notary's full name
    @param streetName Notary's address
    @param state Notary's US state full name
    */
    function addValidator(
        address miningKey,
        uint zip,
        uint licenseID,
        uint licenseExpiredAt,
        string fullName,
        string streetName,
        string state
    ) {
        assert(!(!checkVotingKeyValidity(msg.sender) && !checkInitialKey(msg.sender)));
        assert(licensesIssued < licensesLimit);
        validator[miningKey] = Validator({
            fullName: fullName, 
            streetName: streetName, 
            state: state, 
            zip: zip, 
            licenseID: licenseID, 
            licenseExpiredAt: licenseExpiredAt, 
            disablingDate: 0, 
            disablingTX: ""
        });
    }
    
    /**
    @notice Gets active notaries mining keys
    @return { "value" : "Array of active notaries mining keys" }
    */
    function getValidators() constant returns (address[] value) {
        return validators;
    }
    
    /**
    @notice Gets disabled notaries mining keys
    @return { "value" : "Array of disabled notaries mining keys" }
    */
    function getDisabledValidators() constant returns (address[] value) {
        return disabledValidators;
    }
    
    /**
    @notice Gets notary's full name
    @param addr Notary's mining key
    @return { "value" : "Notary's full name" }
    */
    function getValidatorFullName(address addr) constant returns (string value) {
        return validator[addr].fullName;
    }
    
    /**
    @notice Gets notary's address
    @param addr Notary's mining key
    @return { "value" : "Notary's address" }
    */
    function getValidatorStreetName(address addr) constant returns (string value) {
        return validator[addr].streetName;
    }
    
    /**
    @notice Gets notary's state full name
    @param addr Notary's mining key
    @return { "value" : "Notary's state full name" }
    */
    function getValidatorState(address addr) constant returns (string value) {
        return validator[addr].state;
    }
    
    /**
    @notice Gets notary's zip code
    @param addr Notary's mining key
    @return { "value" : "Notary's zip code" }
    */
    function getValidatorZip(address addr) constant returns (uint value) {
        return validator[addr].zip;
    }
    
    /**
    @notice Gets notary's license ID
    @param addr Notary's mining key
    @return { "value" : "Notary's license ID" }
    */
    function getValidatorLicenseID(address addr) constant returns (uint value) {
        return validator[addr].licenseID;
    }
    
    /**
    @notice Gets notary's license expiration date
    @param addr Notary's mining key
    @return { "value" : "Notary's license expiration date" }
    */
    function getValidatorLicenseExpiredAt(address addr) constant returns (uint value) {
        return validator[addr].licenseExpiredAt;
    }

    /**
    @notice Gets notary's disabling date
    @param addr Notary's mining key
    @return { "value" : "Notary's disabling date" }
    */
    function getValidatorDisablingDate(address addr) constant returns (uint value) {
        return validator[addr].disablingDate;
    }
}

```

## Deployment scripts for the mining node

``` 
#!/bin/bash
set -e
set -u
set -x

EXT_IP="$(curl ifconfig.co)"

# Install logentries daemon /*
start_logentries() {
    echo "=====> start_logentries"
    sudo bash -c "echo 'deb http://rep.logentries.com/ trusty main' > /etc/apt/sources.list.d/logentries.list"
    sudo bash -c "gpg --keyserver pgp.mit.edu --recv-keys C43C79AD && gpg -a --export C43C79AD | apt-key add -"
    sudo apt-get update
    sudo apt-get install -y logentries
    sudo le reinit --user-key=0665901a-e843-41c5-82c1-2cc4b39f0b21 --pull-server-side-config=False

    mkdir -p /home/${ADMIN_USERNAME}/logs
    touch /home/${ADMIN_USERNAME}/logs/netstats_daemon.err
    touch /home/${ADMIN_USERNAME}/logs/netstats_daemon.out
    touch /home/${ADMIN_USERNAME}/logs/parity.err
    touch /home/${ADMIN_USERNAME}/logs/parity.out
    touch /home/${ADMIN_USERNAME}/logs/parity.log
    touch /home/${ADMIN_USERNAME}/logs/transferRewardToPayoutKey.out
    touch /home/${ADMIN_USERNAME}/logs/transferRewardToPayoutKey.err

    sudo bash -c "cat >> /etc/le/config << EOF
[install_err]
path = /var/lib/waagent/custom-script/download/0/stderr
destination = AlphaTestTestNet/${EXT_IP}
[install_out]
path = /var/lib/waagent/custom-script/download/0/stdout
destination = AlphaTestTestNet/${EXT_IP}
[netstats_daemon_err]
path = /home/${ADMIN_USERNAME}/logs/netstats_daemon.err
destination = AlphaTestTestNet/${EXT_IP}
[netstats_daemon_out]
path = /home/${ADMIN_USERNAME}/logs/netstats_daemon.out
destination = AlphaTestTestNet/${EXT_IP}
[parity_err]
path = /home/${ADMIN_USERNAME}/logs/parity.err
destination = AlphaTestTestNet/${EXT_IP}
[parity_out]
path = /home/${ADMIN_USERNAME}/logs/parity.out
destination = AlphaTestTestNet/${EXT_IP}
[parity_log]
path = /home/${ADMIN_USERNAME}/logs/parity.log
destination = AlphaTestTestNet/${EXT_IP}
[transferReward_out]
path = /home/${ADMIN_USERNAME}/logs/transferRewardToPayoutKey.out
destination = AlphaTestTestNet/${EXT_IP}
[transferReward_err]
path = /home/${ADMIN_USERNAME}/logs/transferRewardToPayoutKey.err
destination = AlphaTestTestNet/${EXT_IP}
EOF"
    sudo apt-get install -y logentries-daemon
    sudo service logentries start
    echo "<===== start_logentries"
}

start_logentries

# */

echo "========== AlphaTestTestNet/mining-node/install.sh starting =========="
echo "===== current time: $(date)"
echo "===== username: $(whoami)"
echo "===== working directory: $(pwd)"
echo "===== operating system info:"
lsb_release -a
echo "===== memory usage info:"
free -m
echo "===== external ip: ${EXT_IP}"
echo "===== environmental variables:"
printenv

# script parameters
#INSTALL_DOCKER_VERSION="17.03.1~ce-0~ubuntu-xenial"
#INSTALL_DOCKER_IMAGE="parity/parity:v1.6.8"
INSTALL_CONFIG_REPO="https://raw.githubusercontent.com/poanetwork/test-templates/AlphaTestTestNet/TestTestNet/mining-node"
GENESIS_REPO_LOC="https://raw.githubusercontent.com/poanetwork/oracles-scripts/alphadevtestnet/spec.json"
GENESIS_JSON="spec.json"
NODE_TOML="node.toml"
NODE_PWD="node.pwd"

export HOME="${HOME:-/home/${ADMIN_USERNAME}}"

#echo "===== will use docker version: ${INSTALL_DOCKER_VERSION}"
#echo "===== will use parity docker image: ${INSTALL_DOCKER_IMAGE}"
echo "===== repo base path: ${INSTALL_CONFIG_REPO}"

# this should be provided through env by azure template
NETSTATS_SERVER="${NETSTATS_SERVER}"
NETSTATS_SECRET="${NETSTATS_SECRET}"
MINING_KEYFILE="${MINING_KEYFILE}"
MINING_ADDRESS="${MINING_ADDRESS}"
MINING_KEYPASS="${MINING_KEYPASS}"
NODE_FULLNAME="${NODE_FULLNAME:-Anonymous}"
NODE_ADMIN_EMAIL="${NODE_ADMIN_EMAIL:-somebody@somehere}"
ADMIN_USERNAME="${ADMIN_USERNAME}"

prepare_homedir() {
    echo "=====> prepare_homedir"
    #ln -s "$(pwd)" "/home/${ADMIN_USERNAME}/script-dir"
    cd "/home/${ADMIN_USERNAME}"
    mkdir -p logs
    mkdir -p logs/old
    echo "<===== prepare_homedir"
}

add_user_to_docker_group() {
    # based on https://askubuntu.com/questions/477551/how-can-i-use-docker-without-sudo
    echo "=====> add_user_to_docker_group"
    sudo groupadd docker
    sudo gpasswd -a "${ADMIN_USERNAME}" docker
    newgrp docker
    echo "===== Groups: "
    groups
    echo "<===== add_user_to_docker_group"
}

install_ntpd() {
    echo "=====> install_ntpd"
    sudo timedatectl set-ntp no
    sudo apt-get -y install ntp

    sudo bash -c "cat > /etc/cron.hourly/ntpdate << EOF
#!/bin/sh
sudo service ntp stop
sudo ntpdate -s ntp.ubuntu.com
sudo service ntp start
EOF"
    sudo chmod 755 /etc/cron.hourly/ntpdate
    echo "<===== install_ntpd"
}

install_haveged() {
    echo "=====> install_haveged"
    sudo apt-get -y install haveged
    sudo update-rc.d haveged defaults
    echo "<===== install_haveged"
}

allocate_swap() {
    echo "=====> allocate_swap"
    sudo apt-get -y install bc
    #sudo fallocate -l $(echo "$(free -b | awk '/Mem/{ print $2 }')*2"  | bc -l) /swapfile
    sudo fallocate -l 1G /swapfile
    sudo chmod 600 /swapfile
    sudo mkswap /swapfile
    sudo swapon /swapfile
    sudo sh -c "printf '/swapfile   none    swap    sw    0   0\n' >> /etc/fstab"
    sudo sh -c "printf 'vm.swappiness=10\n' >> /etc/sysctl.conf"
    sudo sysctl vm.vfs_cache_pressure=50
    sudo sh -c "printf 'vm.vfs_cache_pressure = 50\n' >> /etc/sysctl.conf"
    echo "<===== allocate_swap"
}

install_nodejs() {
    echo "=====> install_nodejs"
    # curl -sL https://deb.nodesource.com/setup_0.12 | bash -
    curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
    sudo apt-get update
    sudo apt-get install -y build-essential git unzip wget nodejs ntp cloud-utils

    # add symlink if it doesn't exist
    [[ ! -f /usr/bin/node ]] && sudo ln -s /usr/bin/nodejs /usr/bin/node
    echo "<===== install_nodejs"
}

install_docker_ce() {
    echo "=====> install_docker_ce"
    sudo apt-get -y install apt-transport-https ca-certificates curl software-properties-common
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
    sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
    sudo apt-get update
    sudo apt-get -y install docker-ce=${INSTALL_DOCKER_VERSION}
    sudo docker pull ${INSTALL_DOCKER_IMAGE}
    echo "<===== install_docker_ce"
}

pull_image_and_configs() {
    echo "=====> pull_image_and_configs"

    # curl -s -O "${INSTALL_CONFIG_REPO}/../${GENESIS_JSON}"
    curl -s -o "${GENESIS_JSON}" "${GENESIS_REPO_LOC}"
    curl -s -O "${INSTALL_CONFIG_REPO}/${NODE_TOML}"
    sed -i "/\[network\]/a nat=\"extip:${EXT_IP}\"" ${NODE_TOML}
    cat >> ${NODE_TOML} <<EOF
[misc]
logging="engine=trace,network=trace,discovery=trace"
log_file = "/home/${ADMIN_USERNAME}/logs/parity.log"
[account]
password = ["${NODE_PWD}"]
unlock = ["${MINING_ADDRESS}"]
[mining]
force_sealing = true
engine_signer = "${MINING_ADDRESS}"
reseal_on_txs = "none"
EOF
    echo "${MINING_KEYPASS}" > "${NODE_PWD}"
    mkdir -p parity/keys/OraclesPoA
    echo ${MINING_KEYFILE} | base64 -d > parity/keys/OraclesPoA/mining.key.${MINING_ADDRESS}
    echo "<===== pull_image_and_configs"
}

# based on https://get.parity.io
install_netstats() {
    echo "=====> install_netstats"
    git clone https://github.com/poanetwork/eth-net-intelligence-api
    cd eth-net-intelligence-api
    #sed -i '/"web3"/c "web3": "0.19.x",' package.json
    npm install
    sudo npm install pm2 -g

    cat > app.json << EOL
[
    {
        "name"                 : "netstats_daemon",
        "script"               : "app.js",
        "log_date_format"      : "YYYY-MM-DD HH:mm:SS Z",
        "error_file"           : "/home/${ADMIN_USERNAME}/logs/netstats_daemon.err",
        "out_file"             : "/home/${ADMIN_USERNAME}/logs/netstats_daemon.out",
        "merge_logs"           : false,
        "watch"                : false,
        "max_restarts"         : 100,
        "exec_interpreter"     : "node",
        "exec_mode"            : "fork_mode",
        "env":
        {
            "NODE_ENV"         : "production",
            "RPC_HOST"         : "localhost",
            "RPC_PORT"         : "8545",
            "LISTENING_PORT"   : "30300",
            "INSTANCE_NAME"    : "${NODE_FULLNAME}",
            "CONTACT_DETAILS"  : "${NODE_ADMIN_EMAIL}",
            "WS_SERVER"        : "http://${NETSTATS_SERVER}:3000",
            "WS_SECRET"        : "${NETSTATS_SECRET}",
            "VERBOSITY"        : 2
        }
    }
]
EOL
    cd ..
    cat > netstats.start <<EOF
cd eth-net-intelligence-api
pm2 startOrRestart app.json
cd ..
EOF
    chmod +x netstats.start
    sudo -u root -E -H ./netstats.start
    echo "<===== install_netstats"
}

install_netstats_via_systemd() {
    echo "=====> install_netstats_via_systemd"
    git clone https://github.com/poanetwork/eth-net-intelligence-api
    cd eth-net-intelligence-api
    #sed -i '/"web3"/c "web3": "0.19.x",' package.json
    npm install
    sudo npm install pm2 -g

    cat > app.json << EOL
[
    {
        "name"                 : "netstats_daemon",
        "script"               : "app.js",
        "log_date_format"      : "YYYY-MM-DD HH:mm:SS Z",
        "error_file"           : "/home/${ADMIN_USERNAME}/logs/netstats_daemon.err",
        "out_file"             : "/home/${ADMIN_USERNAME}/logs/netstats_daemon.out",
        "merge_logs"           : false,
        "watch"                : false,
        "max_restarts"         : 100,
        "exec_interpreter"     : "node",
        "exec_mode"            : "fork_mode",
        "env":
        {
            "NODE_ENV"         : "production",
            "RPC_HOST"         : "localhost",
            "RPC_PORT"         : "8545",
            "LISTENING_PORT"   : "30300",
            "INSTANCE_NAME"    : "${NODE_FULLNAME}",
            "CONTACT_DETAILS"  : "${NODE_ADMIN_EMAIL}",
            "WS_SERVER"        : "http://${NETSTATS_SERVER}:3000",
            "WS_SECRET"        : "${NETSTATS_SECRET}",
            "VERBOSITY"        : 2
        }
    }
]
EOL
    cd ..
    sudo bash -c "cat > /etc/systemd/system/oracles-netstats.service <<EOF
[Unit]
Description=oracles netstats service
After=network.target
[Service]
Type=oneshot
RemainAfterExit=true
User=${ADMIN_USERNAME}
Group=${ADMIN_USERNAME}
Environment=MYVAR=myval
WorkingDirectory=/home/${ADMIN_USERNAME}/eth-net-intelligence-api
ExecStart=/usr/bin/pm2 startOrRestart app.json
[Install]
WantedBy=multi-user.target
EOF"
    sudo systemctl enable oracles-netstats
    sudo systemctl start oracles-netstats
    echo "<===== install_netstats_via_systemd"
}

start_docker() {
    echo "=====> start_docker"
    cat > docker.start <<EOF
sudo docker run -d \\
    --name oracles-poa \\
    -p 30300:30300 \\
    -p 30300:30300/udp \\
    -p 8080:8080 \\
    -p 8180:8180 \\
    -p 8545:8545 \\
    -v "$(pwd)/${NODE_PWD}:/build/${NODE_PWD}" \\
    -v "$(pwd)/parity:/build/parity" \\
    -v "$(pwd)/${GENESIS_JSON}:/build/${GENESIS_JSON}" \\
    -v "$(pwd)/${NODE_TOML}:/build/${NODE_TOML}" \\
    ${INSTALL_DOCKER_IMAGE} --config "${NODE_TOML}" > logs/docker.out 2> logs/docker.err
container_id="\$(cat logs/docker.out)"
sudo ln -sf "/var/lib/docker/containers/\${container_id}/\${container_id}-json.log" logs/parity.log
EOF
    chmod +x docker.start
    ./docker.start
    echo "<===== start_docker"
}

use_deb() {
    echo "=====> use_deb"
    curl -LO 'http://parity-downloads-mirror.parity.io/v1.7.0/x86_64-unknown-linux-gnu/parity_1.7.0_amd64.deb'
    sudo dpkg -i parity_1.7.0_amd64.deb
    sudo apt-get install dtach
    
    cat > parity.start << EOF
dtach -n parity.dtach bash -c "parity -l engine=trace,discovery=trace,network=trace --config ${NODE_TOML} >> logs/parity.out 2>> logs/parity.err"
EOF
    chmod +x parity.start
    ./parity.start
    echo "<===== use_deb"
}

use_deb_via_systemd() {
    echo "=====> use_deb_via_systemd"
    curl -LO 'http://parity-downloads-mirror.parity.io/v1.7.0/x86_64-unknown-linux-gnu/parity_1.7.0_amd64.deb'
    sudo dpkg -i parity_1.7.0_amd64.deb

    sudo bash -c "cat > /etc/systemd/system/oracles-parity.service <<EOF
[Unit]
Description=oracles parity service
After=network.target
[Service]
User=${ADMIN_USERNAME}
Group=${ADMIN_USERNAME}
WorkingDirectory=/home/${ADMIN_USERNAME}
ExecStart=/usr/bin/parity --config=node.toml
Restart=always
[Install]
WantedBy=multi-user.target
EOF"
    sudo systemctl enable oracles-parity
    sudo systemctl start oracles-parity
    echo "<===== use_deb_via_systemd"
}

use_bin() {
    echo "=====> use_bin"
    sudo apt-get install -y dtach unzip
    curl -L -o parity-bin-v1.7.0.zip 'https://gitlab.parity.io/parity/parity/-/jobs/61863/artifacts/download'
    unzip parity-bin-v1.7.0.zip -d parity-bin-v1.7.0
    ln -s parity-bin-v1.7.0/target/release/parity parity-v1.7.0
    
    cat > parity.start << EOF
dtach -n parity.dtach bash -c "./parity-v1.7.0 -l discovery=trace,network=trace --config ${NODE_TOML} >> logs/parity.out 2>> logs/parity.err"
EOF
    chmod +x parity.start
    ./parity.start 
    echo "<===== use_bin"
}

compile_source() {
    echo "=====> compile_source"
    sudo apt-get -y install gcc g++ libssl-dev libudev-dev pkg-config
    curl https://sh.rustup.rs -sSf | sh -s -- -y
    source "/home/${ADMIN_USERNAME}/.cargo/env"
    rustc --version
    cargo --version

    git clone -b "v1.7.0" https://github.com/paritytech/parity parity-src-v1.7.0
    cd parity-src-v1.7.0
    cargo build --release
    cd ..
    ln -s parity-src-v1.7.0/target/release/parity parity-v1.7.0
    
    cat > parity.start << EOF
./parity-v1.7.0 -l discovery=trace,network=trace --config "${NODE_TOML}" >> logs/parity.out 2>> logs/parity.err
EOF
    chmod +x parity.start
    dtach -n parity.dtach "./parity.start"
    echo "<===== compile_source"
}

install_scripts() {
    echo "=====> install_scripts"
    git clone -b alphadevtestnet --single-branch https://github.com/poanetwork/oracles-scripts
    ln -s ../node.toml oracles-scripts/node.toml
    cd oracles-scripts/scripts
    npm install
    sudo bash -c "cat > /etc/cron.daily/transferRewardToPayoutKey <<EOF

#!/bin/bash
cd "$(pwd)"
echo \"Starting at \\\$(date)\" >> \"/home/${ADMIN_USERNAME}/logs/transferRewardToPayoutKey.out\"
echo \"Starting at \\\$(date)\" >> \"/home/${ADMIN_USERNAME}/logs/transferRewardToPayoutKey.err\"
node transferRewardToPayoutKey.js >> \"/home/${ADMIN_USERNAME}/logs/transferRewardToPayoutKey.out\" 2>> \"/home/${ADMIN_USERNAME}/logs/transferRewardToPayoutKey.err\"
echo \"\" >> \"/home/${ADMIN_USERNAME}/logs/transferRewardToPayoutKey.out\"
echo \"\" >> \"/home/${ADMIN_USERNAME}/logs/transferRewardToPayoutKey.err\"
EOF"
    sudo chmod 755 /etc/cron.daily/transferRewardToPayoutKey
    cd ../..
    echo "<===== install_scripts"
}

setup_autoupdate() {
    echo "=====> setup_autoupdate"
    sudo docker pull poanetwork/docker-run
    sudo bash -c "cat > /etc/cron.daily/docker-autoupdate << EOF
#!/bin/sh
outlog='/home/${ADMIN_USERNAME}/logs/docker-autoupdate.out'
errlog='/home/${ADMIN_USERNAME}/logs/docker-autoupdate.err'
echo \"Starting: \\\$(date)\" >> \"\\\${outlog}\"
echo \"Starting: \\\$(date)\" >> \"\\\${errlog}\"
sudo docker run --rm -v /var/run/docker.sock:/tmp/docker.sock poanetwork/docker-run update >> \"\\\${outlog}\" 2>> \"\\\${errlog}\"
echo \"\" >> \"\\\${outlog}\"
echo \"\" >> \"\\\${errlog}\"
EOF"
    sudo chmod 755 /etc/cron.daily/docker-autoupdate
    echo "<===== setup_autoupdate"
}

configure_logrotate() {
    echo "=====> configure_logrotate"
    
    sudo bash -c "cat > /etc/logrotate.d/oracles.conf << EOF
/home/${ADMIN_USERNAME}/logs/*.log {
    rotate 10
    size 200M
    missingok
    compress
    copytruncate
    dateext
    dateformat %Y-%m-%d-%s
    olddir old
}
/home/${ADMIN_USERNAME}/.pm2/pm2.log {
    su ${ADMIN_USERNAME} ${ADMIN_USERNAME}
    rotate 10
    size 200M
    missingok
    compress
    copytruncate
    dateext
    dateformat %Y-%m-%d-%s
}"
    echo "<===== configure_logrotate"
}

# MAIN
main () {
    sudo apt-get update

    prepare_homedir
    #add_user_to_docker_group
    
    install_ntpd
    install_haveged
    allocate_swap

    install_nodejs
    #install_docker_ce
    pull_image_and_configs

    #start_docker
    #use_deb
    use_deb_via_systemd
    #use_bin
    
    #setup_autoupdate

    #install_netstats
    install_netstats_via_systemd
    install_scripts
    configure_logrotate
}

main
echo "========== AlphaTestTestNet/mining-node/install.sh finished =========="
```

# References

    [^fn1]: Ethereum, A Next-Generation Smart Contract and Decentralized Application Platform https://github.com/ethereum/wiki/wiki/White-Paper    
    [^fn2]: Announcing Kovan — A Stable Ethereum Public Testnet https://medium.com/@Digix/announcing-kovan-a-stable-ethereum-public-testnet-10ac7cb6c85f    
    [^fn3]: Kovan proposal https://github.com/kovan-testnet/proposal    
    [^fn4]: Parity pushes new Ethereum testnet 'Kovan' after spam attacks http://www.ibtimes.co.uk/parity-pushes-new-ethereum-testnet-kovan-after-spam-attacks-1609901    
    [^fn5]: Polkadot, a blockchain technology, a heterogeneous multi-chain. https://github.com/w3f/polkadot-white-paper/raw/master/PolkaDotPaper.pdf     
    [^fn6]: The Keccak sponge function family https://keccak.team/keccak.noekeon.org/    
    [^fn7]: Satoshi Nakamoto (2008). Bitcoin: A peer-to-peer electronic cash system https://bitcoin.org/bitcoin.pdf    
    [^fn8]: Public versus Private Blockchains Part 2: Permissionless Blockchains
    http://bitfury.com/content/5-white-papers-research/public-vs-private-pt2-1.pdf    
    [^fn9]: The Issuance Model in Ethereum https://blog.ethereum.org/2014/04/10/the-issuance-model-in-ethereum/    
    [^fn10]: What is Ethereum's inflation rate? (how quickly will new ether be created) https://ethereum.stackexchange.com/questions/12501/what-is-ethereums-inflation-rate-how-quickly-will-new-ether-be-created    
    [^fn11]: https://github.com/paritytech/parity/wiki/Aura    


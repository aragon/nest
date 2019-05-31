# Prysmatic Labs Roadmap

### The Ruby Release: Local Network

Our current work is focused on creating a localized version of phase 1, quadratic sharding that would include the following:

-   A minimal, **validator client** system that will interact with a **Deposit Contract** on a locally running geth node
-   Ability to deposit ETH into the Deposit Contract through the command line and to be selected as a validator by the local **Deposit Contract** in addition to the ability to withdraw the ETH staked.
-   Ability to inspect the shard states and visualize the working system locally through the command line
-   A fleshed out P2P spec in collaboration with other sharding teams

Validators will interact through a local file system, as peer to peer networking considerations for sharding are still under heavy research.

We will forego several security considerations that will be critical for testnet and mainnet release for the purposes of demonstration and local network testing as part of the Ruby Release.

ETA: End Q2, Start Q3 2018

**Completed: Q3 2018**

### The Sapphire Release: Goerli Testnet

Part 1 of the **Sapphire Release** will focus around getting the **Ruby Release** polished enough to be live on an Ethereum testnet and manage a set of collators effectively processing collations through the **on-chain Deposit Contract**. This will require a lot more elaborate simulations around the safety of the randomness behind the collator assignments in the Deposit Contract. Furthermore we need to pass stress testing against DDoS and other sorts of byzantine attacks. Additionally, it will be the first release to have real users proposing collations concurrently along with collators that can accept these proposals and add their headers to the Deposit Contract.

Part 2 of the **Sapphire Release** will focus on implementing state execution and defining the State Transition Function for sharding on as an extension to the Ruby Release.

ETA: Q1, Q2 2019

**Part 1 Completed: Q2 2019**

Part 2 of the **Sapphire Release** will focus on the multi-client test network
such that multiple client implementations can communicate and reach effective
consensus in the network. This part of Sapphire is the final milestone for code
completion before going to Ethereum mainnet for ETH2.0 phase 0.

ETA: Q3, Q4 2019

### The Diamond Release: Ethereum Mainnet

The **Diamond Release** will reconcile the best parts of the previous releases and deploy a full-featured, cross-shard transaction system through a Deposit Contract on the Ethereum mainnet. As expected, this is the most difficult and time consuming release on the horizon for Prysmatic Labs. We plan on growing our community effort significantly over the first few releases to get all hands-on deck preparing for real ether to be staked in the Deposit Contract.

The Diamond Release should be considered the production release candidate for sharding Ethereum on the mainnet.

Prysmatic Labs will begin by focusing its implementation entirely on the **Ruby Release** from our roadmap. We plan on being as pragmatic as possible to create something that can be locally run by any developer as soon as possible. Our initial deliverable will center around a command line tool that will serve as an entrypoint into a collator client that allows staking, a proposer client that allows for simple state execution and creation of collation proposals, and processing collations through on-chain verification via the Deposit Contract.

ETA: Q1, Q2, 2020


### Change log

#### 2019/05/31 

- Rename: collators -> validators
- Remove: proposers. Validators are block proposers.
- Rename: SMC -> Deposit Contract
- Rename: Sharding Manager Contract -> Deposit Contract
- Rename: Robsten -> Goerli
- Add: Part 2 of Sapphire release goal. 


#### 2018/04/13

Initial roadmap added.
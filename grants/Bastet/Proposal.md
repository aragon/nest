# Proposal

# Request for Nest membership and funding (Bastet - An OS-level application for working with Blockchains)

Extended version of: [OS-level Signing Provider #1](https://github.com/aragon/nest/issues/1)

**Teamname / Codename**: Bastet

**Proof-of-concept**: [Bastet](https://github.com/verdverm/bastet)  (description below) ([demo video](https://youtu.be/HQlpE0O0BUA)) ([downloads](https://drive.google.com/open?id=1mGVt5M_3C9NwSFAMJ79G56sGX4qrL899))

**Burn rate**: `$5k / month`

**Legal structure**: none

**Design, Roadmap, Team:**   [Full proposal viewable here](https://github.com/verdverm/nest/tree/master/grants/Bastet)

### Abstract

Current signing providers are usually bundled as wallets or browser extensions.
They both provide a way to sign a transaction with your private key,
and a way to access web3, either using servers, running a full node, or a light client.

#### Currently, this becomes a problem when:

- Interacting with different chains, since they may need different web3 providers that extract state from the blockchain
- Interacting with different dapps, since some dapps may run inside a web browser, or inside an Electron app, or even in the command line
- Storing private keys, since there are multiple possible vector attacks. For example, in the case of a Chrome extension, Google or a malicious attacker may trigger an extension update that steals all private keys. ([sentry - report failed txs by kumavis · Pull Request #3066 · MetaMask/metamask-extension · GitHub](https://github.com/MetaMask/metamask-extension/pull/3066))
- Extensions (like MetaMask) inject a Web3 object into every website, regardless if it's a DApp or not. This needlessly increases the security frontier and attack vectors even more.

#### An independent OS-level application would:

- **Improve Security**
    - Be independent of browsers and their extension stores. Installed to the user's computer.
    - Be for a single purpose (i.e. Don't try manage keys / networks and be a browser).
    - Remove account keys and chain interaction from the DApps' running environments.
    - Act as a proxy between DApps and accounts / keys / chains / APIs
    - Enable users to control DApp access and permissions.
    - Web3 is only injected to approved websites / DApps.
- **Improve User Experience**
    - Create a centralized place for users to manage keys, networks, and DApps.
    - Use multiple DApps at the same time with different chains, either native or browser based.
    - Show human-readable descriptions and increased context for:
        - DApps, where they came from, what permissions / accounts / chains they require
        - Interactions and transaction signing requests on the blockchain
    - Manage chain connectivity for the user, default to option which improves network distributedness (i.e. run light clients rather than connecting via Infura)
- **Increase DApp usability and capabilities**
    - Work with native (electron), command line, and browser based DApps
    - Enable DApps to connect to multiple blockchains
    - Enable simultaneous DApps to access differenct chains, accounts, contracts
    - Enable developers to work with their DApps on different chains simultaneously (i.e. working with a local instance while debugging a production issue; improved CI experience)

[wouldn't include any sort of wallet functionality, just signing _(maybe will include with scope expansion?)_ ]


### Deliverables

**Bastet: The OS-level application that includes:**
- Account and key management
    - A way to securely generate and store keys at the OS-level
    - Encrypt them while unused in the safest manner
    - Support for hardware wallets, at least Ledger and Trezor
- A way to manage DApps and their access / permissions
- A Web3 proxy and multiplexer which routes DApps to one or more blockchains
- A way to manage blockchain connectivity (full/light clients, ganache/testrpc, Infura)

**An Electron UI for interacting with Bastet:**
- Interfaces for account, key, network, and DApp functionality
- Notifications / popups with human-readable transcript of the payloads to be signed, by using radspec

**A thin browser extension:**
- Injects custom Web3 into sites (like MetaMask & Mist do), electron apps can use as well.
- Only inject into websites approved by user (MetaMask injects Web3 into every tab today)
- An expanded interface for DApps to send context with their web3 interactions.
- Little to no in-browser interactions
  - whitelist a DApp on first visit, disable at any time
  - set location for Bastet server (user _could_ have Bastet on one machine and clients on multiple machines)

**Extras:**
- Website and documentation for users and developers
- A Boilerplate repository for developing native DApps with Electron and React.

### Grant size

`Up to $45k in ETH, to cover a $5k/month burn rate, for up to 9 months.`

`$50k in ANT, given out as milestones are reached.`

### Proof-of-concept:

A Proof-of-concept can be found [here](https://github.com/verdverm/bastet) with instructions for setup and running. There is a demo setup included, though it should work with and Dapp that can work with ganache at this point.

P.O.C. Demonstrations:

- Transaction signing UX
    - Interecpts Dapp request in proxy
    - Presents TX details to user for approval / denial
    - Signs transaction with private key and sends to the chain for execution
    - Sends user's response to Dapp
- Dapp proxy to prevent direct communication with the chains
- Separate Node processes for isolation of sensative data handling
- Secure IPC, because Electron IPC is not
- Works on all required Operating Systems
- _Should_ work with all Dapps against `ganache-cli -i 22323 --seed 22323 -d`

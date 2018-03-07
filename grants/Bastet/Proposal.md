# Proposal

# Request for Nest membership and funding (Bastet - An OS-level application for working with Blockchains)

(formerly: [OS-level Signing Provider #1](https://github.com/aragon/nest/issues/1))

**Teamname / Codename**: Bastet

**Proof of concept**: [[WIP] EOSP-POC](https://github.com/verdverm/eosp-poc)

**Burn rate**: `$5k / month`

**Legal structure**: none

**Design, Roadmap, Team:**   [files viewable here](https://github.com/verdverm/nest/tree/master/grants/os-level-signing)

### Abstract

Current signing providers are usually bundled as wallets or browser extensions.
They both provide a way to sign a transaction with your private key,
and a way to access web3, either using servers, running a full node, or a light client.

#### Currently, this becomes a problem when:

- Interacting with different chains, since they may need different web3 providers that extract state from the blockchain
- Interacting with different dapps, since some dapps may run inside a web browser, or inside an Electron app, or even in the command line
- Storing private keys, since there are multiple possible vector attacks. For example, in the case of a Chrome extension, Google or a malicious attacker may trigger an extension update that steals all private keys. ([sentry - report failed txs by kumavis · Pull Request #3066 · MetaMask/metamask-extension · GitHub](https://github.com/MetaMask/metamask-extension/pull/3066))

#### An independent OS-level application would:

- **Improve Security**
    - Be independent of browsers and their extension stores. Installed to the user's computer.
    - Be for a single purpose (i.e. Don't try manage keys / networks and be a browser).
    - Remove account keys and chain interaction from the DApps' running environments.
    - Act as a proxy between DApps and accounts / keys / chains / APIs
    - Enable users to control DApp access and permissions.
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

Bastet: The OS-level application that includes:
- Account and key management
    - A way to securely generate and store keys at the OS-level
    - Encrypt them while unused in the safest manner
    - Support for hardware wallets, at least Ledger and Trezor
- A way to manage DApps and their access / permissions
- A Web3 proxy and multiplexer which routes DApps to one or more blockchains
- A way to manage blockchain connectivity (full/light clients, ganache/testrpc, Infura)

An Electron UI for interacting with Bastet:
- Interfaces for account, key, network, and DApp functionality
- Notifications / popups with human-readable transcript of the payloads to be signed, by using radspec

A thin browser extension:
- Injects custom Web3 into sites (like MetaMask & Mist do), electron apps can use as well.
- An expanded interface for DApps to send context with their web3 interactions.
- Little to no in-browser interactions 
  - whitelist a DApp on first visit, disable at any time
  - set location for Bastet server (user _could_ have Bastet on one machine and clients on multiple machines)

Extras:
- A Boilerplate repository for developing native DApps with Electron and React.

### Grant size

`Up to $60k in ETH, to cover a $5k/month burn rate.`

`$50k in ANT, given out when all deliverables are ready.`

### P.O.C.

The following repository demonstrates a Proof-of-concept for the `os-level-provider`.
The POC is composed of the provider application, the provider UI, and two DApps.
A more throrough description can be found in the repository's Readme.

[EOSP-POC](https://github.com/verdverm/eosp-poc)


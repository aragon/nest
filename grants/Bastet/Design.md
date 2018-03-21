# Design

Bastet consists of four components:

1. Bastet - The standalone application for OSX/Win/\*nix
    1. Provides the main UX
    2. Mainly an administrative interface
2. Bastet Key Signer - where the secrets are handled
    1. Eventual support for any external key signer (see discussions in ethereum/signer on gitter)
    1. Able to run on separate hardware or offline
3. Bastet Dapp Proxy - The piece that enables the permissioning of Dapps to networks, accounts, and eth apis 
4. A thin browser extension for DApp workflows and backwards compatibility

The goal will is to enable flexibility in where and how the components are run.
They can be run with a single command on one machine for basic usage,
or run separately with varing degrees of isolation.
This enables users to customize to their sercurity v. simplicity tradeoff point.

#### High-level Diagram:

![Design Diagram](https://github.com/verdverm/nest/raw/master/grants/Bastet/bastet--high-level.png)


#### Internals Diagram:

![Internal Diagram](https://github.com/verdverm/nest/raw/master/grants/Bastet/bastet--internal.png)


### Components

#### 1. Bastet Application

Provides:

- UX for adminstrative tasks
    - Accounts / Keys / Wallets
    - Blockchains and connection methods
    - DApp access and permissions
- Notifications / Popups when DApps need actions by the user
- An administration API for the Bastet UI

Internally:

- Account and key management
    - A way to securely generate and store keys at the OS-level
    - Encrypt them while unused in the safest manner
    - Support for hardware wallets, at least Ledger and Trezor
- Manages DApps and their access / permissions
- Handles events and creating notifications

- Subscribes to events and forwards to UI or DApp

Technologies:

- Based on: [GitHub - chentsulin/electron-react-boilerplate: Live editing development on desktop app](https://github.com/chentsulin/electron-react-boilerplate)
- More resources: [GitHub - sindresorhus/awesome-electron: Useful resources for creating apps with Electron](https://github.com/sindresorhus/awesome-electron)
- Makes use of the Bastet thin browser extension and the separate API for administration

#### 2. Bastet Key Signer

Provides:

- Isoloated process for key usage and transaction signing
- Options for running on separate hardware / offline
- API / IPC interface for interactions

Internally:

- Deals with key encryption and storage
- Transaction signing
    - Receives request
    - Uses key, signs transaction
    - Returns signed result
- Interactions with HW wallets happens here

Technologies:

- Initially a JavaScript / Express application
- EthereumJS repositories (ethereum-tx)
- Will explore moving to Golang

(There is a lot of flexibility here)

#### 3. Bastet DApp Proxy

Provides:

- Web3 interface for DApps

Internally:

- A Web3 proxy and multiplexer which routes DApps to one or more blockchains
- Manage blockchain connectivity (geth full/light clients, ganache/testrpc, Infura)
- Intercepts Web3 calls
    - Injects the signing process
    - Checks permissions and proxies or not

Technologies:

- Initially a JavaScript / Express application
- Will explore moving to Golang
- EthereumJS repositories
- Other repositories:
    - https://github.com/MetaMask/provider-engine
    - [MetaMask · GitHub](https://github.com/MetaMask) has a number of secondary JS libs that will be useful.

(There is a lot of flexibility here)

#### 4. Thin Browser Extension

Provides:

- Cross-browser extension so users can use their normal browser
- Backwards compatibility with existing DApps
- Minimal UX for:
    - approving / revoking DApps
    - setting the location for Bastet

Internally:

- Interacts with Bastet to provide UX around approving / revoking DApps
- Injects a Web3 object into approved DApp sites.

Technologies:

- JavaScript, mimic the way MetaMask and Mist inject the Web3 object
- [GitHub - MetaMask/extensionizer: A JS module for writing cross-browser extensions.](https://github.com/MetaMask/extensionizer)



### Further Considerations

Radspec: 
- [GitHub - aragon/radspec: 🤘 Radspec is a safe alternative to Ethereum's natspec](https://github.com/aragon/radspec)
- will need to contribute to this project as well

Security:

- How to have verified / approved DApps for the user?
    - How do DApps identify themselves on connection?
    - Can we inspect the request hostname? maybe grab the html for title / description (in-browser only?)
    - Radspec?
    - uPort / Signal?
- How to secure inter-DApp / Bastet communication?
    - [GitHub - MichaelVasseur/electron-ipc-bus: An IPC bus for Electron.](https://github.com/MichaelVasseur/electron-ipc-bus)
- More security related links:
    - [Electron Security PDF](https://www.blackhat.com/docs/us-17/thursday/us-17-Carettoni-Electronegativity-A-Study-Of-Electron-Security-wp.pdf)
    - [Electron + MetaMask = Secure, Easy to Use Dapps 🔒 – Aragon](https://blog.aragon.one/electron-metamask-secure-easy-to-use-dapps-5a9987d21034)
    - [How Aragon approaches identity and the Ethereum Keybase Resolver](https://blog.aragon.one/how-aragon-approaches-identity-and-the-ethereum-keybase-resolver-d548133e4a26)
    - [uPort: Self-Sovereign Identity](https://www.uport.me/)
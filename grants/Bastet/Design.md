# Design

Bastet consists of three components:

1. Bastet - The standalone application for OSX/Win/\*nix
2. An Electron UI for interacting with Bastet
3. A thing browser extension for DApp compatibility

#### High-level Diagram:

![Design Diagram](https://github.com/verdverm/nest/raw/master/grants/Bastet/bastet--high-level.png)


#### Internals Diagram:

![Internal Diagram](https://github.com/verdverm/nest/raw/master/grants/Bastet/bastet--internal.png)


### Components

#### 1. Bastet Application

Provides:

- An extended Web3 interface for DApps
- An administration API for the Bastet UI

Internally:

- Account and key management
    - A way to securely generate and store keys at the OS-level
    - Encrypt them while unused in the safest manner
    - Support for hardware wallets, at least Ledger and Trezor
- Manages DApps and their access / permissions
- A Web3 proxy and multiplexer which routes DApps to one or more blockchains
- Manage blockchain connectivity (geth full/light clients, ganache/testrpc, Infura)
- Subscribes to events and forwards to UI or DApp

Technologies:

- Initially a JavaScript / Express application
- Will explore moving to Golang
- EthereumJS repositories
- Other repositories:
    - https://github.com/MetaMask/provider-engine
    - [MetaMask · GitHub](https://github.com/MetaMask) has a number of secondary JS libs that will be useful.

#### 2. Bastet UI

Provides:

- UX for adminstrative tasks
    - Accounts / Keys / Wallets
    - Blockchains and connection methods
    - DApp access and permissions
- Notifications / Popups when DApps need actions by the user

Internally:

- Connects to a Bastet instance
- Handles events and creating notifications

Technologies:

- Based on: [GitHub - chentsulin/electron-react-boilerplate: Live editing development on desktop app](https://github.com/chentsulin/electron-react-boilerplate)
- More resources: [GitHub - sindresorhus/awesome-electron: Useful resources for creating apps with Electron](https://github.com/sindresorhus/awesome-electron)
- Makes use of the Bastet thin browser extension and the separate API for administration


#### 3. Thin Browser Extension

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
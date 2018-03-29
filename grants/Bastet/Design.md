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

The Bastet Application (large middle box) is the conceptual piece which acts as the UI, proxy, and independent signer.
Additionally, there is a _thin_ browser extension which
adds the Bastet Dapp Proxy as the web3 provider in browsers.

From the outside, the user interacts with the Bastet UI and Dapps (either native or browser based). The UI talks directly with the Bastet application over secure IPC. Dapps talk to the Bastet Dapp Proxy by the standard web3 communication protocols.

Behind the Bastet Application, and in particular the Dapp Proxy,
any number and type of Etheruem networks back the Dapp calls to the blockchain. The associations and permissions, for a Dapp, to a network are controlled through the interface and enforced in the proxy.

#### Internals Diagram:

![Internal Diagram](https://github.com/verdverm/nest/raw/master/grants/Bastet/bastet--internal.png)

The Bastet Application, the purple bordered box,
is the conceptual group of processed the realize
Bastet's functionality. One of the core goals,
as requested by some community discussion,
is to make these components pluggable, such that:

- They can be run as a single application, with several internal and separate OS processes.
- Components may be run as separate applications, each with their own command invocation.
- Components may be run on separate hardware, including offline or cloud based. Offline makes sense for key signing. Cloud may make sense for the proxy.

The diagram above shows the single application version,
in which all components are started from a single executable.
Each of the darker boxes are run as OS child processes
of the main process (note the green sub-boxes).
When run as a single application, 
the components use a secure IPC bus to pass messages.

When a user chooses to run a component as a
standalone application, configuration is available
to point the main application at the remote component.
The context and setup will determine how secure
communication is provided (example: TLS & authentication).

Dapps will talk to the networks, through the Dapp Proxy,
by the typical Web3 protocols.
Notifications can happen in the UI and via OS level notifications.
Likely they will happen in both, where the UI will
additionally provide an event history.


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
- Phishing and Malware notifications / blocking

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
- MetaMask also has a phishing library in JS they embedded into their extension
 
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

Storage & Encryption:

- Electron has libraries for persisting configuration and other in-browser data.
- Some more advanced features may require a database (i.e. history for events / signing / permissions / auditing; phishing & malware sites / wallets database)

Radspec / Transaction readability: 

- [GitHub - aragon/radspec: 🤘 Radspec is a safe alternative to Ethereum's natspec](https://github.com/aragon/radspec)
- will need to contribute to this project as well?

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
    
Various Library Issues:

- Package Electron Routing
    - [Routes not working on production · Issue #1423 · chentsulin/electron-react-boilerplate · GitHub](https://github.com/chentsulin/electron-react-boilerplate/issues/1423)
    - [Programmatic navigation fails · Issue #1007 · chentsulin/electron-react-boilerplate · GitHub](https://github.com/chentsulin/electron-react-boilerplate/issues/1007)

# UX

### Example Bastet UX Flows

#### Bastet Installation and Setup

#### Managing Accounts and Keys

#### Managing Blockchains and Connectivity 

#### Managing DApps and Permissions 


### Example DApp UX Flows
---
(old content for this section)
- DApp communicates with the signing-server on `127.0.0.1:<port>`
    - Enables flexible interaction for cross-browser support or other local applications
- On signing event
    - DApp -> local-signing-server (payload enough for signer to lookup)
    - signing-electorn-app -> user (UI notification)
    - user does thing in UI (signing / new app approve)
    - local-signing-server -> DAPP (optimistic success / error event)



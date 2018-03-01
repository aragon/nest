# Aragon Nest Proposal: OS-level signing provider (#1)

### Abstract

Current signing providers are usually
bundled as wallets or browser extensions.
They both provide a way to sign a transaction with your private key,
and a way to access web3, either using servers, running a full node, or a light client.

This becomes a problem when:

- Interacting with different chains, since they may need different web3 providers that extract state from the blockchain
- Interacting with different dapps, since some dapps may run inside a web browser, or inside an Electron app, or even in the command line
- Storing private keys, since there are multiple possible vector attacks. For example, in the case of a Chrome extension, Google or a malicious attacker may trigger an extension update that steals all private keys

An independent OS-level signing provider 
wouldn’t be dependent on browsers or their extension stores, 
and it wouldn't include any sort of wallet functionality, just signing.

It could also show human-readable descriptions of what the payload to sign entails, by using something such as radspec.

### Deliverables

A signing provider that includes:

- A way to securely generate and store keys at the OS-level, and encrypt them while unused in the safest manner
- An interface for dapps to send payloads to be signed
- An interface for dapps to discover if the OS-level provider is available
- A Client library for dapp developers
- A key chooser, so the user can choose which key should be used to sign
- Support for hardware wallets, at least Ledger and Trezor
- Support for Linux, macOS and Windows
- Human-readable transcript of the payloads to be signed, by using radspec


### Grant size

`$50k in ETH, split into 4 chunks, one each quarter.`

`$50k in ANT, given out when all deliverables are ready.`

### Application requirements

- [ ] Diagram with all the components
- [ ] Document detailing the architecture and possible libraries and tools to be used
- [x] Details of the team members: __myself__
- [x] Estimated average burn rate for completing the deliverables: `~ $4K / month`
- [x] Legal structure to be adopted: __none__


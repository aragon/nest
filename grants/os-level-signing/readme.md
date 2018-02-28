# Aragon Nest Proposal: OS-level signing provider

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

$50k in ETH, split into 4 chunks, one each quarter.
$50k in ANT, given out when all deliverables are ready.

### Application requirements

- [ ] Diagram with all the components
- [ ] Document detailing the architecture and possible libraries and tools to be used
- [x] Details of the team members: __myself__
- [x] Estimated average burn rate for completing the deliverables: `~ $4K / month`
- [x] Legal structure to be adopted: __none__

# Development Timeline

Phases:

1. Alpha implementation
    1. Prototype to testnet
        1. Signing functionality
        1. DApp integration (browser & non-browser based)
        1. Wallet integration (?)
    1. Test-suite
    1. os-level-signer developer documentation
    1. Demo / example using application
1. Beta implementation
  1. Application
    1. Wallet integration (?)
    1. Full suite of platform implementations
  1. Documentation for building apps with os-level-signer
  1. Code audits and other security
  1. User testing / feedback
  1. End-to-end CI
  1. (flex-room for the unpredictable)
1. Release Candidate implementation
  1. Finalize interfaces / APIs
  1. Website / download location
  1. End-user documentation
  1. More security related activities
  1. (flex-room for the unpredictable)
1. First Release and Beyond!
  1. Bugfixes and Documentation updates
  1. More wallets / enhancements
  1. Spread the good word

Schedule:

Estimated total: time 3-4 Quarters.

I expect Phases 1 & 2 to occupy about 2 Quarters (with `1 < 2`),
with some first end-to-end prototypes within a month.



## Completed
- Interface for dapps to send payloads to be signed
- Interface for dapps to discover if the OS-level provider is available
- Signing selector where the user can choose which account should be used to sign
- Universal interface via local websocket server for interacting with any dapp
- Inject OS-level provider into web apps
- Support hardware wallets Ledger and Trezor
- Support macOS, Windows and Linux
- Implement user account settings and dapp permissions
- Improve interface for dapps to discover if an OS-level provider is available
- Add go-signer as signing module
- Create browser extension to inject Frame provider

## Roadmap

### Q2 2018
- Implement payload typing and create patterns around different types of requests so users can clearly understand what they're signing
- Testing and third-party security audit
- Release of v0.1.0 (hardware-signers-only)

### Q3 2018
- Develop UX patterns around hot signing to help users understand risks and prevent loss
- Create hot signing modules to generate and store keys at the OS-level
- Testing and third-party security audit of hot signing modules
- Release of v0.2.0 (hot-signing-support)

### Deliverables
- v0.1.0 (hardware-support-only)
- v0.2.0 (hot-signing-support)

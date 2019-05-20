![images](https://user-images.githubusercontent.com/2212651/58053982-15cf8600-7b51-11e9-82cb-8e2d8720e9d7.jpeg)

# Empower The DAO

This document explains the background, objectives, scope and plan for the first project by EmpowerTheDAO.

## Abstract

The Ethereum community is an energetic and innovative environment, with a diverse array of projects bringing "decentralization" to their communities of individual humans, through their Smart Contract protocols and dApps.

Many of its participants think of DAOs as being something that _somebody else_ works on. Like Aragon, or DAOStack, or Colony, or Moloch. That it's still an esoteric concept that once got hacked, and represents a different part of Ethereum that they aren't involved in.

They certainly don't think about a DAO _interacting with_ the tools and protocols they are building in their projects. To them, a DAO is just a way to use a blockchain to vote about how resources are allocated. In fact, they don't really even understand what it means for a DAO to interact with their dApp, or even how it could work.

## Objectives

This project seeks to integrate Aragon with a number of well-known Ethereum-based projects and their communities. To show them what it means and how it works...

- ...so that they _"get it"_ - demonstrated to them in terms they understand and even witness within their own platform

  - a DAO "acting as a Transcoder" on Livepeer
  - a DAO "Setting a Reverse Record" on ENS
  - a DAO "doing a Token to Token swap" on Uniswap
  - a DAO "attaching a Gitcoin bounty to a Github issue" using Gitcoin
  - a DAO "opening a CDP" on Maker.

- ...so that they understand how it works at a technical level, with an Aragon DAO calling smart contract functions on their protocol

- ...so that they have a starting point, a thin thread of an integration with Aragon, to be further developed 

- and ***most crucially*** ... so that they start __using Aragon DAOs for their own projects__, and encourage their communities and users to __use Aragon DAOs__ to interact with their project's protocol.

The Ethereum community is awash with early-adopters, so is a fertile breeding ground for innovation. Aragon can become the "orchestration layer" for Ethereum-based projects, connecting the dots to deliver real business value for end users.

### Project Scope

This project proposes to to build _Minimum Viable_ Aragon Agent Applications to empower DAOs to interact with the protocols being developed by some other well-known Ethereum-based projects, specifically: [MakerDAO](https://makerdao.com/), [ENS](https://ens.domains/), [Uniswap](https://uniswap.exchange) and [Gitcoin](https://gitcoin.co/).

Once installed, the applications will appear in the App Selector, allowing users of that DAO to interact with the applications connecting to other protocols:

![image4653](https://user-images.githubusercontent.com/2212651/57991942-bd917900-7aa9-11e9-9627-04856a49084f.png)
Image showing how a DAO's homepage could look, with a list of options of applications to allow the DAO to interact with other Ethereum-based protocols.

### Why _Minimum Viable_?

Nobody knows a project's inner mechanics more than the people who work in the project's community. The protocol's smart contracts have been meticulously crafted by the researchers and engineers. The UIs have been carefully designed and developed by Designers and Javascript developers. It is not possible for the EmpowerTheDAO to gain this deep an understanding within the scope of this project.

Instead, this project seeks to take the _first step_ to connecting Aragon with MakerDAO, ENS, Uniswap and Gitcoin. To demonstrate the base case application, and prove an embryonic _proof-of-DAO_ in their ecosystem. Taking this first step will seek to raise awareness of an Aragon DAO as an actor in these projects' communities, and will provide a starting point for existing members of these projects' communities to grow the capabilities of these apps, and also to evolve them as their protocols evolve.

Furthermore, it will provide an entry point for Aragon into these project's communities, to enage users to use DAOs to operate projects in their ecosystems.

### Deliverables

The project proposes to build Minimum Viable Applications for any Aragon DAO to be able to install:

- **[MakerDAO](https://cdp.makerdao.com/) Aragon App** - empower a DAO to _Deposit ETH to open a CDP_

- **[ENS](https://manager.ens.domains/) Aragon App** - empower a DAO with the ability to _Set a Reverse Record_ for an ENS Name.

- **[Uniswap](https://uniswap.exchange/swap) Aragon App** - empower a DAO with the ability to do a _Token to Token Swap_.

- **[Gitcoin](https://gitcoin.co/) Aragon App** - empower a DAO to _Fund an issue_

The code will be open source in [EmpowerTheDAO's Github Repository](https://github.com/empowerthedao), and will be published to Aragon Package Manager.

### Reference Implementation

The EmpowerTheDAO team are in the process of finalising the [Livepeer Aragon App](https://github.com/videoDAC/livepeer-aragon/blob/master/README.md). This app empowers an Aragon DAO to perform some of the key roles in Livepeer's protocol - those of **Delegator** (enabling the DAO to stake to the network, and earn rewards) and **Transcoder** (enabling a DAO to govern the protocol interactions for a Transcoder node in Livepeer's network).

Through this project, the team gained experience working with Agent.sol, as well as a strong understanding of how to build an app for an Aragon DAO which integrates with other Ethereum-based protocols.

![images](https://user-images.githubusercontent.com/2212651/57972471-086c9d00-7993-11e9-896d-ee7fa5f471aa.png)

### Project Timeline and Interim Deliverables

The project can be broken down into 3 phases, with varying levels of involvement from members of the team, during the project.

#### Phase 1

- Research & Design - 2 weeks
  - Research each protocol being integrated with
  - Engage with stakeholders in the communities of the projects to raise awareness and seek guidance
  - Interim Deliverable: Detailed scope of the functionality of each application, including contract calls, 

- Development Environment Configuration - 1 week
  - Create local test environments for each of the 4 protocols (ENS, Uniswap, Gitcoin, MakerDAO)
  - Deployment of "stub" contracts on Rinkeby for protocols which test on Ropsten
  - Interim Deliverable: Test environments and harnesses for each protocol

#### Phase 2

- Application Development - 4 weeks
  - Interim Deliverable: Applications ready for manual testing, published to Rinkeby Testnet
  - Interim Deliverable: Installation scripts for installing on local and Testnet environments

- Test + Bugfix - 1 week
  - Interim Deliverable: Test report with issues detailed how to replicate, and associated transaction records
  - Interim Deliverable: Final application installation to release to Security Audit.

#### Phase 3

- Security Audit - 2 weeks
  - Interim Deliverable: Report on vulnerabilities, and recommended changes

- Response to Security Audit - 1 week (or less)
  - Interim Deliverable: Response to recommendations, and any necessary changes

- Packaging and Release - 2 weeks
  - Final deliverable: 4 applications published to Aragon Package Manager

### Project Fees

The total fees for this project are proposed as 45,000 DAI, to be deposited into the [empowerthedao.aragonid.eth DAO](https://mainnet.aragon.org/#/empowerthedao.aragonid.eth/) via [the DAO's Finance App](https://mainnet.aragon.org/#/empowerthedao.aragonid.eth/0xf8ccac9c44058008014624068d0e03fe569e54d6).

We propose a payment schedule to align with the ends of each phase.

- 10,000 DAI after Phase 1
- 25,000 DAI after Phase 2
- 10,000 DAI after Phase 3

In addition, we request a Success reward of 9,000 ANT for completion of this project to the Aragon Associations's full satisfaction.

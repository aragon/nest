# Request for Nest membership and funding #3

**Team name:** Macor161

## Proof of concept

The following repo is a port of opencollab-cli as a NodeJs library:
github.com/macor161/opencollab-lib

And this is a proof of concept for the frontend: 
github.com/macor161/opencollab-frontend

Here is a video demonstration of what the frontend looks like right now:
https://www.youtube.com/watch?v=v754daqvXAA


## Whitepaper

The whitepaper is pretty much already written, Yondon gave us a thoughtful and detailed description on how to implement his idea. Although some truly interesting improvements were discussed in the comments, my proposition would be to build a minimum viable product close to the original whitepaper and then iterate from there. I’m far from an expert at launching crypto projects, but I think it would reasonably be the best usage of time and resources to build a small proof of concept with the basic functionalities from where we could start the discussions and the testing. And at the end of the day, it’s almost impossible to know in advance what feature will be missing or what modifications will be needed until we actually start using the product. Also, the sooner we have a working, stable and well tested app, the sooner we can migrate the codebase from Github to OpenCollab so it can be managed by the community.


## Burn rate

$14,000 / month.


## Legal structure

Aragon DAO, of course ;O)


## Team and roadmap

- [Team](./team.md)
- [Roadmap](./roadmap.md)

## Proposal

OpenCollab contains essentially four parts, all based on the OpenCollab Token (OCT) : 

1. **Governance voting:** Token holders can use their tokens to vote on different topics and issues, like challenged pull requests, electing new maintainers or choosing the best way to allocate funds. Some work has already been done by Yondon regarding the votes on challenged pull requests.  

2. **Issue curation:** Like the majority of open source development workflow, OpenCollab lets users submit issues, which are descriptions for bugs, new feature requests or general suggestions. It’s possible to stake a number of tokens to an issue to signal the importance you place on the issue. Developers are then incentivized to allocate their time corresponding to the popularity of those issues. 

3. **Pull requests:** Contributors can submit pull requests by staking a number of tokens predetermined in the repository settings. If the pull request is successfully merged, the developer receives his tokens back plus a percentage as a reward. Yet if the pull request is rejected, the tokens are then destroyed­. This creates an incentive to submit code that respects basic levels of quality and is relevant to existing issues.

4. **Merge requests:** Maintainers can merge pull requests by staking tokens and opening a challenge period, during which any token holder can object the merge. If a maintainer is not challenged, the pull request is merged and he/she receives a reward in tokens. If it is challenged, a voting period begins with a two-step commit.


The work here will be to complete the existing smart contracts already written by Yondon and to migrate them to AragonOS so it can benefit from the upgradeability and authorization mechanisms it provides.


And for every feature above, a corresponding frontend component will need to be created so token holders and developers can use OpenCollab with a minimum of programming knowledge. Since the NodeJs part of OpenCollab is built as a command line interface, The opencollab-cli must first be ported to a library so it can be easier to integrate into a NodeJs or Electron app.

As for the storage choice for the git repositories, issues and other files, the approach I suggest is to stick with Yondon idea and to make OpenCollab storage agnostic, with options readily available out of the box. Furthermore, neither IPFS or Swarm are production ready at the moment, so this will give the end user the final decision as to what he/she prefers to use. 

Finally, in my opinion, a Q1 testnet release is a little bit ambitious and I think a more realistic goal would be a testnet release on Q2 2018 and mainnet in Q3.

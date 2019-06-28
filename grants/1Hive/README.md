# Request for Nest membership and funding (#168)

**Team name**: [1Hive](https://1hive.org)

**Proof of concept / research whitepaper**: [Redemptions app](https://github.com/1Hive/redemptions-app), redeem tokens in exchange for a proportional amount of the organization's eligible assets.

**Burn rate**: \$17k/month for 5 months

- \$15k once for audits and bug bounties

We estimate needing approximate 1 month to deliver each app, though we plan to do some development in parallel (e.g. Dandelion Org template and onboarding site)

**Legal structure**: [1Hive DAO](https://mainnet.aragon.org/#/1hive/0xbc5231084d86d26a09a2c63100431da7b63d6a5f)

**[Team](https://github.com/1Hive/nest/blob/master/grants/1Hive/team.md) and [roadmap](https://github.com/1Hive/nest/blob/master/grants/1Hive/roadmap.md)**

## Proposal

We propose breaking the monolithic [Moloch DAO](https://molochdao.com) concept into the following modular Aragon apps:

- **Redemptions**: Allows users to manage a list of eligible assets held within an organizations `Vault` and allow members of the organization to redeem (burn) organization token in exchange for a proportional amount of the eligible assets.
- **Token Request**: Allows users to propose minting tokens in exchange for a payment to the organization, subject to the approval of existing members.
- **Lock**: Allows an organization to require users to lock a configure amount of tokens for a configurable amount of time in order to forward an intent.
- **Delay**: Allows an organization to require a configurable delay before an action may be executed.
- **Dissent Oracle**: Enhances the voting app to implement an [ACL Oracle](https://hack.aragon.org/docs/acl_IACLOracle) which allows an organization to configure permissions that restrict actions to only members which have recently voted `Yes`.

These applications can be combined with the existing `Vault`, `Finance`, and `Token Manager` apps to create an organization template based on the fundamental mechanism and game theory used in Moloch. But unlike Moloch, this organization could easily be extended by incorporating the task management and issue prioritization capability of Autark's `Projects` and `Dot Voting` apps or implement streaming payments via Aragon One's upcoming `Payroll` app.

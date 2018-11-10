# That Planning Suite - Revised Roadmap
#### 23-Oct-2018
Whenever we starting working on the Planning app, we assumed that we would be able to build a single Aragon app using multiple interconnected contracts, which would be able to spawn additional contracts within it. As we did a deep dive, we started to understand that we had to change our initial assumptions for how to architect the system. Instead of making a single app with a very large smart contract, we had to make design sacrifices and develop a new architecture composed of six total apps (Allocations, Range Voting, Projects, Address Book, Consensus, and Rewards) which we are now calling That Planning Suite.

* **Allocations**: Propose new multi-party financial allocations, which are forwarded to the Range Voting app.
* **Range Voting**: Vote on the percentage of an allocation that distinct tasks, projects, or people should receive. Unique forwarding pattern allows for data to be added to EVM scripts within Aragon.
* **Projects**: Curate issues and allocate bulk-bounties via a vote. Integration with Github & StandardBounties.
* **Address Book**: Maintain a list of Ethereum addresses (external contacts/collaborators) mapped to human-readable names.
* **Rewards**: Distribute rewards/dividends based on the number of tokens one has earned/one holds.
* **Consensus**: Special voting tool to facilitate full consensus on the financial value of bounty, project, or salary.

Based on the change in direction for how the system is architected, a new roadmap for the Planning Suite’s Milestones have been defined. These changes have already been under discussion, especially the scope of work for Milestone 1 which was addressed in the August update. Our plan was to also update this official roadmap as soon as we delivered on Milestone 1 and had a clearer picture of the work ahead.

We plan to enhance the kit and deploy to the Rinkeby testnet after the completion of each milestone. The mainnet deployment will be targeted after the final milestone.

### Milestone 1 
###### Estimated completion: 10 weeks
###### Actual completion time: 29 weeks

* Allocations App v1 (Satisfies the feature: Payout Engine)
  * Ability to create an allocation account
  * Ability to create an allocation proposal for an account, which forwards a proposal to the Range Voting app
  * Executes a payout for a completed Allocation range vote
* Range Voting App
  * Receives Allocation proposal from Allocations app
  * Ability to cast votes on an Allocation range vote

Due to the change in strategic direction with the Projects app to go in the direction of StandardBounties and general re-architecting of system, we are not including the complete delivery of the Projects app in Milestone 1 (this was also described in our August update). Although what has been completed for the Projects app are the designs, specs, most of the front-end work, and some initial experiments with a Github integration using access tokens. We started off the access token method since it didn’t require any centralized service, but now we are planning on the Github App approach and have come to terms with the reliance of a centralized service being necessary until we transition into a fully decentralized git solution (Pando). 

### Milestone 2 
###### Estimated completion: 4-8 weeks

Gitcoin/StandardBounties is becoming the industry standard tool for posting bounties in Ethereum, hence we have adjusted our design for the Projects app to initially work with the StandardBounties contract. We think this is the better strategic choice than using Status Open Bounty due the emerging industry standard. The Status implementation would have been simpler, but the StandardBounties approach enables more possibilities with what the Projects app can ultimately accomplish.  

* Projects App v1
    * Github integration
    * Issue curation
    * Off-chain bulk-bounties
* Address Book App
    * Satisfies Fixed Payout feature
* Allocations App v2
    * Satisfies Dynamic Payout feature

### Milestone 3 
###### Estimated completion: 4-8 weeks

Since we are going down the StandardBounties path, this means that it is now possible to enable bounty/work approval directly within Aragon. If this is desired as part of the terms of our grant, a trade off needs to be made between this feature and the Consensus app. Since the work/bounty approval was out of scope from our original milestones, we are allowing the preferred path for this milestone be directed by Aragon One.

#### Option A 
* Projects App v2
  * Work/bounty approval within **_Aragon_**

#### Option B
* Projects App v2
  * Work/bounty approval within **_Gitcoin_**
* Consensus App
  * Consensus voting
  * On-chain bulk-bounties

### Milestone 4
###### Estimated completion: 4-6 weeks

* Rewards App
  * Satisfies the *Rewards Engine* feature


### Milestone 5 
###### Estimated completion: 6-8 weeks

This is the final, “close out” milestone. One focus of this milestone will be to make the Planning Suite consistent with the rest of the Aragon apps. For example, new design patterns and components have started to become released by Aragon One in the last few months. Instead of up taking these midway through a milestone, we can do it here. 

Additionally, this milestone serves another purpose to make the suite robust and secure by getting the code audited and incorporating any changes.

* Finalize the UI
  * Incorporate new Aragon UI components (as there are a few under development at the moment, such as Address Badge, Card View, etc)
  * Ensure all of our UIs are responsive/mobile friendly (time permitting)
  * Fine tune the kit to refine permissions and include additional Aragon apps
* Secure it
  * 1 - Comprehensive Scenario Testing
  * 2 - Refactor smart contract/web3 code per code review/audit results
  * 3 - Comprehensive code review/security audit
  * Repeat steps 1- 3 until we get green light
* Mainnet deployment
* Enhancement Plan for Pando Cross-Compatibility (Document)
  * This impacts two apps in our suite (Consensus, Projects)
  * Technical architecture

### Nice to Haves
* Create another version of the Projects app that is integrated with Pando instead of Github
* Complete both options specified in Milestone 3 

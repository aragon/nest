# BrightID Roadmap

![Roadmap](https://docs.google.com/spreadsheets/d/e/2PACX-1vSTQ4JbFuExdItDOCGGiatfcHnwK4XGjQUe5UO0B9cNoKPaSirYBZDmZUWWJ0PY4GgWJLrnp40dRMIg/pubchart?oid=629651607&format=image)
[Complete spreadsheet of tasks, milestones, and projects--used to generate the above image.](https://docs.google.com/spreadsheets/d/e/2PACX-1vSTQ4JbFuExdItDOCGGiatfcHnwK4XGjQUe5UO0B9cNoKPaSirYBZDmZUWWJ0PY4GgWJLrnp40dRMIg/pubhtml)

## Milestones

### M1: BrightID mobile: organizing connections
#### 8/6/2018 - 8/19/2018

Mobile app showing on-boarding, creating, and organizing connections, using fake data, since connecting two devices won't be completed until M3. Demo with test flight.

### M2: First anti-sybil demo
#### 8/6/2018 - 9/2/2018

Anti-sybil system based on promising systems from the literature. At least two sets of parameters will be tested. Graphical output and a written report of results delivered at the end of the milestone.

### M3: BrightID mobile: making a connection
#### 8/6/2018 - 9/16/2018

Complete system for registering a connection between two devices. Probably QR + webrtc. Signatures are exchanged and verified on the backend. Connection is incorporated into the graph. Connection is added to the users connection list. Demo with test flight.
 
### M4: BrightID mobile: creating, joining and leaving groups
#### 9/16/2018 - 9/30/2018

Creating, joining and leaving groups functionality. [See the mobile spec for group functionality](https://github.com/BrightID/BrightID/wiki/BrightID---Full-Mobile-Spec#groups). Demo with test flight.

### M5: Second anti-sybil demo
#### 9/3/2018 - 10/14/2018

In-house anti-sybil system based on what we learned from the results of the first anti-sybil system. At least two sets of parameters will be tested. Graphical output and a written report of results delivered at the end of the milestone.

### M6: Show trust scores in BrightID
#### 10/1/2018 - 10/28/2018

Ability to see your own trust score, trust score of your groups, connections, and eligible groups. This is based on actual computations by an anti-sybil algorithm running on a BrightID node. Demo using test-flight.

### M7: Launch BrightID beta
#### 10/28/2018 - 11/11/2018

Demo internally at onset of milestone and bug bash. Announce beta. Launch BrightID in app stores.

### M8: Aragon-ID integration
#### 10/15/2018 - 11/25/2018

BrightID node can set and update trust scores in ethereum. Can import a BrightID key pair using metamask. (Used to respond to validation requests). Can request BrightID validation from another address, lookup and remember their BrightID key and trust score. Fork of the Aragon-ID app, demonstrating all the functionality listed above. Launched on either mainnet or testnet, depending on where Aragon-ID resides.

# BrightID Roadmap

![Roadmap](https://docs.google.com/spreadsheets/d/e/2PACX-1vSTQ4JbFuExdItDOCGGiatfcHnwK4XGjQUe5UO0B9cNoKPaSirYBZDmZUWWJ0PY4GgWJLrnp40dRMIg/pubchart?oid=629651607&format=image)
[Complete spreadsheet of tasks, milestones, and projects--used to generate the above image.](https://docs.google.com/spreadsheets/d/e/2PACX-1vSTQ4JbFuExdItDOCGGiatfcHnwK4XGjQUe5UO0B9cNoKPaSirYBZDmZUWWJ0PY4GgWJLrnp40dRMIg/pubhtml)

## Milestones

### M1: BrightID mobile: organizing connections

Mobile app showing on-boarding, creating, and organizing connections, using fake data, since connecting two devices won't be completed until M3. Demo with test flight.

### M2: First anti-sybil demo

Anti-sybil system based on promising systems from the literature. At least two sets of parameters will be tested. Graphical output and a written report of results delivered at the end of the milestone.

### M3: BrightID mobile: making a connection

Complete system for registering a connection between two devices. Probably QR + webrtc. Signatures are exchanged and verified on the backend. Connection is incorporated into the graph. Connection is added to the users connection list. Demo with test flight.
 
### M4: BrightID mobile: creating, joining and leaving groups

Creating, joining and leaving groups functionality. [See the mobile spec for group functionality](https://github.com/BrightID/BrightID/wiki/BrightID---Full-Mobile-Spec#groups). Demo with test flight.

### M5: Second anti-sybil demo

In-house anti-sybil system based on what we learned from the results of the first anti-sybil system. At least two sets of parameters will be tested. Graphical output and a written report of results delivered at the end of the milestone.

### M6: Show trust scores in BrightID

Ability to see your own trust score, trust score of your groups, connections, and eligible groups. This is based on actual computations by an anti-sybil algorithm running on a BrightID node. Demo using test-flight.

### M7: Launch BrightID beta

Demo internally at onset of milestone and bug bash. Announce beta. Launch BrightID in app stores.

### M8: BrightID AragonApp

BrightID AragonApp to allow DAOs to manage how BrightID is used in the organization. DAOs can choose a trust context (DAO-specific or more general). They can also choose which brightid nodes to whitelist. The BrightID AragonApp acts as a forwarder so trust score thresholds can allow actions in other AragonApp contracts. Publish the app and demo on testnet.

### M9: Aragon-ID integration

Extend BrightID AragonApp to allow users to link trust scores to ethereum addresses. BrightID mobile app component for initiatiing brightid to ethereum link. Integrate display of trust scores into Aragon-ID app. Demo on either mainnet or testnet, depending on where Aragon-ID resides. 

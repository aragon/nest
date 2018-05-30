# Scalable Voting Roadmap
Below is a breakdown of work, with ordered dependencies. As parts of the work require specific skillets, not all of the team will be working at the same time - e.g. the implementation phase is dependent on the outcome of the research phase.

## Q2-Q3 - Research Phase
- Month 1: 
  - Research possible paths (accumulators, bilinear sigs, threshold sigs).
  - Find most feasible/efficient scheme.
- Month 2-3: 
  - Write report with findings (performance and scalability difference between approaches)
  - Formalize final algorithm/approach into a paper
  - Peer review scheme

## Q3-Q4 - Smart Contracts / Infrastructure Phase
- Month 3-4: 
  - Prototype/implement chosen scheme in Solidity (on-chain component)
  - Write userland tools for signature generation, testing
- Month 4-5:
  - Write supporting libraries, server/relay tools in Python/Go/Haskell (off-chain/infrastrucure components)
  - Write test integration into Aragon app
  - Document APIs and write final specification
- Month 5-6:
  - Formal audit/review of complete implementation


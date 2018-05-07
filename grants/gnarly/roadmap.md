# Gnarly Roadmap

### Mid-May 2018

- Initial prototype of server-side gnarly, proving the initial concept. Supports:
    - monitoring arbitrary Ethereum blockchain events via developer-defined state function,
    - handling short-lived forks, uncles, and blockchain uncertainty while keeping the persisted state up to date,
    - includes event logs for every state transition recorded,
    - persisting the reduced state to arbitrary stores,
    - ensures that the persisted state is GraphQL-compatible for reactive frontends.

### Mid-May to August 2018

- Production ready version of server- and client-side gnarly. Supports:
    - optimistic state transitions,
    - confidence intervals and mempool introspection for tx monitoring.
- a Gas Price Estimation API powered by gnarly,
    - with a very generous free tier, subsidized by the grant.
- a Token Balances API powered by gnarly,
    - with a very generous free tier, subsidized by the grant.


### History
- 2018-05-07 pushed timeline back ~1 month due to unexpected complexity

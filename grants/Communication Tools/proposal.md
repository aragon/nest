# Aragon Communication Tools + Datastore Encryption Support

We believe that building tools that facilitate communication is an integral part of our work on DAOs. That is why alongside the launch of [Espresso Drive](https://github.com/espresso-org/aragon-drive), we have also released the [aragon-comments](https://github.com/espresso-org/aragon-comments) widget, which offers an easy way for developers to integrate comment threads in their Aragon App.

While aragon-comments currently stores messages on-chain, we have discussed with developers from Status and established a roadmap on how to migrate to Whisper and possibly to their [Network Incentivisation Protocol](https://discuss.status.im/t/network-incentivisation-first-draft/1037) when it becomes available.

Besides reducing the friction of participating in a discussion, storing messages off-chain would enable many features that were previously difficult to implement, including the ones found in the Nest Proposal #49: better communication tools for effective governance.

Also, the current release of Espresso Drive doesn’t support encryption as no privacy layer was available during the development schedule of our Aragon Nest contract. Fortunately, we recently found a solution to this problem using deterministic key pair generation.

We therefore submit in the following document a 6 months funding request during which we propose to:

1. Build and release a complete implementation of the Discussion App, specified in the Nest #49 proposal. A proof of concept is available [here](https://github.com/espresso-org/communication-poc) along with a [demo](https://www.youtube.com/watch?v=94HOq2YrNl0).
2. Improve the aragon-comments widget and migrate it to an off-chain protocol.
3. Implement file encryption support to the Datastore and Espresso Drive, along with other improvements such as extracting the “Groups” section into a standalone app.

Finally, and most importantly for us, this funding would let us continue working within the Aragon community, helping out new users and other Nest teams get up and running with their projects, contributing to Aragon codebase and to continue to take part in the decentralization movement full time.


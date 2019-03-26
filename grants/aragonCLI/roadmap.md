# Abstract Roadmap

## Short-term

What brings the most value to developers right now?

To figure this out, we need to be active in the `#dev-help` channel and on GitHub, assist people in debugging their DevOps problems, which seems to be the responsibility of the CLI (automating all the logistics of setting up, publishing, etc. so they can focus on the app-specific code).

Obviously we don’t want to end up in a situation where we are always chasing bugs, which is why a significant effort should go into creating test cases - so that we don’t fix a bug twice.

## Long-term

How would these tools look like in a few years? How should they?

A lot of issues can also be avoided by better design, but perfect is the enemy of good, and we would never ship anything if we tried to get it right from the beginning. Instead we should go for an agile approach, something like “Ship in days, Plan in months, Dream in years”.

Better define the use cases:
- CLI client to interact with DAOs (aimed at power users; should be able to do what Aragon GUI client can do and more, because is faster to implement features without a rich visual representation)
- Dev tooling (automating DevOps: setting up ipfs, ganache; making deployments easy;)
- Aragon-specific dev tooling (deploying aragon dependencies to a devchain, i.e.: aragen; cli clients: apm, acl; boilerplates)

Figure out the best practices for this use cases:
- Verbose logging
- Legibility and stability first, performance-second
- In-depth guides
- Short code snippets for the most common workflows (e.g.: creating a token & configuring a token-manager)

## Medium-term

How would a roadmap to achieve our long-term goals look like?

We started working on [specific roadmap items on aragonCLI repository](https://github.com/aragon/aragon-cli/blob/master/ROADMAP.md) and we have created a [GitHub Project](https://github.com/orgs/aragon/projects/3#card-19271602) to track our work.

The roadmap should be a "living" document on which we collaborate together with the Aragon community. We should be the facilitators of the conversation and figure out how to capture the feedback of Aragon devs. What are the pains they have? Besides writing app-specific code, what takes most of their time? What would they like to see implemented? Which aragon command they found confusing/annoying?

By involving the community not only we reduce the risk of carrying faulty assumptions, but, most importantly, we leverage the collective wisdom of developers with various backgrounds - which is what makes Aragon special (open source + formalized governance).
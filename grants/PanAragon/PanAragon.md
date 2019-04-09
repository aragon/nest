# PanAragon Nest Proposal

## Abstract

We are working on a product dedicated to the needs of the informal economy. We are committed to building a generalized solution for real-world DAO equivalents regardless of their geographical location or development stage.

It is designed to:

* enable anybody regardless of geography to quickly set up, operate and grow informal autonomous financial organisations, e.g. digital co-ops, guilds, mutuals

* enables a previously impossible interoperable scalable network between them and external third parties, whereby value can be exchanged freely in a trust-minimised way (e.g. 
* co-invest, lend/borrow, trade)

* reduces instances of fraud and misuse of funds

Given the time restrictions for a full FLOCK proposal and the kind feedback that the Aragon community have taken the time to provide to us at short notice, we are adjusting our proposal to NEST. In this proposal, we remove the elements deemed non-essential and focus on the part of the original proposal that received the most positive support so far: a layer-2 solution for voting on Polkadot as a core technology buildout for Aragon.


## Deliverables

**Layer-2 Governance solution** 

An organisation, incorporated or informal, has to make a multitude decisions. AragonOS is a technically complex product and it consumes a large amount of gas, 150,000+ units of gas based on our analysis of Aragon smart contracts. In this regard, the cost of on-chain governance which is at the heart of Aragon becomes an impediment to ability of Aragon-based organisations to grow. 

Therefore, to address the cost of on-chain governance as an impeding factor to growth of the overall network, we propose to create a layer-2 solution adapted for on-chain voting, similar to Plasma. To provide an additional layer of security, we propose to implement it on Substrate. Subsequently, we aim to deliver parachain working with Aragon contracts on Ethereum, with the parachain’s native smart contract API accepting signed transactions for voting messages. 

An additional layer of security enabled by the Polkadot protocol ensures that votes cannot be manipulated and voting system cannot be easily attacked. When the voting ends (voting rules will be described in the Polkadot’s contracts), the results will be synchronized with the Ethereum network.

Given that Aragon announced its research towards the implementation of the protocol on Polkadot, we can build the Arachain adapted to the protocol, andfast-track the overall R&D efforts and roadmap. Our team has already created their own chain using Substrate and is acting as a validator for Polkadot testnets. Polkadot Telemetry details  are here: 

* https://telemetry.polkadot.io/#/Akropolis

* https://telemetry.polkadot.io/#/Krumme%20Lanke

* https://telemetry.polkadot.io/#/Alexander



## Product-Market-Fit R&D: Real World Use Cases

We are already focusing our research on real-world DAO equivalents identified by the team during the extensive research into [chamas as precursors to DAOs](https://docs.google.com/presentation/d/16P9pAqSryjJpk37R-CtXDEw-0pNtYpuBei2cmfIR2E8/edit#slide=id.g35c0209681_0_0) - and see the Aragon SDK as a toolkit to super-charge traditional co-op/mutual structures and enable them to save, transact and grow at scale safely, without dependency on banks, financial institutions such a state pension funds which are a de facto Ponzi scheme, or nation-states themselves for that matter.

Our scope is catalysed by chamas but not restricted to them - we are committed to building a generalized solution for real-world DAO equivalents regardless of their geographical location or development stage.


## Requirements

* Blog access on blog.aragon.org

* Unrestricted use of the Aragon trademark

* Publish access to aragonpm.eth

* Access to Aragon servers and cloud infrastructure

* Access to Aragon DNS and ENS domains

* Admin/moderator access on aragon.chat, forum.aragon.org, and /r/AragonProject


## Grant Size

We would like to request the standard $150,000 grant allocation paid in DAI to cover the operating costs. 



## Development timeline

This timeline is an estimation after the deployment of the funds for the Nest is confirmed. It is based on deliverables/milestones per month to keep our goals clear and stages well-defined.

* 1st month - Working on a Proof of Concept. Results: 
Development of the tech specification for AraDot Chain.

The AraDot will be based on OCEAN model (Off-Chain Event AggregatioN) and will use state channels to bridge Aragon tokens to AraDot. 

* 2nd month -system of offchain-voting and decision making - Using state channels and native Substrate smart contracts

* 3rd month -Oracle development for voting results transferring from AraDot to Aragon DAO. 
  
* 4th month- Adding the ability to work with any DAO
At the 1st stage (1-3 months) we take a test list of DAOs, that can work with our solution. 
In the next stage (this one mentioned above, month 4 - we "open" our solution to all DAOs. 

* 5th month - Refactoring, stabilization, launch of the public TestNet network
PoC full preparation within budget specified. 
The product can be packaged as a standalone box version in the future, but this is planned for stage 2 - within the framework of the Aragon Flock Grant.

### Future plans: 

*  6-8 month - Development of a proof-of-concept DSL (domain-specific language) that makes it possible to create a different voting logic within AraDot.

* 9-12 month - Stabilization and launch of the public Mainnet. 


## Team 


### Ana Andria

Ana is an experienced special situations investment professional with a strong interest in decentralization and blockchain. She currently sits on the advisory board for the Web3 Foundation, and she has analyzed and transacted over USD3.5bn and advised on over USD300mn of private equity and debt transactions. Ana is a business-builder, team-builder, technology and data obsessive, with particular strength in forensic analysis, seeing efficiencies and optimising processes. She’s passionate about individual empowerment and helping others fulfill their potential. FCA-regulated fund management professional and a board member of a regulated private equity fund.

**Commitment**: Part Time

**Socials**: [**LinkedIn**](https://www.linkedin.com/in/anastasia-andrianova-79198b4)  | [**Twitter**](https://twitter.com/ana_andrianova/)



### Alex Maz

Blockchain engineer, educator and a co-founder of St.Petersburg Ethereum meetup, Alex graduated with BSc Applied Mathematics and Computing Sciences and is a PhD (cand.) Machine Learning.
He has 16 scientific publications focussing on natural language recognition and 10 commercially implemented applications to his name.
Alex has both shipped product in fintech, banking, and gaming, and is passionate about educating the new generation of blockchain developers.


**Commitment**: Full Time

**Socials**: [**LinkedIn**](https://www.linkedin.com/in/alexander-mazaletskiy/)  | [**Github**](https://github.com/AlexanderMazaletskiy)


### Alex Koz

Software Engineer, Consultant, Game Developer & reverse-engineering enthusiast. OSS enthusiast, active contributor of DDG, Haxe. Had more than fifteen years of development of real-world applications since 2000. Worked for many companies such as SmartGames, Dulton Media, Games.Mail.ru, Leo Burnett, Rambler, Clickberry and other companies with various projects.


**Commitment**: Full Time

**Socials**: [**LinkedIn**](https://www.linkedin.com/in/akozlovskij/)  | [**Github**](https://github.com/fzzr-)


### Dima Serd


**Commitment**: Full Time

**Socials**: [**Github**](https://github.com/in19farkt)


### Ilgiz Gimal

Fintech professional with 10+ years experience. Prior to joining Akropolis overseed all product development for incubator projects at fintech fund. Earlier worked at Digital Business Development Department at VTB Bank, one of the leading universal banks of Russia. Graduated Lomonosov MSU, PhD in computer Science & Mathematics. Launched several startups from 0, also under management VTB bank integrated and launched digital sales.

**Commitment**: Part Time

**Socials**: [**LinkedIn**](https://ru.linkedin.com/in/ilgiz-gimaltdinov-8bbba411) | [**Github**](https://github.com/apeir99n)


### María Paula Fernández

**Commitment**: Part Time

**Socials**: [**Twitter**](https://twitter.com/mptherealmvp)



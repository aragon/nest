# Proposal: Datastore + Aragon Drive App

Sharing and storing files is a fundamental necessity in every organization. The majority of services available today (Dropbox, Google Drive, Box, Onedrive...) are centralized and though they provide cheap and easy access to storage, there are also numerous consequences to this centralization: [far from perfect](https://www.computing.co.uk/ctg/news/3015553/onedrive-down-were-having-issues-admits-microsoft) server availability, [arbitrary censorship](https://mashable.com/2017/10/31/google-docs-locking-people-out/#KOlSXh.PsaqN), flawed privacy, possibility of power misuse and these are just a few examples of the drawbacks it can cause.

Of course, decentralized alternatives exist and are starting to fill the gap, but nothing is specifically designed to address the needs of DAOs. With the recent release of Aragon 0.5, creating and managing DAOs is more simple than ever but there is still a need for a service that would let people as well as apps to easily store and share files with specific permissions to other members of the organization and to the general public.

This is what we propose here: **The Datastore**, a set of smart contracts based on AragonOS coupled with a javascript interface that will let entities of an organization store, modify, delete and set permissions to files and other data. 

To showcase the possibilities of this tool, we also propose to create **Drive**, an Aragon app that will use the Datastore to let members of a DAO upload files and organize them by folders.

### Preview of the Drive App:
![Preview of the Drive App](https://user-images.githubusercontent.com/642515/38653140-45332bda-3dd7-11e8-9bf6-e0d0a081ce32.jpg)


![Preview of the comments](https://user-images.githubusercontent.com/642515/38653172-753a420a-3dd7-11e8-8b9f-9fb79a1f13af.jpg)

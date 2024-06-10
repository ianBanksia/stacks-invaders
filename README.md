# stacks-invaders
This repository contains the first DMT art project based on the Stacks Blockchain.

More documentation on Stacks can be found here:
https://docs.stacks.co/




# Digital Matter Theory
Concept that evolves from the hability of one chain to understand their own blocks, and therefore allow a smart-contract to create art based on it.
Stacks and Clarity, being high level programming artifacts, allow for that execution and art to be saved completelly on chain.

The way we achieve this, was to create scripts able to generate images direclty on the Smart Contract.
Clarity always knows what block it is (block-height), so we just choose to link some of these numbers to specific images variations, for our case:
- Last number from the right: Colour 1;
- 2nd from the last: Colour 2;
- 3rd & 4th numbers: Pattern (~49 patterns)
- Random combinations: Special traits

You can, of course, make this as complicated or as simple as you want. 

Another important detail on this implementation is the use of SVG as a file type, for a few reasons:
- Human and machine readable (WYSIWYG)
- Expandable pixel art
- lower file size for resolution

You can, of course, use any file type you want... limited by the ability of Clarity to handle binary and hashed files.




# ART: STACKS INVADERS
The Art makes reference to imaginary elements that may exist in the blockchain blocks, called INVADERS.

Invaders are 12x12 pixel elements that can very in shape and colour, and can also inhabit different places and thereforebe presented on different backgrounds by their owner.
Each Stacks block can have only ONE Invader, that will be registered forever on the Stacks Blockchain.

To facilitate trading and use of current tooling, the art and metadata will also be persisted on IFPS, making this the first DMT hybrid token on Stacks.



# MINT PROCESS
Only one Invader can be generated per block, which creates an interest dynamic regarding the block competition.
- Users need to be aware of the risk of a mint not proceeding;
- Users need to be aware that any STX spent acceleratting their transactions can't be refund;
- Users need to be aware that only one transaction will succeed per block;
- Price will start at 1 STX and will gradually increase to up to 10 STX



# GONZO ORIENTED DEVELOPMENT
The development approach for this project finds inspiration on the ways of working estabilshed by Hunter S. Thompson when finding his own way of writing.
Code is to me but a different language, ideas should be found and executed via a continous experimentation of a open mind.
Most likely we will break som things in the process. Enjoy the ride.

More on Gonzo Journalism can be found here:
https://en.wikipedia.org/wiki/Gonzo_journalism



# SMART-CONTRACT
Please use the BACKEND folder to find any examples and SmartContract code.
Deployed version can be found here: https://explorer.hiro.so/txid/SPV8C2N59MA417HYQNG6372GCV0SEQE01EV4Z1RQ.stacks-invaders-v0?chain=mainnet



# USER INTERFACE
Please use the FRONTEND folder to find UI example.
Typescript is used as main language, for a few reasons:
- It's type safe(r), which increases security;
- No css + Tailwind: keep it simple and readable;
- Readable (mostly) by the users: how can they verify if it's all giberish?




# IFPS and Image Generation
(to be documented)



# HOW TO HELP
This project was done as a side-task during a week where I was suffering from hay fever and therefore not in a position to dedicate myself to DeFi and more complex numbers.
As a result of that, there's plenty room for improvement in both backend and frontend implementations.

This is a open-source project and all help is welcome.
(MIT Licensed: you can do whatever you want, but there's no garantees of any kind)

Few items you can work on:
- Unit tests: ;)
- Metadata generation: Origina focus was on generating the Art, but generating the metadata JSON file seems the next logical step
- Other file types: currently only SVG was tested, but nothing is blocking other file types to be implemented
- Find and reporting bugs: Please open a PR, ideally with the corresponding solution.
- Any new ideas: again just open a PR. I won't promise to work on it, but you are all welcome to expand and build on top of this one.


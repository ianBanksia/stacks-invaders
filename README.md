# stacks-invaders

This repository contains the first DMT art project based on the Stacks Blockchain.

More documentation on Stacks can be found here:
https://docs.stacks.co/

## Digital Matter Theory

Concept that evolves from the ability of one chain to understand their own blocks, and therefore allow a smart-contract to create art based on it.

Stacks and Clarity, being high level programming artifacts, allow for that execution and art to be saved completely on chain.

The way we achieve this, was to create scripts able to generate images directly on the Smart Contract.

Clarity always knows what block it is (block-height), so we just choose to link some of these numbers to specific images variations, for our case:

- Last number from the right: Colour 1
- 2nd from the last: Colour 2
- 3rd & 4th numbers: Pattern (~49 patterns)
- Random combinations: Special traits

You can, of course, make this as complicated or as simple as you want.

Another important detail on this implementation is the use of SVG as a file type, for a few reasons:

- Human and machine readable (WYSIWYG)
- Expandable pixel art
- lower file size for resolution

You can, of course, use any file type you want... limited by the ability of Clarity to handle binary and hashed files.

## ART: STACKS INVADERS

The Art makes reference to imaginary elements that may exist in the blockchain blocks, called INVADERS.

Invaders are 12x12 pixel elements that can vary in shape and colour, and can also inhabit different places and therefore be presented on different backgrounds by their owner.

Each Stacks block can have only ONE Invader, that will be registered forever on the Stacks Blockchain.

To facilitate trading and use of current tooling, the art and metadata will also be persisted on IPFS, making this the first DMT hybrid token on Stacks.

There's an inspirational component from 80's arcade games, but we believe it to be a different element on its own and not copying any existing elements. If you own an IP and believe this art to be in breach, please get in touch, happy to make any adjustments.

## MINT PROCESS

Only one Invader can be generated per block, which creates an interesting dynamic regarding the block competition.

- Users need to be aware of the risk of a mint not proceeding
- Users need to be aware that any STX spent accelerating their transactions can't be refunded
- Users need to be aware that only one transaction will succeed per block
- Price will start at 1 STX and will gradually increase to up to 10 STX
- There's no need to rush, mint will be live for a little under 5000 Stacks blocks, which is ~34 days
- You will receive a token that won't load any image at first, IPFS data will be loaded gradually in a progressive reveal of the art.
- We are working with Gamma to check if they can read the images directly from the contract, plan is to reach out to Leather and XVerse next.

## GONZO ORIENTED DEVELOPMENT

The development approach for this project finds inspiration on the ways of working estabilshed by Hunter S. Thompson when finding his own way of writing.

Code is to me but a different language, ideas should be found and executed via a continous experimentation of a open mind.

Most likely we will break some things in the process. Enjoy the ride.

More on Gonzo Journalism can be found here:
https://en.wikipedia.org/wiki/Gonzo_journalism

## SMART-CONTRACT

Please use the BACKEND folder to find any examples and smart contract code.

Deployed version can be found here: https://explorer.hiro.so/txid/SPV8C2N59MA417HYQNG6372GCV0SEQE01EV4Z1RQ.stacks-invaders-v0?chain=mainnet

Functions worth exploring:

- get-current-block-height-design: returns the Invader living on the current block. (Output is a SVG file)
- get-dmt-for-block-height: returns the Invader Living on any block. (Input is a block number, Output is a SVG file)
- get-token-svg: returns the art for a specific token ID. (Input is a token number, Output is a SVG file)

Currently the fucntions are all packed in the contract directly, but plan ( suggestion by @tripnm0nkey ) is to deploy it as a trait (DMT-001/SIP-XXX) so it can be easily implemented by the existing ecosystem.

## USER INTERFACE

Please use the FRONTEND folder to find UI example.

Typescript is used as main language, for a few reasons:

- It's type safe(r), which increases security
- No css + Tailwind: keep it simple and readable
- Readable (mostly) by the users: how can they verify if it's all gibberish?

## IPFS and Image Generation

(to be documented)

## HOW TO HELP

This project was done as a side-task during a week where I was suffering from hay fever and therefore not in a position to dedicate myself to DeFi and more complex numbers.

As a result of that, there's plenty room for improvement in both backend and frontend implementations.

This is a open-source project and all help is welcome.

(MIT Licensed: you can do whatever you want, but there's no guarantees of any kind)

Few items you can work on:

- Unit tests: ;)
- Metadata generation: Origina focus was on generating the Art, but generating the metadata JSON file seems the next logical step
- Other file types: currently only SVG was tested, but nothing is blocking other file types to be implemented
- Find and reporting bugs: Please open a PR, ideally with the corresponding solution.
- Any new ideas: again just open a PR. I won't promise to work on it, but you are all welcome to expand and build on top of this one.

## PHASE 2   
## DMT Sandwich Engine

Evolving from the Successful DMT mint process, we are deploying a new framework that allow the customisation of the original artwork: DMT Sandiwch Engine.
From a techincal standpoint, this an additional umbrella contract that should call before by any participant marketplace or wallet. 

This umbrella contract will execute these commands:
- Get the number of layers and respective contracts (in our example: 4 layers)
- Find and save original DMT Artwork;
- Use the same token ID to find any skins to adjust the DMT colourwork;
- Third call to retrieve any special traits;
- Final call using the same token ID to find the correct background;
- Return all the layers as outputs;

The marketplace/wallet will then overlay all outputs so it can correct render the image.

Ackonologinh this is a first try for am experimental model, a few adapctive measures are in place:
- IPFS still in use and linking to a pre-rendered image as a persisted failsafe mechanism;
- Custom background will allow both on-chain DMT and IPFS links, for better onboard of artists.

Infographic here:
https://roo-stx.com/dmt-sandwich


# O'Ruggin


- [x] Expansion of core gameplay and content 

We focused on a few key areas to push this goal forward:

		Wallet connections and World deployment / sessions

![[orug-mud-0.2.0-fluent-wagmi-integration.png]]

We are currently laying the foundations for building on the hybrid multiplayer/single player designs as noted here [Hybrid_Multiplayer_Singleplayer-f] previously. We are getting the systems in place that allows us to iterate on how we can have both single player session and multiplayer session over lap in a stateful world.

A lot of this emanates from how we handle the token gating and recognition of different wallets and users.  We've integrated WAGMI for wallet connections to give more flexibility on this front and get away from some of the limitations of how MUD handles wallets and burners, and have set up token gating as described below. 

---

- [x] Feature driven development, iterating with regular playtests 

		Wallet connections & Token gating, and Ferry Tickets


We have been focused on how to handle users with closed tests, allowing us to limit the availability of the game while on public testnets, and building this into our next goals of how to create an innovative approach for how to deal with hybrid single/multiplayer on a stateful system where there is a shared world.

The fist part was creating and deploying a "Ferry Ticket" NFT to get a token we can use for gating online and available to test.

https://blockscout.dev.gblend.xyz/address/0x0598663FA887839303B858EDc86f86678383fd07

![[orug-mud-0.2.0-fluent-token-gating-01.png]]



		helping simplify their tools for MUD Foundry / Hardhat integration:

While prepping we worked on figuring out a build chain for MUD and ECS that would work comfortably for deployments to Fluent.

This included a decent amount of work for getting the Fluent SDK (hardhat tooling) to work with MUD projects (foundry tooling). The top level detail of this is that we have taken the hard hat plugin / made modifications for using in the context of a MUD project, so that other devs can come in and more easily use MUD / Fluent SDK with small tweaks to a config and removing the need for devs to alter or change MUD itself.

---


- [x] Tests around ways in which blended execution give rise to new mechanics or features for O’Ruggin

We took the exposed endpoint for Pistols64 in the Dojo version of the O'Ruggin Trail, now replicating this in MUD to allow for the ability for an outside contract to send commands into O'Ruggin, this gives the base framework for how we then get contracts of any language to be able to make such calls and make use of blended execution.

For now we effectively send a hello world command from a Rust contract into the pistols 64 endpoint in O'Ruggin as a Proof Of Concept to build on. Next steps will be working on switching out a core contract like the Object contract to further prove the usecase.

---


- [x] "Soft" Testnet releases and playtesting from Nov 

		 Local deploys working and playtests functional

We started with getting local deploys functional across all team members machines to ensure passing tests and stability ahead of deploying to testnet,. 

		 Initial testnet deploy 17th/18th Dec, with wallet / token gated access

Links to accessible tests and deploys here, updates over the next few days:

**Contract deployment:**

https://blockscout.dev.gblend.xyz/address/0xe9051c7C1d14D37114e804b16F650C01D0e76E5A?tab=txs

**Stable/develop branch working, slightly behind and gated behind vercel:**
https://the-oruggin-trailf1-ftwet6aw1-archetypal-tech.vercel.app/

**Latest working now:**
https://the-oruggin-trailf1-git-develop-archetypal-tech.vercel.app/?_vercel_share=0DsGwxq4gX9obhjqX54lXjyjnN4WPhhO 
- uses "Ferry Ticket" token


![[orug-mud-0.2.0-fluent-working-deployment.png]]

## How to Play

- Go to https://the-oruggin-trailf1-git-develop-archetypal-tech.vercel.app/?_vercel_share=0DsGwxq4gX9obhjqX54lXjyjnN4WPhhO
- Set RPC for Fluent testnet: 
	- https://docs.fluentlabs.xyz/learn/developer-preview/connect-to-the-fluent-devnet
- Make sure you have "Ferry Ticket" token in your wallet 
	- (contract address: 0xf7C073b7d96865d8034C45E92203314BCA8F7d7A)
	- The game is gated by this ticket and will just not connect if you don't have one
- Type "connect" in the command field
	- It will ask you which wallet you want to connect with, select a number. Only currently tested in any depth with Metamask so best to use that one.
	- It will then ping back a session key / player ID available, there is only one currently, so hit "1" to confirm that key.
- Rudimentary commands 
	- look around
	- go $direction (west etc.)
	- inventory
	- take $object
	- drop $object
	- kick $object at $object

This is a very basic early version, there are bugs and thing will break!
- There are only 3 rooms to explore and a couple of objects to interact with. Really it is mostly just a test environment to show the base mechanics at this stage. Not much content there to platy with yet.
- Currently no sessions / account abstraction to allow for not needing tx confirmation every move, for now you will just have to use a wallet extension to confirm each command.
- The game is just a single world instance and a single player at the moment, this means depending on when you play you may be spawned halfway through the world or with a couple of puzzles / items already interacted with. 
- If you want to reset the game for someone else drop the ball on a plain somewhere and make sure you aren't in the barn and it will effectively 
- DONT climb though the window in that barn, it takes the player out of the world and requires a redeploy of contract! (If you do by mistake then no worries, just let us know so we know to redeploy)

That's it for now!


# Bridgebuilder


- [x] UX, FE prototypes pass 2

- Taken the initial UX designs into Three.js and Force Graphs to make more dynamic / interactive
- Done a basic mapping of the Fluent ecosystem

![[bb-0.2.0-tjs-forcegraph-fluent-eco.gif]]


- We are building up Groups to help further illustrate relationships and overlaps in entities, worlds, and therefore ecosystems![[bb-0.2.1-d3-fluent-eco-groups.gif]]

- We also explored how Bb might be used as part of the tooling for how players write or commission new stories, bounties and content with an "O'ruggin-extension" that adds additional layers of data users can build and map with:

![[bb-0.2.3-orug-view-editor-bounties.gif]]


---


- [x] Continue design process around researching what blended execution can bring to Bridgebuilder.
- The above use of `rooms and bounties for new content` as `entities` on bridgebuilder opens up some interesting domains of exploration for blended execution, the UGC tests we outlined at the top and in the design docs in M2 cover how we can have blended execution in O'Ruggin, but this addition gives us potentially how users might submit blended content for O'Ruggin through Bridgebuilder too.


# Summary

This completes the stated goals for Milestone 3. We are very happy with the momentum we now have and the foundations we have built up. This sets us in good stead for strong progress during Milestone 4. 



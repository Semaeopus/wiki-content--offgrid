The intent of this article and design doc is to explore how Fluent and its blended VM can improve the mechanics or usability of Archetypal Tech products. 
## Blended Execution and Modular Game Design

Explore using blended execution to make text adventure game mechanics more composable and accessible to modders aligning with Fluent's vision of superior and more flexible DevEx for applications.

Blended execution allows developers to use different languages to create applications that can natively interoperate on Fluent, expanding their toolset and composability.

Fluent brings more extensibility than and alternative like Arbitrum Stylus, potentially allowing anyone to expand functionality by adding new execution environments. 

### Archetypal Usecases

Most immediately, we see 3 potential use cases for Blended execution in our work (although we are sure there could be many others):

A) Modder friendly Blended Execution 
Using the BlendedVM for allowing different languages to be used for modular and composable core components to the game, giving superior DevEx and familiar languages for UGC creators
- Cascading DevEx and accessibility of blended execution and multiple options for language use in modding, user generated content, and composability, opening up the ability for power users, technical fans, and fellow game devs to extend our games and products in a manner that best suits their own expertise, or if doing composability with other products aligns best with what they have already built, reducing friction and opening up more opportunity for great community extension of our products. 
	- Choosing a language already very widely used by and for modders would make the most sense, so that it is inviting to people who already have experience making interesting extensions and mods of game. do this extent a scripting language like Lua ( a wasm targeted version, so long as still featureful enough to be comfortable to conventional game modders) has the most potential. The other option is Assemblyscript - a typescript/javascript-like language, but although many game developers and modders may be familiar, it is not as ubiquitous as a modding language.

B) Access to existing and extablished libraries in other languages
- The is a significant upside to being able to bring preexisting libraries from other languages and programming paradigms enabled by blended execution. Entire game engines, AI (in the traditional sense) models and implementations for game NPCs, language parsers for command input, and much much more. 
	- The most directly useful example we can think of would be the potential for adding Rust targeted "no-code" or visual scripting tools and a further way to lower barriers to entry for modders. 
	- This seems like a nice potential option, we'd have to find a  versionon a supported language, we assumed rust would have one but not iimediately obvious it does, Blockly supported LUA and python though - https://developers.google.com/blockly

C) MultiVM listings for the Planetary "world DNS look up"
- We also wonder if blended execution could create some potential wins for the "Shoggoth's Planetary Deli" contract we collaborated with the Underware team on. This is effectively a DNS like look up protocol for finding "worlds" (games) with exposed functions to allow for composable and intercahngeable mechanics. see the repo here for more detail: https://github.com/ArchetypalTech/Shoggoths-Planetary-Deli/tree/main
	- Could using blended execution in Planetary allow for more diverse sets of worlds or contracts to be listed in the Worlds "DNS" making for a way to connect and do composability between games written or running on different frameworks like MagicBlocks (SVM/RUst) and MUD (EVM/Solidity) and maybe even Dojo (CVM/Cairo)?
	- This would be a very heavy lift and not immediately useful, but is an interesting proposition none the lest and worth keeping in mind and on the back burner for the future as the MultiVM ecosystem evolves.


## Fluent Roadmap and Priorities

How does this fit into Fluent's current development velocity and plans?

They plan to integrate top 3 most adopted execution environments, optimizing them to minimize overhead and optimize performance, rather than integrating many environments which could lead to inefficiency.  We assume this meanEVM and SVM, but we should check waht the 3rd is likely o be... we assume Assemblyscript based on conversation, but should confirm. 

AssemblyScript is a TypeScript-like language with static typing and restricted execution, as an alternative to full JavaScript support. 

Fluent is happy to investigate supporting a restricted version of Lua that can be translated to WebAssembly at our request as it is a common scripting language in games. 
This will be a point to further discuss, we will look into it form our side and come back with whether a priority for us or if easier to pursue a different goal.

The fact that embedded verifiers for zk-proofs in Fluent are on the roadmap but not a current priority, as the team is focused on GKVM integration, is not an issue as it does not have any impact on the 3 potential areas of exploration we have identified above.

**Rust VM and Gas Optimization**

For Rust VM integration, deployment will automatically inject gas and computation fee requirements checks, without needing to write custom logic. Currently using default gas cost policies, but working to align WebAssembly and EVM instruction costs to optimize gas usage. 


## Fluent Ecosystem Integration

We have started looking into other games and dapps being built on Fluent, and how to integrate that ecosystem data into the Bridgebuilder platform, or potentially as an example of composability between O'Ruggin and other games on the ecosystem in the future (at the moment no obvious examples that would work).

A great coincidence is Fluent's existing relationship with protocols like Joke Race, which enable on-chain contests, seeing as this is something we have previously considered as to whether it could potentially integrate or compose with Bridge Builder, and to add to this we hve mutuals in other ecosystems and align with them philosophically in terms of phat app thesis as far as we can tell.

Bridgebuilder has the potential for possible privacy and collaboration Integrations with other teams in the Fluent ecosystem. Fluent's DevRel Chris is working on a demo using Fairblock's privacy functionality, which could be useful for the 'blended execution' design that Bridge Builder is exploring. new need to explore this further but it could align with the 'speakeasies' concept we are already investigating using with Tonk, where private collaboration spaces could be integrated with Bridge Builder's bounty system. 

![[bb-0.1.0-fluent-eco.png]]

### Bridgebuilder as an Ecosystem and composability mapping tool

It is worth noting that Bridgebuilder can map out ideas for relationships between protocols, not just existing connections, to help model potential integrations between blended applications and be a way of visualizing the benefits of blended execution. 

## Conclusions and where we are leaning for The O'Ruggin Trail and Blended Execution:

**Conceptual Approach**: 

Effectively - as ORUG is an experiment in maximally composable games, then we can cascade the benefits of FLuent DevEx directly to users making mods and adding to the game. Aiding their ability to quickly and easily add to the game with varying complexity.

The wasm target is really interesting as more and more languages are going to target it eventually, and so it will keep getting better, giving more entry points for people interested in UGC (adding composable smart contracts).

Blended execution as Fluent sees it  aligns with Archetypal’s strategy to leverage different ecosystems that the game can be deployed to (currently Mud and Dojo, but potentially Rust environments like MagicBlock on Solana in the future) in tandem with each other and have content be created by creative players in an environment agnostic format.

**Most likely Use Cases 

*Modder friendly Blended Execution* is likely the best fitting usecase for us at the moment. Not lest is gives us a thin end of the wedge to experiment with that we a can increase complexity with as we go. 

As a start we can just see about using the currently supported VMs to replace an existing smart contract in the game with an different language to test the thesis. 
Ideally the next stage would be to look at whether LUA is a viable option for this. 
Then lastly we could look to make a core system like the verb/ actions, or Biomes into generic functions allowing for the maximum extensibility by players. In the original Zork a verb is a procedure, therefore a verb can be a smart contract. In essence anywhere we have a constant / const we can potentially allow other players to extend or change this code e.g. Biome, Verb, etc.

Biome:
	Weather
	Default Hazards

Although not finalized, the idea of "biomes" is a potential candidate for blended execution. This concept could involve making the different config files for environments or levels in the game as generic as possible to give opportunity for player to extensively mod them, with he use of blended execution for flexibility.

This approach would make the game maximally composable, we would need to design contracts that are granular, define what the hooks are etc and it could be rolled out acrross different core systems. Verbs as a secondary example: you could create object you meant to be triggered only by new specific verb, it could be passed to a custom contract made by anyone -  and this almost like a plugin system for game mechanics (building on the MOSAICstrict model).

This is overly ambitious and not the starting point but could be an optional direction of travel to move in the direction of once we see how initial tests evolve.

To summarize: 

- **Actions as Contracts**: Verbs (such as “take,” “move”) act as contracts, making it possible to attach unique functionality to each action in the game.
- **Modularity in Objects**: Beyond actions, objects themselves could be defined as smart contracts, allowing for unique interactions (e.g., earning tokens when interacting with certain objects).
- **Custom Functionality**: Custom contracts allow players to modify or create new behaviors for existing game objects or environments.
- **Plugin Architecture**: Functions as entry points for contracts, allowing modders to integrate custom actions and behaviors into existing game objects and environments.
## Practical Considerations

- **Benefits**:
    - **Multi-language Support**: Modders can create in multiple languages (e.g., Solidity, Rust, AssemblyScript) as long as they compile to WebAssembly (WASM).
    - **Accessibility**: Lower entry barriers for modders by supporting familiar languages, increasing engagement and broadening the development community.

- **Challenges**: Balancing composability with stability; fully composable systems can become difficult to manage if they allow unrestricted modification of core components.

- **Control vs. Flexibility**: Enabling too much freedom can make core mechanics unpredictable; moderation in composability can prevent destabilizing gameplay.

- **Developer and Modder Guidelines**: It will be significant work to Establish API documentation and best practices for creating contracts within the game's ecosystem to maintain consistency, even more so with the option of different languages and blended execution.


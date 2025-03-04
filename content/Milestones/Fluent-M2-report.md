#OrugginTrail #Bridgebuilder #Fluent #BlendedExecution 
# O'Ruggin

- [x]  **M2 Oruggin Goal A) expand rust tooling for User generated content**
---
 
Please find the repo for our rust based UGC tooling "Pray Machine" here: https://github.com/ArchetypalTech/PrayMachine
 
We have created 2 tools and 1 common library, to allow ease of use creation of worlds where players and authors only have to use Markdown.

The UGC tool follows a 2 step process, 1st markdown generates a config file, and then the second step takes this config file and generates a world and rooms for Dojo and MUD. This tool sits outside of the actual contracts and execution, but is written in Rust for ease of use and accesibility and is a nice starting point for where we want to take the composability of O'Ruggin, which will lead to how we look at the potential for blended execution. The tool could generate rust contracts, rooms, etc. with no modification needed to the source the player or creator uses., and so could form the basis of User Generated blended contracts.

The tool is interesting for some other reasons also, as essentially the tool doesn't care about the input, it could be made generic enough to take another config format, potentially from another game and parse it in order to then generate contracts for blended games / apps in Solidity, Rust, Cairo, or any other target contract language in the long run. Ultimately this gives us the ability to allow users to write very simple markdown files describing rooms and objects in them and this can then be used to generate the smart contracts to deploy this in multiple languages and to different (or the same, blended) VMs.

What's next: This currently just deploys a whole world, with the evolution of the game and mechanics we now want to add to existing worlds (players should be able to create new rooms and extend each others stories) , rather than deploy a whole world with hard coded content as is currently the case. and so we want to have the tool able to update existing content and move to now being able to call a function in the contracts so that users can additively create  on top of each other. This raises some interesting questions around how we want to handle composability (and blended execution), and how we give scope for players to create or change some of the base contracts for things like verbs / actions / biomes etc... we'll cover this below and in our initial research into blended execution for O'Ruggin...

---

- [x]  **M2 Oruggin Goal B) design & research ways in which blended execution give rise to new mechanics or features for O’Ruggin**
---
**Oruggin overall design iterations:**

Building on the lessons learnt from expanding and using the UGC tooling mentioned above, we've spent a significant amount of time this month going deep on the core design of O'Ruggin and how blended execution can further empower the designs for creating a metagame and mechanics around players and authors competing to make the most interesting user generated content. 

The easiest place to get a summary overview of this is [[ORug-Design-Overview-f]], and from inside that doc we dive into the detail and links that explore these design iterations.'

**R&D for Blended Exec**

The most obvious place we can see for blended execution is by splitting out different components or objects to be more composable (as separate smart contract) that can then be accessed and altered with blended execution, making them more accessible to a wider number of users interested in modding. We explore this in a deep dive here: [[Potential for Blended Execution]]

---
# Bridgebuilder

- [x] **M2 Bridgbuilder Goal A) : UX, FE prototypes pass 1**
---
Deployed to https://bridge.archetypaltech.com/, this is a very early and janky test base for how to illustrate the benefits Bb can bring. 

![[bb-0.1.0-how-to-access-01.png]]

In order to gain access change the salt value to "tonic" - the password in the field is 2334:

![[bb-0.1.0-how-to-access-02.png]]

It is quite unwieldy and unintuitive to use at the moment as it was created purely to give a visaul representation of the concepts for which it can be used. You might find you just prefer to watch our talk from Dojo Demo day last month to get a sense of the benefit the tool can eventually bring: https://www.dropbox.com/scl/fo/7c5ca0my3hqhfrkbmws8j/AM1epaXCu1MkxwIcf-Zhzy8?dl=0&e=1&preview=DojoDayPresentation3.mp4&rlkey=vc02v5dee4m3kujxkl0h8bdrv&st=jtzj3iyv 

The rest of the work on Bb this month has been around:

- Building up our physics engine and how we can view Bridgebuilder graphs (extending from canvas and Cryptoscape tools to three.js to allow for more satisfying interactions)  
- Expanding the data set to add in Fluent ecosystem, start to show how it fits in Bb context
- Outlined the broader structure of how bb will work as a cross chain product / 

![[bb-0.1.0-outposts-map-fluent-01.png]]
 - Further research on overlapping projects that we can build off off:
	 - Story Protocol primitives that we can borrow from, effectively making the App thesis version of their Fat Protocol thesis for IP
 
---
- [x] **M2 Bridgbuilder Goal B) : start design process around researching what blended  execution can bring to Bridgebuilder**
--- 
We want as many users as possible to engage with creating bounties on Bb, and Fluent / blended execution brings this benefit across all the products we are building. 

We do a fairly detailed analysis here in [[Potential for Blended Execution#Fluent Ecosystem Integration]]

---
### NOTE Fluent announcements:

- Bridgebuilder is not publicly announced yet (we have only spoken about it inside of presentations about our wider work) , because it is still in R&D and it may not carry the name Bridgebuilder into the future we think the announce might be better to Be Oruggin and a "tease" of what Bridgebuider is without it being a direct announcement of the project  - eg. We are also working on an as of yet announced project that explores incentivisation and collaboration between composable games, mods, and UGC ... etc)
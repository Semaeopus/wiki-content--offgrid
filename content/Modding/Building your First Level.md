###### note: This is just a general overview of the process.The hyperlinks throughout this document will explain in detail each section so be sure to click them if you are unsure about anything.
## Setup
To Start Building your level you will need to download Unity and the support packages for Linux, pc and mac not doing this can cause errors when attempting to build your level. For an overview on setting up unity click here:[Getting Started with the LevelKit](Getting_Started_with_the LevelKit)
Before you start building your level you must set up your [IDE](Mission Scripting) so that you can begin programming using Lua more effectively.
### Getting Started
Now that you have your IDE set up you now need to generate a level in order to create a mod. This can all be done in the[The LevelKit GUI](Getting_Started_with_the LevelKit).
The LevelKit GUI can also be used to access your mods mission script and will allow you to add the core logic to your mod.
# Level design
#### Templates
When building your level it is often helpful just to use a series of planes and cubes to block out the level you wish to create.You can use templates to speed up your workflow which can be found within Levelkit/Collections - The collections folder contains several scenes that you can drag and drop into your current scenes Hierarchy. Be sure to copy the object you wish to use and paste it into the scene to avoid messing up the template scene.Once you have finished with a template collection right-click the scene and select remove from scene.
### Networks
Networks are one of the most important aspects of your level as it allows you to communicate with people and devices. There are a few different types of networks, to learn more about implementing you can click[here](Network_Lua API)for the API ref, and soon we will add more "manual" like page.
### Devices
Devices are anything in your mod that can be interacted with or hacked. When creating your mod you can either choose from the selection of pre-made devices or create your own.
To learn how to create your own devices click[here](Device Scripting)
### Characters
Characters within OffGrid are essential to add life to your mod.Characters tables will allow you to add the player, NPC's and dialogue options to your mod.To create a character you must first create a character table to the[characters](Mission Scripting)also, see[Character Types and Prefabs](Character_Types_and Prefabs)for specific character types.
### Triggers
Triggers are areas that can be activated when a specified object enters the specified trigger area. This can be useful for activating conversations or other story elements for more information click[here](Triggers_and Examples)
### Conversations
Currently, conversations allow the player to communicate with virtual characters. In order to create conversations, you must ensure that the characters have been added first. If you have all the characters set up click[Character Types and Prefabs](Character_Types_and Prefabs).
### Objectives
Objectives within OffGrid allow you to set the player on tasks throughout your level.For information on adding objectives to your mod click:[Objectives](Mission Scripting)
### Lighting
**LightProbes**
generate navmesh 
then generate light probes
[https://docs.unity3d.com/Manual/class-LightProbeGroup.html](https://web.archive.org/web/20200807130614/https://docs.unity3d.com/Manual/class-LightProbeGroup.html)
Reflection Probes
Light Settings
Use mixed lights in nealt all circumstances
set up a couple of 'main light per room - with low shadow strenght to get the main tine
then set othe lights with lowere intesity just to decorate
Setup skybox,
use a directional light srt as sun
### Uploading your mod
To upload your mod:
* Load up the OffGrid game
* Open up the LevelKit GUI
* click on the networking tab
* click search for game.
* Select an icon for your mod
* Enter a name and description
* Select the visibility of your mod (This will determine who can view your mod)
* Lastly select upload your mod.
### Further Reading
[Modding Manual](Modding Manual)
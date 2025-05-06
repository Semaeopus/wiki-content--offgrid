# Hackable_Object_Creation

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Hackable_Object_Creation*

*Scraped on: 2025-05-02 18:41:14*

## Choose a Mesh
Take a prop that is going to represent your hack-able object and place it in your scene.
It can be anything really, but to to make full use of the options available either:
* Choose from the Hackable Devices Collection scene in LevelKit.
The scene to pick hackable objects from
* Piece your own together from pre-made models and parts of models in the LevelKit>Models>Props>Devices and it's sub-folder 'ModularTechParts'
* or follow this guide to [Modeling your own Hackable Devices](Modeling_your_own_Hackable Devices)
## Add the Hackable component
Decide how you want it too behave in it's different states, as explained on the[Devices](Devices)page.
Eg. 
Amok() sets of a sparks particle effect 
RunOnce() spits out a sheet of paper
Create the corresponding effects, animations or behaviours you want and connect them to the corresponding Unity Events in the Hackable component
## Add the MissionObject component
This is explained in more depth in the [Mission Objects](Mission Objects) page, but essentially in this example we just need to add the MissionObject component and set it to 'Hackable'.
## Setup a Lua Device Script
Follow this guide to [Device Scripting](Device Scripting) to create a device script and set up the devices buttons to call the functions you setup in the 'Hackable' component.
Or even call anything else from the [Lua Apis](Category:LuaAPI) .
## Add to your mission script and connect to networks
* [Setup the device](Mission Scripting) and point is to your Device Script as explained above
* [Add the device](Mission Scripting)
* [Connect the device to a Network](Mission Scripting)
## Add item prop
When a NPC interacts with a hackable device sometimes that action needs some item to show on the NPC hand (for example: the soda machine makes a soda can appear on the NPC hand when the drinking animation is triggered). This item is set in the inspector, having a reference to the wanted object in the field 'Animation Item Prop', it's also possible to select the slot that the item will show (right hand is the default slot).
## Setup to affect a player and NPC on amok
It's possible to make a hackable object to knock out an enemy and affect the player when it's running amok, it's important to have attention to some details for everything to work as intended.
The first thing that needs to be set manually is the NPC animation, the Failed Use Gesture animation set on the Interest Point component must have an animation event for the system to know when to stun the NPC, this event need to call the function **NPCUseHackableDevice** , if this animation event doesn't exist the character will not be knocked out, it's also important to time this event with the animation for the user to know when is NPC is stunned, for example, adding this event when the character is on the ground is a good idea.
The hackable object can also affect the player, for that the device's game object needs to have an **AmokRangeOnPlayer** prefab as a child object. After that it's recommended to set that object Sphere Collider center and radius to make the wanted area that the player should be affected.
Note: When the player is being affected the **AmokDeviceReaction** blend tree is played, but this is only a template animation.
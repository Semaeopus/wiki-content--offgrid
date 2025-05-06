# Mission_Objects

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Mission_Objects*

*Scraped on: 2025-05-02 18:37:39*

## Mission Objects
Mission Objects, as the name suggests, are objects that are found within a level, with their purpose being to help the player complete the mission. Mission Objects can include many things like player spawns, interactable items, hackable devices, and triggers - all vital features that most levels will need.
Examples of what some Mission Objects look like in Unity
### Triggers
Triggers are Mission Objects which are used to start an event (like a conversation pop-up window) when a player walks into the trigger zone. They are a very commonly used Mission Object and have many uses, like starting conversations, triggering a sound to play, mission objective updates, and much more. For a detailed guide on how to create triggers, and for more on what they can be used for, read the [Triggers and Examples](Triggers_and Examples)page.
### Spawns
Spawns are a Mission Object simply used to tell the game where exactly to spawn into the level the characters that have been defined in the Mission Script - this includes the player, but also NPCs like Guards. For more on creating working spawns, read up on the [Configuring Spawnpoints](Configuring Spawnpoints)page.
### Interactable Objects
Interactable objects are Mission Objects that are found within the level that the player can interact with physically, this includes objects that the player can grab and put into their Inventory, but also objects like door handles, and keycard scanners to gain entry into a room. Interactable objects will be commonly found within levels to progress through the objectives, and to progress through levels themselves. If you want to read on how to implement interactable objects into your level, read the [Adding Interactable Objects](Adding_Interactable Objects)page.
### Hackable Devices
Hackable objects are a core feature of*Off Grid*, they come in many shapes and sizes, including phones, cameras, refrigerators... the list is endless, anything can be turned into a hackable object and hackable objects are again a very common Mission Object, mainly because one of the main features of the game is to hack into things! Hackable devices are interacted with by using the SSH Connection app and the access, UI, and function of each hackable device can be very varied and easily modified by modders. For a detailed run-through of hackable devices, take a look at the [Hackable Devices](Hackable Devices)page.
## Creating a Mission Object in your level
### Adding in a pre-made Mission Object
In the Hierarchy tab, click Create and then navigate to the directory shown in the image below, then click on the Mission Object which you are looking to create.
Adding Mission Objects
Depending on which Mission Object you want to create, you will need to take a different approach on editing the components. For example, creating a working spawn and creating a working trigger need different ways to make them functional. As such, if you want to see a detailed page for creating specific Mission Objects (like hackable objects, or triggers), look at the section for the Mission Object you are looking for above and follow the link to the page which shows you how to implement that particular Mission Object in your level.
### Manually creating a Mission Object
Let's say you've created a model for a stapler and now you want to configure it such that it acts as an object that the player could pick up. In this scenario, you would want to turn the stapler into a Mission Object, specifically an interactable object that the player will grab. To make this work, there is another way you could configure it, rather than adding many components into the pre-made Grab Interaction object.
To start with, place the model into your level. We'll use the stapler as our example, so once the stapler has been placed into the level, the object should only have a couple of components (those that make it act as a static model).
From here on, it's quite simple to configure it to be an interactable object, just click on the Add Component button in the Inspector View for the object, and add the Mission Object component to the model as shown below.
Adding the Mission Object component
Next it will start off as a Generic Mission Object, just click on the drop down button for Mission Objective Type and change it to Interaction. Now you have manually created an interactable Mission Object! Look at the image below for what your object should now look like, highlighted in red are things you may want to consider changing, and also parts you will need to add in to make it function properly - since it hasn't been configured properly yet to act as an interactable (to see how to do that just read the [interactable items](Interactables)page).
A manually-created interactable Mission Object
## Adding functionality to a Mission Object
The Grab action will allow player input to play the animation make the player character reach and grab an object, but this is all it will do. Deciding on how you want the object, in our case a stapler, to behave is still to be done. 
What we would want to do in this instance most likely would be:
* make the interactable object disable it's mesh renderer or the object itself (this can be explained in [Enabling and Disabling Objects to hide them](Enabling_and_Disabling_Objects_to_hide them))
* then add the stapler as a new item to the inventory ( this can be explained in [Creating new Inventory Items and adding and removing Items from the Inventory](Creating_new_Inventory_Items_and_adding_and_removing_Items_from_the Inventory))
Ofcourse what the inventory item could be used for still needs to be defined too. It could be set as a precondition for an objective such as "Steal the prototype IoT stapler". You can read about setting up objectives at .... TO BE COMPLETED
Essentially you would set up the precondition that the stapler needed to be the inventory  to complete the objective by ... TO BE COMPLETED
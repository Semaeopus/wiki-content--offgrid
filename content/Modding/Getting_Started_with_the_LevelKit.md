# Getting_Started_with_the_LevelKit

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Getting_Started_with_the_LevelKit*

*Scraped on: 2025-05-02 18:43:51*

## Getting Started
1. Download [Unity](https://web.archive.org/web/20200803173057/https://store.unity.com/download?ref=update). You will need the most up to date version, and to have installed the following components:... (Fill in required components here) gardless of whether you are using the Win/Mac/Linux build of the Unity Editor.
3. [Download LevelKit](Download LevelKit)(If you have been given BETAS access then use the properties / BETAS window and put in the password you have been given for both the game *and* for Levelkit - they have to be done separately)
4. [Open up the LevelKit project in Unity](Open_up_the_LevelKit_project_in Unity) Make sure to MOVE the level kit folder out of Steam apps and into a safe folder in your User account to prevent steam from overwriting in an update
Now go to the menu Item for Off Grid and select 'LevelKit Tool'
Where to find the LevelKit Tools window
## The LevelKit GUI
### Create Tab
Once you're in the level Kit project and have opened the LevelKit tool you should be presented with this UI
Enter your:
* mission's "Name"
* a "Description"
* the "District" on the map you want it to show up in. ("Map" district is only used for conversations done at map screen, and should not be used for actual levels).
* the "Location" - this can be a anything, mods with the same Location name will show up on the same tile. *NOTE - at time of writing there is no way to select between two levels on the same tile so for now best to give unique Locations to different mods / levels
* and hit the "Create new Mod"
This will create your mission based on a template, it will open up the missions folder in your file browser as well as dropping you into the missions scene in Unity
### Build Tab
The build tab allows you to compile your level so that you can test or upload your level.
**Current level**
This drop down box will allow you to create a new level or select an existing level.
**Save level info**
The save level info page will allow you to save any information put within the text fields above.
This includes :
* Level Name
* Level Description
* District
* Location
**Open level folder**
This will open up the folder in which your mod level is stored.
**Open mission script**
This will open your Mission Script for your mod within your preferred code editor.
**Lightmaps**
By default your Lightmaps are built automatically, when you make a change to the level. By clicking the button "Build on Demand" will stop the lightmaps automatically being created.This will help with performance while you are creating your mod. Selecting the checkbox "On Build" will allow you to generate the lightmaps as you compile your mod.
**Navigation mesh**
A navigation mesh is used to set areas that the AI can navigate.The navigation mesh by default is generated when you compile your mod.This can be changed by unchecking the "On Build" checkbox. The navigation mesh can also be built on demand when you select the "Build Now" Button.
**Build Level**
The "Build Level" button will allow you to compile your level so that you can test or upload your level. The text on this button will change to let you know if any changes have been detected.
### Tweaks Tab
**Fix Up Architecture**
This will allow you to make small adjustments to your level geometry. Fixing issues with small gaps in your geometry caused by odd rounding on the GameObject transform component.This will allow you to make your geometry conform to a single decimal.
**Fill Vertex Colours**
Using Fill vertex will flood the object with a new vertex colour specified by the colour bar.This is ideal for objects that only have a single colour as it will flood the entire object.
### Validate Tab
The Validation Tab checks that objects within your mod are set up correctly. Be sure to check this before building your mod.Some errors can be fixed using the "fix" button that appears next to the error.
### Networking Tab
**Testing**
Essentially you need to have a copy of the game running in the background (as in launch it from steam as if you were going to play it)
Then in the Level Kit tools window, click on the Networking tab and click the 'Search for game' button. Your window should now look like the above.
Once you have connected to the game click "start" to run your level. Clicking "stop" will stop your level and return you to the main menu. "Stop networking" will remove the connection between the Level Kit and the game.
## Your mission folder
Your mission folder contains all the files that the game will read when loading your mission, here's an overview:
| Folder | Description |
| --- | --- |
| Bundles/ | This folder shouldn't be edited by users, it contains[Unity asset bundles](https://web.archive.org/web/20200803173057/https://docs.unity3d.com/Manual/AssetBundlesIntro.html) |
| level.lua | This contains metadata about the mission that's read in by the game, see[here](Level.lua)for more information |
| Scripts/ | The scripts folder should contain all the Lua files that your mission will run |
| Scripts/Example_mission.lua | This is the main mission script, see[Mission Scripting](Mission Scripting)for more information |
| Scripts/Conversations/ | Your[conversation scripts](Conversations)should be placed here |
| Scripts/Devices/ | Your[device scripts](Device Scripting)should be placed here |
## Building your First Level
This will take you on a tour around the wiki and the Levelkit [click here to get started](Building_your_First Level)
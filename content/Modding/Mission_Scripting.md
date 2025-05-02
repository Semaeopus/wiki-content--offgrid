# Mission_Scripting

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Mission_Scripting*

*Scraped on: 2025-05-02 18:38:54*

## Contents
* *1Intro*
* *2Pre-requisites**2.1IDE**2.2LevelKit & Game*
* *3The Mission Script Structure**3.1Mission table**3.1.1Initial Mission State**3.1.2State**3.1.3Characters**3.1.4Physical Items**3.1.5Data**3.1.6Networks**3.1.7Devices**3.1.8Objectives**3.2Starting the mission**3.2.1Mission Setup**3.2.1.1Adding in Characters**3.2.1.2Connect Doors to the Network and set Zones**3.2.2Mission Start*
* *4Including other files*
## Intro
This article will describe everything you need to know in order to understand how to write and modify missions scripts in Off Grid!
Mission scripts can get a little bit large but don't let that overwhelm you, they're deceptively simple, we promise!
## Pre-requisites
All modding scripts for Off Grid are written in Lua, it's a lovely little language which is simple (*don't tell it I said that*) and extensible thanks to the marvellous[MoonSharp](https://web.archive.org/web/20200807124924/http://www.moonsharp.org/).
Lua is quite easy to pick up, even people with no programming experience should be able to get hacking in next to no time!
You'll need the following tools for editing and writing new mission scripts:
### IDE
Firstly you'll need an[IDE](Integrated_development_environment.md), we recommend the[Atom](https://web.archive.org/web/20200807124924/https://atom.io/)with the following extensions:
| [language-lua](https://web.archive.org/web/20200807124924/https://atom.io/packages/language-lua) | Syntax highlighting for Lua |
| [autocomplete-lua](https://web.archive.org/web/20200807124924/https://atom.io/packages/autocomplete-lua) | Auto-complete support for Lua, we recommend enabling the "Override lower priority providers" in the plugin settings |
You might also want to get our[Atom Snippets](Atom_Snippets.md)code and copy&paste it into Atom's Snippets file to add nice autocompletion for Off Grid API.
### LevelKit & Game
Both of these are needed in order to run and test and scripts you create
**TO DO**
## The Mission Script Structure
As mentioned above, mission scripts can get rather large so this article will attempt to break down all the little sub elements, it can be helpful to try and think of the mission script in the same way you might think of a film script.
The vast majority of the script is simply defining what is in the world of the mission you've created.
Enough talking, lets jump into an example! Rather than posting an entire example script, we'll go from top to bottom exploring what each element does.
### Mission table
#### Initial Mission State
```
name = "MyNewMission",
	description = "The best mod ever",
	startTime = "27/04/2009/21:30",
```
In this first code block we create the*mission*Lua table and define its first value.
| Name | Description |
| --- | --- |
| startTime | The start time of the mission in the game world (Day/Month/Year/Hour:Mins) |
startTime doesn't have to (and probaly shouldn't) be the current date, you can set your mission in any time you desire.
#### State
State includes anything you'd like to be saved & loaded. So for instance, you might want to set a bool on the first time a player enters a building, or performs an action, or completes a particular objective. Currently we only support numbers, bools and strings, and these need to have string keys (rather than indices).
```
state = {
		hasEnteredBuilding = true,
		sideObjectivesComplete = 17,
		mostAnnoyedGuard = "Brian",
	},
```
#### Characters
```
-- Character definitions:
	characters = {
		player = {
			displayName = "Joe Harman",
			characterType = "player",
			prefab = "player",
			spawnpoint = "PlayerSpawn",
		},
	},
```
This is the first example of us creating a sub table in the*mission*table, the*characters*table contains all the information about the characters in your mission! Different types of characters might need different values, and there are some optional settings as well for different purposes. Different character types and creating background profiles for the characters is explained in more detail in[Character Profiles](Character_Profiles.md).
In this example we've added Joe, the protagonist of Off Grid. Here's a break down of what the value of Joe's table means:
| Character Table | Name | Description |
| --- | --- | --- |
| displayName | The name that will be used any game UI referencing the character |
| characterType | The 'type' of the character, see[Character Types and Prefabs](Character_Types_and_Prefabs.md)for more information on possible values |
| 'prefab' | The prefab for the character, see[Character Types and Prefabs](Character_Types_and_Prefabs.md)for more information on possible values |
| spawnpoint | The name of the spawn mission object, the position of this object will be where the character is spawned |
The*characters*table can hold information on as many characters as you'd like to fill the mission with, they won't be spawned into the mission until you decide (more on that later)
#### Physical Items
```
-- Inventory items:
	items = {
		usbkey = {
			displayName = "USB dongle",
			description = "Modified USB Bluetooth dongle given to you by the hackers",
			uiSpriteName = "usbdongle.png",
                        onItemUse = function()
                            // Do stuff.
                        end,
		},
	},
```
The*items*table contains information about physical items that the player will be able to add to their inventory over the course of the mission, in this example we're marking up a USB dongle that the player can plug into computers
| Item Table | Name | Description |
| --- | --- | --- |
| displayName | The display name of the item, this is what will be displayed in the games UI |
| description | The description of the item, this will be displayed to users in the players inventory UI |
| uiSpriteName | The path to the image file to be used for the item in game menus. |
| onItemUse | Optional. Function that's ran when the player selects to use the item in inventory menu. |
#### Data
```
--[[ Data files:
Available data types: generic, text, SMS, encrypted, audio, video, location, key, UUID
]]--
	data = {
		PlayerPGPKey = {
			name = "Personal PGP encryption key",
			immutable = true,
			dataType = DataType.Key,
			creatorName = "Player",
			dataString = "PGP Fingerprint: 1d7d ef54 7a63 5756 63a7 cf14 fbd8 775c c39d 4e51",
			description = "AES 256-bit",
			dataColor = {0.0, 0.6, 1.0, 0.3},
		},
		
	},
```
The data table contains data that's specific to your mission, in this example we're defining the players[PGP](Pretty_Good_Privacy.md)encryption key
| Data Table | Name | Description |
| --- | --- | --- |
| name | The display name of the data, this is what will be displayed in the games UI |
| immutable | Optional. Is the data immutable? If true the player won't be able to delete it, this is useful for data items that are part of mission objectives |
| dataType | The type of the data, this is used for displaying the data correctly. Available DataTypes are listed in[Constants page](Constants_Lua_API.md). |
| creatorName | The name of the data's creator (displayed in the UI) |
| dataString | The contents of the data file |
| description | A description of the data file |
| dataColor | RGBA value that's used as the colour of the data point when visible in the players data view |
| script | The path (relative to the mission folder) to the optional Lua script for this data. See[Data Scripting](Data_Scripting.md)for more information. |
#### Networks
```
-- Networks:
	networks = {
		semaeopus4G = {
			name = "Semaeopus 4G",
			networkType = NetworkType.mobile,
			allowPlayerDisconnect = false,
		},
	},
```
The networks table contains all the information about the possible networks in your game, networks can be of different types such as mobile networks, WiFi, and mesh
| Network Table | Name | Description |
| --- | --- | --- |
| name | The name of the network (Must be unique!) |
| networkType | The type of the network. |
| allowPlayerDisconnect | Is the player allowed to disconnect from the network? |
Data sent at higher access levels across a network won't be visible to devices that are connected at a lower access level.
#### Devices
```
devices = {
		laptop = {
			owner = "ownerInternalName",
			dataColor = Color.Orange,
			script = "Scripts/Devices/laptop.lua",
		},
	},
```
| Device Table | Name | Description |
| --- | --- | --- |
| dataColor | The color used when displaying data from this device. |
| owner | Optional. The internalName of the device's owner. Use this if you want too restrict device's access based on owner's metadata or something. |
| script | The script that defines the GUI and the behaviour of the device ( See[device scripts](Device_Scripting.md)for more information ) |
#### Objectives
```
-- Mission objectives:
	objectives = {
		enterTheBuilding = {
			name = "Enter the building",
			description = "Short description of the objective",
			active = false,
			visible = true,
			keyObjective = false,
			
			onStart = function()
				print("Player must now enter the building")
			end,
			onCompleted = function()
				print("The player is now in the building!")
			end,
		},
	},
```
The objectives table contains all the tasks that the player should complete before your mission is finished.
| Objective Table | Name | Description |
| --- | --- | --- |
| name | The name of the objective, displayed to the player. |
| description | Short description displayed to the player in the Tasks menu. |
| active | Is the objective active at the moment (as opposed to already completed, or not even started yet)? (Optional. This is handled automatically when you call Mission.StartObjective() and Mission.CompleteObjective()) |
| visible | Should this objective be displayed to player? Hidden objectives can help organizing your mission scripts. (Optional, defaults to visible) |
| keyObjective | Key objectives are ones the player knows from the start of the level, they are visible even before the actual objective becomes active. (Optional) |
| onStart | A callback function that's triggered when the objective is started. (Optional) |
| onCompleted | A callback function that's triggered when the objective is completed (Optional) |
### Starting the mission
In addition to the big mission table, you'll need two more things to get a mission up and running; MissionSetup() and MissionStart() functions.
#### Mission Setup
SetupMission() is executed every time the mission is started, be it a fresh start, or when loading a saved game.
```
function SetupMission()

	-- add player and guards:
	Mission.SpawnCharacter("player")
	-- these two below add in the guards which you might not have created yet!
	Mission.SpawnCharacter("jack")
	Mission.SpawnCharacter("john")

	-- Doors:
	Doors.SetNetwork("ApostleWiFi")

	Doors.SetZoneKeys("Maintenance", {"Maintenance", "Staff", "Security", "Admin"})
	Doors.SetZoneKeys("Staff", {"Staff", "Security", "Admin"})
	Doors.SetZoneKeys("Security", {"Security", "Admin"})
	Doors.SetZoneKeys("Admin", {"Admin"})

	Mission.MissionStarted()
	end
```
This will add in all of your created elements into your level, below you will see what the function of each part of this code will do.
##### Adding in Characters
```
-- add player and guards:
	Mission.SpawnCharacter("player")
	-- these two below add in the guards which you might not have created yet!
	Mission.SpawnCharacter("jack")
	Mission.SpawnCharacter("john")
```
This part of the code shows the format of spawning in characters - this includes the player and any NPCs like the guards, which you will have created further up in your Mission Script. If the title of your character table for your player was called`jenson`, you would simply change`Mission.SpawnCharacter("player")`to`Mission.SpawnCharacter("jenson")`, this would now let your new character spawn in.
##### Connect Doors to the Network and set Zones
Once you have[created doors](Setting_up_Doors.md)you can then also add them to a network. Network-connected doors arre controlled by the electronic lock systems in the buildings and opened by specific access keys. Firstly you add the door to a network, then you can set the door's zone to require a specific key to open it. For example where if you consider the following command to set keys:`Doors.SetZoneKeys("Offices", {"admins", "janitors"})`,`"Offices"`is the name of the zone the door is assigned to, and`{"admins", "janitors"}`telsl that all doors belonging to this zone should be possible to open using either "admin" or "janitors" keys.
#### Mission Start
StartMission() is ran when the mission is started form the beginning. When loading a save or checkpoint, the same things would be covered by data loaded from the save instead. Use this to set initial state of things in your level.
```
function StartMission()

	-- Add items to player inventory:
	Player.ClearInventory()
	Player.AddItemToInventory("usbkey")
	Player.AddItemToInventory("meshnode")

	--  Add files to data inventory:
	Player.ClearDataFiles()
	Player.AddDataFile("PlayerPGPKey", mission.data.PlayerPGPKey)
	Player.AddDataFile("CoffeeOffer", mission.data.CoffeeOffer)

	--mobile
	Network.ConnectToNetwork(
		{
			"player",
			"DevLaptop",
			"Smedley",
			"Terrence",
			"securityChief",
			"apostleItIntern",
			"guard1","guard2","guardF1a","guardF1b","guardF1c","guard4","guard5",
			"drone1",
			"davesEPhone",
			"BasementSmartTV",
			"BasementLaptop",
			"iDeskLampTEST",
			"testRadio",
			"SmartFridge",
			"sodamachine",
		},
		"Semaeopus4G",
		"user"
	)

	-- WIFI
	Network.ConnectToNetwork("player", "ApostleWiFi", "none" )
	Network.ConnectToNetwork(
		{
			"guard1","guard2","guardF1a","guardF1b","guardF1c","guard4","guard5",
		},
		"ApostleWiFi",
		"user"
	)

	-- MESH
	Network.ConnectToNetwork(	{"Smedley","MeshleaksSecureDrop"},	"MESH", "admin"	)

	Mission.DevicesConnected()

	-- Doors
	Doors.SetKeyOnDevice("Maintenance", "IDcard01")
	Doors.SetKeyOnDevice("Admin", "IDcard02")

	Doors.AssignKeyToCharacter("Security", "guard1")
	Doors.AssignKeyToCharacter("Security", "guard2")

	-- Set up music (we'll set it to silent in start, and set gameplay state from a trigger when entering lobby)
	Sound.TriggerEvent("Set_MX_Mission_1")
	Sound.TriggerEvent("Set_State_MX_Mission_Silent")

	---[[ Things to enable when testing & debugging:
	Apps.RequestAppState("DevTools", AppState.off)
	--]]

end
```
## Including other files
We know how long these mission scripts can become. As a result, we came up with a method of splitting up your mission into smaller, bite-size pieces. You're more than welcome to keep your mission in a single file, but if you want to manage them differently, read on...
Let's say you want to keep all your device related shenanigans in a separate file for clarity. We'll call this 'mission_devices.lua', and put it in the same folder as the mission.
```
MyDevices = {
    somedevice = {
      internalName = "Device Z",
      script = "device.lua"
    },
    someotherdevice = {
      internalName = "Another Device",
      script = "device.lua"
    },
}
```
Now, this obviously seems rather pointless as there are only two devices. But if there were many, many more, it could prove quite useful.
To use this in the mission.lua file, we need to utilise Lua's dofile() function.
```
dofile("mission_devices.lua")

mission = {
    -- some tables!
    devices = MyDevices
    -- lots of other tables!
}
```
The key bit here is that the devices table is now defined to be the table we wrote in mission_devices.lua. If we took this to its natural conclusion, we end up with the following:
```
dofile("mission_characters.lua")
dofile("mission_devices.lua")
dofile("mission_data.lua")
dofile("mission_items.lua")
dofile("mission_networks.lua")

mission = {
    character = MyCharacters,
    devices = MyDevices,
    data = MyData,
    items = MyItems,
    networks = MyNetworks,
    objectives = {
        -- objectives here...
    },
}
```
We hope this proves useful in organising and managing your creations!
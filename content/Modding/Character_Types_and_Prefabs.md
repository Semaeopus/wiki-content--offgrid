# Character_Types_and_Prefabs

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Character_Types_and_Prefabs*

*Scraped on: 2025-05-02 18:39:20*

## Contents
* *1Characters**1.1Character Types and Prefabs**1.2Voice**1.3Custom LUTs and head props**1.4Virtual characters**1.5Adding Guards**1.5.1Spawn points**1.5.2Patrol route**1.5.3Profile*
## Characters
Adding characters to your level is important as this will allow you to add other important systems such as conversations which is one way to introduce story elements to your level.
To add characters to your level you must open up the mission script and locate the character table. It should look something like this:
[[File:|frame|none|alt=|caption charactertable.png]]
To add a character in the table you must include the following:
* name
* displayName
* internalName
* characterType
* prefab
You can also include some optional parameters:
* *headProps*
This would look like the following in code:
```
-- Character definitions:
	characters = {
		joe = {
			displayName = "Joe Harman",
			internalName = "Joe",
			characterType = "player",
			prefab = "player",
            headProps = {"F_Med_Glasses-01"},
			spawnpoint = "PlayerSpawn",
			voice = "Big_Guard",
		},
	},
```
**Note.**When the characterType is virtual you do not need to add a prefab or spawn-point.
### Character Types and Prefabs
| character type | prefab name | description | notes (image eventually) | LUT template (to be removed when all same) |
| --- | --- | --- | --- | --- |
| virtual | * n/a | virtual characters are characters that you won't see in the level but may communicate with the player using via CryptoChat |  |  |
| player | * Player_Joe* Player_Jen | This will allow you to add a playable character to your game.There can only be one per level. |  |  |
| npc | * Masculine_Med_BomberJacket_NPC | used for Jake Davis | working as intended, will need leaf bone removal | LUT version 2 working with the colour map :  M_Jake_Col |
| npc | * Feminine_Med_CardiganNecklace_NPC | used for Biella Coleman | working as intended, will need leaf bone removal | LUT version 2 working with the colour map : Biella_Col |
| npc | * Masculine_Med_CasualBlazer_NPC | used for Barrett Brown | working as intended, will need leaf bone removal | LUT version 2 working with the colour map : M_Barret_Col |
| npc | * Masculine_Med_CasualJumper_NPC | used for Shad | not working as intended, yet to be revamped |  |
| npc | * Masculine_Med_CoatScarf_NPC | used for Darren Martyn | working as intended, will need leaf bone removal | LUT version 2 working with the colour map : Darren_Col |
| npc | * Feminine_Med_Hoodie_NPC | used for Jaime | yet to be revamped |  |
| npc | * Masculine_Med_HorseHead_NPC | used for HF | yet to be revamped - look at changing head to a prop and making this Masculine_Med_Hoodie_NPC so reuseable |  |
| npc | * Masculine_Med_LeatherJacket_NPC | used for March O'neill | yet to be revamped |  |
| npc | * Feminine_Lrg_LongJacket_NPC* Feminine_Med_LongJacket_NPC* Masculine_Lrg_LongJacket_NPC* Masculine_Med_LongJacket_NPC | used for Emmanuel and Kyle | first pass, expect Lut issues, currently LongJacket_Col_Docker is the only working LUT | LUT version 2 working with the colour map : LongJacket_Col_Docker |
| npc | * Masculine_Med_OpenShirt_NPC | used for Lauri Love | yet to be revamped |  |
| npc | * Feminine_Lrg_SmartJumper_NPC* Feminine_Med_SmartJumper_NPC* Masculine_Lrg_SmartJumper_NPC* Masculine_Med_SmartJumper_NPC | used for Mustafa Al Bassam | yet to be revamped | Smart Jumper LUT |
| npc | * Feminine_Lrg_SmartSuit_NPC* Feminine_Med_SmartSuit_NPC* Masculine_Lrg_SmartSuit_NPC* Masculine_Med_SmartSuit_NPC* Player_Joe | description | yet to be revamped | SmartSuit LUT |
| npc | * Feminine_Med_Shirt_NPC | used for Naomi Colvin | yet to be revamped |  |
| npc | * Feminine_Med_Teen_NPC* Player_Jen | description | yet to be revamped |  |
| npc | * Masculine_Med_TShirt_NPC | used for mc.fly | yet to be revamped |  |
| npc | * Feminine_Lrg_Vest_NPC* Feminine_Med_Vest_NPC* Masculine_Lrg_Vest_NPC* Masculine_Med_Vest_NPCX- broken rig | description | first pass, expect Lut issues, currently Vest_Col_Security-Apostle is the only working LUT | LUT version 2 working with Vest_Col_Security-Apostle |
| npc | * Feminine_Lrg_Waistcoat_NPC* Feminine_Med_Waistcoat_NPC* Masculine_Lrg_Waistcoat_NPC* Masculine_Med_Waistcoat_NPC | description | yet to be revamped | Waistcoat LUT |
### Voice
There are currently two voices, "Big_Guard" or "Huge_Guard". A table giving more information should go here when more voices are added.
### Custom LUTs and head props
This is a subject of it's own, to customise the look of your characters further you will want to read up on[Head props](Head_props.md)and[Character Colours](Character_Colours.md).
### Virtual characters
Once you have created your virtual characters in order to use them within conversations you will have to add them to a network that is shared with the player. By default the mission script includes a mobile network called "Semaeopus4G" to connect other characters to this network you must use the ConnectToNetwork function. For example:`Mission.ConnectToNetwork(mission.characters.terrance,mission.networks.Semaeopus4G.name,mission.networks.Semaeopus4G.userAccessKey)`
### Adding Guards
When creating guards you must add:
* Spawn points
* Patrol route
* Profile
* Agent
```
-- Guard definitions:
	characters = {
		guard01 = {
	             displayName = "Thomas Template",
	             internalName = "Thomas",
	             characterType = "enemy",
		     prefab = "bigGuard",
                     profile = "GuardTemplate.lua",
                     agent = "Guard.lua",
		     spawnpoint = "GuardSpawn",
                     patrolroute = {
                             points = {
                                      "PatrolPoint_0-001",
                                      "PatrolPoint_0-002",
                                       },
                                      cyclic = false,
                                      },
		         },
	            },
```
#### Spawn points
To create a spawn point:
* Create empty game object
* Add the mission object script to the empty game object
* Select type "Spawn"
Your inspector should look something like this:
#### Patrol route
To create a Patrol point:
* Create empty game object
* Add the Patrol point script to the empty game object
* Within the Patrol point script component section you can define the maximum and minimum time a guard spends at the particular point.
* Repeat this process for as many points as you require.
Your inspector should look something like this:
#### Profile
When creating a guard you can give each one a personal profile, which will effect how each guard communicates and behaves.
This is a basic template and structure you should use:
```
Character ={

    Motivation = 0.6,
    Sociability = 0.5,
    FavouriteColor = { 1, 0.5586207, 0, 1 },
    Background = {

		FirstName = "THOMAS",

		LastName = "TEMPLATE",

		Nickname = {
			"Tommy",
		},

		DerogetoryName = {
			"Noggin",
		},

		FavouriteSwear = {
			"gosh-darn",
		},

		FavouriteFood = {
			"slice of Wensleydale cheese",
		},

		FavouriteSnack = {
			"Babybell",
		},

		FavouriteDrink = {
			"coffee",
		},

		BestFriend = {
			"Tristan",
		},

		RecipientPetName = {
			"Sweetums",
		},

		SenderPetName = {
			"Hubby",
		},

		FavouriteExclamation = {
			"Golly",
		},

		RandomHashtag = {
		  "#ROFL",
		},

		Mood = {
	    "happy",
		},

		PastEvent = {
		 "ate",
		},

		FutureEvent = {
			 "eat",
		 },
     },
    },
```
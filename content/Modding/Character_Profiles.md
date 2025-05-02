# Character_Profiles

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Character_Profiles*

*Scraped on: 2025-05-02 18:43:44*

Characters in Off Grid are defined in two places. First, the character's name, type, and few other details are set in your level's mission Lua script, in the*characters*-table. Then, for certain character types, you'll also need another Lua script that describes their personality and contains a profile to describe the character's background.
There are some pre-made personality scripts available in the [Common folder](Common_folder.md), but be aware that a background profile should be used for one character only, so if you grab a certain guard's personality script and use it in your level, that will be*the same guard that was walking around some other level*. If you want a new character, it's usually the best to just create a duplicate of one of the existing files inside your mission's folders, and edit the values to fill in some background info about your new character.
Another thing worth keeping in mind is that if you have same character in multiple levels, you should always use the same name for the character, both in your mission scripts and in the personality script. This makes sure the social engineering mechanics recognize that character correctly and any new information the player learns is matched with the correct profile.
You*can*, however, use a different personality file for the same character in different missions. One reason to do so would be to have some background information about your character that the player only learns about later on in your multi-level story line.

## Mission script and different character types
### Player
For the player character you only need few pieces of information in the mission script. Set the*internalName*,*characterType*and*prefab*all to "player", and*spawnPoint*to name of the MissionObject you are using as player's starting location.
```
-- Character definitions:
	characters = {
		player = {
			displayName = "Joe Harman",
			internalName = "player",
			characterType = "player",
			prefab = "player",
			spawnpoint = "PlayerSpawn",
		},
	},
```
| Character Table | Name | Description |
| --- | --- | --- |
| displayName | The name that will be used any game UI referencing the character |
| internalName | The internalName can be thought of as the id for the character, you'll reference the character by this value in a few places including conversations (Must be unique!) |
| characterType | The 'type' of the character, see[Character Types and Prefabs](Character_Types_and_Prefabs.md)for more information on possible values |
| 'prefab' | The prefab for the character, see[Character Types and Prefabs](Character_Types_and_Prefabs.md)for more information on possible values |
| spawnpoint | The name of the spawn mission object, the position of this object will be where the character is spawned |
### Enemies
```
-- Character definitions:
	characters = {
		guard1 = {
			displayName = "Marcus Fordham",
			internalName = "guard1",
			prefab = "M_Lrg_LongJacket-01",
			characterType = "enemy",
			colorTexture = "M_Lrg_LongJacket-01_Col_Docker01.png",
			metalSmoothTexture = "M_Lrg_LongJacket-01_Met_Docker01.png",
			profile = "BigGuard-Mk3-4.lua",
			spawnpoint = "GuardSpawn-1",
			patrolroute = {
				points = {
					"PatrolPoint-1",
					"PatrolPoint-2",
					"PatrolPoint-3",
					"PatrolPoint-4",
					"PatrolPoint-5",
					"PatrolPoint-6",
				},
				cyclic = true,
			},
		},
	},
```
| Character Table | Name | Description |
| --- | --- | --- |
| displayName | The name that will be used any game UI referencing the character |
| internalName | The internalName can be thought of as the id for the character, you'll reference the character by this value in a few places including conversations (Must be unique!) |
| characterType | The 'type' of the character, see[Character Types and Prefabs](Character_Types_and_Prefabs.md)for more information on possible values |
| 'prefab' | The prefab for the character, see[Character Types and Prefabs](Character_Types_and_Prefabs.md)for more information on possible values |
| spawnpoint | The name of the spawn mission object, the position of this object will be where the character is spawned |
| colorTexture | Name of the color look-up texture used to customize the character model |
| metalSmoothTexture | Name of the metallic/smoothness look-up texture used to customize the character model |
| profile | name of the character's profile file |
| patrolroute | list of PatrolPoint objects placed in the scene, defining the guard's patrol route; and setting for changing between cyclic and back-and-forth patrol modes. |
### Drones
### Neutral characters
### Virtual characters
Virtual characters are not physically present in your scene, but still exist "somewhere else". They can take part in conversations, own files, and can be connected to networks so they can send files to the player, and player to them.
As such, they only need minimal information in your mission scripts. Just setting the*characterType*to*virtual*, and filling in*internalName*and*displayName*is enough.
```
-- Character definitions:
	characters = {
		smedley = {
			displayName = "Smedley Butler",
			internalName = "Smedley",
			characterType = "virtual",
		},
	},
```
## Character personality files
Personality files are divided into 3 sections; "Stats", for numeric data used to set default values for various personality traits and tracked values; "Colors", which is used for color data and for now should only contain single entry for "FavouriteColor"; and finally "Profile, which contains the main bulk of the character's background information.
All information is listed using the same format, data + tags. And both of these can either be individual strings, or lists of strings. (So you can in one go define multiple pieces of information that all have same tag, or single string of information that has multiple tags. In case of Stats or Colors, the "data" should of course be a float between 0 and 1, or a  list of four floats (to represent red, green, blue and alpha of RGBA color).
At the moment, the required information every character must have includes:
* Motivation (float 0-1)
* "FavouriteColor" (colour)
* "FirstName"
* "LastName"
In addition, having a value for "Gluttony" in Stats section will change the character model between thin and fat one based on the value.
Due to how our social engineering mechanics work, the more information there is defined about a character, the easier it is for the player to collect enough unique pieces of knowledge to gain access to that character's devices etc. If there's only few pieces of information, the player is more likely to just find character metadata he already knows about, which won't then contribute to the total gained knowledge. Since the data player can find about characters is procedural, and randomized, it's best to make sure there's decent amount of information about every character you create, as searching through duplicate data to collect large enough profile about a character would be more tedious than enjoyable for the player. If the goal is to make certain character's devices more difficult to access, it's recommended to increase the difficulty on the device script rather than by limiting the character's profile size.
...and, of course, the tags we have used in our existing profiles are not a limitation, feel free to add any new ones as you go, there is no limitation to what you can add!
(If you end adding lots of new interesting tags, it might be worth checking out the Lua scripting for[Message Templates](Message_Templates.md)as well, so you can put those tags into good use)
```
Character = {
	Stats = {
		{ data = 0.6, tags = {"Motivation"}},
		{ data = 0.5, tags = {"Sociability"}},
		{ data = 1.0, tags = {"Gluttony"}},
	},
	Colors = {
		{data = { 0.1490196, 1, 0.5819339, 1 }, tags = {"FavouriteColor"}},
	},
	Profile = {
		{ data = "Simon", tags = {"FirstName", "name"} },
		{ data = "Wasserman", tags = {"LastName", "name"} },
		{ data = {
			"Tommy",
			"T-dog",
			"Bumpkin",
			"Essex-boy",
			},
			tags = {"NickName", "name"}
		},
		{ data = "Dickhead", tags = {"DerogatoryName"} },
		{ data = "Asshat", tags = {"FavouriteSwear"} },
		{ data = "bread meat bread", tags = {"FavouriteFood", "food", "favourite"} },
		{ data = "crisps", tags = {"FavouriteSnack", "food", "favourite"} },
		{ data = "Irn Bru", tags = {"FavouriteDrink", "drink", "favourite"} },
		{ data = "Tristan", tags = {"friend", "BestFriend"} },
		{ data = {
			"Sweetums",
			"Dimps",
			"Tata",
			},
			tags = {"PetName", "name"}
		},
		{ data = {
			"Golly",
			"Oh man",
			"Cripes",
			"Gosh",
			"Geez",
			"Geewhiz",
			"Grrr",
			"gahhh!",
			"Ahhh",
			"WTF",
			},
			tags = {"exclamation"}
		},
		{ data = {
				"#ROFL",
				"#Grrr",
				"LMAO",
				"LOL",
				"#Tots",
				"#BigGuns",
				"#Life",
				"#WTF",
			},
			tags = {"hashtag"}
		},
		{ data = {
			"happy",
			"excited",
			"sad",
			"frustrated",
			"upset",
			"down",
			"good",
			},
			tags = {"mood"}
		},
		{ data = {
			"ate",
			"had lunch",
			"went for a walk",
			"got up",
			"broke into your house",
			"spoke to my doctor",
			"released a mobile game",
			"checked the scores",
			"procrastinated",
			},
			tags = {"PastEvent"} },
		{ data = {
			"eat",
			"have lunch",
			"take a nap",
			"go skydiving",
			"sleep",
			"speak to your wife",
			"speak to my doctor",
			"get my doctor's degree",
			"run in the rain",
			},
			tags = {"FutureEvent"}
		},
	}
}
```
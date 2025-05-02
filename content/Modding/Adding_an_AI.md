# Adding_an_AI

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Adding_an_AI*
*Scraped on: 2025-05-02 18:40:54*

# Adding AI to your level
This page will guide you through the process of getting an AI Agent into your level. You should already have created your level, and have the mission script for it open before you start!
## The Characters Table
The first step is to add a table to the characters table in the mission script.
```
-- Character definitions:
	characters = {
		guard = {
			displayName = "Marcus Fordham",
			internalName = "Marcus_Fordham",
			prefab = "hugeGuard",
			agent = "Guard.lua",
			characterType = "enemy",
			profile = "MarcusFordham.lua",
			spawnpoint = "guard1spawn",
			patrolroute = {
				points = {
					"PatrolPoint_F0-LobbyStairsA",
					"PatrolPoint_F0-LobbyDiningHallA",
					"PatrolPoint_F0-DiningHallSnackMachine",
				},
				cyclic = false,
			},
		},
	},
```
| attribute | type | description |
|-----------|------|-------------|
| displayName | string | The name of the character that will be displayed in-game. |
| internalName | string | The name that will be used within the game. This is the name that would be used with the API. |
| prefab | string | The prefab to use. |
| colorTexture | string | The colourising texture to use. |
| metalSmoothTexture | string | TBC |
| agent | string | The agent definition to use. |
| characterType | string | enemy, virtual, npc or player. |
| profile | string | The personality file to use. |
| spawnpoint | string | Where the Agent will first appear. |
| patrolroute | string | The (optional) set of points that the Agent will patrol along. |
| sounds | string | The (optional) table of sounds specific to this character that will be used by this character when performing certain actions (see below). |

Let's look at a few of these in more detail.
### prefab
These are currently hard coded. This will be changing in time. The current options are:
| prefab name | description |
|-------------|-------------|
| player | Joe, our protagonist. |
| hugeGuard | A big, burly male. |
| Secretary | Female office worker. Also can be seen as the leader of the shady government forces in the intro. |
| drone | A drone. |
| M_Lrg_LongJacket-01 | A large male. |
| M_Lrg_Waistcoat-01 | A large male. |
| M_Med_SmartShirt-01 | An average sized male. |
| F_Med-WorkSuit-01 | An average sized woman. |
These can be colourised using the attributes "colorTexture" & "metalSmoothTexture".
### agent
There are currently two basic Agent definitions that can be used - "Guard.lua" & "OfficeWorker.lua". For information on writing custom Agent definitions, see[Agent Definitions](Agent_Definitions.md).
### patrolroute
Agents with a PatrolAction need a list of GameObjects within this table.
### sounds
Many agents can share the same agent profile (so that they will behave in largely the same way). But variety is important, so the sounds table can be used to customise the audio responses among your AI. This might mean that one agent is more talkative than another, says something specific when chasing the player, etc.
Here's an example sounds table (which would form part of your character table):
```
sounds =
	{
		Patrol = "Play_Bored_Patrol",
		SearchIntruder = "Play_Excited_Search",
		UseCoffee = "Play_Want_Coffee",
	}
```
So what happens to these? Each Action has a name; some are special cases (like "Patrol"), and some are defined by the agent definition ("UseCoffee" is the name of the action that is produced by adding "Coffee" to your AI's canUse table). Each action is looked at in turn, and any that match the string name (in the example table, these are Patrol, SearchIntruder & UseCoffee) have their audio event set to the value of the corresponding string, which should exist in your soundbank. So in this example, when the UseCoffee action is active, the sound event "Play_Want_Coffee" will be triggered. Note that this will be played when the agent is in its move phase, so if there is some distance between the agent and this action's target, the event will occur well in advance of the actual action being performed. Audio to be played during the Action's performance should be added to the Agent Definition itself.
## SetupMission
This is the first function to run. For all the magic to work, the Mission has to have each character added to it. There are two methods of doing this:
All in one go!
```
for k, character in pairs(mission.characters) do
		Mission.AddCharacter(character)
	end
```
Or one by one.
```
Mission.AddCharacter(mission.characters.guard)
```
## StartMission
This function is called after SetupMission, and you can rely on certain things being done by this point (such as characters being present, among other things)! As a result, we can start to do things to our character. The most important being adding it to a network (or two, or three). Not much of a hacking game otherwise!
```
Mission.ConnectToNetwork(mission.characters.guard, mission.networks.4G.name, mission.networks.4G.userAccessKey)
	Mission.ConnectToNetwork(mission.characters.guard, mission.networks.WiFi.name, mission.networks.WiFi.userAccessKey)
```
For more information on networks, please refer to XXXX.
So what else? It's quite possible that you want to empower your character with the ability to get through doors. If you've not covered the Door System yet, follow the link.
```
Doors.AssignKeyToCharacter("Security", mission.characters.guard)
```
This is probably the bare minimum required to get a new Agent into your level. But there's more that can be done, so keep in mind that the AI API (and others) can be used to create interesting behaviours during your mission. There's nothing to stop you from making all your Agents tired after the player finishes an objective, for instance, and that's just one example.
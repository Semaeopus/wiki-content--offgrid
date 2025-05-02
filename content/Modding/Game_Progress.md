# Game_Progress

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Game_Progress*

*Scraped on: 2025-05-02 18:38:08*

Off Grid is built to support much more complicated stories than the linear main story is. And it's also built to allow modders to hook their own new missions or stories in middle of the original story and it's missions. This means that there is no existing script that tells"when you've completed this level, load this other level next" and so on until you've completed the game. Instead, we've set up a system based on simple preconditions and effects that tell what's needed for a mission to "unlock" in game so it can be played, and how completing that mission changes the game world (or story, or characters, or whatever you might want).

## GameProgress
The GameProgress is a list of key & value pairs, stored as part of your save games, and the main mechanism for telling what missions you've completed, which ones are available now, and also what specific extra objectives you might have completed, the player's relationships with different characters due to choices made in conversations and so on. The list itself is simple enough, each piece of saved data has a name, and a value (which is just a text string).
For example your save gamne might contain data like this:
```
"ApartmentIntroCompleted" = "false"
"CourthouseCompleted" = "false"
"IntroductionCompleted" = "true"
"NewspaperCompleted" = "false"
"FoundDevLaptopInHarbor" = "true"
```
It's worth keeping in mind that the values are stored as strings, so*"true"*and*"True"*would not be the same thing, and you are not limited to saving just true/false values, for example if you want to do a branching story you can save the name of the branch in the game progress and easily trigger different things based on that information.
Since this information can be used (and changed) throughout the game, in your mission scripts, conversations, based on devices you hack and files you gain, it's worth using names that actually describe something that was done. That way it's much easier to keep track of what the data actually means, and to hook into the same values in more interesting ways, and to combine and mix different levels and mods and stories together.
For example, if the objective of your mission is to connect a server at Semaeopus Headquarter's data center to the Mesh network, you might want the effect of completing that mission to be *"SemaeopusServerConnectedToMESH" = "true"*  rather than *"CompletedLevel12" = "true"*. Think of it as events happening in your story rather than just mechanism for triggering the next mission.
## Missions
Each mission has a *level.json* file that tells the game some necessary background data about the mission. Which asset bundles are needed, which Unity scene to load, where and when the mission takes place and so on. If you are using LevelKit, you don't need to edit this file by hand, the LevelKit tools let you fill in all the required information. But which ever way you do it, you'll probably want to make sure you fill in suitable GameProgress information to control when your mission should be playable, and how it affects everything else in the game (if it does, of course).
### Preconditions
Preconditions are used to tell when the mission is available to play. Each value listed here*must*exist in the saved GameProgress, and the value*must*match with the precondition.
If any listed value doesn't match, or is missing, that mission will not be selectable to play in the map screen until the conditions are met.
### Effects
Effects describe what changes when player completes the mission. Usually this would be what you want to happen in overall GameProgress as the result of that mission being completed, and what's needed for the next mission to become playable. However it's not*required*to have an effect, for example if you just want a mission that can be played again and again for some reason. Or, if you are setting the required values from something else in your mission. (for clarity, it's probably best idea to set it here if there's only one possible outcome for the mission anyway).
If you are building a branching narrative, you could leave the mission effect empty, and instead set some value in your mission script (or some other script, of course) based on the choices the player made. As far as the GameProgress system is concerned, there's no difference between a value set as part of mission definition versus a value set somewhere else.
### Rules
Rules allow you to set some initial values in GameProgress. Any value that doesn't exist in the GameProgress yet will be added there as soon as the game recognizes a mission with a rule. So in practice the first time you start a new game, it looks for all rules form all missions in the game, and fills in your GameProgress based on them. And if you later on get a mod or expansion that adds new missions, the first time you start the game with those installed their rules will be added as well (as long as they don't try to overwrite some value that was already there, of course).
For most of the mission you create you shouldn't need to add any rules at all. But when you create a new storyline, you might need something in place to make the first mission of the story playable or to add some other background data about that story.
### Example of multiple missions
### About level.json syntax
If you for some reason end needing to edit the level.json file by hand, you'll notice the keys and values are stored on separate arrays. This is for sake of easy reading & writing of those files from the game. Just put the keys and values in their own arrays in matching order.
```
"preconditions": {
	"keyArray": [
		"NewspaperCompleted",
		"WorkplaceCompleted"
	],
	"valueArray": [
		"false",
		"true"
	]
},
"effects": {
	"keyArray": [
		"NewspaperCompleted"
	],
	"valueArray": [
		"true"
	]
},
"rules": {
	"keyArray": [
		"NewspaperCompleted"
	],
	"valueArray": [
		"false"
	]
}
```
## Using GameProgress in mission scripts, conversations etc
You can check if a value exists in GameProgress, read the value, change it or add new one from any Lua script in Off Grid. This is all done using the [GameProgress Lua API](GameProgress_Lua_API.md).
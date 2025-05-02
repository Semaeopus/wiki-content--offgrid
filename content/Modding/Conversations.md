# Conversations

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Conversations*

*Scraped on: 2025-05-02 18:39:07*

## Contents
* *1How to write up a crypto chat conversation*
* *2Set up a trigger volume*
* *3In the mission script, create the trigger*
* *4Create the objective*
* *5Creating the actual conversation*
* *6Call back functions*
* *7Single messages*
## How to write up a crypto chat conversation
The in game conversations through cryptochat are an important way to deliver narrative context, tutorialisation of tools and mechanics, or telegraphing the goals and objectives you might need to, to a player playing your level.
To start building your own conversations you only need to know the locations of two lua scripts,
our old friend the 'Mission Script' which as a reminder sits in` Assets\StreamingAssets\Levels\*YourLevelName*\Scripts `
and then a new script, or actually scripts, you see each conversation is its own lua script found in` Assets\StreamingAssets\Levels\NewsPaperOffice\Conversations `
Create a new file for your new conversation and give it a name, it can be anything, it is only used a reference for starting the conversation, tieing the name to an objective or event can make it easier to keep in your head when and where the conversation will be called while editing them. The example we are using here is **testConversation.lua**
The file path for the conversations lua files
Conversations can be triggered in many different ways but the most basic example is by a trigger volume such as a mission object.
## Set up a trigger volume
Create a game object and give it a name, in this example "MissionObject_1_1"
Give it a mission object component, set the drop down to trigger
Make sure the game object has a box collider, and tick the isTrigger box.
## In the mission script, create the trigger
```
-- [[ Mission triggers & interactions]] --

MissionObjects["MissionObject_1_1"].OnTriggerEnter = function(name)
	if name == Player.GetName() then
		Mission.StartObjective("enterbuilding")
	end
end
```
This will fire off the objective on player entry.
## Create the objective
Here we create the 'enterbuilding' (or objective name of your choosing) objective.
```
-- Mission objectives:
	objectives = {
	--[[ Find way into the building ]]--
		enterbuilding = {
			name = "Etner the Building",
			description = "Try to find a way to sneak in to the Apostle offices.",
			onStart = function()
				print("Started objective 'enterbuilding'")
				**Conversation.StartScript("testConversation")**
			end,
			onCompleted = function()
				print("Completed objective 'enterbuilding'")
			end,
		},
```
The operative part of the objective here is obviously the moment where we call **Conversation.StartScript("testConversation")** and so now we have all the constituent parts.
## Creating the actual conversation
You have already created your conversation script (the example being 'testConversation.lua' that you created at the start of this example) open up this file and then we are ready to get down to the creative bit.
Our example conversation looks like this:
```
anger = 0
sendData = true
encrypted = true
singleMessage = false

characters = {
	"Joe",
	"Smedley",
	"Terrence",
	-- "HW",
}

begin = function()
	Send( {"Smedley", "Joe..."} )
	Send( {"Smedley", "you there yet?"} )
	SendResponse( {"yes"} )
	Send( {"Smedley", "Ok this is Terrence, the newspaper editor I told you about"})
	Send( {"Terrence", --[["theapostle_obj_enterbuilding_msg_1"]] 
	"Thanks for turning up, I know this was a strange request. Firstly you're going to need to find a way into the buildings server room in the basement"})
	Send( {"Smedley", 
		function() 
			return "Yeah, follow my cues and we'll work that out, something like " .. tostring(math.random(1, 40)) .. " young people have been vanished without a trace in the last " .. tostring(math.random(1,4)) .." months."
			end } )
	-- Send( {"HW", "Oh, it's you."} )
	SendResponse( { "Yes but what the hell am I doing here?!", rude }, { "But why a newspaper office?", ignore } )
end

rude = function ()
	anger = anger+1
	Send( {"Smedley", "Keep calm, we have alot to get through"} )
	continue()
end

ignore = function ()
	anger = anger-1
	Send( {"Terrence", "Apologies for being cryptic, I promise all will be revealed"} )
	continue()
end

continue = function()
	End()
end
```
There is quite a lot of power behind the conversations system, it's open to being made in the sprawling, branching mess you have always dreamed of creating, or purely an interactive way of tailoring the humour of the player, with a few witty conversational choises and apt trite responses.
Not only this but you can run functions within conversations to either draw from variables or use mathematical operators, to create complex reactions that draw on 'memory' of previous events in the game.
The conversations themselves can run generate or add to variables, giving the ability to track elements of the conversation and use it to influence events later in the game for instance unlocking a mission by selecting a particular conversation path could be done by having certain choices add increment a variable with each correct selection. That variable reaching the correct value would then unlock the level.
More subtly perhaps this functionality could be used to track the players temperament by choices and give varied reactions from different characters dependent on how the player chooses to talk to them.
## Call back functions
It's also possible to get interesitng things to happen once a conversation has ended
```
Conversation.StartScript("path/to/conversation", callbackFunc)

    function callbackFunc() { makeModal() }
```
an example would be:
TO BE COMPLETED...
## Single messages
If you need want to just send a single message from a character to player, without pausing the game for a full-on conversation, you can do that by setting the*singleMessage*variable in the conversation to*true*.
```
sendData = true
encrypted = true
singleMessage = true

...
```
Other than that, the script works exactly like normal conversations. However keep in mind that the UI is built for reasonably short single messages only, any buttons for player responses etc will not be displayed at all, and the single message window closes automatically after a while. But most importantly, because the game doesn't pause for the message and there's no guarantee the player pays any attention to it, or notices it soon enough to read it fully,**single messages should never be used for any important things.**If there's something you need the player to be aware of, use normal conversation instead (or a modal popup).
If the*singleMessage*option is not included in the script, the game defaults to normal conversation.
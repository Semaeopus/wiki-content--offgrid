# Agent_Definitions

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Agent_Definitions*

*Scraped on: 2025-05-02 18:43:25*

Each AI's behaviour is defined by its Agent definition.
# Concepts
## GOAP State
The World State and Goal states are made up of GOAP States. GOAP stands for "Goal-Oriented Action Planning". Each state comprises a unique string ID, and a boolean (true/false) value. The state as a whole is made up of multiple state items.
| GOAP State Item | Name | Description |
| --- | --- | --- |
| state | The unique name of the state. |
| value | The true/false value. |
A state is made up of 1-n items. This can be represented either as
```
{
	{ state = "amused", value = false },
	{ state = "tired", value = false },
}
```
or, for a state with a single item in, as
```
{ state = "amused", value = false }
```
...which saves some slightly untidy extra braces. Note that in the former example, the items are just an anonymous list, the keys are implicit. GOAP State is a type that will appear throughout this guide and it is always parsed in the same way.
## Personality
Each AI (TBC: Human AI?) should have a[personality profile](Character_Profiles.md). This describes the AI's likes, loves, family, dog... anything you like. This is one of the main mechanisms for differentiating behaviour between agents - thus allowing a player's actions to affect multiple agents in multiple ways, and allows for complex behaviour. The mechanism for doing this is the Personality Requirement.
| Personality Requirement | Name | Type | Description |
| --- | --- | --- | --- |
| subject | string | The primary tag that this requirement is seeking. |
| value | string | Optional. The value that has a tag matchingsubject. |
| other | string | Optional. Another tag, or list of tags, that the value must match with for this requirement to be satisfied. |
| inverse | boolean | Defaults to false. Setting to true swaps the result of the requirement - so a match means the requirement fails, and the lack of a match means the requirement passes. |
Here's a snippet of a Personality Profile.
```
{ data = { "HipHop", "Pop"}, tags = { "music", "likes" } },
{ data = { "Rock"}, tags = { "music", "dislikes" } },
{ data = { "Classical", "HipHop"}, tags = { "music", "relaxes" } },
{ data = { "LiverpoolReds" }, tags = { "sport", "likes", "celebrates" } },
```
So, this AI considers that HipHop & Pop are both music, and they like it. They consider Rock to be music, but they dislike it. They consider Classical and HipHop to be music that relaxes them. They consider LiverpoolReds to be related to sport, they like it, and they celebrate it.
The only mandatory part of a requirement is the subject. The subject is merely a tag, but it's the tag we look for first, and it's the tag that can be specified by[API call ChangeSubject](AI_Lua_API.md). Let's write a requirement that will pass using only the subject.
```
personalityRequirement = { subject = "music" },
```
This requirement, wherever it's used, will pass if the subject of "music" is set to "HipHop", "Pop", "Rock", or "Classical". So for instance, we might trigger a Dance Action if music is set to any of these. But that might not make a huge amount of sense for this AI, because they're not so keen on Rock music. So let's add an extra tag that we need for this requirement to be satisfied.
```
personalityRequirement = { subject = "music", other = "likes" },
```
This means the requirement will no longer pass for "Classical" or "Rock", because they aren't tagged as "likes" in their profile. That makes more sense! But... do we want the AI to perform the same dance to "HipHop"*and*"Rock"? Possibly not. This is where the value attribute is useful.
```
personalityRequirement = { value = "Rock", subject = "music", other = "likes" },
```
This requirement only passes for agents who like Rock music.
Finally, what's inverse for? Essentially, it's for checking for the absence of something. Consider the requirement
```
personalityRequirement = { value = "ManchesterBlues", subject = "celebrates", inverse = true },
```
Well spotted - "ManchesterBlues" is not present in our profile snippet. This means that, without the inverse flag, this requirement would fail. But with it, it passes! So, supposing we had a radio which set the subject as "celebrates", and the value as "ManchesterBlues", we could get this AI to sob gently to himself, while the one stood next to him is overcome with joy.
## Statistics
Each statistic is a tracked, saved, numerical value that represents a particular aspect of the AI. The value is clamped between 0 and 1. Each stat has two lists, above and below, of names and thresholds. These will become world states that become true when the value becomes greater or equal/lesser or equal (respectively) to the threshold value. Statistics can be adjusted by*actions*,*responses*, and*reactions*. In doing so the*world state*may change, and new*goals*become achievable.
Personality Effects will be referred to throughout this, so let's dig into them here.
| Personality Effect | Name | Type | Description |
| --- | --- | --- | --- |
| stat | string | The unique name of the stat. |
| adjust | number | The value to be added to the current value of this stat. Use a negative number to reduce it! |
One of the simpler tables in the Agent Definition. Simply put, when this effect happens, the named*stat*will have*adjust*added to it. The stat will then be clamped in the range 0 - 1, and the world states that rely on it will be recalculated.
### Usage / Intention
# Personality Effects

Personality Effects may or may not be a great name for these, but we are stuck with them! You may consider them to be side effects or secondary effects - things that happen as a result of an Action, that aren't to be taken into account when planning. Also, because they act upon statistics ranging from 0-1, the effects can be gradual.

## Example: Soda Machine

A simple example would be a Soda machine. An Agent may plan to use the soda machine because they are thirsty, because they need energy, because they are bored - or a combination. All valid use cases. However, a side effect of drinking is the need to go to the toilet! 

Nobody has a drink with the aim of going to the toilet, but it's something that happens. So a Soda machine could quite feasibly:
- Stop an Agent from being thirsty (requirement of "isThirsty" = true, effect of "isThirsty" = false)
- Add personalityEffect of "bladder-o-meter" adjust = 0.2

Thus, each time an Agent uses the Soda machine, their bladder-o-meter is incremented by 0.2. Depending on the threshold of the bladder-o-meter stat, a world state change will eventually happen, and the Agent will have to consider going to the toilet - depending on the priority of the toilet goal, of course!
# File Format
The definition is a single table, named Agent, containing several tables that define different aspects of an Agent.
## Fails
This table contains a string or strings that are turned into [AI_Gestures](AI_Gestures.md) and used when the Agent no longer has a valid goal. So if you add "Yawn", and see your agent yawning, constantly, they probably don't have anything better to do! Ensure you type the gesture precisely - it's case sensitive.
## World State
The World State is a description of everything an AI knows about, in the context of planning. It is simply a*GOAP State*.
## Goals
A Goal is a state that an Agent desires to be in. The planner will seek to use the Actions at its disposal to come up with a plan (set of Actions) that it can run to adjust the current World State so that it includes the Goal state. At its heart is a*GOAP State*, but it has some extra wizardry too.
| Personality Effect | Name | Type | Description |
| --- | --- | --- | --- |
| goal | table | A*GOAP State*. |
| interrupts | boolean | Defaults to false. When set to true, this Goal will interrupt any of lower priority if it becomes achievable. For instance, chasing the player is more important than eating a snack. |
| priority | number | The higher the priority a goal is, the more important it is. As a result it will be attempted before lower priority goals. |
| onCompletion | table | Optional. This is a*GOAP State*that will be applied to the*World State*when this goal is successful. Useful for cyclic tasks (e.g. patrolling). |

So the goal state is what we would like our world state to include (it doesn't have to be an exhaustive list of all the state items we know about). 

Any difference between goal and world mean it is a candidate for planning, where we try to use Actions we have that we are able to perform to turn our world state into the goal state. 

If the goal interrupts, it means that the agent will stop what its doing if it's suddenly possible for this goal to be achieved.


The onCompletion state is useful for undoing changes made in the course of planning (or 'unlocking' state for another goal). 

So it might be that once your AI has patrolled you reset "patrolled" back to false so that it can patrol again.

## Stats
List of *Statistics*.
Statistics are adjusted by PersonalityEffects. They're used to change the world state in a gradual way - so you might have an Action that slowly makes an Agent more and more tired, eventually triggering a change in world state that allows new goals to be planned for.
| Statistic Table | Name | Type | Description |
| --- | --- | --- | --- |
| name | string | Unique name for this statistic. |
| default | number | Default value for this statistic. |
| above | table | List of states that will become true when above or equal to the specified threshold (see next table). |
| below | table | List of states that will become true when below or equal to the specified threshold (see next table). |
| Statistic-State Table | Name | Type | Description |
| --- | --- | --- | --- |
| id | string | The name of the world state to be created. |
| threshold | number | Threshold for this statistic. Behaviour depends upon whether this state is in the above or below table. |

So, what might this look like?
```
{
	name = "happiness",
	default = 0.5,
	above = { 
			{ id = "elated", threshold = 1.00 }
			{ id = "cheerful", threshold = 0.8 }
		}
},
```
This stat is called happiness. It starts at 0.5. It has two world states, "elated", which becomes true at maximum happiness (1.0), and "cheerful", which happens when it's merely 0.8.
```
{
			name = "energy",
			default = 0.5,
			above = { id = "energized", threshold = 1.0 },
			below = { id = "tired", threshold = 0.0 }
		},
```
Notice that this one has a single entry in both above and below, missing out the nested brackets.
## Actions
An Actions is something that the AI **does**. In order to **do** it, it must have a particular world state. After having **done** it, it will change its world state.
| Action Table | Name | Description |
| --- | --- | --- |
| name | The name of the Action, which should be unique. |
| gesture | Optional. The gesture to play when performing this Action. |
| audio | Optional. The Wwise event to play when performing this Action. |
| effect | The effect GOAP State. This will be applied to the World State when this Action is performed. See XXXX |
| required | The required GOAP State. The World State must include this state in order for the Action to be used. |
| personalityEffect | Optional. The effect on personality stats that performing this Action has. |
| targetAgent | Default false. If true, the Agent requires that there be another agent nearby for this Action to be performed. |
| targetPlayer | Default false. If true, the Agent requires that the player be nearby for this Action to be performed. |
| targetRequirement | Optional. The required[personality profile](Character_Profiles.md)this AI needs for this Action to run. |
| data | Optional. When this Action happens, the data will be sent. The recipient of the data is held in the sending agent's worldstate. A state named {this action's name} with "DataRecipient" appended will be used for this. See the further explanation below. |
### Sending Data as part of an Action
This is where things become a little more complicated. Actions can result in an agent sending data. The data is fixed in the Agent profile, but the recipient is not - this is because this would mean this Action would require the presence of a particular device (which could be the mobile phone device of another agent). The solution to this issue is to store the name of this device in the world state (yes, states can hold data other than booleans!). The name of the state that this is stored in is derived from the name of the action itself.
Let's consider the following Action:
```
{
	name = "SendEmail",
	effect = { state = "hasMotivation", value = true },
	data = {
		internalName = "AI Email",
		name = "Data Name",
		description = "A description of this name",
		immutable = true,
		dataType = 3,
		creatorName = "Top Secret Source",
		dataString = "All Your Base Are Belong To Us",
	},
},
```
First we must work out where this is going to be sent, and change the relevant state within the AI that is performing the Action! The name of the Action is "SendEmail". The state that will be inspected to find the recipient is this name, with "DataRecipient" appended to it. So the state to store it in is "SendEmailDataRecipient". Let's see what this looks like for an example AI - in this case the AI is called "Edward", and the recipient is called "Julian":
```
AI.AlterNPCWorldState("Edward", "SendEmailDataRecipient", "Julian")
```
Now, if we were to inspect Edward's AI state, we would see that the state "SendEmailDataRecipient" is now set to the string, "Julian". This will be used by the Action. If and when Edward runs this Action, this data will be sent from him to Julian. If this state is not set, the Action will still run, but the data will not be sent (because there is nowhere for it to go).
## Special Actions
There are a number of special actions. These can be turned off if not required, but are on by default. You may like to explicitly mark them as "on" in your Agents.
### Patrol
The patrol action looks for Patrol points in the Mission definition, and uses the "patrolCompleted" world state; this state is set to true once a patrol is finished, and the common thing to do is to set it to false once this has happened (to repeat it), or after some other Action has happened (drinking coffee, receiving certain data).
```
canPatrol = true,
```
### Taser
This action tasers the player, if the player is within range. It uses the "hasPrisoner" world state; this is set to true after the player has been tasered, which is useful for ceasing all other activity after.
```
canTaser = true,
```
### Search
This action searches for the player, if the player has been seen but is no longer visible. It uses the "intruderVisible" world state, aiming to move the agent into a position such that this becomes true, allowing other behaviours (requiring the player to be in sight) to become available.
```
canSearch = true,
```
## Responses
A response is a method of adjusting an AI's personality stats when another AI performs an Action on them.
| Response Table | Name | Description |
| --- | --- | --- |
| Action | The name of the Action, which should be unique. |
| personalityEffect | The effect on personality stats that being the victim of this Action has. |
So what's the point of this? Basically, its purpose is to create a mechanism of having one AI's behaviour directly affect another. Recall the "targetAgent" attribute of the*Action*table. When this is true, the Action is performed*on*another AI. If we are that AI, our Responses are looked at, and if there is a Response that matches the Action that has been performed on us, our*effect*is applied to our stats. This is a neat way of creating chains of sociable Actions among AI. A player could send an SMS to two agents, resulting in one becoming sad and the other happy. The happy agent could then tease the sad agent, angering them, causing an argument! All allowing the player to sneak by.
## Reactions
A reaction is a method of adjusting an AI's personality stats when they do something, based on their[personality profile](Character_Profiles.md). These effects will be performed when[ReactTo](AI_Lua_API.md)is called, if the requirement is satisfied.
| Reaction Table | Name | Description |
| --- | --- | --- |
| personalityRequirement | The*requirement*, which, when reacted to, will bring about the effect. |
| personalityEffect | The*effect*on personality stats that occurs. |

Let's look at a quick example of how to use this.
```
{
	personalityEffect = { stat = "energy", adjust = -0.5 },
	personalityRequirement = { subject = "music", other = "relaxes" },
}
```
Here we have an effect that requires a personality entry that is tagged both as "music", and "relaxes". How does this get used? Well, for the purpose of this example, let's assume this AI has stepped into earshot of a radio, which has its own script. As a result, the following is called
```
AI.ReactTo(theAI, "music", "Classical")
```
What does this do? This says that the AI (which will be referred to by the variable theAI, a string referencing the AI's ID) should "React To" some external influence of tag "music", with the value of "Classical". If this requirement holds, the effect applies.
So the AI with this personality will have the effect applied, in this situation...
```
{ data = { "Classical", "HipHop"}, tags = { "music", "relaxes" } },
```
...and this AI won't.
```
{ data = { "Dance"}, tags = { "music", "relaxes" } },
```
### Reactions to Data
Agents can also react to data, and the key to this is the (optional) metadata within the DataPoint. This metadata can be compared with an Agent's personality, and Reactions can occur in much the same way.
Let's look at the following DataPoint table, that might appear in a mission script:
```
CoffeeOffer = {
			internalName = "CoffeeOffer",
			name = "theapostle_data_Coffee_name",
			dataType = 1,
			creatorName = "Baltar Beans",
			description = "text/UTF8",
			dataColor = {1.0, 1.0, 1.0, 1.0},
			meta = { { data = { "coffee" }, tags = { "drink" } } },
		},
```
Notice the meta table on the end. This tells the AI that the data is about "coffee", and that "coffee" is a "drink". How could we make use of this in a level?
Let's make a Reaction that makes use of this.
```
{
	personalityEffect = { stat = "thirst", adjust = 0.5 },
	personalityRequirement = { subject = "drink", other = "likes" },
}
```
This Reaction is looking for something that is tagged as a drink, and that the agent likes. To complete this example, we need to inspect some personality files.
This agent will React to this DataPoint, because they know that coffee is a drink, and they like it.
```
{ data = { "coffee", "tea"}, tags = { "drink", "likes" } },
```
This AI won't, because while they know coffee is a drink, they don't like it (it's tagged as "dislikes").
```
{ data = { "coffee"}, tags = { "drink", "dislikes" } },
```
...and nor will this one. This AI doesn't even know what coffee is.
```
{ data = { "tea"}, tags = { "drink", "likes" } },
```
#### One last thing...
It might be that you have a cunning piece of data that has to do something very specific. Don't forget you can use AI.ReactTo() (and many other API functions) in a DataPoint's luaScript - which is a lua script that is run when the data is received.
## Interests
An Interest may be a Device, or may simply be a particular part of a level that an AI needs to get to in order to perform an Action. An Interest is created by adding an InterestPoint to a GameObject (or making a new GameObject with an InterestPoint added). Be sure to orient the GameObject such that the Z axis is pointing in the direction the AI should use the InterestPoint from.
Note that each Interest may define its own World State which will be added to any AI able to use it - thereby guaranteeing that any adjustments the Device makes to AI using it are valid.
### canUse
This is a using Action. The Agent will attempt to reach the nearest Interest that they know to be working, and try to use it. If it's in an Amok state, this may fail. The table is pretty similar to a standard*Action*.
| canUse Table | Name | Description |
| --- | --- | --- |
| interest | The name of the InterestPoint this Action will take place at. |
| effect | The effect*GOAP State*. This will be applied to the World State when this Action is performed. |
| required | The required*GOAP State*. The World State must include this state in order for the Action to be used. |
| personalityEffect | Optional. The*effect*on personality stats that performing this Action has. |
| personalityRequirement | Optional. For this Action to be performed, this*requirement*must be satisfied. |
| gesture | Optional. This is the gesture to be played when the agent uses a working instance of this Interest. |
| gestureAmok | Optional. This is the gesture to be played when the agent uses an instance of this Interest that is in its Amok state. |
#### World State
Adding a canUse to an Agent also adds a state to its world state, in the form of "usedXXX", where "XXX" is the name of the interest; so an agent able to use a "Printer" will have a "usedPrinter" state, initially set to false. This is useful to create a sequence of "uses", perhaps within a goal where each state is reset upon completion.
### canFix
This will eventually be a fixing Action. (TODO!)
# Case Study
Brace yourselves for a long, long example from the game, with some discussion afterwards.
## Guard Example
The Guard is the standard 'enemy' AI currently in the game. Please be aware that the game is still in development and there may (will!) be bugs in this.
```
Agent =
{
	canPatrol = true,
	canTaser = true,
	canSearch = true,
	fails =
	{
		"Yawn",
		"WaitingHandsOnHips",
	},
	world =
	{
		{ state = "unreadMessages", value = false },
	},
	stats =
	{
		{
			name = "motivation",
			default = 0.5,
			above = { id = "hasMotivation", threshold = 0.01 }
		},
		{
			name = "energy",
			default = 0.5,
			above = { id = "energized", threshold = 1.0 },
			below = { id = "tired", threshold = 0.0 }
		},
		{
			name = "bladder",
			default = 0.0,
			above = { id = "needsToilet", threshold = 1.0 }
		},
		{
			name = "happiness",
			default = 0.5,
			above = { id = "happy", threshold = 1.0 },
			below = { id = "sad", threshold = 0.0 }
		},
		{
			name = "anger",
			default = 0.0,
			above = { id = "angry", threshold = 1.0 }
		},
	},
	goals =
	{
		{
			goal =
			{
				{ state = "hasPrisoner", value = true },
			},
			interrupts = true,
			priority = 100,
		},
		{
			goal =
			{
				{ state = "investigate", value = false },
			},
			interrupts = true,
			priority = 99,
		},
		{
			goal =
			{
				{ state = "intruderVisible", value = true },
			},
			interrupts = true,
			priority = 98,
		},
		{
			goal =
			{
				{ state = "happy", value = false },
				{ state = "sad", value = false },
				{ state = "tired", value = false },
				{ state = "energized", value = false },
				{ state = "angry", value = false },
				{ state = "needsToilet", value = false },
			},
			priority = 50,
			--interrupts = true,
		},
		{
			goal =
			{
				{ state = "patrolCompleted", value = true },
				{ state = "hasMotivation", value = true },
				{ state = "unreadMessages", value = false },
			},
			priority = 10,
			onCompletion =
			{
				{ state = "patrolCompleted", value = false },
			}
		},
	},
	actions =
	{
		{
			name = "Argue",
			effect = { state = "angry", value = false },
			required = { state = "angry", value = true },
			personalityEffect = { stat = "anger", adjust = -1.0 },
			targetRequirement = { state = "angry", value = true },
			targetAgent = true,

		},
		{
			name = "Tease",
			effect = { state = "amused", value = false },
			required = { state = "amused", value = true },
			targetRequirement = { state = "sad", value = true },
			targetAgent = true,
		},
		{
			name = "Laugh",
			effect = { state = "happy", value = false },
			required = { state = "happy", value = true },
			personalityEffect = { stat = "happiness", adjust = -0.5 },
			personalityRequirement = { subject = "amusing" },
		},
		{
			name = "Celebrate",
			effect = { state = "happy", value = false },
			required = { state = "happy", value = true },
			personalityEffect = { stat = "happiness", adjust = -0.5 },
			personalityRequirement = { subject = "celebrates" }
		},
		{
			name = "Yawn",
			gesture = "Yawn",
			effect = { state = "tired", value = false },
			required = { state = "tired", value = true },
			personalityEffect = { stat = "energy", adjust = 0.5 },
		},
		{
			name = "Despair",
			effect = { state = "sad", value = false },
			required = { state = "sad", value = true },
			personalityEffect = { stat = "happiness", adjust = 0.5 },
			personalityRequirement = { subject = "celebrates", inverse = true }
		},
		{
			name = "DanceGuitar",
			gesture = "DanceGuitar",
			effect = { state = "energized", value = false },
			required = { state = "energized", value = true },
			personalityEffect = { stat = "energy", adjust = -1.0 },
			personalityRequirement = { value = "Rock", subject = "music", other = "likes" },
		},
		{
			name = "DanceHipHop",
			gesture = "DanceHipHop",
			effect = { state = "energized", value = false },
			required = { state = "energized", value = true },
			personalityEffect = { stat = "energy", adjust = -1.0 },
			personalityRequirement = { value = "HipHop", subject = "music", other = "likes" },
		},
		{
			name = "DanceSalsa",
			gesture = "DanceSalsa",
			effect = { state = "energized", value = false },
			required = { state = "energized", value = true },
			personalityEffect = { stat = "energy", adjust = -1.0 },
			personalityRequirement = { value = "Salsa", subject = "music", other = "likes" },
		},
	},
	responses =
	{
		{
			action = "Tease",
			personalityEffect = { stat = "anger", adjust = 1.0 },
		},
		{
			action = "Argue",
			personalityEffect = { stat = "happiness", adjust = -0.5 },
		}
	},
	reactions =
	{
		{
			personalityEffect = { stat = "happiness", adjust = 0.5 },
			personalityRequirement = { subject = "celebrates", other = "likes" },
		},
		{
			personalityEffect = { stat = "energy", adjust = -0.5 },
			personalityRequirement = { subject = "music", other = "relaxes" },
		}
	},
	canUse =
	{
		{
			interest = "Soda",
			effect = { state = "hasMotivation", value = true },
			personalityEffect =
			{
				{ stat = "motivation", adjust = 1.0 },
				{ stat = "bladder", adjust = 0.1 },
			}
		},
		{
			interest = "Coffee",
			effect = { state = "hasMotivation", value = true },
			personalityEffect =
			{
				{ stat = "motivation", adjust = 1.0 },
				{ stat = "bladder", adjust = 0.1 },
				{ stat = "energy", adjust = 1.0 },
			}
		},
		{
			interest = "Snacks",
			effect = { state = "hasMotivation", value = true },
			personalityEffect = { stat = "motivation", adjust = 1.0 },
		},
		{
			interest = "Sink",
			effect = { state = "tooHot", value = false },
		},
		{
			interest = "Toilet",
			effect = { state = "needsToilet", value = false },
			personalityEffect = { stat = "bladder", adjust = -1.0 },
			required = { state = "needsToilet", value = true },
		}
	},
	canFix = {	},
}
```
Phew. Let's go over the sections in turn.
### Special Action Toggles
These are true by default, but let's include them explicitly. We want this Agent to be able to Patrol, Taser the player, and Search for the player. This allows us to make Goals later that use these Actions.
### World State
Brief - the single added state here is necessary to use the 'Read Messages' Action. Otherwise nothing of note here.
### Stats
We define five statistics here, and a total of seven world states. It's hopefully pretty clear what each is for. One point to note is that for the "motivation" stat, the threshold is 0.01 (an arbitrarily small number). This is because the 'above' threshold is greater than*or equal*. If we set the threshold to 0.0, "hasMotivation" could never be false.
### Goals
Let's look at this from top to bottom. The goals are in priority order (which isn't mandatory, but it makes working with large definitions easier).
The first three goals are special cases and use "special" states:
* "hasPrisoner", true: this occurs when an AI has caught the player. This is the ultimate goal of any Guard, interrupting all others.
* "investigate", false: If investigate is true, the AI must stop what it's doing and satisfy itself that the investigation is complete.
* "intruderVisible", true: This may appear counter-intuitive but it makes sense - the AI is always seeking Actions that enable it to see where the player is. However usually it has no set of Actions that enable it to achieve this state.
Next up we have a much bigger goal. You'll notice that all of these are mood related. The thinking behind this is that, if the AI ever gets into a non-default "mood" state, it should do something to get back to equilibrium. So if it's sad, it should cry a little and feel better. If it's happy, laugh a little - etc.
The final goal, our lowest, is the one that we want this AI to be doing most of the time. This is its bog-standard goal. It requires the agent have motivation, no unread phone messages, and that it hasn't completed patrolling already. Cunningly, it resets patrolling back to false every time it finishes, meaning it can repeat.
### Actions
These are all variations on the same theme; to 'undo' states that are caused by statistics reaching their extremes. Note that some have the same effect, but may occur when the AI is near another agent. In the case of the three dance actions, they all do the same job, but play different animations depending on their personality and environment.
### Responses
These mirror what exists in Actions, where there are two that target other agents. Because we (currently) have several guards running the same definition, it's important that if agent A does something to agent B, B will have some kind of response to it. Agent definitions by their nature will have dependencies on each other in this way, because without them the agents will not fully interact with each other.
### Reactions
These are two reactions that are used by the Radio device to adjust Agent stats, inducing the above Actions to take place. The first will aim to grant extra happiness to the Guard who supports the correct sports team, and the second will try to get a yawn out of an agent who finds the played music to be relaxing.
### canUse
The first three Interests are methods of recovering motivation, which is reduced by patrolling. Each modifies an agent's stats in different ways. The next Interest is the Sink, which is used to cool down a player who has been burnt by a malevolent coffee machine. The final Interest is the Toilet, which hopefully needs no explanation!
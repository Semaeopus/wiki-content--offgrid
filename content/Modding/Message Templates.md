
The messages that NPCs receive are generated from data in their [Character Profiles](Character Profiles) that is then fed into message templates in DefaultSMSCollection.lua.
```
{
	requirements = {
		"exclamation",
		"RandomHashtag",
		},
		content = "$exclamation, gonna be a busy shift! $RandomHashtag"
	},
```
The logic behind all this is located in the randomized SMS generator for Off Grid [SMS Generator](SMS Generator)lua file. This can be modded in a multitude of different ways - in case you want to mod the SMS generation to do something more fancy such as create a more fine grained model for the way the generator uses grammar, or support other language (bearing in mind that procedurally generated grammar rule sets will be harder for different languages!)

As a simpler way of extending the kinds of messages you want NPCs to generate, you can just add new tags and fields for data in the Character Profiles and then create new message templates in DefaultSMSCollection.lua and the generator will then use them.

Multiple pieces of data in a field will mean that you get move variety when the message template you have written is used.

Conversation
============

Description
-----------

Allows the user to start scripted conversations

Functions
---------

### StartScript

``` lua
Conversation.StartScript(path, onCompleteCallback)
```

**Expected parameter types**

| Name               | Type     |
|--------------------|----------|
| path               | string   |
| onCompleteCallback | Lua Type |

**Description**: Starts a conversation from Lua file

**Returns**: Nothing

**Notes**: Must be in MissionFolder/Conversations/\$path

Global Functions [global functions]
----------------

### Send

``` lua
Send(message)
```

**Expected parameter types**

| Name    | Type      |
|---------|-----------|
| message | Lua Table |

**Description**: Sends a message to the UI.

**Returns**: Nothing

### SendResponse

``` lua
SendResponse(message1, message2, message3, message4, message5, message6)
```

**Expected parameter types**

| Name     | Type      |
|----------|-----------|
| message1 | Lua Table |
| message2 | Lua Table |
| message3 | Lua Table |
| message4 | Lua Table |
| message5 | Lua Table |
| message6 | Lua Table |

**Description**: Sends player's repsonses to the UI

**Returns**: Nothing

### EndConversation

``` lua
EndConversation()
```

**Description**: Ends the conversation.

**Returns**: Nothing

This file is auto generated, please don't edit manually!

**Docs last hacked together on**: 09/12/2024 12:54

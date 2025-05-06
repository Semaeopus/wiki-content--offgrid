# Conversation_Lua_API

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Conversation_Lua_API*

*Scraped on: 2025-05-02 18:42:09*

# Conversation
## Description
Allows the user to start scripted conversations
## Functions
### StartScript
```
Conversation.StartScript(path, onCompleteCallback)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| path | string |
| onCompleteCallback | Lua Type |

**Description**: Starts a conversation from a name
**Returns**: Nothing
**Notes**: Must be in MissionFolder/Conversations/$path

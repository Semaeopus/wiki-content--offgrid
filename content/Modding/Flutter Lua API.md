# Flutter_Lua_API

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Flutter_Lua_API*

*Scraped on: 2025-05-02 18:41:57*

# Flutter
## Description
The Flutter API allows modders to send Flutter messages
## Tables
### FlutterMessage
**Table definition**
| Name | Type | Default | Optional | Description |
| --- | --- | --- | --- | --- |
| message | string |  | No | Content string for the message |
| hashTags | table |  | No | custom hash tags for the message |
| tags | table |  | No | metadata tags |
| metadata | table |  | No | metadata values |
## Functions
### SendMessageFromCharacter
```
Flutter.SendMessageFromCharacter(message, internalName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| message | Lua Type |
| internalName | string |

**Description**: Sends a custom FlutterMessage from NPC in current level
**Returns**: Nothing
### SendRandomMessageFromCharacter
```
Flutter.SendRandomMessageFromCharacter(internalName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| internalName | string |

**Description**: Sends a generated Flutter message from NPC in current level
**Returns**: Nothing
### SendRandomMessage
```
Flutter.SendRandomMessage()
```

**Description**: Sends a generated Flutter message from generated random character
**Returns**: Nothing
### SetFlutterEnabled
```
Flutter.SetFlutterEnabled(enabled)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| enabled | bool |

**Description**: Set Flutter app enabled or disabled.
**Returns**: Nothing
# GameProgress_Lua_API

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=GameProgress_Lua_API*

*Scraped on: 2025-05-02 18:37:52*

# GameProgress
## Description
The GameProgress api allows the modder to control and query the state of the players game progress
## Functions
### GetValue
```
GameProgress.GetValue(key)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| key | string |

**Description**: Returns a value from the game progress by key, empty string if it doesn't exist
**Returns**: string
### SetValue
```
GameProgress.SetValue(key, value, overwrite)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| key | string |
| value | string |
| overwrite | bool (optional) |

**Description**: Sets a value in the game progress
**Returns**: Nothing
### HasKey
```
GameProgress.HasKey(key)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| key | string |

**Description**: Does the specified key exist?
**Returns**: bool
This file is auto generated, please don't edit manually!
**Docs last hacked together on**: 23/07/2020 11:58
# Sound_Lua_API

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Sound_Lua_API*

*Scraped on: 2025-05-02 18:43:38*

# Sound
## Description
The sound API allows modders to trigger sound events in game
## Functions
### TriggerEvent
```
Sound.TriggerEvent(eventName, sourceName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| eventName | string |
| sourceName | string |

**Description**: Triggers a sound even with name*eventName*
**Returns**: The event id, this can be used in other sound API functions (see*StopAudio*)
**Notes**: If _sourceName_ is not provided the sound will be played as a '2D' event
### SetRTPC
```
Sound.SetRTPC(sourceName, RTPCName, value)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| sourceName | string |
| RTPCName | string |
| value | number |

**Description**: Set Real-Time Parameter Curve for an audio event playign on this object
**Returns**: Nothing
**Notes**: You need to have started an audio event on this object before tryign to use SetRTPC, and that event must have RTPC control for something.

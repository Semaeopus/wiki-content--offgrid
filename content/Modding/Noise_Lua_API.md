# Noise_Lua_API

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Noise_Lua_API*

*Scraped on: 2025-05-02 18:37:48*

# Noise
## Description
The Noise system provides a method of producing sounds that the AI can be aware of and respond to.
## Tables
### Noise
Table representing a noise
**Table definition**
| Name | Type | Default | Optional | Description |
| --- | --- | --- | --- | --- |
| soundName | string |  | No | The name of the sound event |
| attraction | number |  | No | How much attraction this noise will cause (range 0-1) |
| volume | number | 1.0 | Yes | The volume of the sound event (range (0-1) |
| duration | number | 0.0 | Yes | How long does this noise last? 0 will loop the sound and require it to be explicitly ended |
| trusted | boolean | false | Yes | Whether this noise is trusted by AIs |
## Functions
### Emit
```
Noise.Emit(deviceName, noiseTable)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
| noiseTable | Lua Table |

**Description**: Emits a noise from deviceName with attributes in noiseTable
**Returns**: Nothing
**Notes**: Attraction value is required, volume is optional (default 1.0), as is duration (defaults to 0, which loops the sound).
### Silence
```
Noise.Silence(deviceName, noiseTable)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
| noiseTable | Lua Table |

**Description**: Silences the noise
**Returns**: Nothing
**Notes**: Silences the noise, principally from an AI perspective. Will attempt to stop the audio if this noise was set up with an end event.

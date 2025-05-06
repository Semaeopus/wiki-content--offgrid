# Particles_Lua_API

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Particles_Lua_API*

*Scraped on: 2025-05-02 18:38:31*

# Particles
## Description
The Particles API allows modders to trigger behaviours on the particle systems attached to mission objects and their children.
For more information see [Unity's documentation](https://docs.unity3d.com/Manual/class-ParticleSystem.html) on Particle Systems
## Functions
### Play
```
Particles.Play(deviceName, searchChildren)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
| searchChildren | bool (optional) |

**Description**: Sets the particle system into play mode and beings emitting
**Returns**: Nothing
**Notes**: Sets the particle systems into play mode and enables emitting (if it has been disabled).
						If the particle system has been paused, then this resumes playing from the previous time.
						If the particle system has stopped, then the system starts from time 0, and, if it is relevant, the startDelay is applied.
### Pause
```
Particles.Pause(deviceName, searchChildren)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
| searchChildren | bool (optional) |

**Description**: Pauses playing the particle system.
**Returns**: Nothing
### Stop
```
Particles.Stop(deviceName, searchChildren)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
| searchChildren | bool (optional) |

**Description**: Stops playing the particle system.
**Returns**: Nothing
### Toggle
```
Particles.Toggle(deviceName, searchChildren)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
| searchChildren | bool (optional) |

**Description**: Toggles the particle system playing
**Returns**: Nothing
### Emit
```
Particles.Emit(deviceName, count, searchChildren)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
| count | number |
| searchChildren | bool (optional) |

**Description**: Emit _count_ particles immediately.
**Returns**: Nothing
### IsPlaying
```
Particles.IsPlaying(deviceName, searchChildren)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
| searchChildren | bool (optional) |

**Description**: Is the particle system playing right now?
**Returns**: bool

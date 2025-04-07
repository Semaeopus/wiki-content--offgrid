Particles
=========

Description
-----------

The Particles API allows modders to trigger behaviours on the particle
systems attached to mission objects and their children. For more
information see [Unity's
documentation](https://docs.unity3d.com/Manual/class-ParticleSystem.html)
on Particle Systems

Functions
---------

### Play

``` lua
Particles.Play(deviceName, searchChildren)
```

**Expected parameter types**

| Name           | Type            |
|----------------|-----------------|
| deviceName     | string          |
| searchChildren | bool (optional) |

**Description**: Sets the particle system into play mode and beings
emitting

**Returns**: Nothing

**Notes**: Sets the particle systems into play mode and enables emitting
(if it has been disabled).

`                       If the particle system has been paused, then this resumes playing from the previous time.`  
`                       If the particle system has stopped, then the system starts from time 0, and, if it is relevant, the startDelay is applied.`

### Pause

``` lua
Particles.Pause(deviceName, searchChildren)
```

**Expected parameter types**

| Name           | Type            |
|----------------|-----------------|
| deviceName     | string          |
| searchChildren | bool (optional) |

**Description**: Pauses playing the particle system.

**Returns**: Nothing

### Stop

``` lua
Particles.Stop(deviceName, searchChildren)
```

**Expected parameter types**

| Name           | Type            |
|----------------|-----------------|
| deviceName     | string          |
| searchChildren | bool (optional) |

**Description**: Stops playing the particle system.

**Returns**: Nothing

### Toggle

``` lua
Particles.Toggle(deviceName, searchChildren)
```

**Expected parameter types**

| Name           | Type            |
|----------------|-----------------|
| deviceName     | string          |
| searchChildren | bool (optional) |

**Description**: Toggles the particle system playing

**Returns**: Nothing

### Emit

``` lua
Particles.Emit(deviceName, count, searchChildren)
```

**Expected parameter types**

| Name           | Type            |
|----------------|-----------------|
| deviceName     | string          |
| count          | number          |
| searchChildren | bool (optional) |

**Description**: Emit \_count\_ particles immediately.

**Returns**: Nothing

### IsPlaying

``` lua
Particles.IsPlaying(deviceName, searchChildren)
```

**Expected parameter types**

| Name           | Type            |
|----------------|-----------------|
| deviceName     | string          |
| searchChildren | bool (optional) |

**Description**: Is the particle system playing right now?

**Returns**: bool

This file is auto generated, please don't edit manually!

**Docs last hacked together on**: 09/12/2024 12:54

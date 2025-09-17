Timeline
========

Description
-----------

Allows controlling Timelines on MissionObjects

Functions
---------

### Play

``` lua
Timeline.Play(missionObjectName)
```

**Expected parameter types**

| Name              | Type   |
|-------------------|--------|
| missionObjectName | string |

**Description**: Starts the timeline

**Returns**: Nothing

### Pause

``` lua
Timeline.Pause(missionObjectName)
```

**Expected parameter types**

| Name              | Type   |
|-------------------|--------|
| missionObjectName | string |

**Description**: Pauses the timeline

**Returns**: Nothing

### Stop

``` lua
Timeline.Stop(missionObjectName)
```

**Expected parameter types**

| Name              | Type   |
|-------------------|--------|
| missionObjectName | string |

**Description**: Stops the timeline

**Returns**: Nothing

### SetDynamicCameraTarget

``` lua
Timeline.SetDynamicCameraTarget(missionObjectName, targetName)
```

**Expected parameter types**

| Name              | Type   |
|-------------------|--------|
| missionObjectName | string |
| targetName        | string |

**Description**: Sets the look at & follow target for all dynamically
targeted cameras in the timeline

**Returns**: Nothing

### PauseAI

``` lua
Timeline.PauseAI(characterName)
```

**Expected parameter types**

| Name          | Type   |
|---------------|--------|
| characterName | string |

**Description**: Pauses an AI agent.

**Returns**: Nothing

**Notes**: Bit of a hack for Timeline use, this might get removed later
on!

### UnpauseAI

``` lua
Timeline.UnpauseAI(characterName)
```

**Expected parameter types**

| Name          | Type   |
|---------------|--------|
| characterName | string |

**Description**: Unpauses an AI agent, resuming standard behaviour.

**Returns**: Nothing

**Notes**: Bit of a hack for Timeline use, this might get removed later
on!

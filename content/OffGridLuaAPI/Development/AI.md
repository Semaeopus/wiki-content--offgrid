AI
==

Description
-----------

API to control the logic of AI in the mission

Functions
---------

### Pause

``` lua
AI.Pause(characterName)
```

**Expected parameter types**

| Name          | Type   |
|---------------|--------|
| characterName | string |

**Description**: Pauses the agent, and stops it from doing anything.

**Returns**: Nothing

**Notes**: The AI will be hidden from networks, meaning it will no
longer interact with devices or send/receive messages.

### Unpause

``` lua
AI.Unpause(characterName)
```

**Expected parameter types**

| Name          | Type   |
|---------------|--------|
| characterName | string |

**Description**: Unpauses a hidden agent, resuming standard behaviour.

**Returns**: Nothing

### IsPaused

``` lua
AI.IsPaused(characterName)
```

**Expected parameter types**

| Name          | Type   |
|---------------|--------|
| characterName | string |

**Description**: Returns a bool based on if a character is currently
paused or not

**Returns**: bool

### AddGoal

``` lua
AI.AddGoal(characterName, goal)
```

**Expected parameter types**

| Name          | Type      |
|---------------|-----------|
| characterName | string    |
| goal          | Lua Table |

**Description**: Adds a defined goal

**Returns**: Nothing

### RemoveGoal

``` lua
AI.RemoveGoal(characterName, goalName)
```

**Expected parameter types**

| Name          | Type   |
|---------------|--------|
| characterName | string |
| goalName      | string |

**Description**: Removes any defined goals

**Returns**: Nothing

### AddTemporaryGoal

``` lua
AI.AddTemporaryGoal(characterName, goal)
```

**Expected parameter types**

| Name          | Type      |
|---------------|-----------|
| characterName | string    |
| goal          | Lua Table |

**Description**: Adds a goal, taking top priority, to the named AI

**Returns**: Nothing

**Notes**: This goal will be removed from the AI once complete. If it
isn't achievable it will be removed immediately.

### GetNPCProfileByTag

``` lua
AI.GetNPCProfileByTag(characterName, tag)
```

**Expected parameter types**

| Name          | Type   |
|---------------|--------|
| characterName | string |
| tag           | string |

**Description**: Get all values of a tag from a chaarcter's profile, if
the tag exists.

**Returns**: System.String\[\]

### Lua\_CheckNPCProfile

``` lua
AI.Lua_CheckNPCProfile(characterName, tag, value)
```

**Expected parameter types**

| Name          | Type   |
|---------------|--------|
| characterName | string |
| tag           | string |
| value         | string |

**Description**: Check if character's profile data contains a specific
tag wiht a specific value

**Returns**: bool

### GetNPCStat

``` lua
AI.GetNPCStat(characterName, statName)
```

**Expected parameter types**

| Name          | Type   |
|---------------|--------|
| characterName | string |
| statName      | string |

**Description**: Returns current value of NPC's stat

**Returns**: number

**Notes**: This is only intended for debugging purposes, and not
recommended in any actual game scripts.

### SetNPCStat

``` lua
AI.SetNPCStat(characterName, statName, newValue)
```

**Expected parameter types**

| Name          | Type   |
|---------------|--------|
| characterName | string |
| statName      | string |
| newValue      | number |

**Description**: Sets an NPC's AI stat to absolute value

**Returns**: Nothing

**Notes**: This is only intended for debugging purposes, and not
recommended in any actual game scripts.

### AlterNPCStat

``` lua
AI.AlterNPCStat(characterName, statName, statDelta)
```

**Expected parameter types**

| Name          | Type   |
|---------------|--------|
| characterName | string |
| statName      | string |
| statDelta     | number |

**Description**: Alters an NPC's AI stat by relative value

**Returns**: Nothing

### AlterNPCWorldState

``` lua
AI.AlterNPCWorldState(characterName, state, value)
```

**Expected parameter types**

| Name          | Type     |
|---------------|----------|
| characterName | string   |
| state         | string   |
| value         | Lua Type |

**Description**: Change the World State of an NPC.

**Returns**: Nothing

### FavourInterest

``` lua
AI.FavourInterest(characterName, device, permanent)
```

**Expected parameter types**

| Name          | Type   |
|---------------|--------|
| characterName | string |
| device        | string |
| permanent     | bool   |

**Description**: Reduce the cost of an AI using a particular Interest

**Returns**: Nothing

**Notes**: If permanent is false, the cost will revert to normal the
next time this is successfully used

### AvoidInterest

``` lua
AI.AvoidInterest(characterName, device, permanent)
```

**Expected parameter types**

| Name          | Type   |
|---------------|--------|
| characterName | string |
| device        | string |
| permanent     | bool   |

**Description**: Increase the cost of an AI using a particular Interest

**Returns**: Nothing

**Notes**: If permanent is false, the cost will revert to normal the
next time this is successfully used

### SetNPCFavouredComputer

``` lua
AI.SetNPCFavouredComputer(characterName, computer)
```

**Expected parameter types**

| Name          | Type          |
|---------------|---------------|
| characterName | string        |
| computer      | MissionObject |

**Description**: Set NPC's computer, this will be used for a variety of
actions

**Returns**: Nothing

### AddAction

``` lua
AI.AddAction(characterName, action)
```

**Expected parameter types**

| Name          | Type      |
|---------------|-----------|
| characterName | string    |
| action        | Lua Table |

**Description**: Adds an action that can be used immediately

**Returns**: Nothing

### RemoveAction

``` lua
AI.RemoveAction(characterName, actionName)
```

**Expected parameter types**

| Name          | Type   |
|---------------|--------|
| characterName | string |
| actionName    | string |

**Description**: Removes any action

**Returns**: Nothing

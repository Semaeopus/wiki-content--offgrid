Mission
=======

Description
-----------

The Mission API controls the flow of the mission, this includes starting
and stopping the mission, and dealing with objectives and other
mission-related information

Functions
---------

### CompletedMissionSetup\_Always

``` lua
Mission.CompletedMissionSetup_Always()
```

**Description**: This should be called at the end of
MissionSetup\_Always() After it the game will either load last save and
start, or execute MissionSetup\_NoSave()

**Returns**: Nothing

### CompletedMissionSetup\_NoSave

``` lua
Mission.CompletedMissionSetup_NoSave()
```

**Description**: This should be called at the end of
MissionSetup\_NoSave() Call this AFTER all Devices have been connected
to their networks. This allows DataPoints to be processed correctly.

**Returns**: Nothing

### MissionCompleted

``` lua
Mission.MissionCompleted()
```

**Description**: This should be called when the final objective of the
mission has been completed It will trigger the game to fade to black and
return to the main menu

**Returns**: Nothing

### MissionFailed

``` lua
Mission.MissionFailed()
```

**Description**: This function will fail the current mission, as if Joe
had been tazed (or similar).

**Returns**: Nothing

### SpawnCharacter

``` lua
Mission.SpawnCharacter(internalName)
```

**Expected parameter types**

| Name         | Type   |
|--------------|--------|
| internalName | string |

**Description**: Spawn a registered character in the game

**Returns**: Nothing

### ObjectiveIsActive

``` lua
Mission.ObjectiveIsActive(objectiveName)
```

**Expected parameter types**

| Name          | Type   |
|---------------|--------|
| objectiveName | string |

**Description**: Returns true if objective has been started but not
completed yet.

**Returns**: bool

### ObjectiveIsCompleted

``` lua
Mission.ObjectiveIsCompleted(objectiveName)
```

**Expected parameter types**

| Name          | Type   |
|---------------|--------|
| objectiveName | string |

**Description**: Returns true if objective has been completed.

**Returns**: bool

### AddObjective

``` lua
Mission.AddObjective(internalName, table)
```

**Expected parameter types**

| Name         | Type      |
|--------------|-----------|
| internalName | string    |
| table        | Lua Table |

**Description**: Add a new objective

**Returns**: Nothing

### StartObjective

``` lua
Mission.StartObjective(objectiveName)
```

**Expected parameter types**

| Name          | Type   |
|---------------|--------|
| objectiveName | string |

**Description**: Start the provided objective

**Returns**: Nothing

### CompleteObjective

``` lua
Mission.CompleteObjective(objectiveName)
```

**Expected parameter types**

| Name          | Type   |
|---------------|--------|
| objectiveName | string |

**Description**: Complete the provided objective

**Returns**: Nothing

### GetCurrentObjective

``` lua
Mission.GetCurrentObjective()
```

**Description**: Get the name of the current objective

**Returns**: string

### TriggerAutoSave

``` lua
Mission.TriggerAutoSave()
```

**Description**: Triggers an autosave, only if the game is current in a
mission

**Returns**: Nothing

### SetMissionObjectEnabled

``` lua
Mission.SetMissionObjectEnabled(name, enabled)
```

**Expected parameter types**

| Name    | Type   |
|---------|--------|
| name    | string |
| enabled | bool   |

**Description**: Sets if a MissionObject should be visible and
interactable

**Returns**: Nothing

### MissionObjectIsEnabled

``` lua
Mission.MissionObjectIsEnabled(name)
```

**Expected parameter types**

| Name | Type   |
|------|--------|
| name | string |

**Description**: Check if a MissionObject is visible & interactable

**Returns**: bool

### SetMissionObjectInteractionRequirement

``` lua
Mission.SetMissionObjectInteractionRequirement(name, requirement)
```

**Expected parameter types**

| Name        | Type   |
|-------------|--------|
| name        | string |
| requirement | number |

**Description**: Sets if a MissionObject should request the player to
select an item or data file before interaction

**Returns**: Nothing

### SetCharacterInteractionRequirement

``` lua
Mission.SetCharacterInteractionRequirement(name, requirement)
```

**Expected parameter types**

| Name        | Type   |
|-------------|--------|
| name        | string |
| requirement | number |

**Description**: Sets if a Character should request the player to select
an item or data file before interaction

**Returns**: Nothing

**Notes**: The character must also have OnCharacterInteraction function
defined in the mission script!

### SetNPCInteractable

``` lua
Mission.SetNPCInteractable(name, state)
```

**Expected parameter types**

| Name  | Type   |
|-------|--------|
| name  | string |
| state | bool   |

**Description**: Sets if a NPC should be interactable or not at the
moment

**Returns**: Nothing

**Notes**: The character must also have OnCharacterInteraction function
defined in the mission script!

### SetPlayerControlled

``` lua
Mission.SetPlayerControlled(tf)
```

**Expected parameter types**

| Name | Type |
|------|------|
| tf   | bool |

**Description**: Set whether the player is currently in control (or
not). Used for cutscenes, and other things that we haven't thought of
yet.

**Returns**: Nothing

### GetBool

``` lua
Mission.GetBool(key)
```

**Expected parameter types**

| Name | Type   |
|------|--------|
| key  | string |

**Description**: Get a boolean value of a key in mission Lua script.
Returns false if key doesn't exist.

**Returns**: bool

### SetBool

``` lua
Mission.SetBool(key, newBool)
```

**Expected parameter types**

| Name    | Type   |
|---------|--------|
| key     | string |
| newBool | bool   |

**Description**: Sets a boolean value of a key in mission Lua script.

**Returns**: Nothing

### GetString

``` lua
Mission.GetString(key)
```

**Expected parameter types**

| Name | Type   |
|------|--------|
| key  | string |

**Description**: Get a string value of a key in mission Lua script.
Returns empty if key doesn't exist.

**Returns**: string

### SetString

``` lua
Mission.SetString(key, newString)
```

**Expected parameter types**

| Name      | Type   |
|-----------|--------|
| key       | string |
| newString | string |

**Description**: Sets a string value of a key in mission Lua script.

**Returns**: Nothing

### GetNumber

``` lua
Mission.GetNumber(key)
```

**Expected parameter types**

| Name | Type   |
|------|--------|
| key  | string |

**Description**: Get a numeric value of a key in mission Lua script.
Returns 0 if key doesn't exist.

**Returns**: number

### SetNumber

``` lua
Mission.SetNumber(key, newValue)
```

**Expected parameter types**

| Name     | Type   |
|----------|--------|
| key      | string |
| newValue | number |

**Description**: Sets a numeric value of a key in mission Lua script.

**Returns**: Nothing

### GetMissionState

``` lua
Mission.GetMissionState(t)
```

**Expected parameter types**

| Name | Type      |
|------|-----------|
| t    | Lua Table |

**Description**: Fill a table with current mission state

**Returns**: Nothing

### StartVibrationEvent

``` lua
Mission.StartVibrationEvent(objectName)
```

**Expected parameter types**

| Name       | Type   |
|------------|--------|
| objectName | string |

**Description**: Start a mission object vibration event

**Returns**: Nothing

### StopVibrationEvent

``` lua
Mission.StopVibrationEvent(objectName)
```

**Expected parameter types**

| Name       | Type   |
|------------|--------|
| objectName | string |

**Description**: Stop a mission object vibration event

**Returns**: Nothing

### SpawnWanderNPCs

``` lua
Mission.SpawnWanderNPCs(spawnPoint, spawnNum, characterPrefabs, headProps, colorTextures, metalTextures, gestures)
```

**Expected parameter types**

| Name             | Type     |
|------------------|----------|
| spawnPoint       | Lua Type |
| spawnNum         | number   |
| characterPrefabs | Lua Type |
| headProps        | Lua Type |
| colorTextures    | Lua Type |
| metalTextures    | Lua Type |
| gestures         | Lua Type |

**Description**: Spawns various Wander NPCs in a randomized way

**Returns**: Nothing

**Notes**: All the parameters, expect the spawnNum, can be a string or a
table of strings. For the head props and the the gestures the string
"None" can be used to have the possibility to not have any head props
and gestures, respectively, in the wander NPCs. Also for the color
textures and metal textures the string "Default" can be used for the
character's default textures.

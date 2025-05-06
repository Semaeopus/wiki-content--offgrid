# Mission_Lua_API

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Mission_Lua_API*

*Scraped on: 2025-05-02 18:40:26*

# Mission
## Description
The Mission API controls the flow of the mission, this includes starting and stopping the mission, and dealing with objectives and other mission-related information
## Functions
### MissionStarted
```
Mission.MissionStarted()
```

**Description**: This should be called once the initial state of the mission has been set
						It will cause the game to begin gameplay
**Returns**: Nothing
### MissionCompleted
```
Mission.MissionCompleted()
```

**Description**: This should be called when the final objective of the mission has been completed
						It will trigger the game to fade to black and return to the main menu
**Returns**: Nothing
### MissionFailed
```
Mission.MissionFailed()
```

**Description**: This function will fail the current mission, as if Joe had been tazed (or similar).
**Returns**: Nothing
### SpawnCharacter
```
Mission.SpawnCharacter(internalName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| internalName | string |

**Description**: Spawn a registered character in the game
**Returns**: Nothing
### ObjectiveIsActive
```
Mission.ObjectiveIsActive(objectiveName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| objectiveName | string |

**Description**: Returns true if objective has been started but not completed yet.
**Returns**: bool
### ObjectiveIsCompleted
```
Mission.ObjectiveIsCompleted(objectiveName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| objectiveName | string |

**Description**: Returns true if objective has been completed.
**Returns**: bool
### StartObjective
```
Mission.StartObjective(objectiveName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| objectiveName | string |

**Description**: Start the provided objective
**Returns**: Nothing
### CompleteObjective
```
Mission.CompleteObjective(objectiveName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| objectiveName | string |

**Description**: Complete the provided objective
**Returns**: Nothing
### GetCurrentObjective
```
Mission.GetCurrentObjective()
```

**Description**: Get the name of the current objective
**Returns**: string
### TriggerAutoSave
```
Mission.TriggerAutoSave()
```

**Description**: Triggers an autosave, only if the game is current in a mission
**Returns**: Nothing
### DevicesConnected
```
Mission.DevicesConnected()
```

**Description**: Call this AFTER all Devices have been connected to their networks. This allows DataPoints to be processed correctly.
**Returns**: Nothing
### SetPlayerControlled
```
Mission.SetPlayerControlled(tf)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| tf | bool |

**Description**: Set whether the player is currently in control (or not). Used for cutscenes, and other things that we haven't thought of yet.
**Returns**: Nothing
### GetBool
```
Mission.GetBool(key)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| key | string |

**Description**: Get a boolean value of a key in mission Lua script. Returns false if key doesn't exist.
**Returns**: bool
### SetBool
```
Mission.SetBool(key, newBool)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| key | string |
| newBool | bool |

**Description**: Sets a boolean value of a key in mission Lua script.
**Returns**: Nothing
### GetString
```
Mission.GetString(key)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| key | string |

**Description**: Get a string value of a key in mission Lua script. Returns empty if key doesn't exist.
**Returns**: string
### SetString
```
Mission.SetString(key, newString)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| key | string |
| newString | string |

**Description**: Sets a string value of a key in mission Lua script.
**Returns**: Nothing
### GetNumber
```
Mission.GetNumber(key)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| key | string |

**Description**: Get a numeric value of a key in mission Lua script. Returns 0 if key doesn't exist.
**Returns**: number
### SetNumber
```
Mission.SetNumber(key, newValue)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| key | string |
| newValue | number |

**Description**: Sets a numeric value of a key in mission Lua script.
**Returns**: Nothing
### StartVibrationEvent
```
Mission.StartVibrationEvent(objectName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| objectName | string |

**Description**: Start a mission object vibration event
**Returns**: Nothing
### StopVibrationEvent
```
Mission.StopVibrationEvent(objectName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| objectName | string |

**Description**: Stop a mission object vibration event
**Returns**: Nothing

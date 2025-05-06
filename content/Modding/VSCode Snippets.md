# VSCode_Snippets

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=VSCode_Snippets*

*Scraped on: 2025-05-02 18:38:34*

# Snippets file for Visual Studio Code
Copy & paste the following code into your Snippets file in VisualStudio Code to add autocompletion for Off Grid's Lua API.
```
"AI.Pause": {
    "prefix": "AI.Pause",
    "body": [
        "AI.Pause(${0:characterName})"
    ],
    "description": "Pauses the agent, and stops it from doing anything."
},
"AI.Unpause": {
    "prefix": "AI.Unpause",
    "body": [
        "AI.Unpause(${0:characterName})"
    ],
    "description": "Unpauses a hidden agent, resuming standard behaviour."
},
"AI.IsPaused": {
    "prefix": "AI.IsPaused",
    "body": [
        "AI.IsPaused(${0:characterName})"
    ],
    "description": "Returns a bool based on if a character is currently paused or not"
},
"AI.AddTemporaryGoal": {
    "prefix": "AI.AddTemporaryGoal",
    "body": [
        "AI.AddTemporaryGoal(${0:characterName}, ${1:goal})"
    ],
    "description": "Adds a goal, taking top priority, to the named AI"
},
"AI.AlterNPCMotivation": {
    "prefix": "AI.AlterNPCMotivation",
    "body": [
        "AI.AlterNPCMotivation(${0:characterName}, ${1:motivationDelta})"
    ],
    "description": "Alters an NPCS motivation state"
},
"AI.AlterNPCWorldState": {
    "prefix": "AI.AlterNPCWorldState",
    "body": [
        "AI.AlterNPCWorldState(${0:characterName}, ${1:state}, ${2:value})"
    ],
    "description": "Change the World State of an NPC."
},
"AI.FavourInterest": {
    "prefix": "AI.FavourInterest",
    "body": [
        "AI.FavourInterest(${0:characterName}, ${1:device}, ${2:permanent})"
    ],
    "description": "Reduce the cost of an AI using a particular Interest"
},
"AI.AvoidInterest": {
    "prefix": "AI.AvoidInterest",
    "body": [
        "AI.AvoidInterest(${0:characterName}, ${1:device}, ${2:permanent})"
    ],
    "description": "Increase the cost of an AI using a particular Interest"
},
"AI.ChangeSubject": {
    "prefix": "AI.ChangeSubject",
    "body": [
        "AI.ChangeSubject(${0:characterName}, ${1:subject}, ${2:value})"
    ],
    "description": "Set the value of a particular subject, enabling Actions with Personality requirements"
},
"AI.ReactTo": {
    "prefix": "AI.ReactTo",
    "body": [
        "AI.ReactTo(${0:characterName}, ${1:subject}, ${2:value})"
    ],
    "description": "Much like ChangeSubject, but instead of enabling Actions, this will alter stats within the Agent, modifying its WorldState (and as a result, enabling Actions)"
},
"AI.CreateReactable": {
    "prefix": "AI.CreateReactable",
    "body": [
        "AI.CreateReactable(${0:actionType}, ${1:attraction}, ${2:targetObject})"
    ],
    "description": "Create a new distraction that AI can pick up on"
},
"AI.SetNPCFavouredComputer": {
    "prefix": "AI.SetNPCFavouredComputer",
    "body": [
        "AI.SetNPCFavouredComputer(${0:characterName}, ${1:computer})"
    ],
    "description": "Set NPC's computer, this will be used for a variety of actions"
},
"Animator.SetBool": {
    "prefix": "Animator.SetBool",
    "body": [
        "Animator.SetBool(${0:missionObjectName}, ${1:parameterName}, ${2:value})"
    ],
    "description": "Sets a bool parameter by name"
},
"Animator.SetFloat": {
    "prefix": "Animator.SetFloat",
    "body": [
        "Animator.SetFloat(${0:missionObjectName}, ${1:parameterName}, ${2:value})"
    ],
    "description": "Sets a float parameter by name"
},
"Animator.SetInt": {
    "prefix": "Animator.SetInt",
    "body": [
        "Animator.SetInt(${0:missionObjectName}, ${1:parameterName}, ${2:value})"
    ],
    "description": "Sets a int parameter by name"
},
"Animator.SetTrigger": {
    "prefix": "Animator.SetTrigger",
    "body": [
        "Animator.SetTrigger(${0:missionObjectName}, ${1:parameterName})"
    ],
    "description": "Begins a trigger parameter by name"
},
"Animator.GetBool": {
    "prefix": "Animator.GetBool",
    "body": [
        "Animator.GetBool(${0:missionObjectName}, ${1:parameterName})"
    ],
    "description": "Gets the current value of a bool parameter by name"
},
"Animator.GetFloat": {
    "prefix": "Animator.GetFloat",
    "body": [
        "Animator.GetFloat(${0:missionObjectName}, ${1:parameterName})"
    ],
    "description": "Gets the current value of a float parameter by name"
},
"Animator.GetInt": {
    "prefix": "Animator.GetInt",
    "body": [
        "Animator.GetInt(${0:missionObjectName}, ${1:parameterName})"
    ],
    "description": "Gets the current value of a int parameter by name"
},
"Apps.RequestAppState": {
    "prefix": "Apps.RequestAppState",
    "body": [
        "Apps.RequestAppState(${0:appName}, ${1:newState})"
    ],
    "description": "Ask an App to change it's state"
},
"SetState": {
    "prefix": "SetState",
    "body": [
        "SetState(${0:newState})"
    ],
    "description": "Sets the App's state."
},
"CreateStatusWindow": {
    "prefix": "CreateStatusWindow",
    "body": [
        "CreateStatusWindow()"
    ],
    "description": "Create the status window"
},
"RemoveStatusWindow": {
    "prefix": "RemoveStatusWindow",
    "body": [
        "RemoveStatusWindow()"
    ],
    "description": "Remove this app's status window"
},
"DisplayStatusWindow": {
    "prefix": "DisplayStatusWindow",
    "body": [
        "DisplayStatusWindow(${0:enabled})"
    ],
    "description": "Show or hide the app's status window."
},
"UpdateStatusWindow": {
    "prefix": "UpdateStatusWindow",
    "body": [
        "UpdateStatusWindow(${0:text})"
    ],
    "description": "Update the text content of the app's status window"
},
"SetStatusIcon": {
    "prefix": "SetStatusIcon",
    "body": [
        "SetStatusIcon(${0:id})"
    ],
    "description": "Set the icon used for the app's status window"
},
"SetStatusIconColor": {
    "prefix": "SetStatusIconColor",
    "body": [
        "SetStatusIconColor(${0:color})"
    ],
    "description": "Set the color of the status window icon"
},
"Color.RandomColor": {
    "prefix": "Color.RandomColor",
    "body": [
        "Color.RandomColor(${0:alpha})"
    ],
    "description": "Returns a random color"
},
"Color.Clear" : {
    "prefix": "Color.Clear",
    "body": [
        "Color.Clear"
    ],
    "description": "\r\n{| class=wikitable\r\n! Preview !! RGB\r\n|-\r\n|style=\"background: #ffffff;\"| || 1, 1, 1\r\n|-\r\n|}"
},
"Color.Black" : {
    "prefix": "Color.Black",
    "body": [
        "Color.Black"
    ],
    "description": "\r\n{| class=wikitable\r\n! Preview !! RGB\r\n|-\r\n|style=\"background: #181818;\"| || 0.094, 0.094, 0.094\r\n|-\r\n|}"
},
"Color.DarkGrey" : {
    "prefix": "Color.DarkGrey",
    "body": [
        "Color.DarkGrey"
    ],
    "description": "\r\n{| class=wikitable\r\n! Preview !! RGB\r\n|-\r\n|style=\"background: #585858;\"| || 0.345, 0.345, 0.345\r\n|-\r\n|}"
},
"Color.Grey" : {
    "prefix": "Color.Grey",
    "body": [
        "Color.Grey"
    ],
    "description": "\r\n{| class=wikitable\r\n! Preview !! RGB\r\n|-\r\n|style=\"background: #B8B8B8;\"| || 0.722, 0.722, 0.722\r\n|-\r\n|}"
},
"Color.LightGrey" : {
    "prefix": "Color.LightGrey",
    "body": [
        "Color.LightGrey"
    ],
    "description": "\r\n{| class=wikitable\r\n! Preview !! RGB\r\n|-\r\n|style=\"background: #D8D8D8;\"| || 0.847, 0.847, 0.847\r\n|-\r\n|}"
},
"Color.White" : {
    "prefix": "Color.White",
    "body": [
        "Color.White"
    ],
    "description": "\r\n{| class=wikitable\r\n! Preview !! RGB\r\n|-\r\n|style=\"background: #F8F8F8;\"| || 0.972, 0.972, 0.972\r\n|-\r\n|}"
},
"Color.Red" : {
    "prefix": "Color.Red",
    "body": [
        "Color.Red"
    ],
    "description": "\r\n{| class=wikitable\r\n! Preview !! RGB\r\n|-\r\n|style=\"background: #AB4642;\"| || 0.671, 0.275, 0.259\r\n|-\r\n|}"
},
"Color.Orange" : {
    "prefix": "Color.Orange",
    "body": [
        "Color.Orange"
    ],
    "description": "\r\n{| class=wikitable\r\n! Preview !! RGB\r\n|-\r\n|style=\"background: #DC9656;\"| || 0.863, 0.589, 0.336\r\n|-\r\n|}"
},
"Color.Yellow" : {
    "prefix": "Color.Yellow",
    "body": [
        "Color.Yellow"
    ],
    "description": "\r\n{| class=wikitable\r\n! Preview !! RGB\r\n|-\r\n|style=\"background: #F7CA88;\"| || 0.969, 0.792, 0.533\r\n|-\r\n|}"
},
"Color.Green" : {
    "prefix": "Color.Green",
    "body": [
        "Color.Green"
    ],
    "description": "\r\n{| class=wikitable\r\n! Preview !! RGB\r\n|-\r\n|style=\"background: #A1B56C;\"| || 0.631, 0.71, 0.424\r\n|-\r\n|}"
},
"Color.Cyan" : {
    "prefix": "Color.Cyan",
    "body": [
        "Color.Cyan"
    ],
    "description": "\r\n{| class=wikitable\r\n! Preview !! RGB\r\n|-\r\n|style=\"background: #86C1B9;\"| || 0.525, 0.757, 0.725\r\n|-\r\n|}"
},
"Color.Blue" : {
    "prefix": "Color.Blue",
    "body": [
        "Color.Blue"
    ],
    "description": "\r\n{| class=wikitable\r\n! Preview !! RGB\r\n|-\r\n|style=\"background: #7CAFC2;\"| || 0.486, 0.686, 0.761\r\n|-\r\n|}"
},
"Color.Purple" : {
    "prefix": "Color.Purple",
    "body": [
        "Color.Purple"
    ],
    "description": "\r\n{| class=wikitable\r\n! Preview !! RGB\r\n|-\r\n|style=\"background: #BA8BAF;\"| || 0.729, 0.545, 0.686\r\n|-\r\n|}"
},
"Color.Brown" : {
    "prefix": "Color.Brown",
    "body": [
        "Color.Brown"
    ],
    "description": "\r\n{| class=wikitable\r\n! Preview !! RGB\r\n|-\r\n|style=\"background: #A16946;\"| || 0.631, 0.412, 0.275\r\n|-\r\n|}"
},
"Conversation.StartScript": {
    "prefix": "Conversation.StartScript",
    "body": [
        "Conversation.StartScript(${0:path}, ${1:onCompleteCallback})"
    ],
    "description": "Starts a conversation from a name"
},
"DataPoints.GetAllDataPoints": {
    "prefix": "DataPoints.GetAllDataPoints",
    "body": [
        "DataPoints.GetAllDataPoints()"
    ],
    "description": "Return all the data points that are currently in the level"
},
"DataPoints.GetObjectDataPoints": {
    "prefix": "DataPoints.GetObjectDataPoints",
    "body": [
        "DataPoints.GetObjectDataPoints(${0:objectName})"
    ],
    "description": "Return all the data points received by an object or a character "
},
"DataPoints.FilterNetwork": {
    "prefix": "DataPoints.FilterNetwork",
    "body": [
        "DataPoints.FilterNetwork(${0:dataPoints}, ${1:networkName})"
    ],
    "description": "Filter data points with the network name"
},
"DataPoints.FilterDataType": {
    "prefix": "DataPoints.FilterDataType",
    "body": [
        "DataPoints.FilterDataType(${0:dataPoints}, ${1:dataType})"
    ],
    "description": "Filter data points with the data type"
},
"DataPoints.DeleteDataPoints": {
    "prefix": "DataPoints.DeleteDataPoints",
    "body": [
        "DataPoints.DeleteDataPoints(${0:dataPoints})"
    ],
    "description": "Remove data points from the level"
},
"DataPoints.GetData": {
    "prefix": "DataPoints.GetData",
    "body": [
        "DataPoints.GetData(${0:dataPoints})"
    ],
    "description": "Return all the data string from the given data points"
},
"DataPoints.GetDataPointInfo": {
    "prefix": "DataPoints.GetDataPointInfo",
    "body": [
        "DataPoints.GetDataPointInfo(${0:dataPoints})"
    ],
    "description": "Return all the data info from the given data points"
},
"DataPoints.PlayersInventorySave": {
    "prefix": "DataPoints.PlayersInventorySave",
    "body": [
        "DataPoints.PlayersInventorySave(${0:dataFile})"
    ],
    "description": "Save data info in the the players inventory"
},
"DataPoints.PlayersInventoryRemove": {
    "prefix": "DataPoints.PlayersInventoryRemove",
    "body": [
        "DataPoints.PlayersInventoryRemove(${0:dataFile})"
    ],
    "description": "Save data info in the the players inventory"
},
"Debug.ConnectToDevLaptop": {
    "prefix": "Debug.ConnectToDevLaptop",
    "body": [
        "Debug.ConnectToDevLaptop()"
    ],
    "description": "Open SSH connection to DevLaptop Device, if there's one in the level."
},
"Debug.ShowPlayerPath": {
    "prefix": "Debug.ShowPlayerPath",
    "body": [
        "Debug.ShowPlayerPath(${0:value})"
    ],
    "description": "ShowPlayerPath"
},
"Devices.SetPower": {
    "prefix": "Devices.SetPower",
    "body": [
        "Devices.SetPower(${0:deviceName}, ${1:state})"
    ],
    "description": "Change the powered on state of the device"
},
"Devices.TogglePower": {
    "prefix": "Devices.TogglePower",
    "body": [
        "Devices.TogglePower(${0:deviceName})"
    ],
    "description": "Flip the powered on state of the device"
},
"Devices.GetPower": {
    "prefix": "Devices.GetPower",
    "body": [
        "Devices.GetPower(${0:deviceName})"
    ],
    "description": "Get the powered on state of the device"
},
"Devices.SetActive": {
    "prefix": "Devices.SetActive",
    "body": [
        "Devices.SetActive(${0:deviceName}, ${1:state})"
    ],
    "description": "Change the active state of the device"
},
"Devices.ToggleActive": {
    "prefix": "Devices.ToggleActive",
    "body": [
        "Devices.ToggleActive(${0:deviceName})"
    ],
    "description": "Flip the active state of the device"
},
"Devices.GetActive": {
    "prefix": "Devices.GetActive",
    "body": [
        "Devices.GetActive(${0:deviceName})"
    ],
    "description": "Get the active state of the device"
},
"Devices.RunOnce": {
    "prefix": "Devices.RunOnce",
    "body": [
        "Devices.RunOnce(${0:deviceName})"
    ],
    "description": "Trigger a single update of the device"
},
"Devices.SetAmok": {
    "prefix": "Devices.SetAmok",
    "body": [
        "Devices.SetAmok(${0:deviceName}, ${1:state})"
    ],
    "description": "Begin an 'Amok' state, cause the device to act in an unstable/broken manor"
},
"Devices.ToggleAmok": {
    "prefix": "Devices.ToggleAmok",
    "body": [
        "Devices.ToggleAmok(${0:deviceName})"
    ],
    "description": "Flip the amok state"
},
"Devices.GetAmok": {
    "prefix": "Devices.GetAmok",
    "body": [
        "Devices.GetAmok(${0:deviceName})"
    ],
    "description": "Get the 'Amok' state of the device"
},
"Devices.SetValue": {
    "prefix": "Devices.SetValue",
    "body": [
        "Devices.SetValue(${0:deviceName}, ${1:newValue})"
    ],
    "description": "Pass a string value to the device"
},
"Devices.GetValue": {
    "prefix": "Devices.GetValue",
    "body": [
        "Devices.GetValue(${0:deviceName})"
    ],
    "description": "Get the current value of the device"
},
"Devices.GetDataInventory": {
    "prefix": "Devices.GetDataInventory",
    "body": [
        "Devices.GetDataInventory(${0:deviceName}, ${1:index})"
    ],
    "description": "Get the description of the data at this index in the DataInventory"
},
"Devices.GetDataPointFromInventory": {
    "prefix": "Devices.GetDataPointFromInventory",
    "body": [
        "Devices.GetDataPointFromInventory(${0:deviceName}, ${1:index})"
    ],
    "description": "Get a table of useful data from the DataPoint at this index in the DataInventory"
},
"Devices.GetDataInventoryCount": {
    "prefix": "Devices.GetDataInventoryCount",
    "body": [
        "Devices.GetDataInventoryCount(${0:deviceName})"
    ],
    "description": "Get the number of DataPoints in the DataInventory of this device"
},
"Doors.SetZoneKeys": {
    "prefix": "Doors.SetZoneKeys",
    "body": [
        "Doors.SetZoneKeys(${0:zoneName}, ${1:keyNames})"
    ],
    "description": "Sets a key as unlocking a specific zone"
},
"Doors.SetNetwork": {
    "prefix": "Doors.SetNetwork",
    "body": [
        "Doors.SetNetwork(${0:networkName})"
    ],
    "description": "Sets the name of the network for the door system to use"
},
"Doors.SetKeyOnDevice": {
    "prefix": "Doors.SetKeyOnDevice",
    "body": [
        "Doors.SetKeyOnDevice(${0:keyName}, ${1:deviceName})"
    ],
    "description": "Sets a key as the current NFC file on a net device"
},
"Doors.AssignKeyToCharacter": {
    "prefix": "Doors.AssignKeyToCharacter",
    "body": [
        "Doors.AssignKeyToCharacter(${0:keyName}, ${1:character})"
    ],
    "description": "Adds a key to a characters inventory and sets it as the characters current NFC data"
},
"Doors.Open": {
    "prefix": "Doors.Open",
    "body": [
        "Doors.Open(${0:doorID})"
    ],
    "description": "Open the specified door."
},
"Doors.Close": {
    "prefix": "Doors.Close",
    "body": [
        "Doors.Close(${0:doorID})"
    ],
    "description": "close the specified door."
},
"Doors.Unlock": {
    "prefix": "Doors.Unlock",
    "body": [
        "Doors.Unlock(${0:doorID})"
    ],
    "description": "Unlock the specified door"
},
"Doors.Lock": {
    "prefix": "Doors.Lock",
    "body": [
        "Doors.Lock(${0:doorID})"
    ],
    "description": "Lock the specified door"
},
"Flutter.SendMessageFromCharacter": {
    "prefix": "Flutter.SendMessageFromCharacter",
    "body": [
        "Flutter.SendMessageFromCharacter(${0:message}, ${1:internalName})"
    ],
    "description": "Sends a custom FlutterMessage from NPC in current level"
},
"Flutter.SendRandomMessageFromCharacter": {
    "prefix": "Flutter.SendRandomMessageFromCharacter",
    "body": [
        "Flutter.SendRandomMessageFromCharacter(${0:internalName})"
    ],
    "description": "Sends a generated Flutter message from NPC in current level"
},
"Flutter.SendRandomMessage": {
    "prefix": "Flutter.SendRandomMessage",
    "body": [
        "Flutter.SendRandomMessage()"
    ],
    "description": "Sends a generated Flutter message from generated random character"
},
"Flutter.SetFlutterEnabled": {
    "prefix": "Flutter.SetFlutterEnabled",
    "body": [
        "Flutter.SetFlutterEnabled(${0:enabled})"
    ],
    "description": "Set Flutter app enabled or disabled."
},
"GameProgress.GetValue": {
    "prefix": "GameProgress.GetValue",
    "body": [
        "GameProgress.GetValue(${0:key})"
    ],
    "description": "Returns a value from the game progress by key, empty string if it doesn't exist"
},
"GameProgress.SetValue": {
    "prefix": "GameProgress.SetValue",
    "body": [
        "GameProgress.SetValue(${0:key}, ${1:value}, ${2:overwrite})"
    ],
    "description": "Sets a value in the game progress"
},
"GameProgress.HasKey": {
    "prefix": "GameProgress.HasKey",
    "body": [
        "GameProgress.HasKey(${0:key})"
    ],
    "description": "Does the specified key exist?"
},
"Mission.MissionStarted": {
    "prefix": "Mission.MissionStarted",
    "body": [
        "Mission.MissionStarted()"
    ],
    "description": "This should be called once the initial state of the mission has been set\r\n\t\t\t\t\t\tIt will cause the game to begin gameplay"
},
"Mission.MissionCompleted": {
    "prefix": "Mission.MissionCompleted",
    "body": [
        "Mission.MissionCompleted()"
    ],
    "description": "This should be called when the final objective of the mission has been completed\r\n\t\t\t\t\t\tIt will trigger the game to fade to black and return to the main menu"
},
"Mission.MissionFailed": {
    "prefix": "Mission.MissionFailed",
    "body": [
        "Mission.MissionFailed()"
    ],
    "description": "This function will fail the current mission, as if Joe had been tazed (or similar)."
},
"Mission.SpawnCharacter": {
    "prefix": "Mission.SpawnCharacter",
    "body": [
        "Mission.SpawnCharacter(${0:internalName})"
    ],
    "description": "Spawn a registered character in the game"
},
"Mission.ObjectiveIsActive": {
    "prefix": "Mission.ObjectiveIsActive",
    "body": [
        "Mission.ObjectiveIsActive(${0:objectiveName})"
    ],
    "description": "Returns true if objective has been started but not completed yet."
},
"Mission.ObjectiveIsCompleted": {
    "prefix": "Mission.ObjectiveIsCompleted",
    "body": [
        "Mission.ObjectiveIsCompleted(${0:objectiveName})"
    ],
    "description": "Returns true if objective has been completed."
},
"Mission.StartObjective": {
    "prefix": "Mission.StartObjective",
    "body": [
        "Mission.StartObjective(${0:objectiveName})"
    ],
    "description": "Start the provided objective"
},
"Mission.CompleteObjective": {
    "prefix": "Mission.CompleteObjective",
    "body": [
        "Mission.CompleteObjective(${0:objectiveName})"
    ],
    "description": "Complete the provided objective"
},
"Mission.GetCurrentObjective": {
    "prefix": "Mission.GetCurrentObjective",
    "body": [
        "Mission.GetCurrentObjective()"
    ],
    "description": "Get the name of the current objective"
},
"Mission.TriggerAutoSave": {
    "prefix": "Mission.TriggerAutoSave",
    "body": [
        "Mission.TriggerAutoSave()"
    ],
    "description": "Triggers an autosave, only if the game is current in a mission"
},
"Mission.DevicesConnected": {
    "prefix": "Mission.DevicesConnected",
    "body": [
        "Mission.DevicesConnected()"
    ],
    "description": "Call this AFTER all Devices have been connected to their networks. This allows DataPoints to be processed correctly."
},
"Mission.SetPlayerControlled": {
    "prefix": "Mission.SetPlayerControlled",
    "body": [
        "Mission.SetPlayerControlled(${0:tf})"
    ],
    "description": "Set whether the player is currently in control (or not). Used for cutscenes, and other things that we haven't thought of yet."
},
"Mission.GetBool": {
    "prefix": "Mission.GetBool",
    "body": [
        "Mission.GetBool(${0:key})"
    ],
    "description": "Get a boolean value of a key in mission Lua script. Returns false if key doesn't exist."
},
"Mission.SetBool": {
    "prefix": "Mission.SetBool",
    "body": [
        "Mission.SetBool(${0:key}, ${1:newBool})"
    ],
    "description": "Sets a boolean value of a key in mission Lua script."
},
"Mission.GetString": {
    "prefix": "Mission.GetString",
    "body": [
        "Mission.GetString(${0:key})"
    ],
    "description": "Get a string value of a key in mission Lua script. Returns empty if key doesn't exist."
},
"Mission.SetString": {
    "prefix": "Mission.SetString",
    "body": [
        "Mission.SetString(${0:key}, ${1:newString})"
    ],
    "description": "Sets a string value of a key in mission Lua script."
},
"Mission.GetNumber": {
    "prefix": "Mission.GetNumber",
    "body": [
        "Mission.GetNumber(${0:key})"
    ],
    "description": "Get a numeric value of a key in mission Lua script. Returns 0 if key doesn't exist."
},
"Mission.SetNumber": {
    "prefix": "Mission.SetNumber",
    "body": [
        "Mission.SetNumber(${0:key}, ${1:newValue})"
    ],
    "description": "Sets a numeric value of a key in mission Lua script."
},
"Mission.StartVibrationEvent": {
    "prefix": "Mission.StartVibrationEvent",
    "body": [
        "Mission.StartVibrationEvent(${0:objectName})"
    ],
    "description": "Start a mission object vibration event"
},
"Mission.StopVibrationEvent": {
    "prefix": "Mission.StopVibrationEvent",
    "body": [
        "Mission.StopVibrationEvent(${0:objectName})"
    ],
    "description": "Stop a mission object vibration event"
},
"Network.CreateDataPoint": {
    "prefix": "Network.CreateDataPoint",
    "body": [
        "Network.CreateDataPoint(${0:internalName}, ${1:dataTable}, ${2:locationObject}, ${3:characterName}, ${4:networkName})"
    ],
    "description": "Create a DataPoint in a specific place, from a specific character, with pre filled in data."
},
"Network.ConnectToNetwork": {
    "prefix": "Network.ConnectToNetwork",
    "body": [
        "Network.ConnectToNetwork(${0:connector}, ${1:targetNetwork}, ${2:accessKey})"
    ],
    "description": "Connect a device (or a table of devices) to a specified network"
},
"Network.SendData": {
    "prefix": "Network.SendData",
    "body": [
        "Network.SendData(${0:internalName}, ${1:dataTable}, ${2:sender}, ${3:receiver})"
    ],
    "description": "Send a data file from one device to another"
},
"Network.SetNetDeviceNFCData": {
    "prefix": "Network.SetNetDeviceNFCData",
    "body": [
        "Network.SetNetDeviceNFCData(${0:internalName}, ${1:dataTable}, ${2:deviceTable})"
    ],
    "description": "Sets NFC data on a mission object"
},
"Network.SetNetDeviceNFC": {
    "prefix": "Network.SetNetDeviceNFC",
    "body": [
        "Network.SetNetDeviceNFC(${0:deviceName}, ${1:enabled})"
    ],
    "description": "Set if a mission object supports NFCAddNetDevice"
},
"Noise.Emit": {
    "prefix": "Noise.Emit",
    "body": [
        "Noise.Emit(${0:deviceName}, ${1:noiseTable})"
    ],
    "description": "Emits a noise from deviceName with attributes in noiseTable"
},
"Noise.Silence": {
    "prefix": "Noise.Silence",
    "body": [
        "Noise.Silence(${0:deviceName}, ${1:noiseTable})"
    ],
    "description": "Silences the noise"
},
"Particles.Play": {
    "prefix": "Particles.Play",
    "body": [
        "Particles.Play(${0:deviceName}, ${1:searchChildren})"
    ],
    "description": "Sets the particle system into play mode and beings emitting"
},
"Particles.Pause": {
    "prefix": "Particles.Pause",
    "body": [
        "Particles.Pause(${0:deviceName}, ${1:searchChildren})"
    ],
    "description": "Pauses playing the particle system."
},
"Particles.Stop": {
    "prefix": "Particles.Stop",
    "body": [
        "Particles.Stop(${0:deviceName}, ${1:searchChildren})"
    ],
    "description": "Stops playing the particle system."
},
"Particles.Toggle": {
    "prefix": "Particles.Toggle",
    "body": [
        "Particles.Toggle(${0:deviceName}, ${1:searchChildren})"
    ],
    "description": "Toggles the particle system playing"
},
"Particles.Emit": {
    "prefix": "Particles.Emit",
    "body": [
        "Particles.Emit(${0:deviceName}, ${1:count}, ${2:searchChildren})"
    ],
    "description": "Emit _count_ particles immediately."
},
"Particles.IsPlaying": {
    "prefix": "Particles.IsPlaying",
    "body": [
        "Particles.IsPlaying(${0:deviceName}, ${1:searchChildren})"
    ],
    "description": "Is the particle system playing right now?"
},
"Player.AddItemToInventory": {
    "prefix": "Player.AddItemToInventory",
    "body": [
        "Player.AddItemToInventory(${0:itemName})"
    ],
    "description": "Adds an item to the players inventory (silently, wihtout a notification. Also check Mission.SendData() )."
},
"Player.RemoveItemFromInventory": {
    "prefix": "Player.RemoveItemFromInventory",
    "body": [
        "Player.RemoveItemFromInventory(${0:itemName})"
    ],
    "description": "Removes an item to the players inventory"
},
"Player.HasItem": {
    "prefix": "Player.HasItem",
    "body": [
        "Player.HasItem(${0:itemName})"
    ],
    "description": "Is an item in the players inventory"
},
"Player.ClearInventory": {
    "prefix": "Player.ClearInventory",
    "body": [
        "Player.ClearInventory()"
    ],
    "description": "Removes all items from the players inventory"
},
"Player.SetPlayerNFCData": {
    "prefix": "Player.SetPlayerNFCData",
    "body": [
        "Player.SetPlayerNFCData(${0:internalName}, ${1:dataTable})"
    ],
    "description": "Sets the NFC data on the players phone"
},
"Player.AddDataFile": {
    "prefix": "Player.AddDataFile",
    "body": [
        "Player.AddDataFile(${0:internalName}, ${1:dataTable})"
    ],
    "description": "Adds a data file directly to the players data inventory without a sender"
},
"Player.ClearDataInventory": {
    "prefix": "Player.ClearDataInventory",
    "body": [
        "Player.ClearDataInventory()"
    ],
    "description": "Removes all data files from the players data inventory"
},
"Player.ItemInQuickSlot": {
    "prefix": "Player.ItemInQuickSlot",
    "body": [
        "Player.ItemInQuickSlot()"
    ],
    "description": "Gets the name of the item currently in the players quick slot"
},
"Player.HasDataFile": {
    "prefix": "Player.HasDataFile",
    "body": [
        "Player.HasDataFile(${0:dataFileName})"
    ],
    "description": "Does the player have a data file with this name?"
},
"Player.HasEncryptedFile": {
    "prefix": "Player.HasEncryptedFile",
    "body": [
        "Player.HasEncryptedFile(${0:dataFileName})"
    ],
    "description": "Does the player have a file with the name _dataFileName_ and is it encrypted?"
},
"Player.HasDecryptedFile": {
    "prefix": "Player.HasDecryptedFile",
    "body": [
        "Player.HasDecryptedFile(${0:dataFileName})"
    ],
    "description": "Does the player have a file with the name _dataFileName_ and is it unencrypted?"
},
"Player.GetDataString": {
    "prefix": "Player.GetDataString",
    "body": [
        "Player.GetDataString(${0:internalName})"
    ],
    "description": "Returns the data string of a file in the players inventory, takes in the internal name of the file"
},
"Player.SetDataString": {
    "prefix": "Player.SetDataString",
    "body": [
        "Player.SetDataString(${0:internalName}, ${1:newString})"
    ],
    "description": "Sets the data string of a data file in the players data inventory"
},
"Player.GetAllDataFileNames": {
    "prefix": "Player.GetAllDataFileNames",
    "body": [
        "Player.GetAllDataFileNames()"
    ],
    "description": "Return internalNames of all files in the players data inventory"
},
"Player.GetAllDataFiles": {
    "prefix": "Player.GetAllDataFiles",
    "body": [
        "Player.GetAllDataFiles()"
    ],
    "description": "Return a table of all files in the players data inventory"
},
"Player.SendData": {
    "prefix": "Player.SendData",
    "body": [
        "Player.SendData(${0:internalName}, ${1:receiver})"
    ],
    "description": "Send a file from player's inventory to receiver"
},
"Player.GetSocialProfileSize": {
    "prefix": "Player.GetSocialProfileSize",
    "body": [
        "Player.GetSocialProfileSize(${0:internalName})"
    ],
    "description": "Returns the size of the background profile player has collected about a character"
},
"Player.SocialProfileContainsTag": {
    "prefix": "Player.SocialProfileContainsTag",
    "body": [
        "Player.SocialProfileContainsTag(${0:internalName}, ${1:tag})"
    ],
    "description": "Returns true if social profile contains any character data with specified tag"
},
"Player.SocialProfileContainsTagData": {
    "prefix": "Player.SocialProfileContainsTagData",
    "body": [
        "Player.SocialProfileContainsTagData(${0:internalName}, ${1:tag}, ${2:data})"
    ],
    "description": "Returns true if social profile contains character data matching both tag and data"
},
"Player.SocialProfileContainsData": {
    "prefix": "Player.SocialProfileContainsData",
    "body": [
        "Player.SocialProfileContainsData(${0:internalName}, ${1:data})"
    ],
    "description": "Returns true if social profile contains specified character data (regardless of it's tag)"
},
"Player.AddSocialProfileInformation": {
    "prefix": "Player.AddSocialProfileInformation",
    "body": [
        "Player.AddSocialProfileInformation(${0:internalName}, ${1:tag}, ${2:data})"
    ],
    "description": "Add new background data about a character to SocialInventory"
},
"Player.GetSocialProfileInformation": {
    "prefix": "Player.GetSocialProfileInformation",
    "body": [
        "Player.GetSocialProfileInformation(${0:internalName})"
    ],
    "description": "Get all known background data about a character from player's SocialInventory"
},
"Player.GetPlayerTrackingState": {
    "prefix": "Player.GetPlayerTrackingState",
    "body": [
        "Player.GetPlayerTrackingState()"
    ],
    "description": "Get current tracking state from Player's phone."
},
"Player.GetNetPointsCount": {
    "prefix": "Player.GetNetPointsCount",
    "body": [
        "Player.GetNetPointsCount()"
    ],
    "description": "Get current amount of NetPoints the player has."
},
"Player.SetNetPointsCount": {
    "prefix": "Player.SetNetPointsCount",
    "body": [
        "Player.SetNetPointsCount(${0:count})"
    ],
    "description": "Set player's NetPoints count."
},
"Player.AddNetPoints": {
    "prefix": "Player.AddNetPoints",
    "body": [
        "Player.AddNetPoints(${0:count})"
    ],
    "description": "Add more NetPoints to player"
},
"Player.RemoveNetPoints": {
    "prefix": "Player.RemoveNetPoints",
    "body": [
        "Player.RemoveNetPoints(${0:count})"
    ],
    "description": "Take NetPOintsa from player."
},
"Player.GetName": {
    "prefix": "Player.GetName",
    "body": [
        "Player.GetName()"
    ],
    "description": "Get the Player's internalName"
},
"Player.GetLightLevel": {
    "prefix": "Player.GetLightLevel",
    "body": [
        "Player.GetLightLevel()"
    ],
    "description": "Get the light level around the player"
},
"Player.SetAlwaysRagdoll": {
    "prefix": "Player.SetAlwaysRagdoll",
    "body": [
        "Player.SetAlwaysRagdoll(${0:state})"
    ],
    "description": "Player character aways ragdolls on death"
},
"Player.SetInvisible": {
    "prefix": "Player.SetInvisible",
    "body": [
        "Player.SetInvisible(${0:state})"
    ],
    "description": "Player character is invisible"
},
"Scheduler.CallInSecsReal": {
    "prefix": "Scheduler.CallInSecsReal",
    "body": [
        "Scheduler.CallInSecsReal(${0:func}, ${1:timeInSecs})"
    ],
    "description": "Schedule a lua function to be called in timeInSecs real time"
},
"Scheduler.CallInSecs": {
    "prefix": "Scheduler.CallInSecs",
    "body": [
        "Scheduler.CallInSecs(${0:func}, ${1:timeInSecs})"
    ],
    "description": "Schedule a lua function to be called in timeInSecs scaled time"
},
"Scheduler.CallAtTime": {
    "prefix": "Scheduler.CallAtTime",
    "body": [
        "Scheduler.CallAtTime(${0:func}, ${1:dateTimeString})"
    ],
    "description": "Schedule a lua function to be called at specific time (defined by a date/time string)"
},
"Sound.TriggerEvent": {
    "prefix": "Sound.TriggerEvent",
    "body": [
        "Sound.TriggerEvent(${0:eventName}, ${1:sourceName})"
    ],
    "description": "Triggers a sound even with name ''eventName''"
},
"Sound.SetRTPC": {
    "prefix": "Sound.SetRTPC",
    "body": [
        "Sound.SetRTPC(${0:sourceName}, ${1:RTPCName}, ${2:value})"
    ],
    "description": "Set Real-Time Parameter Curve for an audio event playign on this object"
},
"Spectrum.DeleteDataPoint": {
    "prefix": "Spectrum.DeleteDataPoint",
    "body": [
        "Spectrum.DeleteDataPoint(${0:dataPoint})"
    ],
    "description": "Deletes the passed in data point"
},
"Spectrum.SaveDataPoint": {
    "prefix": "Spectrum.SaveDataPoint",
    "body": [
        "Spectrum.SaveDataPoint(${0:dataPoint})"
    ],
    "description": "Saves currently targeted data point to the players data inventory"
},
"Spectrum.FilterClear": {
    "prefix": "Spectrum.FilterClear",
    "body": [
        "Spectrum.FilterClear()"
    ],
    "description": "Clear the Filter"
},
"Spectrum.FilterType (int, bool)": {
    "prefix": "Spectrum.FilterType (int, bool)",
    "body": [
        "Spectrum.FilterType (int, bool)(${0:t}, ${1:on})"
    ],
    "description": "Filter which types of Data Spectrum shows"
},
"Spectrum.FilterCreator": {
    "prefix": "Spectrum.FilterCreator",
    "body": [
        "Spectrum.FilterCreator(${0:creator})"
    ],
    "description": "Shows only Data from the Creator of the specified DataPoint. Pass nil to clear"
},
"Spectrum.FilterNetwork": {
    "prefix": "Spectrum.FilterNetwork",
    "body": [
        "Spectrum.FilterNetwork(${0:network})"
    ],
    "description": "Shows only Data from the Network of the specified DataPoint. Pass nil to clear"
},
"Timeline.Play": {
    "prefix": "Timeline.Play",
    "body": [
        "Timeline.Play(${0:missionObjectName})"
    ],
    "description": "Starts the timeline"
},
"Timeline.Pause": {
    "prefix": "Timeline.Pause",
    "body": [
        "Timeline.Pause(${0:missionObjectName})"
    ],
    "description": "Pauses the timeline"
},
"Timeline.Stop": {
    "prefix": "Timeline.Stop",
    "body": [
        "Timeline.Stop(${0:missionObjectName})"
    ],
    "description": "Stops the timeline"
},
"Timeline.SetDynamicCameraTarget": {
    "prefix": "Timeline.SetDynamicCameraTarget",
    "body": [
        "Timeline.SetDynamicCameraTarget(${0:missionObjectName}, ${1:targetName})"
    ],
    "description": "Sets the look at & follow target for all dynamically targeted cameras in the timeline"
},
"UI.ToggleClock": {
    "prefix": "UI.ToggleClock",
    "body": [
        "UI.ToggleClock(${0:state})"
    ],
    "description": "Toggles the clock hud element"
},
"UI.ToggleWeather": {
    "prefix": "UI.ToggleWeather",
    "body": [
        "UI.ToggleWeather(${0:state})"
    ],
    "description": "Toggles the weather hud element"
},
"UI.SetDataViewState": {
    "prefix": "UI.SetDataViewState",
    "body": [
        "UI.SetDataViewState(${0:state})"
    ],
    "description": "Sets the state of the data view"
},
"UI.ToggleDebugUI": {
    "prefix": "UI.ToggleDebugUI",
    "body": [
        "UI.ToggleDebugUI(${0:state})"
    ],
    "description": "Toggles the developer debug UI"
},
"UI.OpenRemoteConnection": {
    "prefix": "UI.OpenRemoteConnection",
    "body": [
        "UI.OpenRemoteConnection(${0:missionObject})"
    ],
    "description": "Opens SSH connection to currently targeted device"
},
"UI.SetRadialScanState": {
    "prefix": "UI.SetRadialScanState",
    "body": [
        "UI.SetRadialScanState(${0:shouldScan})"
    ],
    "description": "Control if the radial menu should be scanning for targets"
},
"UI.ToggleUIMarkers": {
    "prefix": "UI.ToggleUIMarkers",
    "body": [
        "UI.ToggleUIMarkers(${0:state})"
    ],
    "description": "Show/Hide UI markers for hackable and interactable objects near the player."
},
"UI.ShowHint": {
    "prefix": "UI.ShowHint",
    "body": [
        "UI.ShowHint(${0:message}, ${1:timeout})"
    ],
    "description": "Displays a hint message. Multiple messages will stack on screen but don't go too crazy..."
},
"UI.ShowModalMessage": {
    "prefix": "UI.ShowModalMessage",
    "body": [
        "UI.ShowModalMessage(${0:luaMessage})"
    ],
    "description": "Displays a modal, multiple calls to this will cause a stack of modals the user can click through"
},
"UI.ShowPopUp": {
    "prefix": "UI.ShowPopUp",
    "body": [
        "UI.ShowPopUp(${0:type}, ${1:header}, ${2:message}, ${3:timeout})"
    ],
    "description": "Displays a small pop up in the centre of the screen"
},
"UI.ShowNotification": {
    "prefix": "UI.ShowNotification",
    "body": [
        "UI.ShowNotification(${0:type}, ${1:header}, ${2:message}, ${3:timeout})"
    ],
    "description": "Displays a notification pop up in the top right corner of the screen"
},
```
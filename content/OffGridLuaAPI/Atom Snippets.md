# Atom_Snippets

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Atom_Snippets*

*Scraped on: 2025-05-02 18:40:12*

# Snippets file for Atom
Copy & paste the following code into your Snippets file in Atom to add autocompletion for Off Grid's Lua API.
(You might also want to make sure you have *language-lua* and *autocomplete-lua* and *starbound-linter-lua* packages installed)
```
'.source.lua':

  'AI.Pause':
    'prefix': 'AI.Pause'
    'body': 'AI.Pause(${0:characterName})'
    'description' : 'Pauses the agent, and stops it from doing anything.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=AI_Lua_API#Pause'

  'AI.Unpause':
    'prefix': 'AI.Unpause'
    'body': 'AI.Unpause(${0:characterName})'
    'description' : 'Unpauses a hidden agent, resuming standard behaviour.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=AI_Lua_API#Unpause'

  'AI.IsPaused':
    'prefix': 'AI.IsPaused'
    'body': 'AI.IsPaused(${0:characterName})'
    'description' : 'Returns a bool based on if a character is currently paused or not'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=AI_Lua_API#IsPaused'

  'AI.AddTemporaryGoal':
    'prefix': 'AI.AddTemporaryGoal'
    'body': 'AI.AddTemporaryGoal(${0:characterName}, ${1:goal})'
    'description' : 'Adds a goal, taking top priority, to the named AI'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=AI_Lua_API#AddTemporaryGoal'

  'AI.AlterNPCMotivation':
    'prefix': 'AI.AlterNPCMotivation'
    'body': 'AI.AlterNPCMotivation(${0:characterName}, ${1:motivationDelta})'
    'description' : 'Alters an NPCS motivation state'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=AI_Lua_API#AlterNPCMotivation'

  'AI.AlterNPCWorldState':
    'prefix': 'AI.AlterNPCWorldState'
    'body': 'AI.AlterNPCWorldState(${0:characterName}, ${1:state}, ${2:value})'
    'description' : 'Change the World State of an NPC.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=AI_Lua_API#AlterNPCWorldState'

  'AI.FavourInterest':
    'prefix': 'AI.FavourInterest'
    'body': 'AI.FavourInterest(${0:characterName}, ${1:device}, ${2:permanent})'
    'description' : 'Reduce the cost of an AI using a particular Interest'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=AI_Lua_API#FavourInterest'

  'AI.AvoidInterest':
    'prefix': 'AI.AvoidInterest'
    'body': 'AI.AvoidInterest(${0:characterName}, ${1:device}, ${2:permanent})'
    'description' : 'Increase the cost of an AI using a particular Interest'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=AI_Lua_API#AvoidInterest'

  'AI.ChangeSubject':
    'prefix': 'AI.ChangeSubject'
    'body': 'AI.ChangeSubject(${0:characterName}, ${1:subject}, ${2:value})'
    'description' : 'Set the value of a particular subject, enabling Actions with Personality requirements'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=AI_Lua_API#ChangeSubject'

  'AI.ReactTo':
    'prefix': 'AI.ReactTo'
    'body': 'AI.ReactTo(${0:characterName}, ${1:subject}, ${2:value})'
    'description' : 'Much like ChangeSubject, but instead of enabling Actions, this will alter stats within the Agent, modifying its WorldState (and as a result, enabling Actions)'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=AI_Lua_API#ReactTo'

  'AI.CreateReactable':
    'prefix': 'AI.CreateReactable'
    'body': 'AI.CreateReactable(${0:actionType}, ${1:attraction}, ${2:targetObject})'
    'description' : 'Create a new distraction that AI can pick up on'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=AI_Lua_API#CreateReactable'

  'AI.SetNPCFavouredComputer':
    'prefix': 'AI.SetNPCFavouredComputer'
    'body': 'AI.SetNPCFavouredComputer(${0:characterName}, ${1:computer})'
    'description' : 'Set NPC\'s computer, this will be used for a variety of actions'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=AI_Lua_API#SetNPCFavouredComputer'

  'Animator.SetBool':
    'prefix': 'Animator.SetBool'
    'body': 'Animator.SetBool(${0:missionObjectName}, ${1:parameterName}, ${2:value})'
    'description' : 'Sets a bool parameter by name'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Animator_Lua_API#SetBool'

  'Animator.SetFloat':
    'prefix': 'Animator.SetFloat'
    'body': 'Animator.SetFloat(${0:missionObjectName}, ${1:parameterName}, ${2:value})'
    'description' : 'Sets a float parameter by name'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Animator_Lua_API#SetFloat'

  'Animator.SetInt':
    'prefix': 'Animator.SetInt'
    'body': 'Animator.SetInt(${0:missionObjectName}, ${1:parameterName}, ${2:value})'
    'description' : 'Sets a int parameter by name'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Animator_Lua_API#SetInt'

  'Animator.SetTrigger':
    'prefix': 'Animator.SetTrigger'
    'body': 'Animator.SetTrigger(${0:missionObjectName}, ${1:parameterName})'
    'description' : 'Begins a trigger parameter by name'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Animator_Lua_API#SetTrigger'

  'Animator.GetBool':
    'prefix': 'Animator.GetBool'
    'body': 'Animator.GetBool(${0:missionObjectName}, ${1:parameterName})'
    'description' : 'Gets the current value of a bool parameter by name'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Animator_Lua_API#GetBool'

  'Animator.GetFloat':
    'prefix': 'Animator.GetFloat'
    'body': 'Animator.GetFloat(${0:missionObjectName}, ${1:parameterName})'
    'description' : 'Gets the current value of a float parameter by name'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Animator_Lua_API#GetFloat'

  'Animator.GetInt':
    'prefix': 'Animator.GetInt'
    'body': 'Animator.GetInt(${0:missionObjectName}, ${1:parameterName})'
    'description' : 'Gets the current value of a int parameter by name'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Animator_Lua_API#GetInt'

  'Apps.RequestAppState':
    'prefix': 'Apps.RequestAppState'
    'body': 'Apps.RequestAppState(${0:appName}, ${1:newState})'
    'description' : 'Ask an App to change it\'s state'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Apps_Lua_API#RequestAppState'

  'SetState':
    'prefix': 'SetState'
    'body': 'SetState(${0:newState})'
    'description' : 'Sets the App\'s state.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Apps_Lua_API#SetState'

  'CreateStatusWindow':
    'prefix': 'CreateStatusWindow'
    'body': 'CreateStatusWindow()'
    'description' : 'Create the status window'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Apps_Lua_API#CreateStatusWindow'

  'RemoveStatusWindow':
    'prefix': 'RemoveStatusWindow'
    'body': 'RemoveStatusWindow()'
    'description' : 'Remove this app\'s status window'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Apps_Lua_API#RemoveStatusWindow'

  'DisplayStatusWindow':
    'prefix': 'DisplayStatusWindow'
    'body': 'DisplayStatusWindow(${0:enabled})'
    'description' : 'Show or hide the app\'s status window.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Apps_Lua_API#DisplayStatusWindow'

  'UpdateStatusWindow':
    'prefix': 'UpdateStatusWindow'
    'body': 'UpdateStatusWindow(${0:text})'
    'description' : 'Update the text content of the app\'s status window'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Apps_Lua_API#UpdateStatusWindow'

  'SetStatusIcon':
    'prefix': 'SetStatusIcon'
    'body': 'SetStatusIcon(${0:id})'
    'description' : 'Set the icon used for the app\'s status window'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Apps_Lua_API#SetStatusIcon'

  'SetStatusIconColor':
    'prefix': 'SetStatusIconColor'
    'body': 'SetStatusIconColor(${0:color})'
    'description' : 'Set the color of the status window icon'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Apps_Lua_API#SetStatusIconColor'

  'Color.RandomColor':
    'prefix': 'Color.RandomColor'
    'body': 'Color.RandomColor(${0:alpha})'
    'description' : 'Returns a random color'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Color_Lua_API#RandomColor'

  'Color.Clear':
    'prefix': 'Color.Clear'
    'body': 'Color.Clear'
    'description' : '
{| class=wikitable
! Preview !! RGB
|-
|style="background: #ffffff;"| || 1, 1, 1
|-
|}'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Color_Lua_API#Clear'

  'Color.Black':
    'prefix': 'Color.Black'
    'body': 'Color.Black'
    'description' : '
{| class=wikitable
! Preview !! RGB
|-
|style="background: #181818;"| || 0.094, 0.094, 0.094
|-
|}'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Color_Lua_API#Black'

  'Color.DarkGrey':
    'prefix': 'Color.DarkGrey'
    'body': 'Color.DarkGrey'
    'description' : '
{| class=wikitable
! Preview !! RGB
|-
|style="background: #585858;"| || 0.345, 0.345, 0.345
|-
|}'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Color_Lua_API#DarkGrey'

  'Color.Grey':
    'prefix': 'Color.Grey'
    'body': 'Color.Grey'
    'description' : '
{| class=wikitable
! Preview !! RGB
|-
|style="background: #B8B8B8;"| || 0.722, 0.722, 0.722
|-
|}'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Color_Lua_API#Grey'

  'Color.LightGrey':
    'prefix': 'Color.LightGrey'
    'body': 'Color.LightGrey'
    'description' : '
{| class=wikitable
! Preview !! RGB
|-
|style="background: #D8D8D8;"| || 0.847, 0.847, 0.847
|-
|}'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Color_Lua_API#LightGrey'

  'Color.White':
    'prefix': 'Color.White'
    'body': 'Color.White'
    'description' : '
{| class=wikitable
! Preview !! RGB
|-
|style="background: #F8F8F8;"| || 0.972, 0.972, 0.972
|-
|}'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Color_Lua_API#White'

  'Color.Red':
    'prefix': 'Color.Red'
    'body': 'Color.Red'
    'description' : '
{| class=wikitable
! Preview !! RGB
|-
|style="background: #AB4642;"| || 0.671, 0.275, 0.259
|-
|}'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Color_Lua_API#Red'

  'Color.Orange':
    'prefix': 'Color.Orange'
    'body': 'Color.Orange'
    'description' : '
{| class=wikitable
! Preview !! RGB
|-
|style="background: #DC9656;"| || 0.863, 0.589, 0.336
|-
|}'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Color_Lua_API#Orange'

  'Color.Yellow':
    'prefix': 'Color.Yellow'
    'body': 'Color.Yellow'
    'description' : '
{| class=wikitable
! Preview !! RGB
|-
|style="background: #F7CA88;"| || 0.969, 0.792, 0.533
|-
|}'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Color_Lua_API#Yellow'

  'Color.Green':
    'prefix': 'Color.Green'
    'body': 'Color.Green'
    'description' : '
{| class=wikitable
! Preview !! RGB
|-
|style="background: #A1B56C;"| || 0.631, 0.71, 0.424
|-
|}'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Color_Lua_API#Green'

  'Color.Cyan':
    'prefix': 'Color.Cyan'
    'body': 'Color.Cyan'
    'description' : '
{| class=wikitable
! Preview !! RGB
|-
|style="background: #86C1B9;"| || 0.525, 0.757, 0.725
|-
|}'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Color_Lua_API#Cyan'

  'Color.Blue':
    'prefix': 'Color.Blue'
    'body': 'Color.Blue'
    'description' : '
{| class=wikitable
! Preview !! RGB
|-
|style="background: #7CAFC2;"| || 0.486, 0.686, 0.761
|-
|}'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Color_Lua_API#Blue'

  'Color.Purple':
    'prefix': 'Color.Purple'
    'body': 'Color.Purple'
    'description' : '
{| class=wikitable
! Preview !! RGB
|-
|style="background: #BA8BAF;"| || 0.729, 0.545, 0.686
|-
|}'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Color_Lua_API#Purple'

  'Color.Brown':
    'prefix': 'Color.Brown'
    'body': 'Color.Brown'
    'description' : '
{| class=wikitable
! Preview !! RGB
|-
|style="background: #A16946;"| || 0.631, 0.412, 0.275
|-
|}'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Color_Lua_API#Brown'

  'Conversation.StartScript':
    'prefix': 'Conversation.StartScript'
    'body': 'Conversation.StartScript(${0:path}, ${1:onCompleteCallback})'
    'description' : 'Starts a conversation from a name'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Conversation_Lua_API#StartScript'

  'DataPoints.GetAllDataPoints':
    'prefix': 'DataPoints.GetAllDataPoints'
    'body': 'DataPoints.GetAllDataPoints()'
    'description' : 'Return all the data points that are currently in the level'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=DataPoints_Lua_API#GetAllDataPoints'

  'DataPoints.GetObjectDataPoints':
    'prefix': 'DataPoints.GetObjectDataPoints'
    'body': 'DataPoints.GetObjectDataPoints(${0:objectName})'
    'description' : 'Return all the data points received by an object or a character '
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=DataPoints_Lua_API#GetObjectDataPoints'

  'DataPoints.FilterNetwork':
    'prefix': 'DataPoints.FilterNetwork'
    'body': 'DataPoints.FilterNetwork(${0:dataPoints}, ${1:networkName})'
    'description' : 'Filter data points with the network name'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=DataPoints_Lua_API#FilterNetwork'

  'DataPoints.FilterDataType':
    'prefix': 'DataPoints.FilterDataType'
    'body': 'DataPoints.FilterDataType(${0:dataPoints}, ${1:dataType})'
    'description' : 'Filter data points with the data type'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=DataPoints_Lua_API#FilterDataType'

  'DataPoints.DeleteDataPoints':
    'prefix': 'DataPoints.DeleteDataPoints'
    'body': 'DataPoints.DeleteDataPoints(${0:dataPoints})'
    'description' : 'Remove data points from the level'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=DataPoints_Lua_API#DeleteDataPoints'

  'DataPoints.GetData':
    'prefix': 'DataPoints.GetData'
    'body': 'DataPoints.GetData(${0:dataPoints})'
    'description' : 'Return all the data string from the given data points'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=DataPoints_Lua_API#GetData'

  'DataPoints.GetDataPointInfo':
    'prefix': 'DataPoints.GetDataPointInfo'
    'body': 'DataPoints.GetDataPointInfo(${0:dataPoints})'
    'description' : 'Return all the data info from the given data points'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=DataPoints_Lua_API#GetDataPointInfo'

  'DataPoints.PlayersInventorySave':
    'prefix': 'DataPoints.PlayersInventorySave'
    'body': 'DataPoints.PlayersInventorySave(${0:dataFile})'
    'description' : 'Save data info in the the players inventory'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=DataPoints_Lua_API#PlayersInventorySave'

  'DataPoints.PlayersInventoryRemove':
    'prefix': 'DataPoints.PlayersInventoryRemove'
    'body': 'DataPoints.PlayersInventoryRemove(${0:dataFile})'
    'description' : 'Save data info in the the players inventory'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=DataPoints_Lua_API#PlayersInventoryRemove'

  'Debug.ConnectToDevLaptop':
    'prefix': 'Debug.ConnectToDevLaptop'
    'body': 'Debug.ConnectToDevLaptop()'
    'description' : 'Open SSH connection to DevLaptop Device, if there\'s one in the level.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Debug_Lua_API#ConnectToDevLaptop'

  'Debug.ShowPlayerPath':
    'prefix': 'Debug.ShowPlayerPath'
    'body': 'Debug.ShowPlayerPath(${0:value})'
    'description' : 'ShowPlayerPath'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Debug_Lua_API#ShowPlayerPath'

  'Devices.SetPower':
    'prefix': 'Devices.SetPower'
    'body': 'Devices.SetPower(${0:deviceName}, ${1:state})'
    'description' : 'Change the powered on state of the device'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Devices_Lua_API#SetPower'

  'Devices.TogglePower':
    'prefix': 'Devices.TogglePower'
    'body': 'Devices.TogglePower(${0:deviceName})'
    'description' : 'Flip the powered on state of the device'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Devices_Lua_API#TogglePower'

  'Devices.GetPower':
    'prefix': 'Devices.GetPower'
    'body': 'Devices.GetPower(${0:deviceName})'
    'description' : 'Get the powered on state of the device'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Devices_Lua_API#GetPower'

  'Devices.SetActive':
    'prefix': 'Devices.SetActive'
    'body': 'Devices.SetActive(${0:deviceName}, ${1:state})'
    'description' : 'Change the active state of the device'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Devices_Lua_API#SetActive'

  'Devices.ToggleActive':
    'prefix': 'Devices.ToggleActive'
    'body': 'Devices.ToggleActive(${0:deviceName})'
    'description' : 'Flip the active state of the device'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Devices_Lua_API#ToggleActive'

  'Devices.GetActive':
    'prefix': 'Devices.GetActive'
    'body': 'Devices.GetActive(${0:deviceName})'
    'description' : 'Get the active state of the device'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Devices_Lua_API#GetActive'

  'Devices.RunOnce':
    'prefix': 'Devices.RunOnce'
    'body': 'Devices.RunOnce(${0:deviceName})'
    'description' : 'Trigger a single update of the device'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Devices_Lua_API#RunOnce'

  'Devices.SetAmok':
    'prefix': 'Devices.SetAmok'
    'body': 'Devices.SetAmok(${0:deviceName}, ${1:state})'
    'description' : 'Begin an \'Amok\' state, cause the device to act in an unstable/broken manor'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Devices_Lua_API#SetAmok'

  'Devices.ToggleAmok':
    'prefix': 'Devices.ToggleAmok'
    'body': 'Devices.ToggleAmok(${0:deviceName})'
    'description' : 'Flip the amok state'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Devices_Lua_API#ToggleAmok'

  'Devices.GetAmok':
    'prefix': 'Devices.GetAmok'
    'body': 'Devices.GetAmok(${0:deviceName})'
    'description' : 'Get the \'Amok\' state of the device'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Devices_Lua_API#GetAmok'

  'Devices.SetValue':
    'prefix': 'Devices.SetValue'
    'body': 'Devices.SetValue(${0:deviceName}, ${1:newValue})'
    'description' : 'Pass a string value to the device'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Devices_Lua_API#SetValue'

  'Devices.GetValue':
    'prefix': 'Devices.GetValue'
    'body': 'Devices.GetValue(${0:deviceName})'
    'description' : 'Get the current value of the device'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Devices_Lua_API#GetValue'

  'Devices.GetDataInventory':
    'prefix': 'Devices.GetDataInventory'
    'body': 'Devices.GetDataInventory(${0:deviceName}, ${1:index})'
    'description' : 'Get the description of the data at this index in the DataInventory'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Devices_Lua_API#GetDataInventory'

  'Devices.GetDataPointFromInventory':
    'prefix': 'Devices.GetDataPointFromInventory'
    'body': 'Devices.GetDataPointFromInventory(${0:deviceName}, ${1:index})'
    'description' : 'Get a table of useful data from the DataPoint at this index in the DataInventory'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Devices_Lua_API#GetDataPointFromInventory'

  'Devices.GetDataInventoryCount':
    'prefix': 'Devices.GetDataInventoryCount'
    'body': 'Devices.GetDataInventoryCount(${0:deviceName})'
    'description' : 'Get the number of DataPoints in the DataInventory of this device'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Devices_Lua_API#GetDataInventoryCount'

  'Doors.SetZoneKeys':
    'prefix': 'Doors.SetZoneKeys'
    'body': 'Doors.SetZoneKeys(${0:zoneName}, ${1:keyNames})'
    'description' : 'Sets a key as unlocking a specific zone'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Doors_Lua_API#SetZoneKeys'

  'Doors.SetNetwork':
    'prefix': 'Doors.SetNetwork'
    'body': 'Doors.SetNetwork(${0:networkName})'
    'description' : 'Sets the name of the network for the door system to use'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Doors_Lua_API#SetNetwork'

  'Doors.SetKeyOnDevice':
    'prefix': 'Doors.SetKeyOnDevice'
    'body': 'Doors.SetKeyOnDevice(${0:keyName}, ${1:deviceName})'
    'description' : 'Sets a key as the current NFC file on a net device'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Doors_Lua_API#SetKeyOnDevice'

  'Doors.AssignKeyToCharacter':
    'prefix': 'Doors.AssignKeyToCharacter'
    'body': 'Doors.AssignKeyToCharacter(${0:keyName}, ${1:character})'
    'description' : 'Adds a key to a characters inventory and sets it as the characters current NFC data'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Doors_Lua_API#AssignKeyToCharacter'

  'Doors.Open':
    'prefix': 'Doors.Open'
    'body': 'Doors.Open(${0:doorID})'
    'description' : 'Open the specified door.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Doors_Lua_API#Open'

  'Doors.Close':
    'prefix': 'Doors.Close'
    'body': 'Doors.Close(${0:doorID})'
    'description' : 'close the specified door.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Doors_Lua_API#Close'

  'Doors.Unlock':
    'prefix': 'Doors.Unlock'
    'body': 'Doors.Unlock(${0:doorID})'
    'description' : 'Unlock the specified door'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Doors_Lua_API#Unlock'

  'Doors.Lock':
    'prefix': 'Doors.Lock'
    'body': 'Doors.Lock(${0:doorID})'
    'description' : 'Lock the specified door'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Doors_Lua_API#Lock'

  'Flutter.SendMessageFromCharacter':
    'prefix': 'Flutter.SendMessageFromCharacter'
    'body': 'Flutter.SendMessageFromCharacter(${0:message}, ${1:internalName})'
    'description' : 'Sends a custom FlutterMessage from NPC in current level'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Flutter_Lua_API#SendMessageFromCharacter'

  'Flutter.SendRandomMessageFromCharacter':
    'prefix': 'Flutter.SendRandomMessageFromCharacter'
    'body': 'Flutter.SendRandomMessageFromCharacter(${0:internalName})'
    'description' : 'Sends a generated Flutter message from NPC in current level'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Flutter_Lua_API#SendRandomMessageFromCharacter'

  'Flutter.SendRandomMessage':
    'prefix': 'Flutter.SendRandomMessage'
    'body': 'Flutter.SendRandomMessage()'
    'description' : 'Sends a generated Flutter message from generated random character'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Flutter_Lua_API#SendRandomMessage'

  'Flutter.SetFlutterEnabled':
    'prefix': 'Flutter.SetFlutterEnabled'
    'body': 'Flutter.SetFlutterEnabled(${0:enabled})'
    'description' : 'Set Flutter app enabled or disabled.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Flutter_Lua_API#SetFlutterEnabled'

  'GameProgress.GetValue':
    'prefix': 'GameProgress.GetValue'
    'body': 'GameProgress.GetValue(${0:key})'
    'description' : 'Returns a value from the game progress by key, empty string if it doesn\'t exist'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=GameProgress_Lua_API#GetValue'

  'GameProgress.SetValue':
    'prefix': 'GameProgress.SetValue'
    'body': 'GameProgress.SetValue(${0:key}, ${1:value}, ${2:overwrite})'
    'description' : 'Sets a value in the game progress'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=GameProgress_Lua_API#SetValue'

  'GameProgress.HasKey':
    'prefix': 'GameProgress.HasKey'
    'body': 'GameProgress.HasKey(${0:key})'
    'description' : 'Does the specified key exist?'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=GameProgress_Lua_API#HasKey'

  'Mission.MissionStarted':
    'prefix': 'Mission.MissionStarted'
    'body': 'Mission.MissionStarted()'
    'description' : 'This should be called once the initial state of the mission has been set
						It will cause the game to begin gameplay'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Mission_Lua_API#MissionStarted'

  'Mission.MissionCompleted':
    'prefix': 'Mission.MissionCompleted'
    'body': 'Mission.MissionCompleted()'
    'description' : 'This should be called when the final objective of the mission has been completed
						It will trigger the game to fade to black and return to the main menu'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Mission_Lua_API#MissionCompleted'

  'Mission.MissionFailed':
    'prefix': 'Mission.MissionFailed'
    'body': 'Mission.MissionFailed()'
    'description' : 'This function will fail the current mission, as if Joe had been tazed (or similar).'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Mission_Lua_API#MissionFailed'

  'Mission.SpawnCharacter':
    'prefix': 'Mission.SpawnCharacter'
    'body': 'Mission.SpawnCharacter(${0:internalName})'
    'description' : 'Spawn a registered character in the game'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Mission_Lua_API#SpawnCharacter'

  'Mission.ObjectiveIsActive':
    'prefix': 'Mission.ObjectiveIsActive'
    'body': 'Mission.ObjectiveIsActive(${0:objectiveName})'
    'description' : 'Returns true if objective has been started but not completed yet.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Mission_Lua_API#ObjectiveIsActive'

  'Mission.ObjectiveIsCompleted':
    'prefix': 'Mission.ObjectiveIsCompleted'
    'body': 'Mission.ObjectiveIsCompleted(${0:objectiveName})'
    'description' : 'Returns true if objective has been completed.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Mission_Lua_API#ObjectiveIsCompleted'

  'Mission.StartObjective':
    'prefix': 'Mission.StartObjective'
    'body': 'Mission.StartObjective(${0:objectiveName})'
    'description' : 'Start the provided objective'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Mission_Lua_API#StartObjective'

  'Mission.CompleteObjective':
    'prefix': 'Mission.CompleteObjective'
    'body': 'Mission.CompleteObjective(${0:objectiveName})'
    'description' : 'Complete the provided objective'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Mission_Lua_API#CompleteObjective'

  'Mission.GetCurrentObjective':
    'prefix': 'Mission.GetCurrentObjective'
    'body': 'Mission.GetCurrentObjective()'
    'description' : 'Get the name of the current objective'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Mission_Lua_API#GetCurrentObjective'

  'Mission.TriggerAutoSave':
    'prefix': 'Mission.TriggerAutoSave'
    'body': 'Mission.TriggerAutoSave()'
    'description' : 'Triggers an autosave, only if the game is current in a mission'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Mission_Lua_API#TriggerAutoSave'

  'Mission.DevicesConnected':
    'prefix': 'Mission.DevicesConnected'
    'body': 'Mission.DevicesConnected()'
    'description' : 'Call this AFTER all Devices have been connected to their networks. This allows DataPoints to be processed correctly.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Mission_Lua_API#DevicesConnected'

  'Mission.SetPlayerControlled':
    'prefix': 'Mission.SetPlayerControlled'
    'body': 'Mission.SetPlayerControlled(${0:tf})'
    'description' : 'Set whether the player is currently in control (or not). Used for cutscenes, and other things that we haven\'t thought of yet.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Mission_Lua_API#SetPlayerControlled'

  'Mission.GetBool':
    'prefix': 'Mission.GetBool'
    'body': 'Mission.GetBool(${0:key})'
    'description' : 'Get a boolean value of a key in mission Lua script. Returns false if key doesn\'t exist.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Mission_Lua_API#GetBool'

  'Mission.SetBool':
    'prefix': 'Mission.SetBool'
    'body': 'Mission.SetBool(${0:key}, ${1:newBool})'
    'description' : 'Sets a boolean value of a key in mission Lua script.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Mission_Lua_API#SetBool'

  'Mission.GetString':
    'prefix': 'Mission.GetString'
    'body': 'Mission.GetString(${0:key})'
    'description' : 'Get a string value of a key in mission Lua script. Returns empty if key doesn\'t exist.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Mission_Lua_API#GetString'

  'Mission.SetString':
    'prefix': 'Mission.SetString'
    'body': 'Mission.SetString(${0:key}, ${1:newString})'
    'description' : 'Sets a string value of a key in mission Lua script.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Mission_Lua_API#SetString'

  'Mission.GetNumber':
    'prefix': 'Mission.GetNumber'
    'body': 'Mission.GetNumber(${0:key})'
    'description' : 'Get a numeric value of a key in mission Lua script. Returns 0 if key doesn\'t exist.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Mission_Lua_API#GetNumber'

  'Mission.SetNumber':
    'prefix': 'Mission.SetNumber'
    'body': 'Mission.SetNumber(${0:key}, ${1:newValue})'
    'description' : 'Sets a numeric value of a key in mission Lua script.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Mission_Lua_API#SetNumber'

  'Mission.StartVibrationEvent':
    'prefix': 'Mission.StartVibrationEvent'
    'body': 'Mission.StartVibrationEvent(${0:objectName})'
    'description' : 'Start a mission object vibration event'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Mission_Lua_API#StartVibrationEvent'

  'Mission.StopVibrationEvent':
    'prefix': 'Mission.StopVibrationEvent'
    'body': 'Mission.StopVibrationEvent(${0:objectName})'
    'description' : 'Stop a mission object vibration event'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Mission_Lua_API#StopVibrationEvent'

  'Network.CreateDataPoint':
    'prefix': 'Network.CreateDataPoint'
    'body': 'Network.CreateDataPoint(${0:internalName}, ${1:dataTable}, ${2:locationObject}, ${3:characterName}, ${4:networkName})'
    'description' : 'Create a DataPoint in a specific place, from a specific character, with pre filled in data.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Network_Lua_API#CreateDataPoint'

  'Network.ConnectToNetwork':
    'prefix': 'Network.ConnectToNetwork'
    'body': 'Network.ConnectToNetwork(${0:connector}, ${1:targetNetwork}, ${2:accessKey})'
    'description' : 'Connect a device (or a table of devices) to a specified network'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Network_Lua_API#ConnectToNetwork'

  'Network.SendData':
    'prefix': 'Network.SendData'
    'body': 'Network.SendData(${0:internalName}, ${1:dataTable}, ${2:sender}, ${3:receiver})'
    'description' : 'Send a data file from one device to another'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Network_Lua_API#SendData'

  'Network.SetNetDeviceNFCData':
    'prefix': 'Network.SetNetDeviceNFCData'
    'body': 'Network.SetNetDeviceNFCData(${0:internalName}, ${1:dataTable}, ${2:deviceTable})'
    'description' : 'Sets NFC data on a mission object'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Network_Lua_API#SetNetDeviceNFCData'

  'Network.SetNetDeviceNFC':
    'prefix': 'Network.SetNetDeviceNFC'
    'body': 'Network.SetNetDeviceNFC(${0:deviceName}, ${1:enabled})'
    'description' : 'Set if a mission object supports NFCAddNetDevice'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Network_Lua_API#SetNetDeviceNFC'

  'Noise.Emit':
    'prefix': 'Noise.Emit'
    'body': 'Noise.Emit(${0:deviceName}, ${1:noiseTable})'
    'description' : 'Emits a noise from deviceName with attributes in noiseTable'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Noise_Lua_API#Emit'

  'Noise.Silence':
    'prefix': 'Noise.Silence'
    'body': 'Noise.Silence(${0:deviceName}, ${1:noiseTable})'
    'description' : 'Silences the noise'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Noise_Lua_API#Silence'

  'Particles.Play':
    'prefix': 'Particles.Play'
    'body': 'Particles.Play(${0:deviceName}, ${1:searchChildren})'
    'description' : 'Sets the particle system into play mode and beings emitting'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Particles_Lua_API#Play'

  'Particles.Pause':
    'prefix': 'Particles.Pause'
    'body': 'Particles.Pause(${0:deviceName}, ${1:searchChildren})'
    'description' : 'Pauses playing the particle system.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Particles_Lua_API#Pause'

  'Particles.Stop':
    'prefix': 'Particles.Stop'
    'body': 'Particles.Stop(${0:deviceName}, ${1:searchChildren})'
    'description' : 'Stops playing the particle system.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Particles_Lua_API#Stop'

  'Particles.Toggle':
    'prefix': 'Particles.Toggle'
    'body': 'Particles.Toggle(${0:deviceName}, ${1:searchChildren})'
    'description' : 'Toggles the particle system playing'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Particles_Lua_API#Toggle'

  'Particles.Emit':
    'prefix': 'Particles.Emit'
    'body': 'Particles.Emit(${0:deviceName}, ${1:count}, ${2:searchChildren})'
    'description' : 'Emit _count_ particles immediately.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Particles_Lua_API#Emit'

  'Particles.IsPlaying':
    'prefix': 'Particles.IsPlaying'
    'body': 'Particles.IsPlaying(${0:deviceName}, ${1:searchChildren})'
    'description' : 'Is the particle system playing right now?'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Particles_Lua_API#IsPlaying'

  'Player.AddItemToInventory':
    'prefix': 'Player.AddItemToInventory'
    'body': 'Player.AddItemToInventory(${0:itemName})'
    'description' : 'Adds an item to the players inventory (silently, wihtout a notification. Also check Mission.SendData() ).'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#AddItemToInventory'

  'Player.RemoveItemFromInventory':
    'prefix': 'Player.RemoveItemFromInventory'
    'body': 'Player.RemoveItemFromInventory(${0:itemName})'
    'description' : 'Removes an item to the players inventory'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#RemoveItemFromInventory'

  'Player.HasItem':
    'prefix': 'Player.HasItem'
    'body': 'Player.HasItem(${0:itemName})'
    'description' : 'Is an item in the players inventory'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#HasItem'

  'Player.ClearInventory':
    'prefix': 'Player.ClearInventory'
    'body': 'Player.ClearInventory()'
    'description' : 'Removes all items from the players inventory'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#ClearInventory'

  'Player.SetPlayerNFCData':
    'prefix': 'Player.SetPlayerNFCData'
    'body': 'Player.SetPlayerNFCData(${0:internalName}, ${1:dataTable})'
    'description' : 'Sets the NFC data on the players phone'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#SetPlayerNFCData'

  'Player.AddDataFile':
    'prefix': 'Player.AddDataFile'
    'body': 'Player.AddDataFile(${0:internalName}, ${1:dataTable})'
    'description' : 'Adds a data file directly to the players data inventory without a sender'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#AddDataFile'

  'Player.ClearDataInventory':
    'prefix': 'Player.ClearDataInventory'
    'body': 'Player.ClearDataInventory()'
    'description' : 'Removes all data files from the players data inventory'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#ClearDataInventory'

  'Player.ItemInQuickSlot':
    'prefix': 'Player.ItemInQuickSlot'
    'body': 'Player.ItemInQuickSlot()'
    'description' : 'Gets the name of the item currently in the players quick slot'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#ItemInQuickSlot'

  'Player.HasDataFile':
    'prefix': 'Player.HasDataFile'
    'body': 'Player.HasDataFile(${0:dataFileName})'
    'description' : 'Does the player have a data file with this name?'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#HasDataFile'

  'Player.HasEncryptedFile':
    'prefix': 'Player.HasEncryptedFile'
    'body': 'Player.HasEncryptedFile(${0:dataFileName})'
    'description' : 'Does the player have a file with the name _dataFileName_ and is it encrypted?'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#HasEncryptedFile'

  'Player.HasDecryptedFile':
    'prefix': 'Player.HasDecryptedFile'
    'body': 'Player.HasDecryptedFile(${0:dataFileName})'
    'description' : 'Does the player have a file with the name _dataFileName_ and is it unencrypted?'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#HasDecryptedFile'

  'Player.GetDataString':
    'prefix': 'Player.GetDataString'
    'body': 'Player.GetDataString(${0:internalName})'
    'description' : 'Returns the data string of a file in the players inventory, takes in the internal name of the file'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#GetDataString'

  'Player.SetDataString':
    'prefix': 'Player.SetDataString'
    'body': 'Player.SetDataString(${0:internalName}, ${1:newString})'
    'description' : 'Sets the data string of a data file in the players data inventory'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#SetDataString'

  'Player.GetAllDataFileNames':
    'prefix': 'Player.GetAllDataFileNames'
    'body': 'Player.GetAllDataFileNames()'
    'description' : 'Return internalNames of all files in the players data inventory'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#GetAllDataFileNames'

  'Player.GetAllDataFiles':
    'prefix': 'Player.GetAllDataFiles'
    'body': 'Player.GetAllDataFiles()'
    'description' : 'Return a table of all files in the players data inventory'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#GetAllDataFiles'

  'Player.SendData':
    'prefix': 'Player.SendData'
    'body': 'Player.SendData(${0:internalName}, ${1:receiver})'
    'description' : 'Send a file from player\'s inventory to receiver'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#SendData'

  'Player.GetSocialProfileSize':
    'prefix': 'Player.GetSocialProfileSize'
    'body': 'Player.GetSocialProfileSize(${0:internalName})'
    'description' : 'Returns the size of the background profile player has collected about a character'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#GetSocialProfileSize'

  'Player.SocialProfileContainsTag':
    'prefix': 'Player.SocialProfileContainsTag'
    'body': 'Player.SocialProfileContainsTag(${0:internalName}, ${1:tag})'
    'description' : 'Returns true if social profile contains any character data with specified tag'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#SocialProfileContainsTag'

  'Player.SocialProfileContainsTagData':
    'prefix': 'Player.SocialProfileContainsTagData'
    'body': 'Player.SocialProfileContainsTagData(${0:internalName}, ${1:tag}, ${2:data})'
    'description' : 'Returns true if social profile contains character data matching both tag and data'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#SocialProfileContainsTagData'

  'Player.SocialProfileContainsData':
    'prefix': 'Player.SocialProfileContainsData'
    'body': 'Player.SocialProfileContainsData(${0:internalName}, ${1:data})'
    'description' : 'Returns true if social profile contains specified character data (regardless of it\'s tag)'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#SocialProfileContainsData'

  'Player.AddSocialProfileInformation':
    'prefix': 'Player.AddSocialProfileInformation'
    'body': 'Player.AddSocialProfileInformation(${0:internalName}, ${1:tag}, ${2:data})'
    'description' : 'Add new background data about a character to SocialInventory'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#AddSocialProfileInformation'

  'Player.GetSocialProfileInformation':
    'prefix': 'Player.GetSocialProfileInformation'
    'body': 'Player.GetSocialProfileInformation(${0:internalName})'
    'description' : 'Get all known background data about a character from player\'s SocialInventory'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#GetSocialProfileInformation'

  'Player.GetPlayerTrackingState':
    'prefix': 'Player.GetPlayerTrackingState'
    'body': 'Player.GetPlayerTrackingState()'
    'description' : 'Get current tracking state from Player\'s phone.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#GetPlayerTrackingState'

  'Player.GetNetPointsCount':
    'prefix': 'Player.GetNetPointsCount'
    'body': 'Player.GetNetPointsCount()'
    'description' : 'Get current amount of NetPoints the player has.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#GetNetPointsCount'

  'Player.SetNetPointsCount':
    'prefix': 'Player.SetNetPointsCount'
    'body': 'Player.SetNetPointsCount(${0:count})'
    'description' : 'Set player\'s NetPoints count.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#SetNetPointsCount'

  'Player.AddNetPoints':
    'prefix': 'Player.AddNetPoints'
    'body': 'Player.AddNetPoints(${0:count})'
    'description' : 'Add more NetPoints to player'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#AddNetPoints'

  'Player.RemoveNetPoints':
    'prefix': 'Player.RemoveNetPoints'
    'body': 'Player.RemoveNetPoints(${0:count})'
    'description' : 'Take NetPOintsa from player.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#RemoveNetPoints'

  'Player.GetName':
    'prefix': 'Player.GetName'
    'body': 'Player.GetName()'
    'description' : 'Get the Player\'s internalName'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#GetName'

  'Player.GetLightLevel':
    'prefix': 'Player.GetLightLevel'
    'body': 'Player.GetLightLevel()'
    'description' : 'Get the light level around the player'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#GetLightLevel'

  'Player.SetAlwaysRagdoll':
    'prefix': 'Player.SetAlwaysRagdoll'
    'body': 'Player.SetAlwaysRagdoll(${0:state})'
    'description' : 'Player character aways ragdolls on death'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#SetAlwaysRagdoll'

  'Player.SetInvisible':
    'prefix': 'Player.SetInvisible'
    'body': 'Player.SetInvisible(${0:state})'
    'description' : 'Player character is invisible'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Player_Lua_API#SetInvisible'

  'Scheduler.CallInSecsReal':
    'prefix': 'Scheduler.CallInSecsReal'
    'body': 'Scheduler.CallInSecsReal(${0:func}, ${1:timeInSecs})'
    'description' : 'Schedule a lua function to be called in timeInSecs real time'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Scheduler_Lua_API#CallInSecsReal'

  'Scheduler.CallInSecs':
    'prefix': 'Scheduler.CallInSecs'
    'body': 'Scheduler.CallInSecs(${0:func}, ${1:timeInSecs})'
    'description' : 'Schedule a lua function to be called in timeInSecs scaled time'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Scheduler_Lua_API#CallInSecs'

  'Scheduler.CallAtTime':
    'prefix': 'Scheduler.CallAtTime'
    'body': 'Scheduler.CallAtTime(${0:func}, ${1:dateTimeString})'
    'description' : 'Schedule a lua function to be called at specific time (defined by a date/time string)'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Scheduler_Lua_API#CallAtTime'

  'Sound.TriggerEvent':
    'prefix': 'Sound.TriggerEvent'
    'body': 'Sound.TriggerEvent(${0:eventName}, ${1:sourceName})'
    'description' : 'Triggers a sound even with name \'\'eventName\'\''
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Sound_Lua_API#TriggerEvent'

  'Sound.SetRTPC':
    'prefix': 'Sound.SetRTPC'
    'body': 'Sound.SetRTPC(${0:sourceName}, ${1:RTPCName}, ${2:value})'
    'description' : 'Set Real-Time Parameter Curve for an audio event playign on this object'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Sound_Lua_API#SetRTPC'

  'Spectrum.DeleteDataPoint':
    'prefix': 'Spectrum.DeleteDataPoint'
    'body': 'Spectrum.DeleteDataPoint(${0:dataPoint})'
    'description' : 'Deletes the passed in data point'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Spectrum_Lua_API#DeleteDataPoint'

  'Spectrum.SaveDataPoint':
    'prefix': 'Spectrum.SaveDataPoint'
    'body': 'Spectrum.SaveDataPoint(${0:dataPoint})'
    'description' : 'Saves currently targeted data point to the players data inventory'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Spectrum_Lua_API#SaveDataPoint'

  'Spectrum.FilterClear':
    'prefix': 'Spectrum.FilterClear'
    'body': 'Spectrum.FilterClear()'
    'description' : 'Clear the Filter'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Spectrum_Lua_API#FilterClear'

  'Spectrum.FilterType (int, bool)':
    'prefix': 'Spectrum.FilterType (int, bool)'
    'body': 'Spectrum.FilterType (int, bool)(${0:t}, ${1:on})'
    'description' : 'Filter which types of Data Spectrum shows'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Spectrum_Lua_API#FilterType (int, bool)'

  'Spectrum.FilterCreator':
    'prefix': 'Spectrum.FilterCreator'
    'body': 'Spectrum.FilterCreator(${0:creator})'
    'description' : 'Shows only Data from the Creator of the specified DataPoint. Pass nil to clear'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Spectrum_Lua_API#FilterCreator'

  'Spectrum.FilterNetwork':
    'prefix': 'Spectrum.FilterNetwork'
    'body': 'Spectrum.FilterNetwork(${0:network})'
    'description' : 'Shows only Data from the Network of the specified DataPoint. Pass nil to clear'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Spectrum_Lua_API#FilterNetwork'

  'Timeline.Play':
    'prefix': 'Timeline.Play'
    'body': 'Timeline.Play(${0:missionObjectName})'
    'description' : 'Starts the timeline'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Timeline_Lua_API#Play'

  'Timeline.Pause':
    'prefix': 'Timeline.Pause'
    'body': 'Timeline.Pause(${0:missionObjectName})'
    'description' : 'Pauses the timeline'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Timeline_Lua_API#Pause'

  'Timeline.Stop':
    'prefix': 'Timeline.Stop'
    'body': 'Timeline.Stop(${0:missionObjectName})'
    'description' : 'Stops the timeline'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Timeline_Lua_API#Stop'

  'Timeline.SetDynamicCameraTarget':
    'prefix': 'Timeline.SetDynamicCameraTarget'
    'body': 'Timeline.SetDynamicCameraTarget(${0:missionObjectName}, ${1:targetName})'
    'description' : 'Sets the look at & follow target for all dynamically targeted cameras in the timeline'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=Timeline_Lua_API#SetDynamicCameraTarget'

  'UI.ToggleClock':
    'prefix': 'UI.ToggleClock'
    'body': 'UI.ToggleClock(${0:state})'
    'description' : 'Toggles the clock hud element'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=UI_Lua_API#ToggleClock'

  'UI.ToggleWeather':
    'prefix': 'UI.ToggleWeather'
    'body': 'UI.ToggleWeather(${0:state})'
    'description' : 'Toggles the weather hud element'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=UI_Lua_API#ToggleWeather'

  'UI.SetDataViewState':
    'prefix': 'UI.SetDataViewState'
    'body': 'UI.SetDataViewState(${0:state})'
    'description' : 'Sets the state of the data view'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=UI_Lua_API#SetDataViewState'

  'UI.ToggleDebugUI':
    'prefix': 'UI.ToggleDebugUI'
    'body': 'UI.ToggleDebugUI(${0:state})'
    'description' : 'Toggles the developer debug UI'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=UI_Lua_API#ToggleDebugUI'

  'UI.OpenRemoteConnection':
    'prefix': 'UI.OpenRemoteConnection'
    'body': 'UI.OpenRemoteConnection(${0:missionObject})'
    'description' : 'Opens SSH connection to currently targeted device'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=UI_Lua_API#OpenRemoteConnection'

  'UI.SetRadialScanState':
    'prefix': 'UI.SetRadialScanState'
    'body': 'UI.SetRadialScanState(${0:shouldScan})'
    'description' : 'Control if the radial menu should be scanning for targets'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=UI_Lua_API#SetRadialScanState'

  'UI.ToggleUIMarkers':
    'prefix': 'UI.ToggleUIMarkers'
    'body': 'UI.ToggleUIMarkers(${0:state})'
    'description' : 'Show/Hide UI markers for hackable and interactable objects near the player.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=UI_Lua_API#ToggleUIMarkers'

  'UI.ShowHint':
    'prefix': 'UI.ShowHint'
    'body': 'UI.ShowHint(${0:message}, ${1:timeout})'
    'description' : 'Displays a hint message. Multiple messages will stack on screen but don\'t go too crazy...'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=UI_Lua_API#ShowHint'

  'UI.ShowModalMessage':
    'prefix': 'UI.ShowModalMessage'
    'body': 'UI.ShowModalMessage(${0:luaMessage})'
    'description' : 'Displays a modal, multiple calls to this will cause a stack of modals the user can click through'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=UI_Lua_API#ShowModalMessage'

  'UI.ShowPopUp':
    'prefix': 'UI.ShowPopUp'
    'body': 'UI.ShowPopUp(${0:type}, ${1:header}, ${2:message}, ${3:timeout})'
    'description' : 'Displays a small pop up in the centre of the screen'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=UI_Lua_API#ShowPopUp'

  'UI.ShowNotification':
    'prefix': 'UI.ShowNotification'
    'body': 'UI.ShowNotification(${0:type}, ${1:header}, ${2:message}, ${3:timeout})'
    'description' : 'Displays a notification pop up in the top right corner of the screen'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : 'http://wiki.offgridthegame.com/index.php?title=UI_Lua_API#ShowNotification'

  'DataType.Generic':
    'prefix': 'DataType.Generic'
    'body': 'DataType.Generic'
    'description' : 'Any random data. Who knows, could be anything.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'DataType.Text':
    'prefix': 'DataType.Text'
    'body': 'DataType.Text'
    'description' : 'Plain text or rich text content.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'DataType.SMS':
    'prefix': 'DataType.SMS'
    'body': 'DataType.SMS'
    'description' : 'SMS. Don\'t use this! Legacy stuff.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'DataType.Image':
    'prefix': 'DataType.Image'
    'body': 'DataType.Image'
    'description' : 'Image file. We\'ll try to display this for you in the File Viewer.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'DataType.Audio':
    'prefix': 'DataType.Audio'
    'body': 'DataType.Audio'
    'description' : 'Audio file. There\'s no viewer for these yet.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'DataType.Video':
    'prefix': 'DataType.Video'
    'body': 'DataType.Video'
    'description' : 'Video file. There\'s no viewer for these yet.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'DataType.Location':
    'prefix': 'DataType.Location'
    'body': 'DataType.Location'
    'description' : 'Location data. just the coordinates, no much use apart from being a location marker in level'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'DataType.Key':
    'prefix': 'DataType.Key'
    'body': 'DataType.Key'
    'description' : 'PGP key. For encryption, device/lock access etc.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'DataType.UUID':
    'prefix': 'DataType.UUID'
    'body': 'DataType.UUID'
    'description' : 'Generic identifier for something.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'MissionObjectType.Trigger':
    'prefix': 'MissionObjectType.Trigger'
    'body': 'MissionObjectType.Trigger'
    'description' : ''
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'MissionObjectType.Interaction':
    'prefix': 'MissionObjectType.Interaction'
    'body': 'MissionObjectType.Interaction'
    'description' : ''
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'MissionObjectType.Spawn':
    'prefix': 'MissionObjectType.Spawn'
    'body': 'MissionObjectType.Spawn'
    'description' : ''
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'MissionObjectType.Hackable':
    'prefix': 'MissionObjectType.Hackable'
    'body': 'MissionObjectType.Hackable'
    'description' : ''
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'MissionObjectType.Generic':
    'prefix': 'MissionObjectType.Generic'
    'body': 'MissionObjectType.Generic'
    'description' : ''
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'MissionObjectType.Deprecated':
    'prefix': 'MissionObjectType.Deprecated'
    'body': 'MissionObjectType.Deprecated'
    'description' : ''
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'MissionObjectType.Timeline':
    'prefix': 'MissionObjectType.Timeline'
    'body': 'MissionObjectType.Timeline'
    'description' : ''
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'InteractionType.Grab':
    'prefix': 'InteractionType.Grab'
    'body': 'InteractionType.Grab'
    'description' : ''
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'InteractionType.OpenDoor':
    'prefix': 'InteractionType.OpenDoor'
    'body': 'InteractionType.OpenDoor'
    'description' : ''
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'InteractionType.Scanning':
    'prefix': 'InteractionType.Scanning'
    'body': 'InteractionType.Scanning'
    'description' : ''
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'AIReactionType.FixAmokDevice':
    'prefix': 'AIReactionType.FixAmokDevice'
    'body': 'AIReactionType.FixAmokDevice'
    'description' : 'The NPC will attempt to fix the amok device'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'AppState.unavailable':
    'prefix': 'AppState.unavailable'
    'body': 'AppState.unavailable'
    'description' : 'The player doesn\'t have this app yet.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'AppState.disabled':
    'prefix': 'AppState.disabled'
    'body': 'AppState.disabled'
    'description' : 'App can\'t be used at the moment, for example no network connection'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'AppState.off':
    'prefix': 'AppState.off'
    'body': 'AppState.off'
    'description' : 'App is not doing anything'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'AppState.on':
    'prefix': 'AppState.on'
    'body': 'AppState.on'
    'description' : 'App is switched on and running in the background'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'AppState.alert':
    'prefix': 'AppState.alert'
    'body': 'AppState.alert'
    'description' : 'App displays alert to notify the player about something.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'AppMenuState.any':
    'prefix': 'AppMenuState.any'
    'body': 'AppMenuState.any'
    'description' : 'Allowed in any of configuration'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'AppMenuState.never':
    'prefix': 'AppMenuState.never'
    'body': 'AppMenuState.never'
    'description' : 'Never allowed in the selected menu'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'AppMenuState.always':
    'prefix': 'AppMenuState.always'
    'body': 'AppMenuState.always'
    'description' : 'Always in the selected menu'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'AppMenuState.byDefault':
    'prefix': 'AppMenuState.byDefault'
    'body': 'AppMenuState.byDefault'
    'description' : 'In the selected menu by default'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'AppMenuState.target':
    'prefix': 'AppMenuState.target'
    'body': 'AppMenuState.target'
    'description' : 'Will be in the radial menu when its target types are selected'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'TrackingStates.off':
    'prefix': 'TrackingStates.off'
    'body': 'TrackingStates.off'
    'description' : 'Not connected to SPECTRUM.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'TrackingStates.tracking':
    'prefix': 'TrackingStates.tracking'
    'body': 'TrackingStates.tracking'
    'description' : 'Connected to SPECTRUM.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'TrackingStates.alert':
    'prefix': 'TrackingStates.alert'
    'body': 'TrackingStates.alert'
    'description' : 'Connected to SPECTRUM, almost out of time.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'TrackingStates.overtime':
    'prefix': 'TrackingStates.overtime'
    'body': 'TrackingStates.overtime'
    'description' : 'Connected to SPECTRUM, over time, restricted to minimum range'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'TrackingStates.cooldown':
    'prefix': 'TrackingStates.cooldown'
    'body': 'TrackingStates.cooldown'
    'description' : 'Disconnected from SPECTRUM, recovering.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'TrackingStates.unlimited':
    'prefix': 'TrackingStates.unlimited'
    'body': 'TrackingStates.unlimited'
    'description' : 'Unlimited connection. Cheater.'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'NetworkType.mobile':
    'prefix': 'NetworkType.mobile'
    'body': 'NetworkType.mobile'
    'description' : 'Mobile network (4G)- This will mainly just contain mobile phone devices'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'NetworkType.wifi':
    'prefix': 'NetworkType.wifi'
    'body': 'NetworkType.wifi'
    'description' : 'Wifi networks will be the most common, and will contain all sorts of devices'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'NetworkType.mesh':
    'prefix': 'NetworkType.mesh'
    'body': 'NetworkType.mesh'
    'description' : 'Mesh networks are mainly set up as part of a storyline'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'NetworkType.nfc':
    'prefix': 'NetworkType.nfc'
    'body': 'NetworkType.nfc'
    'description' : ''
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'TargetType.None':
    'prefix': 'TargetType.None'
    'body': 'TargetType.None'
    'description' : ''
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'TargetType.Data':
    'prefix': 'TargetType.Data'
    'body': 'TargetType.Data'
    'description' : ''
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'TargetType.Interaction':
    'prefix': 'TargetType.Interaction'
    'body': 'TargetType.Interaction'
    'description' : ''
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'TargetType.Hackable':
    'prefix': 'TargetType.Hackable'
    'body': 'TargetType.Hackable'
    'description' : ''
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'TargetType.Character':
    'prefix': 'TargetType.Character'
    'body': 'TargetType.Character'
    'description' : ''
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'NotificationType.sms':
    'prefix': 'NotificationType.sms'
    'body': 'NotificationType.sms'
    'description' : ''
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'NotificationType.generic':
    'prefix': 'NotificationType.generic'
    'body': 'NotificationType.generic'
    'description' : 'Generic notification'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'NotificationType.message':
    'prefix': 'NotificationType.message'
    'body': 'NotificationType.message'
    'description' : 'Communicatiosn message'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'NotificationType.download':
    'prefix': 'NotificationType.download'
    'body': 'NotificationType.download'
    'description' : 'Receicing files'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'NotificationType.newObjective':
    'prefix': 'NotificationType.newObjective'
    'body': 'NotificationType.newObjective'
    'description' : ''
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'NotificationType.completedObjective':
    'prefix': 'NotificationType.completedObjective'
    'body': 'NotificationType.completedObjective'
    'description' : ''
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'PopupType.generic':
    'prefix': 'PopupType.generic'
    'body': 'PopupType.generic'
    'description' : 'A generic popup'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'PopupType.message':
    'prefix': 'PopupType.message'
    'body': 'PopupType.message'
    'description' : 'A message to the player'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'PopupType.warning':
    'prefix': 'PopupType.warning'
    'body': 'PopupType.warning'
    'description' : 'A warning to the player'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'PopupType.download':
    'prefix': 'PopupType.download'
    'body': 'PopupType.download'
    'description' : 'Begin a timed download window'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''

  'PopupType.progress':
    'prefix': 'PopupType.progress'
    'body': 'PopupType.progress'
    'description' : 'Trigger a progress bar'
    'rightLabelHTML': '
Off Grid
'
    'descriptionMoreURL' : ''
```
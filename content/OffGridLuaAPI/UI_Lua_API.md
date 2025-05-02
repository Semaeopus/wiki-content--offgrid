# UI_Lua_API

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=UI_Lua_API*

*Scraped on: 2025-05-02 18:38:28*

## Contents
* *1UI**1.1Description**1.2Functions**1.2.1ToggleClock**1.2.2ToggleWeather**1.2.3SetDataViewState**1.2.4ToggleDebugUI**1.2.5OpenRemoteConnection**1.2.6SetRadialScanState**1.2.7ToggleUIMarkers**1.2.8ShowHint**1.2.9ShowModalMessage**1.2.10ShowPopUp**1.2.11ShowNotification*
# UI
## Description
The UI API allows modders to control UI elements of the game
## Functions
### ToggleClock
```
UI.ToggleClock(state)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| state | bool |
**Description**: Toggles the clock hud element
**Returns**: Nothing
### ToggleWeather
```
UI.ToggleWeather(state)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| state | bool |
**Description**: Toggles the weather hud element
**Returns**: Nothing
### SetDataViewState
```
UI.SetDataViewState(state)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| state | bool |
**Description**: Sets the state of the data view
**Returns**: Nothing
**Notes**: This can be used for dramatic effect when certain story elements trigger
### ToggleDebugUI
```
UI.ToggleDebugUI(state)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| state | bool |
**Description**: Toggles the developer debug UI
**Returns**: Nothing
**Tip**: This can be helpful for debugging your mods!
### OpenRemoteConnection
```
UI.OpenRemoteConnection(missionObject)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| missionObject | MissionObject |
**Description**: Opens SSH connection to currently targeted device
**Returns**: Nothing
### SetRadialScanState
```
UI.SetRadialScanState(shouldScan)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| shouldScan | bool |
**Description**: Control if the radial menu should be scanning for targets
**Returns**: Nothing
### ToggleUIMarkers
```
UI.ToggleUIMarkers(state)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| state | bool |
**Description**: Show/Hide UI markers for hackable and interactable objects near the player.
**Returns**: Nothing
### ShowHint
```
UI.ShowHint(message, timeout)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| message | string |
| timeout | number (optional) |
**Description**: Displays a hint message. Multiple messages will stack on screen but don't go too crazy...
**Returns**: Nothing
**Tip**: These should mainly be used as additioanl help to the player, outside of the context of the game world.
### ShowModalMessage
```
UI.ShowModalMessage(luaMessage)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| luaMessage | Lua Table |
**Description**: Displays a modal, multiple calls to this will cause a stack of modals the user can click through
**Returns**: Nothing
**Tip**: These can be helpful to display story context and tutorialise hacking puzzles
### ShowPopUp
```
UI.ShowPopUp(type, header, message, timeout)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| type | OffGridPopup+PopupTypes |
| header | string |
| message | string |
| timeout | number (optional) |
**Description**: Displays a small pop up in the centre of the screen
**Returns**: Nothing
### ShowNotification
```
UI.ShowNotification(type, header, message, timeout)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| type | OffGridNotification+NotificationTypes |
| header | string |
| message | string |
| timeout | number (optional) |
**Description**: Displays a notification pop up in the top right corner of the screen
**Returns**: Nothing
This file is auto generated, please don't edit manually!
**Docs last hacked together on**: 23/07/2020 11:58
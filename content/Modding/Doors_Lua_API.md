# Doors_Lua_API

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Doors_Lua_API*

*Scraped on: 2025-05-02 18:39:17*

## Contents
* *1Doors**1.1Description**1.2Functions**1.2.1SetZoneKeys**1.2.2SetNetwork**1.2.3SetKeyOnDevice**1.2.4AssignKeyToCharacter**1.2.5Open**1.2.6Close**1.2.7Unlock**1.2.8Lock*
# Doors
## Description
API to control the logic of doors in the mission
## Functions
### SetZoneKeys
```
Doors.SetZoneKeys(zoneName, keyNames)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| zoneName | string |
| keyNames | Lua Table |
**Description**: Sets a key as unlocking a specific zone
**Returns**: Nothing
### SetNetwork
```
Doors.SetNetwork(networkName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| networkName | string |
**Description**: Sets the name of the network for the door system to use
**Returns**: Nothing
### SetKeyOnDevice
```
Doors.SetKeyOnDevice(keyName, deviceName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| keyName | string |
| deviceName | string |
**Description**: Sets a key as the current NFC file on a net device
**Returns**: Nothing
### AssignKeyToCharacter
```
Doors.AssignKeyToCharacter(keyName, character)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| keyName | string |
| character | Lua Type |
**Description**: Adds a key to a characters inventory and sets it as the characters current NFC data
**Returns**: Nothing
### Open
```
Doors.Open(doorID)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| doorID | string |
**Description**: Open the specified door.
**Returns**: Nothing
**Notes**: This call will not open a locked door. If the door is (or could potentially be) locked, call Unlock first to guarantee that it will open
### Close
```
Doors.Close(doorID)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| doorID | string |
**Description**: close the specified door.
**Returns**: Nothing
**Notes**: This will close the door regardless of is someone is in the way. Please contact Semaeopus Health & Safety if this is a problem.
### Unlock
```
Doors.Unlock(doorID)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| doorID | string |
**Description**: Unlock the specified door
**Returns**: Nothing
### Lock
```
Doors.Lock(doorID)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| doorID | string |
**Description**: Lock the specified door
**Returns**: Nothing
This file is auto generated, please don't edit manually!
**Docs last hacked together on**: 23/07/2020 11:58
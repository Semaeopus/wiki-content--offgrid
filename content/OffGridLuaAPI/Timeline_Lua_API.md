# Timeline_Lua_API

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Timeline_Lua_API*

*Scraped on: 2025-05-02 18:41:36*

## Contents
* *1Timeline**1.1Description**1.2Functions**1.2.1Play**1.2.2Pause**1.2.3Stop**1.2.4SetDynamicCameraTarget*
# Timeline
## Description
Allows controlling Timelines on MissionObjects
## Functions
### Play
```
Timeline.Play(missionObjectName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| missionObjectName | string |
**Description**: Starts the timeline
**Returns**: Nothing
### Pause
```
Timeline.Pause(missionObjectName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| missionObjectName | string |
**Description**: Pauses the timeline
**Returns**: Nothing
### Stop
```
Timeline.Stop(missionObjectName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| missionObjectName | string |
**Description**: Stops the timeline
**Returns**: Nothing
### SetDynamicCameraTarget
```
Timeline.SetDynamicCameraTarget(missionObjectName, targetName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| missionObjectName | string |
| targetName | string |
**Description**: Sets the look at & follow target for all dynamically targeted cameras in the timeline
**Returns**: Nothing
This file is auto generated, please don't edit manually!
**Docs last hacked together on**: 23/07/2020 11:58
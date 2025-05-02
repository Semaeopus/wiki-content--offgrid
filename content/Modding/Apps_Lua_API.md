# Apps_Lua_API

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Apps_Lua_API*

*Scraped on: 2025-05-02 18:40:51*

## Contents
* *1Apps**1.1Description**1.2Functions**1.2.1RequestAppState**1.3Global Functions**1.3.1SetState**1.3.2CreateStatusWindow**1.3.3RemoveStatusWindow**1.3.4DisplayStatusWindow**1.3.5UpdateStatusWindow**1.3.6SetStatusIcon**1.3.7SetStatusIconColor*
# Apps
## Description
The Apps API allows modders to control Apps
## Functions
### RequestAppState
```
Apps.RequestAppState(appName, newState)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| appName | string |
| newState | OffGridApp+AppStates |
**Description**: Ask an App to change it's state
**Returns**: Nothing
## Global Functions
### SetState
```
SetState(newState)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| newState | OffGridApp+AppStates |
**Description**: Sets the App's state.
**Returns**: Nothing
### CreateStatusWindow
```
CreateStatusWindow()
```
**Description**: Create the status window
**Returns**: Nothing
### RemoveStatusWindow
```
RemoveStatusWindow()
```
**Description**: Remove this app's status window
**Returns**: Nothing
### DisplayStatusWindow
```
DisplayStatusWindow(enabled)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| enabled | bool |
**Description**: Show or hide the app's status window.
**Returns**: Nothing
**Notes**: Make sure to to create the window first ;)
### UpdateStatusWindow
```
UpdateStatusWindow(text)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| text | string |
**Description**: Update the text content of the app's status window
**Returns**: Nothing
### SetStatusIcon
```
SetStatusIcon(id)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| id | number |
**Description**: Set the icon used for the app's status window
**Returns**: Nothing
**Notes**: ID should match with an image in your app definition's 'statusIcons' table.
### SetStatusIconColor
```
SetStatusIconColor(color)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| color | Lua Type |
**Description**: Set the color of the status window icon
**Returns**: Nothing
This file is auto generated, please don't edit manually!
**Docs last hacked together on**: 23/07/2020 11:58
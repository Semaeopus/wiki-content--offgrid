UI
==

Description
-----------

The UI API allows modders to control UI elements of the game

Functions
---------

### ToggleClock

``` lua
UI.ToggleClock(state)
```

**Expected parameter types**

| Name  | Type |
|-------|------|
| state | bool |

**Description**: Toggles the clock hud element

**Returns**: Nothing

### ToggleWeather

``` lua
UI.ToggleWeather(state)
```

**Expected parameter types**

| Name  | Type |
|-------|------|
| state | bool |

**Description**: Toggles the weather hud element

**Returns**: Nothing

### SetDataViewState

``` lua
UI.SetDataViewState(state)
```

**Expected parameter types**

| Name  | Type |
|-------|------|
| state | bool |

**Description**: Sets the state of the data view

**Returns**: Nothing

**Notes**: This can be used for dramatic effect when certain story
elements trigger

### OpenRemoteConnection

``` lua
UI.OpenRemoteConnection(missionObject)
```

**Expected parameter types**

| Name          | Type          |
|---------------|---------------|
| missionObject | MissionObject |

**Description**: Opens SSH connection to currently targeted device

**Returns**: Nothing

### ToggleUIMarkers

``` lua
UI.ToggleUIMarkers(state)
```

**Expected parameter types**

| Name  | Type |
|-------|------|
| state | bool |

**Description**: Show/Hide UI markers for hackable and interactable
objects near the player.

**Returns**: Nothing

### ShowHint

``` lua
UI.ShowHint(message, timeout)
```

**Expected parameter types**

| Name    | Type              |
|---------|-------------------|
| message | string            |
| timeout | number (optional) |

**Description**: Displays a hint message. Multiple messages will stack
on screen but don't go too crazy...

**Returns**: Nothing

`<span style="color:#009000">`{=html}**Tip**`</span>`{=html}: These
should mainly be used as additional help to the player, outside of the
context of the game world.

### ShowModalMessage

``` lua
UI.ShowModalMessage(luaMessage)
```

**Expected parameter types**

| Name       | Type      |
|------------|-----------|
| luaMessage | Lua Table |

**Description**: Displays a modal window with text filed, an optional
picture, confirm button & optional cancle button.

**Returns**: Nothing

### ShowPopup

``` lua
UI.ShowPopup(type, header, message, timeout)
```

**Expected parameter types**

| Name    | Type                    |
|---------|-------------------------|
| type    | OffGridPopup+PopupTypes |
| header  | string                  |
| message | string                  |
| timeout | number (optional)       |

**Description**: Displays a small popup window in the centre of the
screen

**Returns**: Nothing

### ShowNotification

``` lua
UI.ShowNotification(type, header, message, timeout)
```

**Expected parameter types**

| Name    | Type                                  |
|---------|---------------------------------------|
| type    | OffGridNotification+NotificationTypes |
| header  | string                                |
| message | string                                |
| timeout | number (optional)                     |

**Description**: Displays a notification popup in the top right corner
of the screen

**Returns**: Nothing

### ShowFileViewer

``` lua
UI.ShowFileViewer(fileName, dataTable)
```

**Expected parameter types**

| Name      | Type      |
|-----------|-----------|
| fileName  | string    |
| dataTable | Lua Table |

**Description**: Opens the FileViewer window with the given data as the
content

**Returns**: Nothing

### ShowPopupMenu

``` lua
UI.ShowPopupMenu(table)
```

**Expected parameter types**

| Name  | Type      |
|-------|-----------|
| table | Lua Table |

**Description**: Opens a popup menu with multiple options

**Returns**: Nothing

### ToggleTaskList

``` lua
UI.ToggleTaskList(state)
```

**Expected parameter types**

| Name  | Type |
|-------|------|
| state | bool |

**Description**: Toggles the TaskList HUD element

**Returns**: Nothing

### ToggleTargeting

``` lua
UI.ToggleTargeting(state)
```

**Expected parameter types**

| Name  | Type |
|-------|------|
| state | bool |

**Description**: Toggles the Target selection HUD element

**Returns**: Nothing

### ToggleTCrosshair

``` lua
UI.ToggleTCrosshair(state)
```

**Expected parameter types**

| Name  | Type |
|-------|------|
| state | bool |

**Description**: Toggles the Crosshairs HUD element

**Returns**: Nothing

This file is auto generated, please don't edit manually!

**Docs last hacked together on**: 09/12/2024 12:54

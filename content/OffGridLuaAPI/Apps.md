Apps
====

Description
-----------

The Apps API allows modders to control Apps

Functions
---------

### RequestAppState

``` lua
Apps.RequestAppState(apps, newState)
```

**Expected parameter types**

| Name     | Type                 |
|----------|----------------------|
| apps     | Lua Type             |
| newState | OffGridApp+AppStates |

**Description**: Ask an App to change it's state

**Returns**: Nothing

### SetDefaultApps

``` lua
Apps.SetDefaultApps(apps)
```

**Expected parameter types**

| Name | Type     |
|------|----------|
| apps | Lua Type |

**Description**: Sets the player's apps (if there is no save data wiht
player app config, or if mission is set to override player's apps)

**Returns**: Nothing

### Console\_OutputLine

``` lua
Apps.Console_OutputLine(appName, outputString)
```

**Expected parameter types**

| Name         | Type   |
|--------------|--------|
| appName      | string |
| outputString | string |

**Description**: Output a line to the terminal UI

**Returns**: Nothing

Global Functions [global_functions]
----------------

### SetState

``` lua
SetState(newState)
```

**Expected parameter types**

| Name     | Type                 |
|----------|----------------------|
| newState | OffGridApp+AppStates |

**Description**: Sets the App's state.

**Returns**: Nothing

### CreateStatusWindow

``` lua
CreateStatusWindow()
```

**Description**: Create the status window

**Returns**: Nothing

### RemoveStatusWindow

``` lua
RemoveStatusWindow()
```

**Description**: Remove this app's status window

**Returns**: Nothing

### DisplayStatusWindow

``` lua
DisplayStatusWindow(enabled)
```

**Expected parameter types**

| Name    | Type |
|---------|------|
| enabled | bool |

**Description**: Show or hide the app's status window.

**Returns**: Nothing

**Notes**: Make sure to to create the window first ;)

### UpdateStatusWindow

``` lua
UpdateStatusWindow(text)
```

**Expected parameter types**

| Name | Type   |
|------|--------|
| text | string |

**Description**: Update the text content of the app's status window

**Returns**: Nothing

### SetStatusIcon

``` lua
SetStatusIcon(id)
```

**Expected parameter types**

| Name | Type   |
|------|--------|
| id   | number |

**Description**: Set the icon used for the app's status window

**Returns**: Nothing

**Notes**: ID should match with an image in your app definition's
'statusIcons' table.

### SetStatusIconColor

``` lua
SetStatusIconColor(color)
```

**Expected parameter types**

| Name  | Type     |
|-------|----------|
| color | Lua Type |

**Description**: Set the color of the status window icon

**Returns**: Nothing

### CreateAppWindow

``` lua
CreateAppWindow(title, backgroundImagePath)
```

**Expected parameter types**

| Name                | Type   |
|---------------------|--------|
| title               | string |
| backgroundImagePath | string |

**Description**: Initialize the AppWindow for this App

**Returns**: Nothing

### RemoveAppWindow

``` lua
RemoveAppWindow()
```

**Description**: Reset the AppWindow

**Returns**: Nothing

### ShowAppWindow

``` lua
ShowAppWindow()
```

**Description**: Make the AppWindow visible (rember to create the window
first!)

**Returns**: Nothing

### HideAppWindow

``` lua
HideAppWindow()
```

**Description**: Hide the app window.

**Returns**: Nothing

### SetAppWindowContent

``` lua
SetAppWindowContent(content)
```

**Expected parameter types**

| Name    | Type   |
|---------|--------|
| content | string |

**Description**: Set the content text of the AppWindow

**Returns**: Nothing

### ShowAppWindowProgress

``` lua
ShowAppWindowProgress(display)
```

**Expected parameter types**

| Name    | Type |
|---------|------|
| display | bool |

**Description**: Show (or hide) a progress bar on the AppWindow

**Returns**: Nothing

### SetAppWindowProgress

``` lua
SetAppWindowProgress(progress)
```

**Expected parameter types**

| Name     | Type   |
|----------|--------|
| progress | number |

**Description**: Set the progres on the AppWindow progress bar (remember
to use 'ShowAppWindowProgress(true)' first to enable it!)

**Returns**: Nothing

### StartLuaCoroutine

``` lua
StartLuaCoroutine(dynValue)
```

**Expected parameter types**

| Name     | Type     |
|----------|----------|
| dynValue | Lua Type |

**Description**: ...

**Returns**: Nothing

This file is auto generated, please don't edit manually!

**Docs last hacked together on**: 09/12/2024 12:54

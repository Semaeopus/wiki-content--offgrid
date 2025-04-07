Debug
=====

Description
-----------

Debugging & Testing tools

Functions
---------

### DevModeEnabled

``` lua
Debug.DevModeEnabled()
```

**Description**: Check if the game is currently in Dev mode.

**Returns**: bool

### ConnectToDevLaptop

``` lua
Debug.ConnectToDevLaptop()
```

**Description**: Open SSH connection to DevLaptop Device, if there's one
in the level.

**Returns**: Nothing

### ConnectToDevice

``` lua
Debug.ConnectToDevice(name)
```

**Expected parameter types**

| Name | Type   |
|------|--------|
| name | string |

**Description**: Open SSH connection to specified device, if it can be
found in the level.

**Returns**: Nothing

### TeleportPlayer

``` lua
Debug.TeleportPlayer(spawnPointName)
```

**Expected parameter types**

| Name           | Type   |
|----------------|--------|
| spawnPointName | string |

**Description**: Teleport player to a SpawnPoint in level.

**Returns**: Nothing

### ShowPlayerPath

``` lua
Debug.ShowPlayerPath(value)
```

**Expected parameter types**

| Name  | Type |
|-------|------|
| value | bool |

**Description**: ShowPlayerPath

**Returns**: Nothing

This file is auto generated, please don't edit manually!

**Docs last hacked together on**: 09/12/2024 12:54

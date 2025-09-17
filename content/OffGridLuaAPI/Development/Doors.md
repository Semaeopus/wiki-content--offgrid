Doors
=====

Description
-----------

API to control the logic of doors in the mission

Functions
---------

### SetZoneKeys

``` lua
Doors.SetZoneKeys(zoneName, keyNames)
```

**Expected parameter types**

| Name     | Type      |
|----------|-----------|
| zoneName | string    |
| keyNames | Lua Table |

**Description**: Sets a key as unlocking a specific zone

**Returns**: Nothing

### SetNetwork

``` lua
Doors.SetNetwork(networkName)
```

**Expected parameter types**

| Name        | Type   |
|-------------|--------|
| networkName | string |

**Description**: Sets the name of the network for the door system to use

**Returns**: Nothing

### SetKeyOnDevice

``` lua
Doors.SetKeyOnDevice(keyName, deviceName)
```

**Expected parameter types**

| Name       | Type   |
|------------|--------|
| keyName    | string |
| deviceName | string |

**Description**: Sets a key as the current NFC file on a net device

**Returns**: Nothing

### AssignKeyToCharacter

``` lua
Doors.AssignKeyToCharacter(keyName, character)
```

**Expected parameter types**

| Name      | Type     |
|-----------|----------|
| keyName   | string   |
| character | Lua Type |

**Description**: Adds a key to a characters inventory and sets it as the
characters current NFC data

**Returns**: Nothing

### Open

``` lua
Doors.Open(doorID)
```

**Expected parameter types**

| Name   | Type   |
|--------|--------|
| doorID | string |

**Description**: Open the specified door.

**Returns**: Nothing

**Notes**: This call will not open a locked door. If the door is (or
could potentially be) locked, call Unlock first to guarantee that it
will open

### Close

``` lua
Doors.Close(doorID)
```

**Expected parameter types**

| Name   | Type   |
|--------|--------|
| doorID | string |

**Description**: close the specified door.

**Returns**: Nothing

**Notes**: This will close the door regardless of is someone is in the
way. Please contact Semaeopus Health & Safety if this is a problem.

### Unlock

``` lua
Doors.Unlock(doorID)
```

**Expected parameter types**

| Name   | Type   |
|--------|--------|
| doorID | string |

**Description**: Unlock the specified door

**Returns**: Nothing

### Lock

``` lua
Doors.Lock(doorID)
```

**Expected parameter types**

| Name   | Type   |
|--------|--------|
| doorID | string |

**Description**: Lock the specified door

**Returns**: Nothing

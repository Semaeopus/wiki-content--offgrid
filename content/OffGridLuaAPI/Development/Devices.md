Devices
=======

Description
-----------

The Devices API is used to control the behavior of provided devices in
the level kit each of these calls will have a slightly different
response to each of these calls. Please see the devices page for a full
break down.

Functions
---------

### SetPower

``` lua
Devices.SetPower(deviceName, state)
```

**Expected parameter types**

| Name       | Type   |
|------------|--------|
| deviceName | string |
| state      | bool   |

**Description**: Change the powered on state of the device

**Returns**: Nothing

**Notes**: See provided devices page to see how each device handles this
call

### TogglePower

``` lua
Devices.TogglePower(deviceName)
```

**Expected parameter types**

| Name       | Type   |
|------------|--------|
| deviceName | string |

**Description**: Flip the powered on state of the device

**Returns**: Nothing

**Notes**: See provided devices page to see how each device handles this
call

### GetPower

``` lua
Devices.GetPower(deviceName)
```

**Expected parameter types**

| Name       | Type   |
|------------|--------|
| deviceName | string |

**Description**: Get the powered on state of the device

**Returns**: If the device is currently powered on

### SetActive

``` lua
Devices.SetActive(deviceName, state)
```

**Expected parameter types**

| Name       | Type   |
|------------|--------|
| deviceName | string |
| state      | bool   |

**Description**: Change the active state of the device

**Returns**: Nothing

**Notes**: See provided devices page to see how each device handles this
call

### ToggleActive

``` lua
Devices.ToggleActive(deviceName)
```

**Expected parameter types**

| Name       | Type   |
|------------|--------|
| deviceName | string |

**Description**: Flip the active state of the device

**Returns**: Nothing

**Notes**: See provided devices page to see how each device handles this
call

### GetActive

``` lua
Devices.GetActive(deviceName)
```

**Expected parameter types**

| Name       | Type   |
|------------|--------|
| deviceName | string |

**Description**: Get the active state of the device

**Returns**: If the device is currently active

### RunOnce

``` lua
Devices.RunOnce(deviceName)
```

**Expected parameter types**

| Name       | Type   |
|------------|--------|
| deviceName | string |

**Description**: Trigger a single update of the device

**Returns**: Nothing

**Notes**: See provided devices page to see how each device handles this
call

### SetAmok

``` lua
Devices.SetAmok(deviceName, state)
```

**Expected parameter types**

| Name       | Type   |
|------------|--------|
| deviceName | string |
| state      | bool   |

**Description**: Begin an 'Amok' state, cause the device to act in an
unstable/broken manor

**Returns**: Nothing

**Notes**: See provided devices page to see how each device handles this
call

### ToggleAmok

``` lua
Devices.ToggleAmok(deviceName)
```

**Expected parameter types**

| Name       | Type   |
|------------|--------|
| deviceName | string |

**Description**: Flip the amok state

**Returns**: Nothing

**Notes**: See provided devices page to see how each device handles this
call

### GetAmok

``` lua
Devices.GetAmok(deviceName)
```

**Expected parameter types**

| Name       | Type   |
|------------|--------|
| deviceName | string |

**Description**: Get the 'Amok' state of the device

**Returns**: If the device is currently running 'Amok'

### SetValue

``` lua
Devices.SetValue(deviceName, newValue)
```

**Expected parameter types**

| Name       | Type   |
|------------|--------|
| deviceName | string |
| newValue   | string |

**Description**: Pass a string value to the device

**Returns**: Nothing

**Notes**: See provided devices page to see how each device handles this
call

### GetValue

``` lua
Devices.GetValue(deviceName)
```

**Expected parameter types**

| Name       | Type   |
|------------|--------|
| deviceName | string |

**Description**: Get the current value of the device

**Returns**: The value of the device

### GetDataInventory

``` lua
Devices.GetDataInventory(deviceName, index)
```

**Expected parameter types**

| Name       | Type   |
|------------|--------|
| deviceName | string |
| index      | number |

**Description**: Get the description of the data at this index in the
DataInventory

**Returns**: A description of that piece of data

### GetDataPointFromInventory

``` lua
Devices.GetDataPointFromInventory(deviceName, index)
```

**Expected parameter types**

| Name       | Type   |
|------------|--------|
| deviceName | string |
| index      | number |

**Description**: Get a table of useful data from the DataPoint at this
index in the DataInventory

**Returns**: A description of that piece of data

### GetDataInventoryCount

``` lua
Devices.GetDataInventoryCount(deviceName)
```

**Expected parameter types**

| Name       | Type   |
|------------|--------|
| deviceName | string |

**Description**: Get the number of DataPoints in the DataInventory of
this device

**Returns**: The number of DataPoints

### CheckPlayerAccess

``` lua
Devices.CheckPlayerAccess(deviceName)
```

**Expected parameter types**

| Name       | Type   |
|------------|--------|
| deviceName | string |

**Description**: Check if the PLayer has access to a Device

**Returns**: Device access type

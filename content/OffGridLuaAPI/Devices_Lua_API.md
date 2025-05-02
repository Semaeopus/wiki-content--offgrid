# Devices_Lua_API

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Devices_Lua_API*

*Scraped on: 2025-05-02 18:41:33*

## Contents
* *1Devices**1.1Description**1.2Functions**1.2.1SetPower**1.2.2TogglePower**1.2.3GetPower**1.2.4SetActive**1.2.5ToggleActive**1.2.6GetActive**1.2.7RunOnce**1.2.8SetAmok**1.2.9ToggleAmok**1.2.10GetAmok**1.2.11SetValue**1.2.12GetValue**1.2.13GetDataInventory**1.2.14GetDataPointFromInventory**1.2.15GetDataInventoryCount*
# Devices
## Description
The Devices API is used to control the behavior of provided devices in the level kit each of these calls will have a slightly different response to each of these calls.
					Please see the devices page for a full break down.
## Functions
### SetPower
```
Devices.SetPower(deviceName, state)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
| state | bool |
**Description**: Change the powered on state of the device
**Returns**: Nothing
**Notes**: See provided devices page to see how each device handles this call
### TogglePower
```
Devices.TogglePower(deviceName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
**Description**: Flip the powered on state of the device
**Returns**: Nothing
**Notes**: See provided devices page to see how each device handles this call
### GetPower
```
Devices.GetPower(deviceName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
**Description**: Get the powered on state of the device
**Returns**: If the device is currently powered on
### SetActive
```
Devices.SetActive(deviceName, state)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
| state | bool |
**Description**: Change the active state of the device
**Returns**: Nothing
**Notes**: See provided devices page to see how each device handles this call
### ToggleActive
```
Devices.ToggleActive(deviceName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
**Description**: Flip the active state of the device
**Returns**: Nothing
**Notes**: See provided devices page to see how each device handles this call
### GetActive
```
Devices.GetActive(deviceName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
**Description**: Get the active state of the device
**Returns**: If the device is currently active
### RunOnce
```
Devices.RunOnce(deviceName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
**Description**: Trigger a single update of the device
**Returns**: Nothing
**Notes**: See provided devices page to see how each device handles this call
### SetAmok
```
Devices.SetAmok(deviceName, state)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
| state | bool |
**Description**: Begin an 'Amok' state, cause the device to act in an unstable/broken manor
**Returns**: Nothing
**Notes**: See provided devices page to see how each device handles this call
### ToggleAmok
```
Devices.ToggleAmok(deviceName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
**Description**: Flip the amok state
**Returns**: Nothing
**Notes**: See provided devices page to see how each device handles this call
### GetAmok
```
Devices.GetAmok(deviceName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
**Description**: Get the 'Amok' state of the device
**Returns**: If the device is currently running 'Amok'
### SetValue
```
Devices.SetValue(deviceName, newValue)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
| newValue | string |
**Description**: Pass a string value to the device
**Returns**: Nothing
**Notes**: See provided devices page to see how each device handles this call
### GetValue
```
Devices.GetValue(deviceName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
**Description**: Get the current value of the device
**Returns**: The value of the device
### GetDataInventory
```
Devices.GetDataInventory(deviceName, index)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
| index | number |
**Description**: Get the description of the data at this index in the DataInventory
**Returns**: A description of that piece of data
### GetDataPointFromInventory
```
Devices.GetDataPointFromInventory(deviceName, index)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
| index | number |
**Description**: Get a table of useful data from the DataPoint at this index in the DataInventory
**Returns**: A description of that piece of data
### GetDataInventoryCount
```
Devices.GetDataInventoryCount(deviceName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| deviceName | string |
**Description**: Get the number of DataPoints in the DataInventory of this device
**Returns**: The number of DataPoints
This file is auto generated, please don't edit manually!
**Docs last hacked together on**: 23/07/2020 11:58
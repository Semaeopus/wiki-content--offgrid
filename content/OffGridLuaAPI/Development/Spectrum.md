Spectrum
========

Description
-----------

The Spectrum api allows the manipulation of data points within the game
world

Functions
---------

### DeleteDataPoint

``` lua
Spectrum.DeleteDataPoint(dataPoint)
```

**Expected parameter types**

| Name      | Type      |
|-----------|-----------|
| dataPoint | DataPoint |

**Description**: Deletes the passed in data point

**Returns**: Nothing

### SaveDataPoint

``` lua
Spectrum.SaveDataPoint(dataPoint)
```

**Expected parameter types**

| Name      | Type      |
|-----------|-----------|
| dataPoint | DataPoint |

**Description**: Saves currently targeted data point to the players data
inventory

**Returns**: Nothing

### FilterClear

``` lua
Spectrum.FilterClear()
```

**Description**: Clear the Filter

**Returns**: Nothing

### FilterType (int, bool) [filtertype_int_bool]

``` lua
Spectrum.FilterType (int, bool)(t, on)
```

**Expected parameter types**

| Name | Type   |
|------|--------|
| t    | number |
| on   | bool   |

**Description**: Filter which types of Data Spectrum shows

**Returns**: Nothing

### FilterCreator

``` lua
Spectrum.FilterCreator(creator)
```

**Expected parameter types**

| Name    | Type      |
|---------|-----------|
| creator | DataPoint |

**Description**: Shows only Data from the Creator of the specified
DataPoint. Pass nil to clear

**Returns**: Nothing

### FilterNetwork

``` lua
Spectrum.FilterNetwork(network)
```

**Expected parameter types**

| Name    | Type      |
|---------|-----------|
| network | DataPoint |

**Description**: Shows only Data from the Network of the specified
DataPoint. Pass nil to clear

**Returns**: Nothing

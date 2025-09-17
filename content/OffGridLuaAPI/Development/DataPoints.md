DataPoints
==========

Description
-----------

The DataPoints API returns and manage the wanted available data points

Functions
---------

### GetAllDataPoints

``` lua
DataPoints.GetAllDataPoints()
```

**Description**: Return all the data points that are currently in the
level

**Returns**: System.Collections.Generic.List\`1\[DataPoint\]

### GetObjectDataPoints

``` lua
DataPoints.GetObjectDataPoints(objectName)
```

**Expected parameter types**

| Name       | Type   |
|------------|--------|
| objectName | string |

**Description**: Return all the data points received by an object or a
character

**Returns**: System.Collections.Generic.List\`1\[DataPoint\]

### FilterNetwork

``` lua
DataPoints.FilterNetwork(dataPoints, networkName)
```

**Expected parameter types**

| Name        | Type                                            |
|-------------|-------------------------------------------------|
| dataPoints  | System.Collections.Generic.List\`1\[DataPoint\] |
| networkName | string                                          |

**Description**: Filter data points with the network name

**Returns**: System.Collections.Generic.List\`1\[DataPoint\]

### FilterDataType

``` lua
DataPoints.FilterDataType(dataPoints, dataType)
```

**Expected parameter types**

| Name       | Type                                            |
|------------|-------------------------------------------------|
| dataPoints | System.Collections.Generic.List\`1\[DataPoint\] |
| dataType   | string                                          |

**Description**: Filter data points with the data type

**Returns**: System.Collections.Generic.List\`1\[DataPoint\]

### DeleteDataPoints

``` lua
DataPoints.DeleteDataPoints(dataPoints)
```

**Expected parameter types**

| Name       | Type                                            |
|------------|-------------------------------------------------|
| dataPoints | System.Collections.Generic.List\`1\[DataPoint\] |

**Description**: Remove data points from the level

**Returns**: Nothing

### GetData

``` lua
DataPoints.GetData(dataPoints)
```

**Expected parameter types**

| Name       | Type                                            |
|------------|-------------------------------------------------|
| dataPoints | System.Collections.Generic.List\`1\[DataPoint\] |

**Description**: Return all the data string from the given data points

**Returns**: System.String\[\]

### GetDataPointInfo

``` lua
DataPoints.GetDataPointInfo(dataPoints)
```

**Expected parameter types**

| Name       | Type                                            |
|------------|-------------------------------------------------|
| dataPoints | System.Collections.Generic.List\`1\[DataPoint\] |

**Description**: Return all the data info from the given data points

**Returns**: System.Collections.Generic.List\`1\[DataPointInfo\]

### AddToPlayerInventory

``` lua
DataPoints.AddToPlayerInventory(dataFile)
```

**Expected parameter types**

| Name     | Type          |
|----------|---------------|
| dataFile | DataPointInfo |

**Description**: Save native data object (DataPointInfo) into the
players inventory

**Returns**: Nothing

### RemoveFromPlayerInventory

``` lua
DataPoints.RemoveFromPlayerInventory(dataFile)
```

**Expected parameter types**

| Name     | Type          |
|----------|---------------|
| dataFile | DataPointInfo |

**Description**: Remove native data object (DataPointInfo) from the
players inventory

**Returns**: Nothing

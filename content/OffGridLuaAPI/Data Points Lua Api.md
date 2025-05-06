# Data_Points_Lua_Api

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Data_Points_Lua_Api*

*Scraped on: 2025-05-02 18:43:13*

# DataPoints
## Description
The DataPoints API returns and manage the wanted available data points
## Functions
### GetAllDataPoints
```
DataPoints.GetAllDataPoints()
```


**Description**: Return all the data points that are currently in the level
**Returns**: System.Collections.Generic.List`1[DataPoint]
### GetObjectDataPoints
```
DataPoints.GetObjectDataPoints(objectName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| objectName | string |


**Description**: Return all the data points received by an object or a character
**Returns**: System.Collections.Generic.List`1[DataPoint]
### FilterNetwork
```
DataPoints.FilterNetwork(dataPoints, networkName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| dataPoints | System.Collections.Generic.List`1[DataPoint] |
| networkName | string |


**Description**: Filter data points with the network name
**Returns**: System.Collections.Generic.List`1[DataPoint]
### FilterDataType
```
DataPoints.FilterDataType(dataPoints, dataType)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| dataPoints | System.Collections.Generic.List`1[DataPoint] |
| dataType | string |

**Description**: Filter data points with the data type
**Returns**: System.Collections.Generic.List`1[DataPoint]
### DeleteDataPoints
```
DataPoints.DeleteDataPoints(dataPoints)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| dataPoints | System.Collections.Generic.List`1[DataPoint] |

**Description**: Remove data points from the level
**Returns**: Nothing
### GetData
```
DataPoints.GetData(dataPoints)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| dataPoints | System.Collections.Generic.List`1[DataPoint] |

**Description**: Return all the data string from the given data points
**Returns**: System.String[]
### GetDataPointInfo
```
DataPoints.GetDataPointInfo(dataPoints)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| dataPoints | System.Collections.Generic.List`1[DataPoint] |

**Description**: Return all the data info from the given data points
**Returns**: System.Collections.Generic.List`1[DataPointInfo]
### PlayersInventorySave
```
DataPoints.PlayersInventorySave(dataFile)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| dataFile | DataPointInfo |

**Description**: Save data info in the the players inventory
**Returns**: Nothing
### PlayersInventoryRemove
```
DataPoints.PlayersInventoryRemove(dataFile)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| dataFile | DataPointInfo |

**Description**: Save data info in the the players inventory
**Returns**: Nothing

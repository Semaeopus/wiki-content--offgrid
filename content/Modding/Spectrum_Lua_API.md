# Spectrum_Lua_API

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Spectrum_Lua_API*

*Scraped on: 2025-05-02 18:42:42*

## Contents
* *1Spectrum**1.1Description**1.2Functions**1.2.1DeleteDataPoint**1.2.2SaveDataPoint**1.2.3FilterClear**1.2.4FilterType (int, bool)**1.2.5FilterCreator**1.2.6FilterNetwork*
# Spectrum
## Description
The Spectrum api allows the manipulation of data points within the game world
## Functions
### DeleteDataPoint
```
Spectrum.DeleteDataPoint(dataPoint)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| dataPoint | DataPoint |
**Description**: Deletes the passed in data point
**Returns**: Nothing
### SaveDataPoint
```
Spectrum.SaveDataPoint(dataPoint)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| dataPoint | DataPoint |
**Description**: Saves currently targeted data point to the players data inventory
**Returns**: Nothing
### FilterClear
```
Spectrum.FilterClear()
```
**Description**: Clear the Filter
**Returns**: Nothing
### FilterType (int, bool)
```
Spectrum.FilterType (int, bool)(t, on)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| t | number |
| on | bool |
**Description**: Filter which types of Data Spectrum shows
**Returns**: Nothing
### FilterCreator
```
Spectrum.FilterCreator(creator)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| creator | DataPoint |
**Description**: Shows only Data from the Creator of the specified DataPoint. Pass nil to clear
**Returns**: Nothing
### FilterNetwork
```
Spectrum.FilterNetwork(network)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| network | DataPoint |
**Description**: Shows only Data from the Network of the specified DataPoint. Pass nil to clear
**Returns**: Nothing
This file is auto generated, please don't edit manually!
**Docs last hacked together on**: 23/07/2020 11:58
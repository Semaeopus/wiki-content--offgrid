# Scheduler_Lua_API

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Scheduler_Lua_API*

*Scraped on: 2025-05-02 18:38:50*

# Scheduler
## Description
The Scheduler api allows users to Schedule callback events based on specific time values
## Functions
### CallInSecsReal
```
Scheduler.CallInSecsReal(func, timeInSecs)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| func | Lua Type |
| timeInSecs | number |

**Description**: Schedule a lua function to be called in timeInSecs real time
**Returns**: The id of the scheduled event
### CallInSecs
```
Scheduler.CallInSecs(func, timeInSecs)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| func | Lua Type |
| timeInSecs | number |

**Description**: Schedule a lua function to be called in timeInSecs scaled time
**Returns**: The id of the scheduled event
### CallAtTime
```
Scheduler.CallAtTime(func, dateTimeString)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| func | Lua Type |
| dateTimeString | string |

**Description**: Schedule a lua function to be called at specific time (defined by a date/time string)
**Returns**: The id of the scheduled event
Scheduler
=========

Description
-----------

The Scheduler api allows users to Schedule callback events based on
specific time values

Functions
---------

### CallInSecsReal

``` lua
Scheduler.CallInSecsReal(func, timeInSecs)
```

**Expected parameter types**

| Name       | Type     |
|------------|----------|
| func       | Lua Type |
| timeInSecs | number   |

**Description**: Schedule a lua function to be called after timeInSecs
in real time (counting time even if the game is paused, in a menu, or in
conversation etc)

**Returns**: The id of the scheduled event

### CallInSecs

``` lua
Scheduler.CallInSecs(func, timeInSecs)
```

**Expected parameter types**

| Name       | Type     |
|------------|----------|
| func       | Lua Type |
| timeInSecs | number   |

**Description**: Schedule a lua function to be called after timeInSecs
in game time (time doens't count when the game is paused)

**Returns**: The id of the scheduled event

### CallAtTime

``` lua
Scheduler.CallAtTime(func, dateTimeString)
```

**Expected parameter types**

| Name           | Type     |
|----------------|----------|
| func           | Lua Type |
| dateTimeString | string   |

**Description**: Schedule a lua function to be called at specific time
(defined by a date/time string formatted as dd/MM/yyyy/HH:mm)

**Returns**: The id of the scheduled event

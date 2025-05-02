Sound
=====

Description
-----------

The sound API allows modders to trigger sound events in game

Functions
---------

### TriggerEvent

``` lua
Sound.TriggerEvent(eventName, sourceName)
```

**Expected parameter types**

| Name       | Type   |
|------------|--------|
| eventName  | string |
| sourceName | string |

**Description**: Triggers a sound even with name *eventName*

**Returns**: The event id, this can be used in other sound API functions
(see [StopAudio](#StopAudio "wikilink"))

**Notes**: If \_sourceName\_ is not provided the sound will be played as
a '2D' event

### SetRTPC

``` lua
Sound.SetRTPC(sourceName, RTPCName, value)
```

**Expected parameter types**

| Name       | Type   |
|------------|--------|
| sourceName | string |
| RTPCName   | string |
| value      | number |

**Description**: Set Real-Time Parameter Curve for an audio event
playign on this object

**Returns**: Nothing

**Notes**: You need to have started an audio event on this object before
tryign to use SetRTPC, and that event must have RTPC control for
something.

This file is auto generated, please don't edit manually!

**Docs last hacked together on**: 09/12/2024 12:54

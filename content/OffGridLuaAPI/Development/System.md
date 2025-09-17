System
======

Description
-----------

System API provides access to game settings and other generic system
features

Functions
---------

### SetLanguage

``` lua
System.SetLanguage(langCode)
```

**Expected parameter types**

| Name     | Type   |
|----------|--------|
| langCode | string |

**Description**: Sets the game language

**Returns**: Nothing

### GetCurrentInputMethod

``` lua
System.GetCurrentInputMethod()
```

**Description**: Checks what kind of input method was last used

**Returns**: string, either 'keyboard' or 'gamepad'

**Notes**: Use this to change hint messages etc. tutorialization based
on current input device

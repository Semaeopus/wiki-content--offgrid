Animator
========

Description
-----------

Allows the user to set properties of a mission objects Unity animator

`                   The animator allows users to set key keyframe-able animations to control a large amount of components.`  
`                   See `[`https://docs.unity3d.com/Manual/class-Animator.html`` ``Unity's`` ``documentation`](https://docs.unity3d.com/Manual/class-Animator.html_Unity's_documentation "wikilink")` for more details`

Functions
---------

### SetBool

``` lua
Animator.SetBool(missionObjectName, parameterName, value)
```

**Expected parameter types**

| Name              | Type   |
|-------------------|--------|
| missionObjectName | string |
| parameterName     | string |
| value             | bool   |

**Description**: Sets a bool parameter by name

**Returns**: Nothing

### SetFloat

``` lua
Animator.SetFloat(missionObjectName, parameterName, value)
```

**Expected parameter types**

| Name              | Type   |
|-------------------|--------|
| missionObjectName | string |
| parameterName     | string |
| value             | number |

**Description**: Sets a float parameter by name

**Returns**: Nothing

### SetInt

``` lua
Animator.SetInt(missionObjectName, parameterName, value)
```

**Expected parameter types**

| Name              | Type   |
|-------------------|--------|
| missionObjectName | string |
| parameterName     | string |
| value             | number |

**Description**: Sets a int parameter by name

**Returns**: Nothing

### SetTrigger

``` lua
Animator.SetTrigger(missionObjectName, parameterName)
```

**Expected parameter types**

| Name              | Type   |
|-------------------|--------|
| missionObjectName | string |
| parameterName     | string |

**Description**: Begins a trigger parameter by name

**Returns**: Nothing

### GetBool

``` lua
Animator.GetBool(missionObjectName, parameterName)
```

**Expected parameter types**

| Name              | Type   |
|-------------------|--------|
| missionObjectName | string |
| parameterName     | string |

**Description**: Gets the current value of a bool parameter by name

**Returns**: The current bool value of the parameter

### GetFloat

``` lua
Animator.GetFloat(missionObjectName, parameterName)
```

**Expected parameter types**

| Name              | Type   |
|-------------------|--------|
| missionObjectName | string |
| parameterName     | string |

**Description**: Gets the current value of a float parameter by name

**Returns**: The current float value of the parameter

### GetInt

``` lua
Animator.GetInt(missionObjectName, parameterName)
```

**Expected parameter types**

| Name              | Type   |
|-------------------|--------|
| missionObjectName | string |
| parameterName     | string |

**Description**: Gets the current value of a int parameter by name

**Returns**: The current int value of the parameter

This file is auto generated, please don't edit manually!

**Docs last hacked together on**: 09/12/2024 12:54

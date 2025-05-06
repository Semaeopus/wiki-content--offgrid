# Animator_Lua_API

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Animator_Lua_API*

*Scraped on: 2025-05-02 18:40:47*

# Animator
## Description
Allows the user to set properties of a mission objects Unity animator
					The animator allows users to set key keyframe-able animations to control a large amount of components.
					See [[Unity's documentation](https://web.archive.org/web/20200807130500/https://docs.unity3d.com/Manual/class-Animator.html)] for more details
## Functions
### SetBool
```
Animator.SetBool(missionObjectName, parameterName, value)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| missionObjectName | string |
| parameterName | string |
| value | bool |

**Description**: Sets a bool parameter by name
**Returns**: Nothing
### SetFloat
```
Animator.SetFloat(missionObjectName, parameterName, value)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| missionObjectName | string |
| parameterName | string |
| value | number |

**Description**: Sets a float parameter by name
**Returns**: Nothing
### SetInt
```
Animator.SetInt(missionObjectName, parameterName, value)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| missionObjectName | string |
| parameterName | string |
| value | number |

**Description**: Sets a int parameter by name
**Returns**: Nothing
### SetTrigger
```
Animator.SetTrigger(missionObjectName, parameterName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| missionObjectName | string |
| parameterName | string |

**Description**: Begins a trigger parameter by name
**Returns**: Nothing
### GetBool
```
Animator.GetBool(missionObjectName, parameterName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| missionObjectName | string |
| parameterName | string |

**Description**: Gets the current value of a bool parameter by name
**Returns**: The current bool value of the parameter
### GetFloat
```
Animator.GetFloat(missionObjectName, parameterName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| missionObjectName | string |
| parameterName | string |

**Description**: Gets the current value of a float parameter by name
**Returns**: The current float value of the parameter
### GetInt
```
Animator.GetInt(missionObjectName, parameterName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| missionObjectName | string |
| parameterName | string |

**Description**: Gets the current value of a int parameter by name
**Returns**: The current int value of the parameter

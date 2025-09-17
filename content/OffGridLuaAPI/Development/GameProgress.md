GameProgress
============

Description
-----------

The GameProgress api allows the modder to control and query the state of
the players game progress

Functions
---------

### GetValue

``` lua
GameProgress.GetValue(key)
```

**Expected parameter types**

| Name | Type   |
|------|--------|
| key  | string |

**Description**: Returns a value from the game progress by key, empty
string if it doesn't exist

**Returns**: string

### SetValue

``` lua
GameProgress.SetValue(key, value, overwrite)
```

**Expected parameter types**

| Name      | Type            |
|-----------|-----------------|
| key       | string          |
| value     | string          |
| overwrite | bool (optional) |

**Description**: Sets a value in the game progress

**Returns**: Nothing

### HasKey

``` lua
GameProgress.HasKey(key)
```

**Expected parameter types**

| Name | Type   |
|------|--------|
| key  | string |

**Description**: Does the specified key exist?

**Returns**: bool

### GetAll

``` lua
GameProgress.GetAll(table)
```

**Expected parameter types**

| Name  | Type      |
|-------|-----------|
| table | Lua Table |

**Description**: Fills a table with all GameProgress data

**Returns**: Nothing

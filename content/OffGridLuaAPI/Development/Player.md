Player
======

Description
-----------

The Player API handles querying and setting the state of the player

Functions
---------

### AddItemToInventory

``` lua
Player.AddItemToInventory(itemName)
```

**Expected parameter types**

| Name     | Type   |
|----------|--------|
| itemName | string |

**Description**: Adds an item to the players inventory (silently,
wihtout a notification. Also check Mission.SendData() ).

**Returns**: Nothing

### RemoveItemFromInventory

``` lua
Player.RemoveItemFromInventory(itemName)
```

**Expected parameter types**

| Name     | Type   |
|----------|--------|
| itemName | string |

**Description**: Removes an item to the players inventory

**Returns**: Nothing

### HasItem

``` lua
Player.HasItem(itemName)
```

**Expected parameter types**

| Name     | Type   |
|----------|--------|
| itemName | string |

**Description**: Is an item in the players inventory

**Returns**: true if the item is in the players inventory, else false

### ClearInventory

``` lua
Player.ClearInventory()
```

**Description**: Removes all items from the players inventory

**Returns**: Nothing

### SetPlayerNFCData

``` lua
Player.SetPlayerNFCData(internalName, dataTable)
```

**Expected parameter types**

| Name         | Type      |
|--------------|-----------|
| internalName | string    |
| dataTable    | Lua Table |

**Description**: Sets the NFC data on the players phone

**Returns**: Nothing

### AddDataFile

``` lua
Player.AddDataFile(internalName, dataTable)
```

**Expected parameter types**

| Name         | Type      |
|--------------|-----------|
| internalName | string    |
| dataTable    | Lua Table |

**Description**: Adds a data file directly to the players data inventory
without a sender

**Returns**: Nothing

### ClearDataInventory

``` lua
Player.ClearDataInventory()
```

**Description**: Removes all data files from the players data inventory

**Returns**: Nothing

### HasDataFile

``` lua
Player.HasDataFile(dataFileName)
```

**Expected parameter types**

| Name         | Type   |
|--------------|--------|
| dataFileName | string |

**Description**: Does the player have a data file with this name?

**Returns**: bool

### HasEncryptedFile

``` lua
Player.HasEncryptedFile(dataFileName)
```

**Expected parameter types**

| Name         | Type   |
|--------------|--------|
| dataFileName | string |

**Description**: Does the player have a file with the name
\_dataFileName\_ and is it encrypted?

**Returns**: bool

### HasDecryptedFile

``` lua
Player.HasDecryptedFile(dataFileName)
```

**Expected parameter types**

| Name         | Type   |
|--------------|--------|
| dataFileName | string |

**Description**: Does the player have a file with the name
\_dataFileName\_ and is it unencrypted?

**Returns**: bool

### GetDataString

``` lua
Player.GetDataString(internalName)
```

**Expected parameter types**

| Name         | Type   |
|--------------|--------|
| internalName | string |

**Description**: Returns the data string of a file in the players
inventory, takes in the internal name of the file

**Returns**: string

### SetDataString

``` lua
Player.SetDataString(internalName, newString)
```

**Expected parameter types**

| Name         | Type   |
|--------------|--------|
| internalName | string |
| newString    | string |

**Description**: Sets the data string of a data file in the players data
inventory

**Returns**: Nothing

### GetAllDataFileNames

``` lua
Player.GetAllDataFileNames()
```

**Description**: Return internalNames of all files in the players data
inventory

**Returns**: System.String\[\]

### GetAllDataFiles

``` lua
Player.GetAllDataFiles()
```

**Description**: Return a table of all files in the players data
inventory

**Returns**: Lua Type

### SendData

``` lua
Player.SendData(internalName, receiver)
```

**Expected parameter types**

| Name         | Type     |
|--------------|----------|
| internalName | Lua Type |
| receiver     | Lua Type |

**Description**: Send a file from player's inventory to receiver

**Returns**: Nothing

### GetDataPointMetaValue

``` lua
Player.GetDataPointMetaValue(dataPoint)
```

**Expected parameter types**

| Name      | Type      |
|-----------|-----------|
| dataPoint | DataPoint |

**Description**: Returns how much new metdata player would gain from
this DataPoint

**Returns**: number

### GetSocialProfileSize

``` lua
Player.GetSocialProfileSize(internalName)
```

**Expected parameter types**

| Name         | Type   |
|--------------|--------|
| internalName | string |

**Description**: Returns the size of the background profile player has
collected about a character

**Returns**: number

### SocialProfileContainsTag

``` lua
Player.SocialProfileContainsTag(internalName, tag)
```

**Expected parameter types**

| Name         | Type   |
|--------------|--------|
| internalName | string |
| tag          | string |

**Description**: Returns true if social profile contains any character
data with specified tag

**Returns**: bool

### SocialProfileContainsTagData

``` lua
Player.SocialProfileContainsTagData(internalName, tag, data)
```

**Expected parameter types**

| Name         | Type   |
|--------------|--------|
| internalName | string |
| tag          | string |
| data         | string |

**Description**: Returns true if social profile contains character data
matching both tag and data

**Returns**: bool

### SocialProfileContainsData

``` lua
Player.SocialProfileContainsData(internalName, data)
```

**Expected parameter types**

| Name         | Type   |
|--------------|--------|
| internalName | string |
| data         | string |

**Description**: Returns true if social profile contains specified
character data (regardless of it's tag)

**Returns**: bool

### AddSocialProfileInformation

``` lua
Player.AddSocialProfileInformation(internalName, tag, data)
```

**Expected parameter types**

| Name         | Type   |
|--------------|--------|
| internalName | string |
| tag          | string |
| data         | string |

**Description**: Add new background data about a character to
SocialInventory

**Returns**: Nothing

### GetSocialProfileInformation

``` lua
Player.GetSocialProfileInformation(internalName)
```

**Expected parameter types**

| Name         | Type   |
|--------------|--------|
| internalName | string |

**Description**: Get all known background data about a character from
player's SocialInventory

**Returns**: Lua Type

### GetPlayerTrackingState

``` lua
Player.GetPlayerTrackingState()
```

**Description**: Get current tracking state from Player's phone.

**Returns**: PlayerPhone+TrackingStates

### GetNetPointsCount

``` lua
Player.GetNetPointsCount()
```

**Description**: Get current amount of NetPoints the player has.

**Returns**: number

### SetNetPointsCount

``` lua
Player.SetNetPointsCount(count)
```

**Expected parameter types**

| Name  | Type   |
|-------|--------|
| count | number |

**Description**: Set player's NetPoints count.

**Returns**: Nothing

### AddNetPoints

``` lua
Player.AddNetPoints(count)
```

**Expected parameter types**

| Name  | Type   |
|-------|--------|
| count | number |

**Description**: Add more NetPoints to player

**Returns**: Nothing

### RemoveNetPoints

``` lua
Player.RemoveNetPoints(count)
```

**Expected parameter types**

| Name  | Type   |
|-------|--------|
| count | number |

**Description**: Take NetPOintsa from player.

**Returns**: Nothing

### RecoverNetPoints

``` lua
Player.RecoverNetPoints(count)
```

**Expected parameter types**

| Name  | Type   |
|-------|--------|
| count | number |

**Description**: Recover used NetPoitns to player.

**Returns**: Nothing

### GetName

``` lua
Player.GetName()
```

**Description**: Get the Player's internalName

**Returns**: string

### GetLightLevel

``` lua
Player.GetLightLevel()
```

**Description**: Get the light level around the player

**Returns**: number

### SetAlwaysRagdoll

``` lua
Player.SetAlwaysRagdoll(state)
```

**Expected parameter types**

| Name  | Type |
|-------|------|
| state | bool |

**Description**: Player character aways ragdolls on death

**Returns**: Nothing

### SetInvisible

``` lua
Player.SetInvisible(state)
```

**Expected parameter types**

| Name  | Type |
|-------|------|
| state | bool |

**Description**: Player character is invisible

**Returns**: Nothing

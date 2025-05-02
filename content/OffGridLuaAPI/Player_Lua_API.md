# Player_Lua_API

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Player_Lua_API*

*Scraped on: 2025-05-02 18:40:22*

## Contents
* *1Player**1.1Description**1.2Functions**1.2.1AddItemToInventory**1.2.2RemoveItemFromInventory**1.2.3HasItem**1.2.4ClearInventory**1.2.5SetPlayerNFCData**1.2.6AddDataFile**1.2.7ClearDataInventory**1.2.8ItemInQuickSlot**1.2.9HasDataFile**1.2.10HasEncryptedFile**1.2.11HasDecryptedFile**1.2.12GetDataString**1.2.13SetDataString**1.2.14GetAllDataFileNames**1.2.15GetAllDataFiles**1.2.16SendData**1.2.17GetSocialProfileSize**1.2.18SocialProfileContainsTag**1.2.19SocialProfileContainsTagData**1.2.20SocialProfileContainsData**1.2.21AddSocialProfileInformation**1.2.22GetSocialProfileInformation**1.2.23GetPlayerTrackingState**1.2.24GetNetPointsCount**1.2.25SetNetPointsCount**1.2.26AddNetPoints**1.2.27RemoveNetPoints**1.2.28GetName**1.2.29GetLightLevel**1.2.30SetAlwaysRagdoll**1.2.31SetInvisible*
# Player
## Description
The Player API handles querying and setting the state of the player
## Functions
### AddItemToInventory
```
Player.AddItemToInventory(itemName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| itemName | string |
**Description**: Adds an item to the players inventory (silently, wihtout a notification. Also check Mission.SendData() ).
**Returns**: Nothing
### RemoveItemFromInventory
```
Player.RemoveItemFromInventory(itemName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| itemName | string |
**Description**: Removes an item to the players inventory
**Returns**: Nothing
### HasItem
```
Player.HasItem(itemName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| itemName | string |
**Description**: Is an item in the players inventory
**Returns**: true if the item is in the players inventory, else false
### ClearInventory
```
Player.ClearInventory()
```
**Description**: Removes all items from the players inventory
**Returns**: Nothing
### SetPlayerNFCData
```
Player.SetPlayerNFCData(internalName, dataTable)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| internalName | string |
| dataTable | Lua Table |
**Description**: Sets the NFC data on the players phone
**Returns**: Nothing
### AddDataFile
```
Player.AddDataFile(internalName, dataTable)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| internalName | string |
| dataTable | Lua Table |
**Description**: Adds a data file directly to the players data inventory without a sender
**Returns**: Nothing
### ClearDataInventory
```
Player.ClearDataInventory()
```
**Description**: Removes all data files from the players data inventory
**Returns**: Nothing
### ItemInQuickSlot
```
Player.ItemInQuickSlot()
```
**Description**: Gets the name of the item currently in the players quick slot
**Returns**: string
### HasDataFile
```
Player.HasDataFile(dataFileName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| dataFileName | string |
**Description**: Does the player have a data file with this name?
**Returns**: bool
### HasEncryptedFile
```
Player.HasEncryptedFile(dataFileName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| dataFileName | string |
**Description**: Does the player have a file with the name _dataFileName_ and is it encrypted?
**Returns**: bool
### HasDecryptedFile
```
Player.HasDecryptedFile(dataFileName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| dataFileName | string |
**Description**: Does the player have a file with the name _dataFileName_ and is it unencrypted?
**Returns**: bool
### GetDataString
```
Player.GetDataString(internalName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| internalName | string |
**Description**: Returns the data string of a file in the players inventory, takes in the internal name of the file
**Returns**: string
### SetDataString
```
Player.SetDataString(internalName, newString)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| internalName | string |
| newString | string |
**Description**: Sets the data string of a data file in the players data inventory
**Returns**: Nothing
### GetAllDataFileNames
```
Player.GetAllDataFileNames()
```
**Description**: Return internalNames of all files in the players data inventory
**Returns**: System.String[]
### GetAllDataFiles
```
Player.GetAllDataFiles()
```
**Description**: Return a table of all files in the players data inventory
**Returns**: Lua Type
### SendData
```
Player.SendData(internalName, receiver)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| internalName | Lua Type |
| receiver | Lua Type |
**Description**: Send a file from player's inventory to receiver
**Returns**: Nothing
### GetSocialProfileSize
```
Player.GetSocialProfileSize(internalName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| internalName | string |
**Description**: Returns the size of the background profile player has collected about a character
**Returns**: number
### SocialProfileContainsTag
```
Player.SocialProfileContainsTag(internalName, tag)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| internalName | string |
| tag | string |
**Description**: Returns true if social profile contains any character data with specified tag
**Returns**: bool
### SocialProfileContainsTagData
```
Player.SocialProfileContainsTagData(internalName, tag, data)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| internalName | string |
| tag | string |
| data | string |
**Description**: Returns true if social profile contains character data matching both tag and data
**Returns**: bool
### SocialProfileContainsData
```
Player.SocialProfileContainsData(internalName, data)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| internalName | string |
| data | string |
**Description**: Returns true if social profile contains specified character data (regardless of it's tag)
**Returns**: bool
### AddSocialProfileInformation
```
Player.AddSocialProfileInformation(internalName, tag, data)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| internalName | string |
| tag | string |
| data | string |
**Description**: Add new background data about a character to SocialInventory
**Returns**: Nothing
### GetSocialProfileInformation
```
Player.GetSocialProfileInformation(internalName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| internalName | string |
**Description**: Get all known background data about a character from player's SocialInventory
**Returns**: Lua Type
### GetPlayerTrackingState
```
Player.GetPlayerTrackingState()
```
**Description**: Get current tracking state from Player's phone.
**Returns**: PlayerPhone+TrackingStates
### GetNetPointsCount
```
Player.GetNetPointsCount()
```
**Description**: Get current amount of NetPoints the player has.
**Returns**: number
### SetNetPointsCount
```
Player.SetNetPointsCount(count)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| count | number |
**Description**: Set player's NetPoints count.
**Returns**: Nothing
### AddNetPoints
```
Player.AddNetPoints(count)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| count | number |
**Description**: Add more NetPoints to player
**Returns**: Nothing
### RemoveNetPoints
```
Player.RemoveNetPoints(count)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| count | number |
**Description**: Take NetPoints from player.
**Returns**: Nothing
### GetName
```
Player.GetName()
```
**Description**: Get the Player's internalName
**Returns**: string
### GetLightLevel
```
Player.GetLightLevel()
```
**Description**: Get the light level around the player
**Returns**: number
### SetAlwaysRagdoll
```
Player.SetAlwaysRagdoll(state)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| state | bool |
**Description**: Player character aways ragdolls on death
**Returns**: Nothing
### SetInvisible
```
Player.SetInvisible(state)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| state | bool |
**Description**: Player character is invisible
**Returns**: Nothing
This file is auto generated, please don't edit manually!
**Docs last hacked together on**: 23/07/2020 11:58
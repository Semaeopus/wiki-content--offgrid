# AI_Lua_API

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=AI_Lua_API*

*Scraped on: 2025-05-02 18:41:10*

## Contents
* *1AI**1.1Description**1.2Functions**1.2.1Pause**1.2.2Unpause**1.2.3IsPaused**1.2.4AddTemporaryGoal**1.2.5AlterNPCMotivation**1.2.6AlterNPCWorldState**1.2.7FavourInterest**1.2.8AvoidInterest**1.2.9ChangeSubject**1.2.10ReactTo**1.2.11CreateReactable**1.2.12SetNPCFavouredComputer*
# AI
## Description
API to control the logic of AI in the mission
## Functions
### Pause
```
AI.Pause(characterName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| characterName | string |
**Description**: Pauses the agent, and stops it from doing anything.
**Returns**: Nothing
**Notes**: The AI will be hidden from networks, meaning it will no longer interact with devices or send/receive messages.
### Unpause
```
AI.Unpause(characterName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| characterName | string |
**Description**: Unpauses a hidden agent, resuming standard behaviour.
**Returns**: Nothing
### IsPaused
```
AI.IsPaused(characterName)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| characterName | string |
**Description**: Returns a bool based on if a character is currently paused or not
**Returns**: bool
### AddTemporaryGoal
```
AI.AddTemporaryGoal(characterName, goal)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| characterName | string |
| goal | Lua Table |
**Description**: Adds a goal, taking top priority, to the named AI
**Returns**: Nothing
**Notes**: This goal will be removed from the AI once complete. If it isn't achievable it will be removed immediately.
### AlterNPCMotivation
```
AI.AlterNPCMotivation(characterName, motivationDelta)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| characterName | string |
| motivationDelta | number |
**Description**: Alters an NPCS motivation state
**Returns**: Nothing
**Notes**: When an NPCs motivation hits 0, they're no longer motivated and will attempt to take a break
### AlterNPCWorldState
```
AI.AlterNPCWorldState(characterName, state, value)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| characterName | string |
| state | string |
| value | Lua Type |
**Description**: Change the World State of an NPC.
**Returns**: Nothing
### FavourInterest
```
AI.FavourInterest(characterName, device, permanent)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| characterName | string |
| device | string |
| permanent | bool |
**Description**: Reduce the cost of an AI using a particular Interest
**Returns**: Nothing
**Notes**: If permanent is false, the cost will revert to normal the next time this is successfully used
### AvoidInterest
```
AI.AvoidInterest(characterName, device, permanent)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| characterName | string |
| device | string |
| permanent | bool |
**Description**: Increase the cost of an AI using a particular Interest
**Returns**: Nothing
**Notes**: If permanent is false, the cost will revert to normal the next time this is successfully used
### ChangeSubject
```
AI.ChangeSubject(characterName, subject, value)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| characterName | string |
| subject | string |
| value | string |
**Description**: Set the value of a particular subject, enabling Actions with Personality requirements
**Returns**: Nothing
**Notes**: value can be null or empty (to unset/reset the subject)
### ReactTo
```
AI.ReactTo(characterName, subject, value)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| characterName | string |
| subject | string |
| value | string |
**Description**: Much like ChangeSubject, but instead of enabling Actions, this will alter stats within the Agent, modifying its WorldState (and as a result, enabling Actions)
**Returns**: Nothing
**Notes**: value can be null or empty (to unset/reset the subject)
### CreateReactable
```
AI.CreateReactable(actionType, attraction, targetObject)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| actionType | AIReaction+Type |
| attraction | number |
| targetObject | MissionObject |
**Description**: Create a new distraction that AI can pick up on
**Returns**: Nothing
### SetNPCFavouredComputer
```
AI.SetNPCFavouredComputer(characterName, computer)
```
**Expected parameter types**
| Name | Type |
| --- | --- |
| characterName | string |
| computer | MissionObject |
**Description**: Set NPC's computer, this will be used for a variety of actions
**Returns**: Nothing
This file is auto generated, please don't edit manually!
**Docs last hacked together on**: 23/07/2020 11:58
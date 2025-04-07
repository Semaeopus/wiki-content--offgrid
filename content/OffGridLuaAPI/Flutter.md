Flutter
=======

Description
-----------

The Flutter API allows modders to send Flutter messages

Tables
------

### FlutterMessage

**Table definition**

| Name     | Type   | Default | Optional | Description                      |
|----------|--------|---------|----------|----------------------------------|
| message  | string |         | No       | Content string for the message   |
| hashTags | table  |         | No       | custom hash tags for the message |
| tags     | table  |         | No       | metadata tags                    |
| metadata | table  |         | No       | metadata values                  |

Functions
---------

### SendMessageFromCharacter

``` lua
Flutter.SendMessageFromCharacter(message, internalName)
```

**Expected parameter types**

| Name         | Type     |
|--------------|----------|
| message      | Lua Type |
| internalName | string   |

**Description**: Sends a custom FlutterMessage from NPC in current level

**Returns**: Nothing

### SendRandomMessageFromCharacter

``` lua
Flutter.SendRandomMessageFromCharacter(internalName)
```

**Expected parameter types**

| Name         | Type   |
|--------------|--------|
| internalName | string |

**Description**: Sends a generated Flutter message from NPC in current
level

**Returns**: Nothing

### SendRandomMessage

``` lua
Flutter.SendRandomMessage()
```

**Description**: Sends a generated Flutter message from generated random
character

**Returns**: Nothing

### SetFlutterEnabled

``` lua
Flutter.SetFlutterEnabled(enabled)
```

**Expected parameter types**

| Name    | Type |
|---------|------|
| enabled | bool |

**Description**: Set Flutter app enabled or disabled.

**Returns**: Nothing

This file is auto generated, please don't edit manually!

**Docs last hacked together on**: 09/12/2024 12:54

Constants
=========

Enums
-----

### DataType

| Usage             | Description                                                                                  |
|-------------------|----------------------------------------------------------------------------------------------|
| DataType.Generic  | Any random data. Who knows, could be anything.                                               |
| DataType.Text     | Plain text or rich text content.                                                             |
| DataType.SMS      | SMS. Don't use this! Legacy stuff.                                                           |
| DataType.Image    | Image file. We'll try to display this for you in the File Viewer.                            |
| DataType.Audio    | Audio file. There's no viewer for these yet.                                                 |
| DataType.Video    | Video file. There's no viewer for these yet.                                                 |
| DataType.Location | Location data. just the coordinates, no much use apart from being a location marker in level |
| DataType.Key      | PGP key. For encryption, device/lock access etc.                                             |
| DataType.UUID     | Generic identifier for something.                                                            |

### DataValue

| Usage               | Description |
|---------------------|-------------|
| DataValue.Low       |             |
| DataValue.Medium    |             |
| DataValue.High      |             |
| DataValue.Important |             |

### MissionObjectType

| Usage                         | Description |
|-------------------------------|-------------|
| MissionObjectType.Trigger     |             |
| MissionObjectType.Interaction |             |
| MissionObjectType.Spawn       |             |
| MissionObjectType.Hackable    |             |
| MissionObjectType.Generic     |             |
| MissionObjectType.Deprecated  |             |
| MissionObjectType.Timeline    |             |

### InteractionType

| Usage                    | Description |
|--------------------------|-------------|
| InteractionType.Grab     |             |
| InteractionType.OpenDoor |             |
| InteractionType.Scanning |             |

### InteractionRequirement

| Usage                       | Description |
|-----------------------------|-------------|
| InteractionRequirement.None |             |
| InteractionRequirement.Item |             |
| InteractionRequirement.Data |             |
| InteractionRequirement.Key  |             |

### AppTypes

| Usage            | Description                                                                  |
|------------------|------------------------------------------------------------------------------|
| AppTypes.Active  | Active apps are used by the player to do specific tasks related to data      |
| AppTypes.Passive | Passive apps run in the background, and their cost is as reserved NetPoints. |

### AppState

| Usage                | Description                                                        |
|----------------------|--------------------------------------------------------------------|
| AppState.unavailable | The player doesn't have this app yet.                              |
| AppState.disabled    | App can't be used at the moment, for example no network connection |
| AppState.off         | App is not doing anything                                          |
| AppState.on          | App is switched on and running in the background                   |
| AppState.alert       | App displays alert to notify the player about something.           |

### TrackingStates

| Usage                    | Description                                                   |
|--------------------------|---------------------------------------------------------------|
| TrackingStates.off       | Not connected to SPECTRUM.                                    |
| TrackingStates.tracking  | Connected to SPECTRUM.                                        |
| TrackingStates.alert     | Connected to SPECTRUM, almost out of time.                    |
| TrackingStates.overtime  | Connected to SPECTRUM, over time, restricted to minimum range |
| TrackingStates.cooldown  | Disconnected from SPECTRUM, recovering.                       |
| TrackingStates.unlimited | Unlimited connection. Cheater.                                |

### NetworkType

The type of network, different devices and characters will only connect
to certain network types

| Usage              | Description                                                                  |
|--------------------|------------------------------------------------------------------------------|
| NetworkType.mobile | Mobile network (4G)- This will mainly just contain mobile phone devices      |
| NetworkType.wifi   | Wifi networks will be the most common, and will contain all sorts of devices |
| NetworkType.mesh   | Mesh networks are mainly set up as part of a storyline                       |
| NetworkType.nfc    |                                                                              |

### TargetType

| Usage                  | Description |
|------------------------|-------------|
| TargetType.None        |             |
| TargetType.Data        |             |
| TargetType.Interaction |             |
| TargetType.Hackable    |             |
| TargetType.Character   |             |

### NotificationType

| Usage                               | Description           |
|-------------------------------------|-----------------------|
| NotificationType.sms                |                       |
| NotificationType.generic            | Generic notification  |
| NotificationType.message            | Communication message |
| NotificationType.download           | Receiving files       |
| NotificationType.newObjective       |                       |
| NotificationType.completedObjective |                       |

### PopupType

| Usage              | Description                   |
|--------------------|-------------------------------|
| PopupType.generic  | A generic popup               |
| PopupType.message  | A message to the player       |
| PopupType.warning  | A warning to the player       |
| PopupType.download | Begin a timed download window |
| PopupType.progress | Trigger a progress bar        |

### DeviceUITypes

| Usage                 | Description               |
|-----------------------|---------------------------|
| DeviceUITypes.Console | Command line              |
| DeviceUITypes.Ncurses | Old-school Text-based UI  |
| DeviceUITypes.Modern  | Simple but modern UI      |
| DeviceUITypes.Desktop | Windowed computer desktop |

### DeviceUISizes

| Usage                | Description       |
|----------------------|-------------------|
| DeviceUISizes.Normal | Normal UI Window  |
| DeviceUISizes.Small  | Smaller UI window |

### DeviceUIItemTypes

| Usage                     | Description                      |
|---------------------------|----------------------------------|
| DeviceUIItemTypes.Empty   | One item's worth of just nothing |
| DeviceUIItemTypes.Heading | Heading                          |
| DeviceUIItemTypes.Button  | Button you can click on          |
| DeviceUIItemTypes.Text    | Content text                     |
| DeviceUIItemTypes.Spacer  | Horizontal line                  |
| DeviceUIItemTypes.Image   | Shows an image in the UI         |

### PageLayout

| Usage           | Description |
|-----------------|-------------|
| PageLayout.Grid | Grid layout |
| PageLayout.List | List layout |

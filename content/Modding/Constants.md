# Constants

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Constants*

*Scraped on: 2025-05-02 18:39:58*

## Contents
* *1Constants**1.1Enums**1.1.1DataType**1.1.2MissionObjectType**1.1.3InteractionType**1.1.4AIReactionType**1.1.5AppState**1.1.6AppMenuState**1.1.7TrackingStates**1.1.8NetworkType**1.1.9TargetType**1.1.10NotificationType**1.1.11PopupType*
# Constants
## Enums
### DataType
| Usage | Description |
| --- | --- |
| DataType.Generic | Any random data. Who knows, could be anything. |
| DataType.Text | Plain text or rich text content. |
| DataType.SMS | SMS. Don't use this! Legacy stuff. |
| DataType.Image | Image file. We'll try to display this for you in the File Viewer. |
| DataType.Audio | Audio file. There's no viewer for these yet. |
| DataType.Video | Video file. There's no viewer for these yet. |
| DataType.Location | Location data. just the coordinates, no much use apart from being a location marker in level |
| DataType.Key | PGP key. For encryption, device/lock access etc. |
| DataType.UUID | Generic identifier for something. |
### MissionObjectType
| Usage | Description |
| --- | --- |
| MissionObjectType.Trigger |  |
| MissionObjectType.Interaction |  |
| MissionObjectType.Spawn |  |
| MissionObjectType.Hackable |  |
| MissionObjectType.Generic |  |
| MissionObjectType.Deprecated |  |
| MissionObjectType.Timeline |  |
### InteractionType
| Usage | Description |
| --- | --- |
| InteractionType.Grab |  |
| InteractionType.OpenDoor |  |
| InteractionType.Scanning |  |
### AIReactionType
The type of reaction that can affect NPCs
| Usage | Description |
| --- | --- |
| AIReactionType.FixAmokDevice | The NPC will attempt to fix the amok device |
### AppState
| Usage | Description |
| --- | --- |
| AppState.unavailable | The player doesn't have this app yet. |
| AppState.disabled | App can't be used at the moment, for example no network connection |
| AppState.off | App is not doing anything |
| AppState.on | App is switched on and running in the background |
| AppState.alert | App displays alert to notify the player about something. |
### AppMenuState
| Usage | Description |
| --- | --- |
| AppMenuState.any | Allowed in any of configuration |
| AppMenuState.never | Never allowed in the selected menu |
| AppMenuState.always | Always in the selected menu |
| AppMenuState.byDefault | In the selected menu by default |
| AppMenuState.target | Will be in the radial menu when its target types are selected |
### TrackingStates
| Usage | Description |
| --- | --- |
| TrackingStates.off | Not connected to SPECTRUM. |
| TrackingStates.tracking | Connected to SPECTRUM. |
| TrackingStates.alert | Connected to SPECTRUM, almost out of time. |
| TrackingStates.overtime | Connected to SPECTRUM, over time, restricted to minimum range |
| TrackingStates.cooldown | Disconnected from SPECTRUM, recovering. |
| TrackingStates.unlimited | Unlimited connection. Cheater. |
### NetworkType
The type of network, different devices and characters will only connect to certain network types
| Usage | Description |
| --- | --- |
| NetworkType.mobile | Mobile network (4G)- This will mainly just contain mobile phone devices |
| NetworkType.wifi | Wifi networks will be the most common, and will contain all sorts of devices |
| NetworkType.mesh | Mesh networks are mainly set up as part of a storyline |
| NetworkType.nfc |  |
### TargetType
| Usage | Description |
| --- | --- |
| TargetType.None |  |
| TargetType.Data |  |
| TargetType.Interaction |  |
| TargetType.Hackable |  |
| TargetType.Character |  |
### NotificationType
| Usage | Description |
| --- | --- |
| NotificationType.sms |  |
| NotificationType.generic | Generic notification |
| NotificationType.message | Communicatiosn message |
| NotificationType.download | Receicing files |
| NotificationType.newObjective |  |
| NotificationType.completedObjective |  |
### PopupType
| Usage | Description |
| --- | --- |
| PopupType.generic | A generic popup |
| PopupType.message | A message to the player |
| PopupType.warning | A warning to the player |
| PopupType.download | Begin a timed download window |
| PopupType.progress | Trigger a progress bar |
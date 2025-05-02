# Data_Scripting

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Data_Scripting*

*Scraped on: 2025-05-02 18:39:23*

## Data Scripting
We saw in [Mission Scripting](Mission_Scripting.md) that Data can have a script attached. Let's have a brief look at what can be done with this.
We have the following globals available:
| Globals | Name | Description |
| --- | --- | --- |
| DeviceName | The name of the device, to be used with [Devices Lua API](Devices_Lua_API.md) |
| macAddress | The MAC address of the device |
| RunMissionCommand | The function enabling access to mission script functionality |

So for instance, let's say we want to set the Device state to Amok when the data is received:
```
Devices.SetAmok(deviceName, true);
```
or trigger an objective to be complete?
```
RunMissionCommand("Mission.CompleteObjective(mission.objectives.ourObjective)")
```
### Advanced
But what if we wanted to do something... naughtier?
The data script runs on the same Lua virtual machine as the device. Which means it has access to everything scripted in the device. So we could, for instance, alter the gui
```
if device ~= nil then
	if device.gui ~= nil then
		if device.gui.buttons ~= nil then
			device.gui.buttons["hax"] =
			{
				name = "Hax",
				desc = "Hacky McHackface",
		 		onClick = function()
		 			print("This works")
		 		end,
		 		subButtons = {
		 			hackButton = {
		 				name = "Enable",
						desc = "",
						onClick = function()
							Devices.SetAmok(DeviceName, true)
						end,
		 			},
				}
			}
		end
	end
end
```
A few things to note here. Before any variable is referenced, it must be checked against nil. This is known as defensive programming. The reason for this is that, in Off Grid, data can be sent to any device. So writing a piece of data that specifically attacks one device will likely break if sent to another (and not in a fun way). The other point is that it is much safer to write code that adds things, than it is to write code that changes things; and writing code that removes things is riskier still. Be sure you've thought through what will happen to other parts of the game when you're writing data scripts.

**Remember... Data is your most powerful weapon!**
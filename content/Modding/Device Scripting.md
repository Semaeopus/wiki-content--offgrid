# Device_Scripting

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Device_Scripting*

*Scraped on: 2025-05-02 18:38:21*

An example of a hackable device

# Introduction
Device scripting is core to creating an Off Grid [Mission](Mission Scripting), they are incredibly extensible and are useful for a multitude of tasks including forwarding your missions plot and world building.
Each device that the player can hack into will have a device script, devices can share scripts if they're similar enough or have their own bespoke scripts.
# Device Concepts
Currently there are some boolean values that can be toggled on each Device.
* Power
* Active
* Amok
* Preserve Active
Power can either be true or false, and is not affected by the others.
Active can either be true or false, but is false if Power is false.
Amok can either be true or false. An Agent will remember Amok devices and avoid them after their first use.
Preserve Active ensures that the value of Active will be remembered if Power is cycled.
This logic is set in code, so cannot be interfered with. It is perfectly acceptable to mix the ideas of Power and Active for simple Devices, but Devices do not exist in isolation, and it is worth creating Devices that can be dropped into any level, published on Steamworks, etc! With that in mind, some tips:
* Use Active to differentiate behaviour in preference to Power.
* Use Power for if you want a Device to be doing *nothing*. Consider this as a way of producing a Off/Standby/On flow.
* Use Amok to alter Agent behaviour.
* Preserve Active gives nice variation between (for instance) a lamp, which might come back on when Power is restored, and a Computer, which might need to be switched on again.
* more, TBC!
## Querying State
This is pretty crucial. It's important not to attempt to store the state of Power, Active, or Amok in a Device script. This is because the state already exists on the code side, and storing it elsewhere will mean that, sooner or later, the code and script are out of sync. Use Device.GetPower, Device.GetActive, and Device.GetAmok to determine the current state.
# Script Example
Let's start with a quick device example and build up from there. One of the Off Grid story missions finds the player needing to hack into the office hand dryers.
Here's a basic example that we'll build upon:*It's not as bad as it looks!*
Visual representation of the example device script
```
device = {
    -- The game calls this function when the player tries to interact with the device,
    -- It determines if the player has permission to view the devices GUI
    canAccess = function()
     return true
    end,
    -- This determines how often the update function gets called
    -- In this example, we'll call it once a second
    updateRate = 1.0,
    update = function()
        print("Updating!")
    end,
    -- The gui table controls the user interface for the device
    gui = {
        -- For the moment, this can only be ncurses, but will eventually allow different styles for your gui
		type = "ncurses",
		-- The text in the title bar of the gui
		header = [[Our test hand dryer]],
		-- The RGB value of the background
		backgroundColour = {0.95, 0.65, 0.19},
		-- The RGB value of the button highlights
		highlightColour = {0.21, 0.48, 0.74},
		-- Here we set up the list of buttons the user can click on
		buttons = {
			{
				-- The name of the first button
				name = "Test button",
				-- Code to execute when it's clicked
				onClick = function()
                    print("test button clicked!")
				end,
				-- The list of sub buttons, these appear as options when the main button is clicked
                subButtons = {
                    {
						-- Name of the sub button
                        name = "Test subbutton",
						-- Sub button logic when clicked
                        onClick = function()
                            print("test subbutton clicked!")
                        end,
                    },
                }
			}
		},
	},
}
```
# Device Access
You can restrict access to a device in few ways. First, setting an owner for the device in the mission script means the player needs to collect some metadata about the owner  to be able to guess the device's password and gain access. By default the amount of required data is 5, but you can configure this in your device script if you want to. And secondly, you can sue the*canAccess()*function in the device script for more customized checks, for example to check if player's data inventory contains certain file, or social inventory contains some exact piece of metadata. Or do checks on mission progress data using something like*Mission.GetBool()*, or even overall game progress data to see if player has done some specific thing in a previous level.
The rules for access are these:
1. IfcanAccess()returns true, player gets access
2. Otherwise, if player's collected metadata about the owner is more or equal to theaccessLimitvalue in device script, the player will be able to use password cracker app to gain access to the device.
3. If the player has 75% or more of the required data, there's a 25% chance to guess the password. After trying this once, the result is remembered, so following tries would yield the same result. The player can try again after collecting at least one more piece of metadata.
4. if all those fail, the device can't be accessed.
So, the minimum setup for a restricted device is defining the owner in your mission script, and setting the*canAccess()*to always return false so the device can only be accessed through collecting enough character metadata.
```
device = {
	...,
	accessLimit = 5,
	canAccess = function()
 		if Player.HasDataFile("Guard1PGPKey") or Player.SocialProfileContainsTagData(owner, "NickName", "Beardman") then
			return true
		else
			return false
		end
	end,
	...,
}
```
# Callbacks
We use the following callbacks to run user code when certain events occur. All are optional unless otherwise specified.
## canAccess
As described in Device Access, this is one of the ways of restricting access to this device. Note that while returning true will grant access, returning false won't necessarily deny access.
## update
Called at a regular interval. See also updateRate.
## willPrefer
**Arguments**
| Type | Description |
| --- | --- |
| string | a personality string used by the Device to determine a preference |

**Returns**
| Type | Description |
| --- | --- |
| bool | true if the Agent should prefer this Device, false if no match |

Called by the Agent to determine if that Agent would prefer to use this Device, when offered a choice of Devices. If true, the 'cost' of using this Device will decrease, thus favouring it over closer options.
## canBeHeardBy
**Arguments**
| Type | Description |
| --- | --- |
| string | the name of the Agent hearing this Device |

Called when an Agent can hear this Device. Consider altering the Agent's world state when this occurs!
## canNoLongerBeHeardBy
**Arguments**
| Type | Description |
| --- | --- |
| string | the name of the Agent no longer able to hear this Device |

Called when an Agent can no longer hear this Device. Less useful than canBeHeardBy, but still handy!
## OnPowerChange
**Arguments**
| Type | Description |
| --- | --- |
| bool | the new Power state |

Called when this Device becomes powered/loses power. Note that if you have some functionality that is supposed to occur when the Power state changes, it is best to put it in here, rather than in, for example, your GUI code. Putting the code here means that if this state changes due to something other than the GUI, your Device behaves consistently. For instance, you might send some data to a Device that turns it off; adding this callback ensures that, in this instance, it behaves the same as if you turned the Device off within your GUI.
## OnActiveChange
**Arguments**
| Type | Description |
| --- | --- |
| bool | the new Active state |

Called when this Device becomes active/inactive. Note that if you have some functionality that is supposed to occur when the Power state changes, it is best to put it in here, rather than in, for example, your GUI code. Putting the code here means that if this state changes due to something other than the GUI, your Device behaves consistently. For instance, you might send some data to a Device that turns it off; adding this callback ensures that, in this instance, it behaves the same as if you turned the Device off within your GUI.
## OnAmokChange
**Arguments**
| Type | Description |
| --- | --- |
| bool | the new Amok state |

Called when this Device goes amok/returns to normal operation. Note that if you have some functionality that is supposed to occur when the Amok state changes, it is best to put it in here, rather than in, for example, your GUI code. Putting the code here means that if this state changes due to something other than the GUI, your Device behaves consistently. For instance, you might send some data to a Device that turns it off; adding this callback ensures that, in this instance, it behaves the same as if you turned the Device off within your GUI.
## RunOnce
## SetValue
## GetValue
## NPCuse
**Arguments**
| Type | Description |
| --- | --- |
| string | the name of the Agent using this Device |

Called when an Agent uses this Device, in the course of a UsePointAction.
Devices can set up a callback for when they receive data, this is done by adding the following to the devices Lua table:
```
device = {
	...,
 	OnReceiveData = function(dataTable)
 		-- Your code here!
	end,
	...,
}
```
The OnReceiveData callback will be triggered when the device is the recipient of the[Mission.SendData](Mission_Lua API)function.
# What do I do now?
Now you've read through and got an idea of how to build up what your interface looks like you might be looking at ways to expand what your device does.
What's important to remember is all Lua Apis are available in device scripts meaning they can:
* Trigger sounds
* Start and stop particle effects
* Complete and start new objectives
* Send data to the player and other devices
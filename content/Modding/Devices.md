# A Device GameObject
First of all, make sure the*Tag*of the GameObject is HackableDevice, and that it's on layer*MissionObjects*.
There are a few prerequisite components needed to set up your Device for hacking.
## MissionObject
This needs to have*Hackable*enabled. Commonly, you will also tick*Interactable*- for Devices that you also want the player to be able to interact with.
## Hackable Component
The other required Component is*Hackable*.
# Hackable Reference
The following details aspects of the Hackable (or Hackable-derived) Component that can be added to a Device to make it*Hackable*!
## Device Power: true/false
Devices need power in order to do anything. Devices that are Off can neither be Active nor Amok. Furthermore, removing a device's power will also set it to not be Active (and Amok, if applicable). Have you tried switching it on and off again?
## Set Active: true/false
This means that the device is operating normally. Requires Power for this to be true.
## Device Amok: true/false
A state to indicate an alternative mode of operation. This could be something malevolent, like a coffee machine spewing steam, or it could be a test cycle for a printer. This also requires Power in order to be set to true.
## Run Once
(devices normal behaviour as a 'one shot' action)
## Set Value
Set a value on a device such as the temperature on the thermostat
## Inventory
Device should make use of or react to receiving a certain data type or piece of data with a specific name.
## Events
Unity Events allow other Unity objects to respond to changes in state. The default Hackable events are set up so that when something about the device changes, an event will fire, allowing further customisation of Devices.
### Power On
This fires when the Device becomes powered (i.e. it didn't have power to begin with). Suggested use: play a light up animation, turn a light on, play a sound effect.
### Power Off
This fires when the Device loses power (i.e. it had power to begin with). Suggested use: turn lights off, play a sound effect.
### Active On
This fires when the Device becomes active (i.e. it was inactive to begin with). Note that this could be called when a Device has lost, then regained, power, if*Preserve Active*is set. Suggested use: Lights, particles, sounds.
### Active Off
This fires when the Device becomes inactive (i.e. it was active to begin with). Note that this will be called when an active Device loses power, as in doing so it will become inactive (as well as unpowered). Suggested use: Lights, particles, sounds!
### Amok On
This fires when the Device goes amok (i.e. it was operating normally to begin with). Suggested use: lights, particles, noises!
### Amok Off
This fires when the Device ceases to be amok (i.e. it was amok to begin with). Note that this will be called when the Device is deactivated, or when power is removed, as both need to be true for a Device to be in an amok state. Have you tried switching it on and off again?!
### Run Once
This fires whenever RunOnce is called. This could be reasonably frequently. RunOnce's general purpose is to happen when a Device is 'used' - a printer printing a sheet, a coffee machine delivering a cup of coffee.
### NPC Use
This fires whenever an NPC uses an InterestPoint, if that InterestPoint has a Device.
# Further Resources
This is all done in the [Device Scripting](Device Scripting) page.
To know what things devices can do you can reference the [Devices Lua API](Devices_Lua API).
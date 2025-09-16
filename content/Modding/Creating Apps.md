## Introduction
The main tool the player has in Off Grid (apart from clever mind and smooth stealth skills, of course) is the apps running on the player's phone, allowing both viewing and interacting with all the devices and data in the levels.
The app system is built to allow creating all kinds of new tools, both very generic and powerful ones, but also small quality-of-life tools that just do some small very specific task, but make it more convenient for the player.
It can also handle different types of targets, display information in the UI, and do pretty much anything our Lua API allows.
On the game side, we handle the controls, app inventory and other boring common tasks automatically, and also keep track of the app use costs, and if the player is able to use an app at the moment or not, so what's left to the modder is just the specific way how*your*app should work.
This page should explain what goes into an app's Lua script, but for more ideas and examples it's worth looking at the existing apps that are included in the game. You'll find them in*StreamingAssets/Common/Apps*folder.
## Example Lua script
```
app = {
    name = "Example App",
    description = "How to make your first app for Off Grid.",
    cost = 2.0,
    targets = {TargetType.Data},
    showInRadial = AppMenuState.target,
    showInAppWheel = AppMenuState.byDefault,
    state = AppState.off,
    icon = "ExampleApp.png",
    iconColor = Color.Blue,
    statusIcons = { "option1.png", "option2.png"},

    actions = {
        {
            name = "DefaultAction",
            run = function(target)
                -- In 3rd person mode executing app will always trigger first action
            end,
        },
        {
            name = "ExtraAction",
            cost = 2.0,
            run = function(target)
                -- In radial menu mode if there's more than one action, triggering the app opens a popup menu to select which action to take.
            end,
        },
    },

    options = {
        someOption = {
            name = "Some option",
            enabled = true,
        },
        anotherOption = {
            name = "Some other option",
            enabled = false,
            OnOptionChange = function()
                -- This runs when the option is toggled.
            end
        },
    },

    OnStateChange = function(state)
        -- This runs when something on game side asks the app to change it's state
        app.state = state
        SetState(app.state)
    end,

    UpdateActions = function(target)
        -- If you want to change available actions based on the target player has selected, do it here.
    end,

    Update = function(time)
        -- Update will run continuously.
    end,

}
```
## App configuration
The first section of the app script is used to define some default settings and basic information about what the app is and how it works.
| Name | Required/Optional | Description |
| --- | --- | --- |
| name | required | Name of the app |
| description | required | Short description of what the app does |
| cost | optional | How many seconds the tracking progress increases when using this app |
| targets | optional | List of what*target types*the app can have |
| showInRadial | optional | How the app should be displayed in Radial menu. See*menu options*. |
| showInAppWheel | optional | How the app should be displayed in the AppWheel. See*menu options*. |
| state | required | Current*state*of the app. |
| icon | required | Path to icon image |
| iconColor | optional | background color for the app icon |
| statusIcons | optional | List of icon images to use for*status window* |
### name
This is both the human-readable name of the app that will be displayed to the player in the UI and in menus, and also what's used to refer to the app in all your Lua scripts, inventories, and in game saves.
### description
Longer description of what the app is and what it does.
### cost
The cost (NetPoints) of having the app running. This is only needed if your app uses the*Update()*function, and you actually want it to cost something. Turning on an app that has a cost will require at least that amount of available NetPoints, and then reserves them while the app is enabled.
### targets
Targets should include either an individual*target type*, or a list of target types. If you don't define anything, the game will use*TargetTypes.None*by default, allowing the app to work when no target is selected. For sake of clarity, it's recommended to define that in the app script anyway.
```
targets = TargetType.Data,
```
```
targets = {TargetType.Hackable, TargetType.Character},
```
Note that TargetType.None still only lets you trigger actions from RadialUI. The AppWheel is intended for more fast actions without interrupting gameplay, and your untargeted action should be triggered by turning the app on. This make sure there's no conflict between physical interactions player does and whatever app happens to be selected at the moment in the AppWheel.
### showInRadial
Rules for if, and how, the app should be listed in the radial UI. See*Menu options*for the details.
### showInAppWheel
Rules for if, and how, the app should be listed in the AppWheel. See*Menu options*for the details.
### state
The default starting*state*of the app. This also used to store the apps*current*state when the game is running. Most of the time setting this to*AppState.off*would work fine, meaning the app is available to the player an listed in menus as defined by the showInRadial and showInAppWheel settings, but isn't doing anything at the moment.
If you want the player to start your mission without this app, and then give it to the player later on (maybe from a device player hacks, or sent by another character during a conversation or something) you can set the state in the app script to*AppState.unavailable*, and then later on call`Apps.RequestAppState(appName, AppState.off)`from the Apps API to make thew app available to the player.
Here's an example onClick() function from one of our devices. This would make the app called "MultiTool" available to player (with a bit of delay to make things happen*after*player has closed the device UI and the game continues running again), and also displaying a notification to make it look like a new app was downloaded on the player character's phone:
```
onClick = function()
    Scheduler.CallInSecs(function()
        Apps.RequestAppState("MultiTool", AppState.off)
        UI.ShowNotification(NotificationType.download, "System", "Installed new application:
**MultiTool**
", 10)
    end, 1)
end,
```
### icon
Name (and path) to the icon file used for the app in the game. The icon should be a square PNG image, with transparent background and a bit of empty space on the sides so it'll fit nicely to the AppWheel & Radial UI. (The borders and backgrounds seen in-game are part of the UI, so the icon really is just the "logo" of the app).
### iconColor
The background color for the app icon (used in AppWheel, Radial UI and the Apps menu). The color you set here will be what's sued when the app is switched on, while the off/disabled etc colors are calculated automatically. Any alpha value in color is ignored.
You can either defince RGB values, or use one of our preset colors:
```
iconColor = Color.Blue,
```
```
iconColor = {0.2, 0.8, 0.6, 1.0},
```
### statusIcons
If you want your app to display a*status window*, you can use this to define one or more icons to be used with it. Same rules as with the app icon so PNG, transparent background, and some space left on sides.
You can add colors to your icon images if you want to, but for best fit with the game and to be able to*set the icon color through code*(rather than having to load a separate image file for different colors) making the icon white works the best.
## Actions & Options
The Actions and Options are the main thing usual app does. As the names suggest, Actions are what the app does when player points at a target and presses the Interact button on the controller. And Options are to provide the player with a way to customize and further define what exactly the app should be doing.
Both are optional, if you just want an app that runs in the background, maybe displaying some information to player using a Status window, then you don't need any actions. And, if your app only ever behaves in single way, or the behaviour is determined by something else than the player, then you don't need to add options either.
Furthermore, if your actions (and/or options) are created dynamically, you might not even need to define anything there and instead just have empty tables for them in your app script, and instead fill in the tables in*UpdateActions()*function instead.
Here's an example from the DataUtil app, with one action that works differently based on the options selected at the moment:
```
actions = {
    {
        name = "Action",
        run = function(target)
            if app.options.save.enabled then
                Spectrum.SaveDataPoint(target.data)
            end
            if app.options.delete.enabled then
                Spectrum.DeleteDataPoint(target.data)
            end
        end,
    },
},

options = {
    save = {
        name = "Save data",
        enabled = true,
    },
    delete = {
        name = "Delete data",
        enabled = false,
    },
},
```
### Actions table
Actions table defines what interactions the app has. The first action is always automatically used when the app is triggered in 3rd-person mode. When using the app from the RadialUI, if there's more than one action, the player gets a popup menu from which to choose the desired action.
```
actions = {
        {
            name = "DefaultAction",
            run = function(target)
                -- In 3rd person mode executing app will always trigger first action
            end,
        },
        {
            name = "ExtraAction",
            cost = 2,
            run = function(target)
                -- In radial menu mode if there's more than one action, triggering the app opens a popup menu to select which action to take.
            end,
        },
    },
```
| Name | Required/Optional | Description |
| --- | --- | --- |
| name | required | The name displayed to player when showing multiple actions in RadialUI |
| cost | optional | How many NetPoints are required to use this action |
| run | required | Function that gets executed when the player triggers the action |

The run function gets passed*target information*when the action is triggered.
### Options table
Options table lets you create some additional toggleable settings for your app. They can be accessed from both AppWheel and the RadialUI by pressing the app options button (by default d-pad down on a controller). Each options represents a true/false value which you can then check elsewhere in your app script (in an action, for example) to change the app's behaviour.
```
options = {
     someOption = {
          name = "Some option",
          enabled = true,
     },
     anotherOption = {
          name = "Some other option",
          enabled = false,
          OnOptionChange = function()
                -- This runs when the option is toggled.
          end
     },
},
```
| Name | Required/Optional | Description |
| --- | --- | --- |
| name | required | The name displayed to player in the app options menu |
| enabled | required | true/false. The value in your script will be sued as the starting value. |
| OnOptionChange | required | Function that gets executed the option is toggled. |

Typical use for the OnOptionChange() function would be to change the icon in app's Status window to reflect what the app is set to do at the moment.
## Functions
There are a few functions that the game tries to call in different situations, so depending on the app you are making you might want to include some of these in your script.
### OnStateChange()
OnStateChange function handles the game requesting the app to change it's state, to turn the app on, or off, and so on, either because the player pressed a button to do so, or some other Lua script or game system asked for it. Ultimately, the app itself gets to decide how to handle the request, although usually you would want the app to comply. When the game calls this function, it will pass the requested*app state*to the function.
The minimun you should do is to se tthe app's state to the requested one, and then trigger the built-in API function to tell the game to change state there as well:
```
OnStateChange = function(state)
    app.state = state
    SetState(app.state)
end,
```
If the app script doesn't include OnStateChange() function, the game assumes this is all you want to do and as a fallback solution handles it for you automatically.
You can also add additional things the app should do when changing the state, for example to show or hide a*status window*as the app is toggled on and off:
```
OnStateChange = function(state)
    if state == AppState.on then
        CreateStatusWindow()
        SetStatusIcon(1)
        SetStatusIconColor(Color.LightGrey)
        DisplayStatusWindow(true)
    elseif state == AppState.off then
        RemoveStatusWindow()
    end
    app.state = state
    SetState(app.state)
end,
```
### UpdateActions()
If the app has UpdateActions() function, it's called when the player has selected a target and presses a button to trigger the app. It let's you rewrite the app's*action table*to change what the app does, or what kind of actions the player can take. The game passes the app*target information*when calling this function.
One option would be to just rewrite the whole actions table based on target type:
```
UpdateActions = function(target)

        if target.type == TargetType.Hackable then
            app.actions = {
                {
                    --
                },
                {
                    --
                },
            }
        else if target.type == TargetType.Character then
            app.actions = {
                {
                    --
                },
            }
        else
            app.actions = {}
        end

    end,
```
You can also use this to dynamically create a list of actions. The following code checks if the target is either a hackable device or a character (so, a target type that you can receive data), and then uses the Player API to get a list of files in player's inventory and adds a new action each file:
```
UpdateActions = function(target)

        if target.type == TargetType.Hackable or target.type == TargetType.Character then
            app.actions = {
                {
                    name = "Select file to send:",
                }
            }
            playerFiles = Player.GetAllDataFiles()
            for _, file in ipairs(playerFiles) do
                newAction = {}
                newAction.name = file.name
                newAction.cost = 1
                newAction.run = function(target)
                    message = string.format("Sending file %s to %s", file.name, target.name)
                    UI.ShowPopUp(PopupType.progress, "FileShare", message, 3)
                    Scheduler.CallInSecsReal(function()
                        Player.SendData(file.internalName, target.name)
                    end, 3)
                end
                table.insert(app.actions, newAction)
            end
        else
            app.actions = {}
        end

    end,
```
### Update()
If the app script has Update() function, it will be called regularly by the game. This allows your apps to do things continuously in the background. The update rate is once every 0.2 seconds, and the game will pass current*time*as the parameter.
The Update function is called regardless of the app's current state, so it's up to you to choose if the app should only do things when it's switched on (which would be the usual case) or if you want the app to continue running in the background.
If the app table includes a cost value (in contrary to the cost defined in actions), this will get applied every tick the update runs.
A good example of app using the Update function would be the light monitor app, which checks the light level continuously and then updates that to a*status window*:
```
Update = function()
    if state == AppState.on then
        lightLevel = Player.GetLightLevel()
        if lightLevel < 0.06 then
            SetStatusIconColor(Color.Green)
        elseif lightLevel < 0.15 then
            SetStatusIconColor(Color.Blue)
        else
            SetStatusIconColor(Color.LightGrey)
        end
        statusText = string.format("%.1f %%", lightLevel * 100)
        UpdateStatusWindow(statusText)
    end
end,
```
## Data types
### Target types
These are the types of targets available from the game's targeting system. Using*TargetType.None*allows the app to work without requiring a target at all. The values are used in the game internally for bitmasking multiple target types at the same time, and in general won't be needed for anything in Lua side, you can just use the more convenient text version in your script.
| Type | Value | Description |
| --- | --- | --- |
| TargetType.None | 0 | No target. Use for apps which don't require any target at all. |
| TargetType.Data | 1 | Any data points currently visible to the player |
| TargetType.Interaction | 2 | Physical interactions in the levels |
| TargetType.Hackable | 4 | Hackable devices in player's current networks |
| TargetType.Character | 8 | People |
### Menu options
| Name | Description |
| --- | --- |
| AppMenuState.always | App is always displayed in this menu. |
| AppMenuState.never | App will never be shown in this menu |
| AppMenuState.byDefault | App will be set as favourite for this menu by default (but can be removed by player) |
| AppMenuState.target | App will always display in Radial menu if current target matches one of the target types for the app. |
### App states
| Name | Description |
| --- | --- |
| AppState.unavailable | The player doesn't have this app yet |
| AppState.disabled | App can't be used at the moment, for example no network connection |
| AppState.off | App is not doing anything |
| AppState.on | App is switched on and running in the background |
| AppState.alert | App displays alert to notify the player about something |
### time
The game will pass a*time*value to the*Update function*. This is just counting seconds from when the game was started. (Equal to Unity's[Time.time](https://web.archive.org/web/20200807123154/https://docs.unity3d.com/ScriptReference/Time-time.html))
### target
When the game runs the UpdateActions function, or triggers an action, it will pass*target*table to the app script. This contains some information about the current target:
| Data | Description |
| --- | --- |
| target.name | the internalName of the current target object |
| target.type | *TargetType*of the current target |
| target.missionObject | Set if the target is a MissionObject.(Check the missionObject table for more details) |
| target.data | Set for data targets. Contain s a table with more information (see data table for details) |
| target.interactionType | Set on interaction targets, this will contain the interactionType |
| target.macAddress | Set on device targets. Contains the device's MAC address as a string. |
If the app's targets list includes TargetType.None, and there is no target selected when UpdateAction() or some action is triggered, the target.name will be an empty string, and target.type is set to TargetType.None.
## Built-in functions
### Status window
Adding a status window for your app lets you display a small message window for the player near the top left corner of the screen. The windows can have an icon, and a small piece of text. While there's no hard limit on text length (for now, at least), it's best to keep things really short to avoid conflicts with how many other apps the player might be running at the same time, and to allow all of them enough screen space.
The LightMontior app is a good example of using status windows:
```
OnStateChange = function(state)
        if state == AppState.on then
            --UI.ToggleLightMonitor(true)
            CreateStatusWindow()
            SetStatusIcon(1)
            SetStatusIconColor(Color.LightGrey)
            DisplayStatusWindow(true)
        elseif state == AppState.off then
            --UI.ToggleLightMonitor(false)
            RemoveStatusWindow()
        end
        app.state = state
        SetState(app.state)
    end,

    Update = function()
        -- Get player light value
        lightLevel = Player.GetLightLevel()
        -- change icon color:
        if lightLevel < 0.06 then
            SetStatusIconColor(Color.Green)
        elseif lightLevel < 0.15 then
            SetStatusIconColor(Color.Blue)
        else
            SetStatusIconColor(Color.LightGrey)
        end
        -- update status text
        statusText = string.format("%.1f %%", lightLevel * 100)
        UpdateStatusWindow(statusText)
    end,
```
So, what happens here is we use OnStateChange() to check if the app has been turned on, and if that's the case then we ask the game to create a status window for the app. It's going to be empty, and invisible, to start with. Next we assign an icon for it (first one form the*status icons*list in the app definition) and set that icon's color to light grey (which matches nicely with rest of the UI content). When all that is done,. we tell the game to actually show the window.
The, in the Update() function, we check the light level, and based on it we change the status icon's color, and then also parse the light level into a nice format to display to user.
Finally, in OnStateChange() function, we make sure to remove the status window when the app is switched off.
We*could*just choose to show and hide the window as needed, and in some cases you might want to do that in Update() or something to only display the window part of the time. It's still best to actually remove the window completely when the app is not running.
All the functions to handle status windows are explained better below:
#### CreateStatusWindow()
This is just a simple instruction for the game that you want your app to have a status window. No further options, the game will create the window for you, with a default Off Grid logo as icon, and no text. The window will be hidden by default.
#### DisplayStatusWindow()
Use`DisplayStatusWindow(true)`and`DisplayStatusWindow(false)`to show and hide the window.
#### RemoveStatusWindow()
When a window is not needed any longer, for example when the app is switched off, use this to remove it from the UI.
#### SetStatusIcon()
SetStatusIcon() sets the status window's icon to one of the icons defined in the statusIcons list in your app definition. Keep in mind that unlike most programming languages, Lua lists start from 1, so to se the first icon you'd run`SetStatusIcon(1)`.
#### SetStatusIconColor()
If you want to change the icon color, SetStatusIconColor() lets you do that. As with everything else in Off Grid scripting, you can either define the color as RGBA values, or use one of our pre-defined colors.
For the best results you should make your original icon image pure white, the color set here will multiply any color values from the icon image with the new color, so anything else than white (or at least grayscale) icon mgiht result in unexpected colors...
using pre-defined color:
```
SetStatusIconColor(Color.Blue)
```
using a table to define red, green, blue and alpha values:
```
SetStatusIconColor({0.2, 0.4, 0.9, 1.0})
```
### App state
As explained in the*OnStateChange()*, to make sure it's always the Lua app that determines what the app does (perhaps excluding some extreme cases like player phone shutting down due to running out of battery etc), nothing on the game side can directly tell the app to change it's state. Instead, the game will*ask*the Lua app to do so, and the app can then do it, or choose not to. Once you have determined what the app does, you should then communicate that back to the game, using SetState() function.
#### SetState()
Use`SetState(app.state)`to set the App's state on the game side to match the state your Lua script is in at the moment. This will be reflected on the app's icon color in AppWheel/RadialUI, and also in player being able to (or not) to use the app.
## Apps in your mission and other scripts
Some of the app functionality can be triggered from your other Lua scripts. Most commonly, you'd want use this to make apps available to the player during your mission rather than from the start, but there are of course more creative ways to make use of the API. It's worth remembering, though, that in the end it's the App's Lua script that determines what the app does, anything else can only*request*it to do something.
### Apps API
The full Apps Lua API is documented [here](Apps_Lua API).
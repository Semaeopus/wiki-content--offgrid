Creating Device UIs
===================

Before you start with the device UIs, yo should be familiar with the [device scripting](OffGrid:Device_Scripting "wikilink") in general.

While device Lua script as a whole describes how the device behaves and reacts to certain things, this document focuses on the part about
creating UI, either for when the player physically interacts with the device, or connects to it remotely using Apps.

Also make sure to check out *StreamingAssets/Common/Devices/* and *StreamingAssets/Common/DeviceThemes/* for some examples and ideas. The
*StreamingAssets/Common/Devices/Templates/* folder also contains some scripts intended for you to copy into your missions and use as starting
points for your own devices.

Basics
------

Devices can have two separate UIs at the same time, *localUI* used for physical interaction with the device, and *remoteUI* used when player
uses apps to access the device remotely. The usual [canAccess()](OffGrid:Device_Scripting#Device_Access "wikilink") and
requirement for player and the device to be connected in same network will only apply to remote access, while we'll by default assume local
access is always possible. (you can, of course, limit the local access by adding some kind of check in your UI itself, or limit it through
other means in your mission script for example).

Apart from the way how the player accesses these UIs, they are just the same, with same supported features (depending on which UI Type you go
for of course) and both running as part of the same device Lua VM so they can both access any data on the device and any global variables in
the device's Lua script.

You can of course choose if you want to add one or the other only, both, or no UI at all for your device.

Both UIs are defined in the device table:

``` lua
device = {
    canAccess = function()
        return true
    end,
    localUI = {
        type = DeviceUITypes.Modern,
        theme = "Modern_Default",
        pages = {},
    }
    remoteUI = {
        type = DeviceUITypes.Ncurses,
        header = [[SnackMaster (TM) Co. Soda Machine Settings]],
        backgroundColour = {0.56, 0.15, 0.13},
        highlightColour = {0.85, 0.85, 0.85},
        buttons = {}
    }
}
```

Note that the definitions are slightly different based on which UI type you are using. the details for different types will be explained below.

There's also more than one way to add the contents to the pages/buttons tables. As long as a valid UI table exists in the end, it's up to you
you want to do it. For a simple UI it might be easiest to just define the contents directly in the pages/buttons table. For a more complex UI
it can be easier to just define an empty table first, and then define and add each page/button to it one by one in your script. For more
complex device behaviours and UIs you might even want to create some function that generate the contents and populate the pages for you...

UI Types
--------

When creating your UI, you get to choose between different UI styles, each with a different styling and supported features. The two currently
implemented styles are Ncurses and Modern.

[Ncurses](OffGrid:Device_UIs#Ncurses "wikilink") is a two-panel layout visually resembling a TUI ( a Text-based use interface), not unlike what you'd see done with the popular ncurses library in real life. This might be a good for for a backend UI on a device, something intended for technical people, administrators etc, rather than as the primary user interface for the end users. The layout is fixed, but the colors can be changed for a bit of customization.

[Modern](OffGrid:Device_UIs#Modern "wikilink"), on the other hand, is a more full-featured, intended for creating all kinds of simple front-end UIs intended for the end user. Be it a smart fridge, a combination lock, a vending machine, or printer. It supports graphics assets (both for the UI styling itself, and as content) and separate re-usable theme files.

Ncurses
-------

For the simpler Ncurses UI, the header is always the same and is defined directly in the UI table. Same goes for the background & foreground
colors, which are set as table of red, green & blue values (in 0-1 range).

The UI contents consists of the *buttons*-table, each item inside it being a button on the left side panel of the device UI. Each button can
then have a sub-buttons table to describe what is displayed on the right-side panel after clicking that button.

For example,. the UI below has two items on left panel, *system* and *log*. Clicking on the system-button will set the right-side panel to
show *powerswitch*, *social*, *test* and *morespeed.*

The items will display their name & description in the UI. Any item with no *onClick* function defined will be displayed as a simple text item
rather than a clickable button.

Note that you can change the contents of the buttons-table (or sub-buttons of any button) at runtime or when some other button is
clicked. Just call the global to refresh the UI afterwards (either *RefreshLocalUI()* or *RefreshRemoteUI()* ) to get the game to read and display the new contents..

``` lua
remoteUI = {
    type = DeviceUITypes.Ncurses,
    updateEveryFrame = false,
    header = [[<link>SnackMaster (TM) Co.</link> Soda Machine Settings]],
    backgroundColour = {0.56, 0.15, 0.13},
    highlightColour = {0.85, 0.85, 0.85},
    buttons = {
        system = {
            name = "Settings",
            desc = "System & product settings.",
            onClick = function()
                print("Opening soda machine system settings")
            end,
            subButtons = {
                powerswitch = {
                    name = "Power \[ON\]",
                    desc = "",
                    onClick = function()
                        TogglePower()
                    end,
                },
                social = {
                    name = "Social media integration \[OFF\]",
                    desc = "Control social media integration",
                    onClick = function()
                        ToggleSocial()
                    end,
                },
                test = {
                    name = "Test vending mechanism",
                    desc = "Deliver a single can",
                    onClick = function()
                        Devices.RunOnce(DeviceName)
                    end,
                },
                morespeed = {
                    name = "Vending mechanism force [5]",
                    desc = "Calibrate force used to deliver cans",
                    onClick = function()
                        ChangeForce()
                    end,
                },
            }
        },
        logs = {
            name = "Sales data",
            desc = "View sales log files",
            onClick = function()
                print("Opening sodamachine logs")
            end,
            subButtons = {
                auth = {
                    name = "sales.csv",
                },
            }
        }
    }
}
```

Modern
------

Modern UI type is designed to support as wide as possible set of graphical UIs while still keeping things as simple as possible. Instead
of the two-panel layout and fixed setup about buttons on left panel and sub-button on right, the Modern UI works by crating separate UI pages,
and navigating between them. Because of more flexible graphics support, the UI look is mostly defined in separate
[deviceTheme](OffGrid:Device_UIs#Modern_UI_Themes "wikilink") files (but can be [overridden](OffGrid:Device_UIs#Overrides "wikilink") per item as well). Layout, title etc are set per each page rather than for the whole UI.

At the simplest, a modern UI can be defined like this:

``` lua
    remoteUI = {
        type = DeviceUITypes.Modern,
        theme = "Modern_Default",
        pages = {},
    }
```

### UI Pages
Pages are where all the actual content of Modern UI happens. Each page you create can set it's own
[layout](OffGrid:Device_UIs#UI_Layouts "wikilink") and [title](OffGrid:Device_UIs#Title_area "wikilink"), and of course it's own contents as well. One of the pages should set *homePage = true* to set it as the default page that'll show when the player first opens the UI. Beyond that, you can use the [SwitchPage()](OffGrid:Device_UIs#SwitchPage() "wikilink") call to navigate between different pages.

The following example code creates a page called "home" in the device's *remoteUI*, sets it as the home page for the UI, override's the [theme's](OffGrid:Device_UIs#Modern_UI_Themes "wikilink") background picture and color, and then adds two buttons for navigating to other pages:

``` lua
device.remoteUI.pages.home = {
    layout = PageLayout.Grid,
    homePage = true,
    background = "homeBackground.png",
    background_color = "#424242",
    title = "Semaeopus Ltd. Server OS - Admin Terminal",
    content = {
        settings = {
            text = "Settings",
            itemType = DeviceUIItemTypes.Button,
            icon = "icons/settings.png",
            onClick = function()
                SwitchPage("settings")
            end
        },
        files = {
            text = "File Manager",
            itemType = DeviceUIItemTypes.Button,
            icon = "icons/files.png",
            overlay = true,
            onClick = function()
                UpdateFiles()
                SwitchPage("files")
            end
        },
    }
}
```

### UI Sizes

Modern UI style has two different UI sizes to choose from:

-   Normal: 1280 x 720
-   Small: 440 x 720

The size is defined in the UI theme, and can't be changed between individual pages.

### Title area

The top part of the Modern UI pages is used for a title area, which can have it's own background image, and can be sued to display some text content outside of the main content area.

Title area is by default 100 pixels tall, but the height can be set in the UI theme (or overridden in the device script for each page).

If you don't want a title area, you can either set the height to 0, or set it to sue a transparent background and just not set any title text.

### Content Area

The content area is where all the actual page contents go. It's by default the whole UI page (minus the title area), but you can set margins as needed to limit it to smaller part of the page. If the contents exceed the content area, a 10px wide scrollbar will automatically be shown on right side. HOw the contents are displayed on the area depends on which UI Layout the page was set to use.

### UI Layouts

You also get two different layouts for the UI contents. Layout is separate for each page. List layout is suitable for most of the use cases, and supports most of the content item types as well. Grid layout, on the other hand, is specifically for creating icons in a grid layout (say, for an apps menu on a device, number pad on a combination lock, or file icons in a file browser). Grid layout only supports Button and Empty item types.

#### Grid

Grid layout shows it's contents on a grid, each item being 120x110 pixels in size. Items are added to the grid starting from top left corner, and it's then filled left to right, with new rows added as needed.

If you want to skip over a slot on the grid, you can add an Empty-type item

For actual content (besides the empty item) the Grid layout only supports Button items, each one the same size, with an icon displayed on top, and bit of space for text underneath.

#### List

List is the more versatile layout of the two, with wider variety of supported items including headings, horizontal spacers, images, and text blocks. Item sizes are not fixed so you can add as long piece of text as you want, for example. The content area is just filled from top to bottom with whatever contents you add.

### UI Items

#### Button

Button is the one functional item of the Modern UI, displayed either s a 120x110 pixel square with an icon and bit of text underneath (on Grid layout) or a full-width clickable button with an icon on left side (on the List layout).

Clicking the Button will execute what ever code is in it's onClick function. You can use them just to switch between different pages, but ultimately all the powers of Off Grid's Lua API and, of course Lua itself, are available for you here!

``` lua
myButton = {
    text = "File Manager",
    itemType = DeviceUIItemTypes.Button,
    onClick = function()
        UpdateFiles()
        SwitchPage("files")
    end
}
```

#### Text

Can't get much simpler than this, the Text item will display a block of text in the UI.

``` lua
myText = {
    text = "File Manager",
    itemType = DeviceUIItemTypes.Text,
}
```

#### Heading

Heading will display a line of text, with a different styling and an optional icon on the left side.

``` lua
myHeading = {
    text = "File Manager",
    itemType = DeviceUIItemTypes.Heading,
}
```

#### Image

Like the name says, Image will show an image in the UI. The image path is relative to the device script (either in mission folders or in Common), PNG and JPEG images are supported, and the image will be displayed as large as possible in the UI, limited by horizontal space, maintaining the original image's aspect ratio.

``` lua
myButton = {
    image = "myimage.png",
    itemType = DeviceUIItemTypes.Image,
}
```

#### Spacer

Spacer shows a simple horizontal line in the List layout.

``` lua
mySpacer = {
    itemType = DeviceUIItemTypes.Button,
}
```

#### Empty

Empty creates an invisible and non-interactive item in the Grid layout, in practice skipping over a slot in the layout.

``` lua
myButton = {
    itemType = DeviceUIItemTypes.Empty,
}
```

### Modern UI Themes

To keep the device scripts at least a bit more manageable, and to allow reusing and sharing UI styles and graphics between multiple devices (and levels), Modern UIs use a theme system. Each theme consists of a folder with a deviceTheme Lua file, plus any images to go with it. When setting up your UI, you choose the theme (by name) in the UI table, and that theme will then set the [size](OffGrid:Device_UIs#UI_Sizes "wikilink") and the look of the UI. You are not limited to the theme, though, as most of the same settings can be [overriden](OffGrid:Device_UIs#Overrides "wikilink") for each individual item as needed in your device script.

Theme files should be named as deviceTheme\*.lua, and the game will attempt to load available themes both form the *StreamingAssets/Common/DeviceThemes/* and from a *DeviceThemes* folder in the current mission.

Colors are defined as HTML-style hex codes, in \#RRGGBB or \#RRGGBBAA format.

Image paths in theme scripts should be relative to the theme file itself.

If you know for sure your theme will only ever be used with device UIs that only use one layout, it's safe to leave out the other one in the theme definition. Similarly, you don't need to define every possible item and value here, the theme system will use built-in defaults for any missing value, or in some case tries to re-use a related value you \*do\* have defined. For example if the theme sets button image for the default state, but not for the selected & disabled states, the default state image will be used for all three.

``` lua
deviceTheme = {

    name = "Modern_Default",
    size = DeviceUISizes.Normal,

    grid = {
        title_color = "#7cafc2",
        title_background_color = "#585858",
        title_background_image = {
            image = "title_background.png",
            borders = {0, 16, 16, 16}
        },

        background_color = "#e8e8e8",
        background_image = "grid_background.png",

        button_color_default = "#d8d8d8",
        button_color_disabled = "#58585880",
        button_color_selected = "#a1b56c",

        button_background_image_default = {
            image = "button_background_default.png",
            borders = {16, 16, 16, 16}
        },
        button_background_image_disabled = {
            image = "button_background_default.png",
            borders = {16, 16, 16, 16}
        },
        button_background_image_selected = {
            image = "button_background_selected.png",
            borders = {16, 16, 16, 16}
        },
        button_padding = {0, 0, 0, 0},

        button_icon_image = "icon_default.png",
        button_icon_color = "#484848",
        button_overlay_image = "grid_button_overlay.png",
        heading_icon_color = "#7cafc2",

        button_text_color_default = "#383838",
        button_text_color_disabled = "#383838",
        button_text_color_selected = "#282828"

    },

    list = {
        title_color = "#7cafc2",
        title_background_color = "#585858",
        title_background_image = {
            image = "title_background.png",
            borders = {0, 16, 16, 16}
        },

        background_color = "#e8e8e8",
        background_image = "list_background.png",

        button_color_default = "#d8d8d8",
        button_color_disabled = "#58585880",
        button_color_selected = "#a1b56c",

        button_background_image_default = {
            image = "button_background_default.png",
            borders = {16, 16, 16, 16}
        },
        button_background_image_disabled = {
            image = "button_background_default.png",
            borders = {16, 16, 16, 16}
        },
        button_background_image_selected = {
            image = "button_background_selected.png",
            borders = {16, 16, 16, 16}
        },
        button_padding = {10, 0, 10, 0},

        button_icon_image = "icon_default.png",
        button_icon_color = "#484848",
        heading_icon_image = "icon_default.png",
        heading_icon_color = "#7cafc2",

        button_text_color_default = "#383838",
        button_text_color_disabled = "#383838",
        button_text_color_selected = "#282828",

        text_color = "#383838",
        heading_color = "#7cafc2",
        spacer_color = "#585858"
    }
}
```

### Images and 9-slicing

Images can be defined in two different ways. The simple way of just using a path to the image file will just display the image as is, so it's best used when the image is exactly the correct size for the UI item:

``` lua
button_background_image_default = "button_background_default.png"
```

The second way allows creating 9-sliced images, so they'll stretch cleanly to different UI item sizes. Rather than setting the image to a path, we set it to a table that contains two items, the image path, and a borders-table that defines the slice borders (in pixels) for top, right, bottom and left sides.

``` lua
button_background_image_default = {
    image = "button_background_default.png",
    borders = {16, 16, 16, 16}
}
```

Image paths can be relative to the device script location, or to root of the theme folder. Both the mission folders, and equivalent locations in StremingAssets/Common/, are checked automatically.

### Overrides

Most of the things defined in the UI theme can also be set on per-item basis in your device script, effectively overriding that part of the them for that specific UI item. this allows for much more varied content, and dynamically changing things in more complex UIs and devices. Sometimes setting something i the device script rather than the theme is the only way, like when setting the "image"-value for an Image item, or setting the overlay graphic enabled for a specific button on Grid layout.

See the table below for more details on which exact things can be overridden.

### Supported Features

| Feature                             | Grid | List | Override | Notes                                                        |
|-------------------------------------|------|------|----------|--------------------------------------------------------------|
| background\_color                   | X    | X    | \-       |                                                              |
| background\_image                   | X    | X    | X        |                                                              |
| overlay\_image                      | X    | X    | \-       | overlay image will be dispalyed on top of the whole UI       |
| Title                               |      |      |          |                                                              |
| title\_height                       | X    | X    | X        | defaults to 100                                              |
| title\_color                        | X    | X    | X        |                                                              |
| title\_background\_color            | X    | X    | X        |                                                              |
| title\_background\_image            | X    | X    | X        |                                                              |
| Content                             |      |      |          |                                                              |
| margins                             | X    | X    | X        |                                                              |
| text\_color                         | \-   | X    | X        |                                                              |
| heading\_color                      | \-   | X    | X        |                                                              |
| heading\_icon\_color                | \-   | X    | X        |                                                              |
| heading\_icon\_image                | \-   | X    | X        |                                                              |
| spacer\_color                       | \-   | X    | \-       |                                                              |
| image                               | \-   | \-   | X        |                                                              |
| Buttons                             |      |      |          |                                                              |
| button\_color\_default              | X    | X    | X        |                                                              |
| button\_color\_disabled             | X    | X    | X        |                                                              |
| button\_color\_selected             | X    | X    | X        |                                                              |
| button\_background\_image\_default  | X    | X    | X        |                                                              |
| button\_background\_image\_disabled | X    | X    | X        |                                                              |
| button\_background\_image\_selected | X    | X    | X        |                                                              |
| button\_padding                     | X    | X    | X        |                                                              |
| button\_icon\_image                 | X    | X    | X        |                                                              |
| button\_icon\_color                 | X    | X    | X        |                                                              |
| button\_overlay\_image              | X    | \-   | X        |                                                              |
| overlay                             | \-   | \-   | X        | Set this to true as override in a button to show the overlay |
| button\_text\_color\_default        | X    | X    | X        |                                                              |
| button\_text\_color\_disabled       | X    | X    | X        |                                                              |
| button\_text\_color\_selected       | X    | X    | X        |                                                              |

Global functions
----------------

There are a couple of global functions related to the device UIs:

### RefreshLocalUI()

*RefreshLocalUI()* triggers the game to re-read the localUI table and update the UI in game accordingly. Call this after making changes to the localUI contents.

If you want to, you can alternatively set *updateEveryFrame = true* in the UI table, and the UI will then automatically refresh each frame while the game is running, without needing to call the refresh function yourself. This is, in general, not recommended for performance reasons, and it's best to just manually refresh the UI when needed.

### RefreshRemoteUI()

Same as RefreshLocalUI, but for the *remoteUI*

### SwitchPage()

*SwitchPage()* is used on the Modern UI type, and triggers the UI to switch to the page you want. For example *SwitchPage("home")* will attmept to switch to a page called "home". (If no such pages exists in the content table, nothing will happen)

Useful code examples
--------------------

### Device inventories

This is a nice way to create a page (for the modern UI) that automatically lists buttons for each data file in the device's inventory.

First we define a new page. We'll also add a "back"-button to it to return the player back to home page.

``` lua
device.remoteUI.pages.files = {
    layout = PageLayout.List,
    title = "Files",
    content = {
        back = {
            itemType = DeviceUIItemTypes.Button,
            text = "Back",
            icon = "back.png",
            onClick = function()
                SwitchPage("home")
            end
        }
    }
}
```

Next we want to create a function to populate that page for us automatically.

We'll create a new empty table for the page's contents, and then use the \`GetDeviceInventory()\` global to get all of the device's data inventory contents. This will return us a table of the C\# native DataPointInfo objects, allowing us both to grab useful info form them, and to use the objects as direct references to data on Unity side for API calls to handle data.

Then to populate the page, we'll iterate through all of that data table, and create a new UI item for each one. Setting the item type to Button allows us to add onClick function, in which we can add whatever we want to happen when the players clicks on that file. In this case we'll use DataPoints.SaveToPlayerInventroy() so the player can "download" files directly from the device. After creating each button, we insert it into the page's content table.

Last, we'll add a back-button so the player has some way to return back to home page.

``` lua
function UpdateFiles()
    device.remoteUI.pages.files.content = {}
    local allFiles = GetDeviceInventory()
    for internalName, dataPointInfo in pairs(allFiles) do
        local newFileItem = {}
        newFileItem.itemType = DeviceUIItemTypes.Button
        newFileItem.text = dataPointInfo.dataPointName
        newFileItem.icon = "files.png"
        newFileItem.onClick = function()
            DataPoints.SaveToPlayerInventory(dataPointInfo)
        end
        table.insert(device.remoteUI.pages.files.content, newFileItem)
    end
    local back = {
        itemType = DeviceUIItemTypes.Button,
        text = "Back",
        icon = "back.png",
        onClick = function()
            SwitchPage("home")
        end
    }
    table.insert(device.remoteUI.pages.files.content, back)
end
```

Now all we need to do is add something somewhere for the player to access this page. We'll also want to call the \`UpdateFiles()\` function before switching the page. We can do that, for example, by adding the following button item to the home page:

``` lua
files = {
    text = "File Manager",
    itemType = DeviceUIItemTypes.Button,
    icon = "files.png",
    onClick = function()
        UpdateFiles()
        SwitchPage("files")
    end
},
```

### Combination Lock

This example can also be found in *StreamingAssets/Common/Devices/Templates/Keypad\_touchscreen\_Template.lua**,* and the related theme files are in *StreamingAssets/Common/DeviceThemes/Keypad\_Default/*.

Rather than defining all of the UI contents manually, this example uses a bit more of Lua scripting to create a numeric lock that can be configured to unlock a specific door with the specified code set in the Configuration section at the top. The code will then automatically generate the number buttons, and even enables the overlay on the buttons used in the specified code to show some fingerprints on the right buttons.

``` lua
-- Configuration: --------------------------------------------
local code = {1,9,8,4}
local doorID = "Door_Slide-Double_01"

local buttonOrder = {7,8,9,4,5,6,1,2,3,"empty",0,"reset"}
-- -----------------------------------------------------------

local isOpened = false

local entryIndex = 1
local enteredCode = {}

local Reset
local NumberButtonClick
local CheckCode

device = {
    canAccess = function()
        return true
    end,
    localUI = {
        type = DeviceUITypes.Modern,
        theme = "Keypad_Default",
        updateEveryFrame = false,
        pages = {},
    }
}

device.localUI.pages.home = {
    layout = PageLayout.Grid,
    homePage = true,
    title = "<size=60><b>****</b></size>",
    content = {}
}

function NumberButtonClick(number)
    enteredCode[entryIndex] = number
    UpdateCodeText()
    entryIndex = entryIndex + 1
    if entryIndex > #code then
        CheckCode()
    end
end

function UpdateCodeText()
    local textTable = {}
    table.insert(textTable, "<size=60><b>")
    for i = 1, entryIndex, 1 do
        table.insert(textTable, enteredCode[i])
    end
    for j = entryIndex+1, #code, 1 do
        table.insert(textTable, "*")
    end
    table.insert(textTable, "</b></size>")
    device.localUI.pages.home.title = table.concat(textTable)
    RefreshLocalUI()
end

function CheckCode()

    local correctCode = true
    for c = 1, #code, 1 do 
        if code[c] ~= enteredCode[c] then
            correctCode = false
            break
        end
    end
    
    if correctCode == true then
        Correct()
    else
        Incorrect()
    end
    
end

function Correct()
    device.localUI.pages.home.title = "<size=40><b>ACCESS GRANTED</b></size>"
    Sound.TriggerEvent("Play_AccessGrantedSound")
    Doors.Unlock(doorID)
    Doors.Open(doorID)
    
    if isOpened == false then
        isOpened = true
    end
    RefreshLocalUI()
end

function Incorrect()
    device.localUI.pages.home.title = "<size=40><b>ACCESS DENIED</b></size>"
    Sound.TriggerEvent("Play_AccessDeniedSound")
    Reset()
    RefreshLocalUI()
end

function Reset()
    entryIndex = 1
    for i = 1, #code, 1 do
        -- reset the entered code table, fill with -1 as it's a number player can't enter so will never match the code.
        -- (this guarantees pressing enter with only part of the code entered will never work)
        enteredCode[i] = -1
    end
    device.localUI.pages.home.title = "<size=60><b>****</b></size>"
    RefreshLocalUI()
end

function TableContains(table, value)
    for _,v in pairs(table) do
        if v == value then
            return true
        end
    end
    return false
end

function GenerateButtons()
    for _,v in ipairs(buttonOrder) do
        local newButton = {}
        if v == "empty" then
            newButton.itemType = DeviceUIItemTypes.Empty
        elseif v == "reset" then
            newButton.itemType = DeviceUIItemTypes.Button
            newButton.text = "Reset"
            newButton.background_default = "c_default.png"
            newButton.background_selected = "c_selected.png"
            newButton.onClick = function() Reset() end
        else
            newButton.itemType = DeviceUIItemTypes.Button
            newButton.text = tostring(v)
            local default_bkg_name = v .. "_default.png"
            local selected_bkg_name = v .. "_selected.png"
            newButton.background_default = default_bkg_name
            newButton.background_selected = selected_bkg_name
            newButton.onClick = function() NumberButtonClick(v) end
            if TableContains(code, v) then
                newButton.overlay = true
            end
end
		table.insert(device.localUI.pages.home.content, newButton)
	end
end

GenerateButtons()
```
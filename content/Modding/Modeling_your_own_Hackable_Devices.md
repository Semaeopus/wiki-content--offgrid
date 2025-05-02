# Modeling_your_own_Hackable_Devices

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Modeling_your_own_Hackable_Devices*

*Scraped on: 2025-05-02 18:41:22*

## What's Required for a Hackable Object
fig 0.1
Hackable Objects should have some way to indicate benfg powered / active. This could be a lights, a screen, both, or something else. If you go for a light or a screen, need to be separate objects so the Materials can be switched around to show whether the Object has been Hacked or not.
If a Hackable Object has a screen we recommend conforming to either a 4x3 or 16x9 ratio. 4x3 is slightly more square and 16x9 is more rectangular. Having thse fixed ratios means it's easier to switch different screen graphics between different objects and have them all work in a consistent way.
4x3 Guide
16x9 Guide
## How to create a Screen for a Hackable Object
Blender is used for this tutorial. The Model for this Fuse Box is already finished, it requires a screen.
Step 1
Create a Plane.
Change the Scale of the plane to 16x9 (this will seem very big)
Step 2
Apply the Scale to the Plane.
Step 3
In Edit Mode; UV Unwrap the Plane.
Step 4
Apply a texture to the Plane to check the UV placement.
Step 5
Scale down the Plane and place it where you want the Screen to be.
You might need to adjust your geometry for the Plane to fit. Don't change the shape of the Plane as this will distort the UVs.
Step 6
Make sure that the Screen has a unique Material name. Then this is ready to export.
# Character_Colours

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Character_Colours*

*Scraped on: 2025-05-02 18:38:15*

## Colour lookup tables with UVs
The characters in Off Grid use a common material which switches out Colour Lookup Tables (LUTs) to change the colour of the Character's UVs. A LUT is a colour grid, each tile in the grid corresponds to a part of the Character's body.
Each LUT is a 64x64 pixel .png texture. Each tile in that texture is 8x8 pixels.
Character coloured in Blender
### Colors in the textures
#### Albedo
Character colours look-up table
The main texture is an Albedo colour map.
Most characters share a lot of tile positions.
The First Row of all characters is the same, it has the tiles for head, eyes, hair and facial hair.
The Second Row is for TorsoThe Third Row is for ArmsThe Fourth Row is for LegsThe Fifth Row is for Shoes
The Final 3 Rows are common across all characters and contain colours for hats and props.
#### Metallic + Smoothness
The second texture is a combined Metallic + Smoothness texture. The colour of the tile sets the smoothness of the material, with black for rough & diffuse, and white for smooth and reflective surface. The alpha value transitions between metallic (0.0) and non-metallic (1.0).
Only the colour texture is absolutely required, if the metallic+smoothness texture is left out the Character will be rendered with a simple diffuse material which will look fine in the game.
For more information on how Unity uses Metallic and Smoothness:[https://docs.unity3d.com/Manual/StandardShaderMaterialCharts.html](https://web.archive.org/web/20200814025633/https://docs.unity3d.com/Manual/StandardShaderMaterialCharts.html)
### Setting up the UVs
Each part of the model is UV'd to a single color tile
Matching character model's UVs to colors in the texture
Because Unity will compress the textures and that can possibly cause some issues like colour bleed around tile borders, it's best to leave a bit of extra space there. As we don't really need to cover any area of the texture in the UVs, just collapsing everything into single points and making sure that's more or less at the centre of a colour tile should work fine.
Model's UVs collapsed into points inside color tiles
## Skin and Hair
Skin and Hair colour ref
These values for skin and hair are used at the end of many LUTs to differentiate them from other version of the same LUT.
However any colour can be used for hair and skin as you like.
## Character LUTs
Many of these LUTs will work between all characters but to make sure the outcome is as expected use these guides when making new LUTs or altering existing LUTs.
### Vest
LUT version 2 working with Vest_Col_Security-Apostle
Vest LUT Examples
Vest_Col_Secuity
Waistcoat_Col_Biker
Vest_Col_Col_TruckerBlue
Vest_Col_SWAT
Vest_Col_WasteCollector
Vest_Col_Police
Vest_Col_Janitor
### LongJacket
LUT version 2 working with the colour map : LongJacket_Col_Docker
LongJacket LUT Examples
LongJacket_Col_BusDriver
LongJacket_Col_Docker
LongJacket_Col_Doctor
LongJacket_Col_HotelClerk
LongJacket_Col_Soldier
LongJacket_Col_Reporter
### SmartSuit
SmartSuit LUT
SmartSuit LUT Examples
SmartShirt_Col_Black_RedTie
SmartShirt_Col_Black_RedTie_Waistcoat
SmartShirt_Col_CourtClerk
### Waistcoat
Waistcoat LUT
Waistcoat LUT Examples
Waistcoat_Col_Biker
Waistcoat_Col_Denim
Waistcoat_Col_Builder
Waistcoat_Col_Docker
Waistcoat_Col_Editor
Waistcoat_Col_Porter
### Smart Jumper
Waistcoat LUT
Smart Jumper LUT Examples
SmartJumper_Col_Blue
SmartJumper_Col_Green
SmartJumper_Col_Red
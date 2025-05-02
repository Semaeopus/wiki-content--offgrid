# Asset_Creation_Pipeline

*Source: https://web.archive.org/web/20200808012308/https://wiki.offgridthegame.com/index.php?title=Asset_Creation_Pipeline*

*Scraped on: 2025-05-02 18:43:48*

## Creating Your First 3D Model
Using Unity as a mod editor means that you don't have to stick with just our models to build your levels, you can make your own, or edit ours to make the props and architecture that will fit your level.
Here is a quick guide with some conventions to follow so that your models will conform to our pipeline and *hopefully import easily.
##### Pre-requisites
First off you  will need a 3D modelling program, for this example we will be using Blender which is the recommended tool for creating assets for Off Grid
##### Setting Up Blender
Before we start creating 3D assets we need to set blender up properly. To start we will change Blenders rendering engine to  Cycles Render. This can be seen in `TO BE INSERTED  0.1`

`TO BE INSERTED fig 0.1`

Now that we have the correct render engine selected we must insure that blender is set to the correct units. A single Unity3D Unit is 1m, therefore we must set our unit preset to meters within Blender.This can be done by selecting scene properties and then selecting the drop down box under the units section. This can be seen in fig 0.2
`TO BE INSERTED fig 0.2`
Once you  have done that we just have to clean up our scene by removing the camera and the lamp. This can simply be done by right clicking them in the hierarchy and selecting delete.
##### Naming Conventions
Now that you have properly set up Blender you are free to create your 3D asset. An Important note while creating your asset is to insure that your 3D Asset follows Off Grids naming conventions:
* All​ ​asset​ ​names​ ​should​ ​use​ ​UpperCamelCase​ ​and​ ​end​ ​with​ ​the​ ​appropriate​ ​number​ ​scheme _01,​ ​_02,​ ​_03
* If​ ​an​ ​asset​ ​is​ ​completely​ ​specific​ ​to​ ​a​ ​location,​ ​for​ ​example​ ​a​ ​sign​ ​for​ ​a​ ​company​ ​building then​ ​the​ ​format​ ​to​ ​follow​ ​would​ ​be:
```
ObjectName-ObjectLocation_0X 

```
```
E.G​ ​-​ ​CompanySign-Bank_01

```
* If​ ​there​ ​are​ ​multiple​ ​variants​ ​of​ ​the​ ​asset​ ​and​ ​you​ ​feel​ ​that​ ​the​ ​asset​ ​needs​ ​further description​ ​then​ ​you​ ​should​ ​use​ ​the​ ​following​ ​format:
```
ObjectName-Adjective-ObjectLocation_0X

```
​​ or
```
​ObjectName-Adjective_0X 

```
```
E.G​ ​CompanySign-Big-Bank_01,​ ​CompanySign-Small-Bank_01,​ ​Fence-Mesh_01, Fence-Wooden_01 

```
* All​ ​mesh​ ​objects​ ​in​ ​Blender​ ​or​ ​your​ ​3D​ ​application​ ​of​ ​choice​ ​should​ ​use​ ​the​ ​postfix​ ​​_mesh
```
E.G​ ​CompanySign-Big-Bank_01_mesh,​ ​Fence-Mesh_01_mesh

```
Example of the correct hierarchy in Blender:
`TO BE INSERTED fig 0.3`
## Mesh Cleanup
Now that you have created your asset it is important to clean up any unnecessary Tris and insure the normals are facing outwards.**Important - Your asset ​should​ ​not​ ​exceed​ ​max​ ​150​ ​tris​ ​for an​ ​average​ ​model​ ​(dependant​ ​on​ ​scale​ ​of object)**
To check the Tris count of your asset all you need to do is select your asset and look at the top bar as shown in `TO BE INSERTED fig 0.4`
##### Normals
To check the normals of an asset while in the perspective window you must press **N** which will open a new panel scroll to the bottom of the panel until you find the **Shading section**. Once at the shading section toggle Backface Culling as shown in fig 0.5
`TO BE INSERTED fig 0.5`
Now that this option has been selected you may find parts of your asset are invisible like the cube on the left shown in fig 0.5, this is because the normals of the object are facing the incorrect way. To fix this you must flip the normals.To fix the normals you must be in edit mode and preferably in face selection mode. Now select the faces that need fixing.Navigate to the left panel shown in fig 0.6 if this is missing for you make sure you select the perspective window and press **T**. Select the Shading/UVs tab and click the button Flip Direction as shown in fig 0.6
`TO BE INSERTED fig 0.6`
## Vertex Painting
Now we need to add some colour to our asset. To do this we use Vertex painting. To apply vertex paint to your asset you need to select Vertex paint from the interaction mode drop-down box as shown in fig 0.7
`TO BE INSERTED fig 0.7`
To begin painting the model you have a few options:**Flood colour**with**Shift K**this will colour the entire selection. The other option is to paint vertices manually like a paint brush. To do this you must have the vertices you wish to paint selected.
`TO BE INSERTED fig 0.8`
In Fig 0.8 you can see the selection types highlighted, The square icon represents face selection and will allow you to select and paint whole faces on your mesh.
`TO BE INSERTED fig 0.9`
Here you can select any colour you wish using the colour wheel or you can select the Hex button to use hex codes to find a specific colour. Using the hex codes in the table below will allow you to match colours used within Off Grid.
### Vertex Colours(base)
| Hex code | Preview 
| --- | --- |
| #FFFBF0 | white​ ​walls​ ​etc. |
| #CCCCCC | Concrete,​ ​grey​ ​floors |
| #F0FAFF | window​ ​glass |
| #FFF7E8 | incandescent​ ​lights |
| #BD9364 | Cardboard |
| #4E4B4B | Tarmac |
| #82817E | Paving |
| #ADB2BD | Aluminium |
| #A97537 | Brass​ |
| #423D3D | Rubber​ |
| #D6B08D | Light ​wood |
| #8B4627 | Medium Wood |
| #753A1A | Dark Wood |
### Vertex Colours(Other)
For extended table of colors used in various models throughout the game, take a look at the [Extra_Colors](Extra_Colors.md) page.
### Off Grid Materials
**Names of possible materials in engine**
| Material name | Description | Has 2 sided |
| --- | --- | --- |
| Diffuse-Vertex | Simple​ ​diffuse​ ​shader | Yes |
| Specular-High-Vertex | Specular​ ​reflections​ ​(Mainly​ ​used​ ​for​ ​plastic), High Smoothness | Yes |
| Specular-Mid-Vertex | Specular​ ​reflections​ ​(Mainly​ ​used​ ​for​ ​plastic) Mid Smoothness | Yes |
| Specular-Low-Vertex | Specular​ ​reflections​ ​(Mainly​ ​used​ ​for​ ​plastic) Low Smoothness | Yes |
| Metallic-Vertex | Specular​ ​reflections​ ​for​ ​metal | Yes |
| Glass-Vertex | Transparent​ ​+​ ​Specular​ ​for​ ​glass | Yes |
| Illuminated-Vertex | Objects​ ​that​ ​illuminate​ ​such​ ​as​ ​screens​ ​and​ ​lights | Yes |
| ScriptControlledLamp | Screens,​ ​Lamps,​ ​etc​ ​that​ ​have​ ​their​ ​color​ ​& emission​ ​controlled​ ​by​ ​code. | No |

In​ ​cases​ ​where​ ​a​ ​mesh​ ​is​ ​one​ ​sided​ ​but​ ​can​ ​we​ ​seen​ ​from​ ​either​ ​side​ ​such​ ​as​ ​plant​ ​leaves or​ ​paper,​ ​use​ ​the​ ​two​ ​sided​ ​version​ ​of​ ​the​ ​above​ ​shaders.​ ​The​ ​naming​ ​convention​ ​simply adds​ ​the​ ​post​ ​fix​ ​“-2sided”.
For​ ​example,​ ​paper​ ​would​ ​use​ ​​Diffuse-Vertex-2sided and​ ​two​ ​sided​ ​glass​ ​would​ ​use Glass-Vertex-2sided
## Preparing To Export
Before you export your asset, it is important to ensure that you perform the following checks:
* Check that the scale is correct – This can be done by selecting the object and pressing N, which will allow you to verify that the scale is 1.0,1.0,1.0
* Check that the pivot is set to the correct place. The default place for setting your pivot should be the centre of the object unless the object is being placed on the ground in which case it would be Bottom centre.
* Check that edges are set to hard/sharp
* Check naming conventions are correct. See naming conventions
* Make sure your blender Export settings are as follows:
## Importing Your Model
To import into Unity, you can drag and drop your FBX file into the appropriate folder.
`TO BE INSERTED fig 11`
Once you have the asset in Unity it is important to check the import settings of your asset. To ensure your model displays correctly within unity make sure that:
* Material Naming is set to From Models material
* Material Search is set to Project-wide
Once set, your asset should display with the correct colours and materials that you have set in Blender.
`TO BE INSERTED fig 12`
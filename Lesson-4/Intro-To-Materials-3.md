---
layout: default
title:  "UE4 Intro to Materials 3"
---

# UE4 Intro To Materials - Page 3
_____ 

## Index
_____ 

* Part 1 - Getting Setup
1. [Getting Set Up](Intro-To-Materials-1#getting-set-up)
2. [Creating a Diffuse Map](Intro-To-Materials-2.html#creating-a-diffuse-map.html#starting-unreal-engine-4)


* Part 2 - Our First Material
1. [**Diffuse Only Material**](Intro-To-Materials-3.html#diffuse-only-material)
2. [Texture Coordinate](Intro-To-Materials-4.html#texture-coordinate)
3. [Normal Mapping](Intro-To-Materials-4.html#normal-mapping)
4. [Roughness and Metallic Constants](Intro-To-Materials-5.html#roughness-and-metallic-constants)

* Part 3 - Material Instances
1. [Material Instance Diffuse](Intro-To-Materials-5.html#material-instance-diffuse)
2. [Metallic and Roughness Parameters](Intro-To-Materials-6.html#metallic-and-roughness-parameters)
3. [Normal Map Parameter](Intro-To-Materials-6.html#normal-map-parameter)
4. [UV Parameters](Intro-To-Materials-6.html#uv-parameters)

* Part 4 - Masked and Transluscent Materials
1.  [Metallic Mask](Intro-To-Materials-7.html#metallic-mask)
2.  [Opacity Mask](Intro-To-Materials-7.html#opacity-mask)
4.  [Translucent Blend Mode](Intro-To-Materials-8.html#translucent-blend-mode)

* Part 5 - Illumination
1.  [Importing a Model](Intro-To-Materials-8.html#importing-a-model)
2.  [Bracket Material](Intro-To-Materials-8.html#bracket-material)
3.  [Lamp Material](Intro-To-Materials-9.html#lamp-material)

* Part 6 - More Material Concepts
1.  [Two Sided Material](Intro-To-Materials-10.html#two-sided-material)
2.  [Decals](Intro-To-Materials-10.html#decals)
3.  [Refraction and Fresnel](Intro-To-Materials-11.html#refraction-and-fresnel)
4. [World Aligned Materials](Intro-To-Materials-12.html#world-aligned-materials)
5.  [Animation](Intro-To-Materials-13.html#animation)

* Part 7 - A Practical Master Material
1.  [A Practical Master Material](Intro-To-Materials-14.html#a-practical-master-material)
2.  [A Practical Master Material Part II](Intro-To-Materials-15.html#a-practical-master-material-part-ii)
3.  [A Practical Master Material Part III](Intro-To-Materials-16.html#a-practical-master-material-part-iii)

_____ 

## Part 2 - Our First Material - Page 3

_____ 

### Diffuse Only Material

_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets go back to UE4.  Select the **Content Browser** and look at the included **Textures** folder.  We will be importing the carpet here. The **Supplied** folder holds textures I have included in the walk through.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ContentBrowserMenu.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. You can drag and drop the **T_Office_Carpet_D texture into the **Textures** folder in **UE4**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DragTOfficeTargetD.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. It takes a few moments to import.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MaterialsFolder.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Double click the texture file you just imported:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DoubleClickTextureFile.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Take a look at the newly imported texture. Confirm that the size is **2048** by **2048**. Look at the **Compression Settings**.  We will use the default compression but you can try different ones and see the difference in size and resolution.  You can also make "Photoshop" like adjustments for some in engine fine tuning but it is probably best to do this in **Photoshop** unless it is a small adjustment.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CompressionAndAdjustments.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go back to the **Import** folder and drag and drop the carpet static mesh into the **StaticMeshes** folder.  The file is called **SM_Carpet_1**:
</div>
</div>
<div class="col-12 col-lg-8">
<div class="col-12 col-lg-8">
<img src="images/ImportSMCarpet.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Look at your FBX settings.  You don't need a collision volume as it is included in the file.  Make sure the others look right to you as this is a simple carpet.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FBXSettings.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Drag an instance of the carpet and put it in the middle of **Room 1**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DragCarpetInRoom1.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now lets create a new material with the tileable texture we just made. Double click the **Materials** folder and press the **Add New** button and select **Material**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddNewMaterial.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Call the name of the newly created Material `M_OfficeCarpet` (by right clicking and selecting **Rename** or press **F2**):
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/M_OfficeCarpetName.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>


_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Double click the new Material and look at the editor.  In the top left corner we have a sphere that shows us the Material.  In the main area we have a node with various pins that we can plug texture maps into.  Lets add a node to add the texture we just created.  Right click to the left of the main node and type **TextureSample** (you don't have to spell the whole name it will reduce the choices based on what it finds). A shortcut is to left click while holding the **T** key on the keyboard.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectTextureSampleNode.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. You should have a node called **Texture Sample**.  This node has 5 pins.  The top pin on the right has all the channels (Red, Green, Blue and Alpha) and the four pins below have the individual channels (R G B A).  In the **Details** panel we can set up the various settings for the pin but the most important one is assigning a texture: 

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/EmptyTextureSample.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. In the details panel select the menu next to the Texture and start to type **T_OfficeCarpet_BC**.  Then select the texture you just exported from Photoshop:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/T_OfficeCarpetSelectionInNode.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We can at any time preview what the Material looks like from that point in the Node tree.  You right click on the **Texture Sample** node and select **Start Previewing Node**:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/StartPreviewingNode.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Drag the top right pin from the **Texture Sample** node and drag it towards **Base Color**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DragPinToBaseColor.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Drag on top the the **Base Color** pin and if it is compatible you will see a green check mark.  Let go of the left mouse button and it should connect the two nodes:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BaseColorConnected.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now right click on the **Texture Sample** node and select **Stop Previewing Node**.  Now you will see the material on the sphere in the top left corner and it will look the same as it did when previewing the node (which makes sense as that is all we are doing).  Now before you can see it in game you need to press the **Apply** button. It is also good practice to save as this prevents you from losing work if the engine crashes (which it can).
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DiffuseConnected.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Drag and drop the material on the on the carpet.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Room1InitialView.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>



{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now run the game and walk up to the carpet.  Look at it and see if you are happy with the tiling and the seams.  Next up we will look at adjusting the scale of the texture if you want to resize it.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ViewOfCarpetInGame.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 


<br><br>

[<- Previous](Intro-To-Materials-2.html)&nbsp;&nbsp;&nbsp;[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](Intro-To-Materials-4.html)
<br />  
<br />  
<br />  




---
layout: default
title:  "UE4 Intro to Materials 8"
---

# UE4 Intro To Materials - Page 8
_____ 

## Index
_____ 

* Part 1 - Getting Setup
1. [Getting Set Up](Intro-To-Materials-1#getting-set-up)
2. [Creating a Diffuse Map](Intro-To-Materials-2.html#creating-a-diffuse-map.html#starting-unreal-engine-4)


* Part 2 - Our First Material
1. [Diffuse Only Material](Intro-To-Materials-3.html#diffuse-only-material)
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
1.  [**Importing a Model**](Intro-To-Materials-8.html#importing-a-model)
2.  [**Bracket Material**](Intro-To-Materials-8.html#bracket-material)
3.  [Lamp Material](Intro-To-Materials-9.html#lamp-material)

* Part 6 - More Material Concepts
1.  [Two Sided Material](Intro-To-Materials-10.html#two-sided-material)
2.  [Decals](Intro-To-Materials-10.html#decals)
3.  [Refraction and Fresnel](Intro-To-Materials-11.html#refraction-and-fresnel)
4. [World Aligned Materials](Intro-To-Materials-12.html#world-aligned-materials)
5.  [Animation](Intro-To-Materials-13.html#animation)

* Part 7 - A Practical Master Material
1.  [A Practical Master Material](Intro-To-Materials-14.html#a-practical-master-material)
3.  [A Practical Master Material Part II](Intro-To-Materials-15.html#a-practical-master-material-part-ii)
3.  [A Practical Master Material Part III](Intro-To-Materials-16.html#a-practical-master-material-part-iii)

_____ 

### Translucent Blend Mode


_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Some objects like glass need to be translucent.  Now in games we want to try and limit how many we use.  This material is very expensive computationally and should be used with discretion. Create a new material called `M_Translucent` and place it in your **Materials** folder. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddOTransparency.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Go to the **Textures** folder and add **CircleMask_T** to the game and rename it to `T_CircleMask_T`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddTCircleMaskT.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Open the **M_Translucent** material and add a **Texture Sample** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreateTranslucentMaterial.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Assign the newly dowloaded **Texture** called **T_CircleMask_T**  Now for the mask we see the gray.  This will be partially opaque.  The white rings will be completly opaque and the black will be transparent like in the previous mask.  Now it is greyed out so we need to change the blend mode. We cannot hook the pin up to **Opacity** as the blend type is wrong.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ImportCircleMaskT.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>


_____ 



{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Change the Blend Mode in the **Details** panel to **Tranlucent** and hook the output of the texture to the **Opacity** pin in the shader.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Translucent1SideBlendMode.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Now go into the game and test it out.  Add another cube to the scene and bind the latest Material we just created. Lets add some color and make the inside of the cube visible: 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/OneSidedTranslucentGrayCube.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Play the game to look at it.  Lets add a color to it and also fix the same two sided problem we had on the previous mask. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TranslucentOneSided.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets add some color and add **Two Sided** to the modes panel. Add a **Constant Vector 3** node, select a nice color and hook it up to the **Base Color** node.  Make sure **Two Sided** is checked under **Material** in the **Details** panel: 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TwoSidedColorCube.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back to the game and it looks better.  But it doesn't cast a shadow.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NoShadowTranslucentBox.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. There are two things we need to do to fix this.  Go back to the Material and change the **Lighting Mode** to `Surface Translucency Volume`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TranslucencyLightingMode.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Then go into the game and select the cube you previously created. Go into the details panel. Go to the **Lighting** section and there is a downward arrow under **Shadows**.  Click this to expand the selection.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AdvancedLightingDetails.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Look for the Radio Button that has **Volumetric Translucent Shadow** and make sure it is selected. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/VolumetricTranslucentShadow.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>


_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go into the game and play it and look at the cube.  We have a nice soft shadow next to the hard ones!
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SoftShadowInGame.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets **Save All**, **Build** the lighting and open GitHub Desktop.  Commit the last set of changes and push them to the server.  We are now done with room 3! 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CommitAndPushChangesToRoom3.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

## Illumination

Now for some objects in the game, they will also be a light source.  Think of the sun, a lamp, a TV set etc...  So our materials can handle light blooms and glow to create the illusion that it is illumiating in game.  To really sell this effect we also need to add a game light to actually light the scene. We will do this but we will work the entire pipeline from a final FBX to a model in the scene.

_____ 


## Importing a Model

_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Look at your **Files Needed for Walkthrough \| SpotlightModel** model folder.  We have a **.fbx** file which is the 3-D model.  Then we see the **.png** files which are all of our texture maps.  The **_D** is diffuse, **.N** is normal, the **.I** is illumination (which we will be introducing here), **_Rough** is the roughness, and there is a new one **_AO**. This stands for ambient occlusion). This is a "technique used to calculate how exposed each point in a scene is to ambient lighting." - [Wikipedia](https://en.wikipedia.org/wiki/Ambient_occlusion)
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SpotLightFolder.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go the **Textures** folder and press the **Import Button**. Import only the **.png** files for now:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ImportAllPNGs.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Your folder should now look like:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ImportedAllPNGs.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Import the **Import \| SpotlightModel \| Spolight.fbx** into this folder.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SpotlightFBXImport.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. If it gives you a material you can delete it.  You should end up with a bracket and lamp mesh.  They are separate meshes so we can rotate the lamp at different angles:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NewStaticMeshesFolder.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now is a good time to hit the **Save All** button to lock in our work.  Notice that the new assets all have an **Asterix** next to their icon.  This means they are not saved.  Once we press **Save All** these go away.  The game does crash so it is important to save often so you don't lose any work.<br><br>Rename the files to `SM_Spotlight_Bracket` and `SM_Spotlight_Lamp`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SallAllSpotlight.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

## Bracket Material
_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets go to the **Materials** folder and create a new Material called `M_BrushedSteel`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MBrushedSteel.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open up **M_BrushedSteel** Add a **Constant Vector 3** node with `.913`, `.921` and `.915` as the RGB values:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BrushedSteelRGB.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a **Constant** node with a setting of `1` and plug it into the **Metallic** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/OneMetallicBSteel.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Repeat this for Roughness but make the roughness `.4` and connecxt the node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RoughnessPointFour.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Double click the Spotlight_bracket Static Mesh. Assign the material you just created:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AssignSpotlightBracketMaterial.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>


_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go to Room 4 and drag both meshes (with both selected) into the game.  You can press **F** for focus to get the camera close to where they go in the scene.  Move them to be close to the wall.  Rotate the lamp part to point at the wall so we can have a light shine on it.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DragBothMeshesInGameRoom4.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 


<br><br>



[<- Previous](Intro-To-Materials-7.html)&nbsp;&nbsp;&nbsp;[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](Intro-To-Materials-9.html)
<br />  
<br />  
<br />  




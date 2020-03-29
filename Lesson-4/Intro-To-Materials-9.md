---
layout: default
title:  "UE4 Intro to Materials 9"
---

# UE4 Intro To Materials - Page 9
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
1.  [Importing a Model](Intro-To-Materials-8.html#importing-a-model)
2.  [Bracket Material](Intro-To-Materials-8.html#bracket-material)
3.  [**Lamp Material**](Intro-To-Materials-9.html#lamp-material)

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


### Lamp Material
_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Now lets create a new material for the lamp. Let's make it a master material and make an instance for the lamp proper.  Create a new Material in the **Materials** folder and call it `M_Spotlight_Lamp_Master`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddSpotlightLampMasterMaterial.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Now double click the newly created Master Material and:

* Add 4 **Texture Sample Parameter 2D** nodes
* Call them `Diffuse Texture`, `Metallic Mask`, `Roughness Mask`, `Normal Mask`.
*  Group them accordingly
* Connect each to the **Base Color**, **Metallic**, **Roughness** and **Normal** nodes on the master node.
* Press **Apply** and **Save**
* Go to game and assign the newly made material
* Press the F key and check out your newly imported model with it initial material pass
</div>
</div>
<div class="col-12 col-lg-8">
<div class="col-12 col-lg-8">
<img src="images/FirstPassSpotlightMatText.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Now go back to the Material and add another **Sample Textue Parameter 2D** and assign **M_Spotlight_AO**.  Call the group `AO`.  Attach the node to the AO node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SpotlightAO.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add another **Sample Texture Parameter 2D**, call it `Emissive`, assign **T_Spotlight_I** and add an appropriate group name. Connect the output pin to the **Emissive Color** input on the main Material node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ImmisiveNode.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go into the game and look at the front of the light. See that it glows.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GlowLightInGame1.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Now illumination on a bright light source like a stage light gets very bright. And in Unreal to have a real bloom on the light you need a value higher than 1. Lets Add a **Scalar Parameter** and call it `Illumination Scalar` that can be adjusted and multiply the mask. Set the default to `6` and connect the nodes:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MultiplyEmission.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go to the game and light bulb is now even brighter.  Now you notice that it doesn't cast a light as this is not an in game light it just reflects the emissive qualities in the material. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BrighterLight.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Lets  parent Base Lamp to the Bracket.  This way moving the Bracket parent will move the base with it. This will stop up from accidentally separating the model.  Wherever the bracket goes the lamp follows.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ParentLampToBracketSpotlight.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go to the **Place** mode in the main menu and select **Lights**.  Drag a **Spotlight** and place it over the lamp in the scene:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MoveSpotllightToScene.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Parent the spotlight to the Lamp.  This way when you move the bracket it will move all the geo and light and leave them in the right spot. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ParentSpotlightToLamp.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now click on the newly created spotlight in the scene and click on it.  You should see the rays and they don't match the light. They point straight down.  Lets fix this.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RaysPointStraightDown.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>


_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Use the **Rotation** tool to position the light to match visually.  Also use the **Translate** tool to make sure it is located in the middle of the light.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RotationToolToPositionLight.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Since we have the game in full daytime with no interiors lets shade this area a bit. Go to **StaticMeshes \| Supplied** and drag and drop **SM_Outside_Wall_EW and rotate it to be on the ceiling above the lamp in room 4 like so:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddStaticMeshCeiling.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go into **Top** view and adjust it it place so it is perfectly aligned in the corner. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GetItJustRight.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go to **Materials \| Supplied** and add drag and drop the **M_Vasic_Wall** material over this ceiling piece in the level.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AssignWallMat.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Name the new static mesh and put it in the appropriate folder in the **World Outliner**. Prss the **Build** button re rebuild the lighting.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NameAndBuild.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Play the level and look at the light cast in the game.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LIghtOnWallTake1.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now what if I want to create another lamp but change the color to red.  What would I do? First we need a variable to change the color of the emissive light source. So add a **Vector Parameter** to the **M_Spotlight_Master** material:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddVectorParameterToEmissive.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now add another Multiply Node. Connect the output of the first multiply into A of the second.  Output the newly created Vector Paramter into the B node.  Output the second multiply into the Emissive node of the master material node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MultiplyEmissive.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Call this node `Spotlight Color` and put it in group **Emissive**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CallColorOfLightGlow.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go back to the **Content Browser** and right click on **M_Spotlight_Master** and select **Create Material Instance**. Call it `MI_Spotlight_Red`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MI_Spotlight_Red.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Double click this new material instance and adjust the color to a nice shade of red:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MakeMIRed.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go back to the game.  Select the Bracket, Lamp and Light in the **World Outliner**. Now we can easily make a copy by press alt (option on the mac) and dragging the transltation arrow.  This will make a copy.  Then assign the newly created **MI_Spotlight_Red** to this copy.  Then look at it.  Oh, the glow has changed but not the light. Go to the newly created spotlight and in the **Details** panel change the **Light Color** to red.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SecondLampInGame.jpg"  class= "img-fluid"  alt="Create new sprite with button"> 
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now run in game and look at your two lights!
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LIghtOnWall2.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. That is it for this room.  Lets **Save All**, **Build** the lighting and open GitHub Desktop.  Commit the last set of changes and push them to the server.  We are now done with room 4! 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GitHubRoom4.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

<br><br>



[<- Previous](Intro-To-Materials-8.html)&nbsp;&nbsp;&nbsp;[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](Intro-To-Materials-10.html)
<br />  
<br />  
<br />  




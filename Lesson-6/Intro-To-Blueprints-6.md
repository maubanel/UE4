---
layout: default
title:  "UE4 Intro to Blueprints 6"
---

_____ 

## Index
_____ 

* Part 1 - Blueprint Basics
1. [Constructor and Begin Play](Intro-To-Blueprints-1.html#constructor-and-begin-play)
2. [Collision Events](Intro-To-Blueprints-2.html#collision-events)
3. [Grouping Meshes](Intro-To-Blueprints-3.html#grouping-meshes)
4. [Dynamic Material and Light Color](Intro-To-Blueprints-4.html#dynamic-material-and-light-color)
5. [Private Variables](Intro-To-Blueprints-5.html#private-variables)

* Part 2 - Blueprint Dynamic
1. [Adding Components in Script](Intro-To-Blueprints-6.html#adding-components-in-script)
2. [Tick Event](Intro-To-Blueprints-7.html#tick-event)
3. [Rotation and Translation](Intro-To-Blueprints-8.html#rotation-and-translation)

* Part 3 - Blueprint Communication
1. [Dynamically Alter Multiple Classes](Intro-To-Blueprints-9.html#dynamically-alter-multiple-classes)
2. [Communicate Through Interface](Intro-To-Blueprints-10.html#communicate-through-interface)

* Part 4 - Miscellaneous Behaviors
1.  [Oribiting Actors](Intro-To-Blueprints-11.html#oribiting-actors)

* Part 5  - Input
1. [Basic User Input on Actor](Intro-To-Blueprints-12.html#intro-to-blueprints)

_____ 


### Adding Components in Script

Up until this point we have hard coded **Components** into our blueprint object classes.  What if we want to dynamically spawn a component in code maybe even gameplay?  In this exercise we will spawn a component dynamically and use a trick to force a recompile so that it takes effect through the constructor.

_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go to the **Blueprints** folder and add a `Room6`. Press the **Add New** button.  Select **Blueprint Class**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NewBPClass.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Select **Actor** as the inherited blueprint class:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectActor.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Name the new blueprint `BP_Dynamic_Component`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BPDynamicComponentRm6.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open the new blueprint and press the **Add Component** button.  Select **Static Mesh**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddStaticMeshComponentRm6.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Rename the component to `Sphere` and drag and drop it on top of **DefaultSceneRoot** to make this the root component:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RenameMakeRootRm6.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now click on the **Mesh** in the **Details Panel** and we want to find the default sphere that we can get from the brush menu in game.  It doesn't show up though.  We need to click on the **View Options** eyeball at the bottom:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ViewOptionsRm6.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Click on **Show Engine Content** as this is hidden by default:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ClickOnShowEngineContentRm6.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Type in **Sphere** and select the static mesh that **just** says **Sphere**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/StaticMeshSphereEngineContent.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go to select a **Material** in the details panel.  Select it and you will see a lot of engine materials.  Press the **View** eyeball and turn **Show Engine Content** off:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TurnEngineContentOff.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Select the **M_Metal_Burnished_Steel** material.  Now we do not see this material updating.  There must be something wrong with it.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectMMetalBurnishedSteel.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go to the **Materials** folder and double click on **M_Metal_Burnished_Steel**.  Go to the Macro Varation textures.  Notice there is a red error.  Go to assign in the **Details** panel the texture and again turn on the **Show Engine Content**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MacroVariationEngineContentRm6.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now you will be able to find the Texture **T_Default_MacroVariation**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectDefaultMacroVariation.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Assign the same material to the other two **Macro** textures:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AssignOtherTwoMacroTexturesRm6.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press the **Apply** button.  Oh, we are still getting errors.  Go to the Base Color Texture Sample and assign **T_Metal_Aluminim_D** texture:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AssignDiffuseRm6.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press **Apply** again. Still more errors.  Go to the Normal texture and assign **T_Metal_Gold_N** as a texture.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TMetalGoldNormalRm6.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press the **Apply** button.  Now it compiles and voila, the material appears as we want it!
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ApplyCompiles.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back to the blueprint and now you should see the mesh with a proper material:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BPWithSteelMatRm6.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We will now be going to the **Construction Script** tab.  We want to add a variable by pressing the **+** button next to **Variable** in the **MyBlueprint** panel. We want to keep it as the default variable type **boolean**.  This type of variable has two values, true or false.  It shows up in unreal as a check box (checked is true and unchecked is false).  Call this variable `Add Light Component`.  Make sure it's Type is `Boolean`.  Set the **Instance Editable** to `true`. Add a **Tooltip** `If true, a light is turned on in the same position as the sphere`.  Make sure **Private** is set to `true`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddLightComponentVariable.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now drag the variable from the **MyBlueprint** tab into the scene graph.  It gives us the option to write (set) to the variable or read (get) it.  We want to read it so we will be selecting **Get Add Light Component**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DragVariableOntoGraph.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Drag off of the boolean's pin and type **Branch**.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BranchFromLightCompRm6.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. This is the equivalent of an if() and else() statement in most programming languages.  If the condition is **true** ( if() ) then the **True** execution pin runs.  If the condition is **false** ( else() ) then the **False** execution pin runs. Drag off of the true pin and we will add a light component:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BranchGraphRm6.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. So start typing **Point Light** and select the **Add Point Light Component**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PointLightComponent.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now look at the input pins.  It asks for relative transform.  Relative is in relation to this actor and is in local space.  World position would be where in the level that actor is located.  So we are looking at it as relative position to the Sphere mesh root component. Right click on **Relative Transform** and select **Split Struct Pins**.  Remember a **Transform** consists of a Location, Rotation and Scale (3 x Vector 3).
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SplitStructPin.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets have it light the top of the ball so move it by `100` on the Z in **Location**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MovdUpOnZ100Rm6.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add two comments.  Select the **Branch** and the comment `Every time a change is made this is run`.  Select the light component and add the comment: `Adds point light to the same location and rotation and scale as the sphere`
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CommentNodesRm6.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go to the game.  Add this blueprint to **Room6**.  You can switch the boolean on and off and see the light turn on and off.  Now if you play the game you can no longer switch the light.  The constructor DOES NOT run during gameplay.  This is a way to cheat the constructor to run in the editor so that you can add a component, but it will not be changable through this interface in game.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FInalLightBall.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. That's it for Room 6. Press **Save All** and update Github by **committing** and **pushing** all the changes made.  Next up we will be adding a timer on the screen that reads the cumulative game time.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Room6Github.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____  

<br><br>

[<- Previous](Intro-To-Blueprints-5.html)&nbsp;&nbsp;&nbsp;[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](Intro-To-Blueprints-7.html)
<br />  
<br />  
<br />  




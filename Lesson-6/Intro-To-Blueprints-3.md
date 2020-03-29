---
layout: default
title:  "UE4 Intro to Blueprints 3"
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


### Grouping Meshes

Now **blueprints** are not just for logic.  We can use them to create a more complex object with multiple meshes and components and save them as one blueprint.  Then you can make multiple instances of them and they will be replicated.  You can also build it in the game world first, then create a bluprint after.  Lets create a spotlight and see how this works.

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go to **Room 3** and go to the **StaticMeshes** folder.  Drag the spotlight_bracket into the room.  Rotate it so it faces the front of the room:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DragBracketRm3.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Move the object in the **World Outliner** into the **Room 3** folder. Then press the **Add Component** button:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MoveToRoom3.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Select another **Static Mesh** component:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddSecondStaticMeshRm3.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Assign the **spotlight_lamp** mesh to this component:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AssignLampToStaticMeshRm3.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a third static mesh component by pressing the **Add Component** button:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Assign3rdStaticMeshComponent.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Assign the **Lightbulb** static mesh:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AssignLightbulbRm3.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Rename the Actor to `Spotlight`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RenameActorToSpotlightRm3.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add another component but this time an actual Spotlight so it can project an in game spotlight. Pressing **Add Component** button then select **Spotlight**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddSpotLightComponent.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now make sure that your **Spotlight** is selected in the **World Outliner**.  Then press the **Blueprint** button to turn this from a actor to a reusable blueprint.  Add it to the **Blueprints** folder and call it `BP_Spotlight`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TurnSpotlightIntoBPRm3.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open the **BP_Spotlight** blueprint and select the **Spotlight**.  You will see that its rotation may not match the light.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RotateLightRm3.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>


_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Make sure it is rotated in the same direction as the lamp.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RotateLight.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Select the **Lamp** component and rotate the lamp so that it doesn't point straight down.  Tune it to your liking:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RotateLampToOffsetIt.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Select the **Spotlight** then set the light color to your preference.  I picked green:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ChangeSpotlightColor.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Check the lamp out in game.  I am noticing a problem with a model casting a shadow I don't like in the light:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CheckInGameLightBehindBulb.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now by having it as a blueprint I can just drop it in the room multiple times and rotate it in different direcions.  I have a game object that I can instance as much as I want with the functionality I need!
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DropBlueprintInMultipleLocations.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now this is what it could look like in game:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/InGameFinalLook.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____  
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. That's it for Room 3. Press **Save All** and update Github by **committing** and **pushing** all the changes made.  Next up we will be alter the light color and create a dynamic material in a blueprint:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GItHubRoom3.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____  

<br><br>

[<- Previous](Intro-To-Blueprints-2.html)&nbsp;&nbsp;&nbsp;[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](Intro-To-Blueprints-4.html)
<br />  
<br />  
<br />  




---
layout: default
title:  "UE4 Intro to Blueprints 5"
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


### Private Variables

What is a **[variable](https://en.wikipedia.org/wiki/Variable_(computer_science))** in computer programming and why would we want to use it?  A variable is a container that allows us to access information stored in memory through a symbolic name.  What the variable refers to is a value that can refer to any type of object.  In video games we use it to store important information such as **High Score**, **Health** and other values that change over time.  We also store data that we want to customize and tune in the game engine.  Lets take the light we did in the last exercise and store the color in a variable.

It is best to keep variables **private** if possible.  This is called **encapsulation** or **data-hiding**.  When working on a project with a team, it is usually best to have all the funtionality that a class/objecdt needs contained within that class (or blueprint).  If another object needs to interact with it then it is best to have getters and setters so that other classes can interact with this class.  This makes the code easier to maintain and debug in the long term.

_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Right click **BP_Spotlight_Dynamic** and select **Duplicate**. Call the new blueprint `BP_Variable_Private`.  Add a new room called `Room5`.  Drag this new blueprint into the folder:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DuplicateBPRm5.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Drag a copy of the new blueprint into the left side of **Room 5**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DragCopyOfObjectInLeftSideOfRoom.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. In the **World Outliner** drag and drop the variable into **Room 5**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DragAndDropIntoRm5.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We want to use a variable to store the light color.  Open the blueprint and press the **+** button next to **Variables** in the **MyBlueprint** menu.  In the details panel type `Linear Color`.  Select this as the type of variable.:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddVariableRm5.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Name the variable something that describes what it does.  CI called it `ColorOfLight`.  I also put it in a **Category** called `Light`.  It is always best practice to also leave a **Tooltip** in the details panel.  This way anytime a user hovers over the variable name a full explanation can be given.  This allows you to use shorter less descriptive variable names and still provide a full description. My tooltip was `Sets color of lightbulb and spotlight beam in game`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetTooltipRm5.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Right now I don't plan on allowing other blueprints to alter this variable.  So if even if I don't know if it will be editable it is best practice to set variables as **private** which you do by clicking the radio button in the **Details** panel:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MakeVariablePrivate.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we no longer need the **Make Linear Color** node as we will be replacing it with a variable.  Delete this node and drag and drop the **ColorOfLight** variable in its place:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DeleteLinearColorDragVariableRm5.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Hook up the pins coming out of the variable to the **Value** pin in the **Set Vector Parameter** node as well as the **New Light Color** pin in the **Set Light Color** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectColorOfLightPinRm5.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now where do we enter the value for this variable?  We go to the default section in the **Details** panel.  If this is not editable then press the **Compile** button, this will make the default available to edit.  This allows us to set what our base value will be.  I double clicked on the color bar and set it to red (original default was black):
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetDefaultValueToRedDetailsPanel.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now run the game and notice that the color is set withing the blueprint through the variable:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/VariableControlsColorOfLightRm5.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. There is another useful feature with variables while still keeping them private.  We can expose them so that they don't have to be edited within the blueprint.  We can edit them within the room and allow each object to have a different color!  To do this right click the **BP_Variable_Private** and select **Duplicate**.  Name this new blueprint `BP_Variable_Editable`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DuplicateVariablePrivateRm5.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open the Blueprint.  There are two places you can make the variable editable.  In the **MyBlueprints** panel there is a closed or open eyball next to the variable name.  If it is open then it is editable.  Also in the **Details** panel is has a radio box called **Instance Editable**.  The word instance here is important as you can have a separate instance for each object in the room!
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/InstanceEditableRm5.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go back to the game engine and select the new blueprint you put in the room.  Go to the **Details** panel and you will see an option to adjust the **Editable** variable we just created.  I changed it to yellow and it changes right away in game as any change runs the construction script.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NewLightInSceneEditableRm5.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Clean up the **World Outliner** by dragging the object into the **Room 5** folder:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CleanUpRm5.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now add another light and double click this color in the details panel.  Adjust the color.  One of benefits of this instance editable variable is we don't have to recompile.  We can see the color update as we change it allowing for more effetive tuning in game:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LiveEditColorOfLightRm5.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Put as many lights with different colors in this room as you like!
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ThreeLightRm5.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. That's it for Room 5. Press **Save All** and update Github by **committing** and **pushing** all the changes made.  Next up we will be adding components dynamically in scripts.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Room5GitHub.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____  

<br><br>

[<- Previous](Intro-To-Blueprints-4.html)&nbsp;&nbsp;&nbsp;[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](Intro-To-Blueprints-6.html)
<br />  
<br />  
<br />  




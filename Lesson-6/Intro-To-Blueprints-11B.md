---
layout: default
title:  "UE4 Intro to Blueprints 15"
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

### Orbiting Actors Continued

_____ 


{% assign num = 49 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now lets draw the radius of this rotation in debug to visualize it.  Add another **Boolean** variable called `Draw Debug Radius`. Make it **Instance Editable** and **Private** with a **Tooltip** and **Category** `Debug`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddDrawDebugRadiusRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now add a **Get** reference to this variable on the graph and send it to a **Branch** node: 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DrawDebugRadiusBranchRb15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Right click on the open graph and select the node **Draw Debug Line**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RightClickDrawDebugLineRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Grab the output of the **Vector + Vector** pin just before the **Set Actor Locaiton** node. This is the location of the player.  Place it in the **Line Start** input pin in the **Draw Debug Line** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GrabPlayerPosPinRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now the line will go to the center of the box we are rotating around.  Grab a get variable of **Target Rotate Around** and attach it to a **Get Actor** location node.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GetTargetLocadtionRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the output Execution pin from the **Set Actor Location** node to the input pin of the **Branch** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectSetActorLocPinRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the output pin of **Get Actor Location** for the cube to the **Line End** input pin of the **Draw Debug Line** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectToLineEndRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. For the **Draw Debug Line** set the **Duration** to `0.0` and the line **Thickness** to `3.0`.  Press the **Compile** button:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetDurationThicknessRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go into the game and make sure the boolean for the drawing of the radius is set to true.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RadiusDrawingInGameRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Run the game and voila, a line drawing the radius of the rotation:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SingleRotateClockRadius.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now the rotation is always clockwise.  What if we wanted the sphere to rotate counter-clockwise?  We would need to send a negative rotation number instead of a positive one.  Lets start by adding a **Boolean** variable called `Clockwise`.  Make it **Instance Editable** and **Private**.  Put it in **Category** `Rotation` and add a **Tooltip**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ClockwiseVariableRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back to the nodes where you are setting the rotation in degrees.  Add a **Get Clockwise** node to access this variable.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GetClockwiseVarRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull from the output pin and add a **Select Float**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectFloatNodeRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Make sure the **Clockwise** pin connects to the **Pick A** input on the **Select Float** node.  This is fairly straight forward.  If **Clockwise** is true then the output is the A pin, it if is false it is the B pin. So for **A** we want `1.0` and for **B** we want `-1.0`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectFloatNegativeOneRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now add a **Float * Float** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FloatTimesFloatRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now multiply the output of the multiplication of the degrees per second times the tick by 1 or -1.  Attach the output of the **Multiplication** node to the input of the new **Multiplication** node and make it times the **Select A Float** node.  The output then gets direction to the **Addition** node like so:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectPinsAsShownRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. So your node chart should look like this.  Press the **Compile** button and hopefully you get the green checkmark on the icon:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NodeChartNewRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Run the game and switch between clockwise and counter-clockwise on the game object.  The rotation should change!
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SingleRotateClockAndCountRadius.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now what if we want to have mulitiple sphere blueprints orbiting around the same object.  If we had more than one, they would all move one atop each other.  What we want to do is add a starting angle (or offset angle) so they are at different distances. Add a variable called `Starting Angle` of type **Float** with **Instance Editable** and **Private** set to `true`.  Change the **Categpory** to `Rotation` and add a **Tooltip**:  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddStartingAngleRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Drag the **Starting Angle** variable as a **Get** to right after the **Current Angle In Degrees** that goes to the **Rotate Vector Around Axis** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DragStartingAngleRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a **Float + Float** noe to add the **Current Angle In Degrees** and **Starting Angle** variables together.  Send the output to the **AngleDeg** input in **RotateVectorAroundAxis** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/StartingAnglePlusAngleRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add three more blueprints in the scene.  Have one set to **Starting Angle** `0.0`, the next to `90.0`, the next to `180.0` and the final to `270.0`.  Run it and it should look like:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Rotate4SpheresNoRotate.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Now the sphere is changing location but is not facing the center cube.  Lets add some functionality so that the sphere looks at the center point during the rotation so that is translates AND rotates during this sequence. Right click on the open graph and look for the **Find Look at Rotation** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddLookAtRotationNodeRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a **Get Actor Location** node and hook the  the output to the  the **Find Look At Rotation** node's **Start** pin:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/HookUpStartRotationRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. So if the starting point of the look is the sphere location.  Then the end point is the center.  Drag a **Get** of the **Target To Rotate Around**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GetTargetToRotateAround.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Drag off of the pin and select the **Get Actor Location** node which returns the location of the actor we are orbiting around.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GetActorLocadtionRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the output of the **Get Actor Location** node to the **Target** input of the **Find Look at Rotation** node.  Grab the **Return Value** pin and select the **Set Actor Rotation** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LookAtRotationHookRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the output of the **Find Look at Rotation** node to the input of the **Set Actor Rotation** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectPins3Rm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the output execution pin of the **Set Actor Location** node to the input execution pin of the **Set Actor Rotation** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetActorLocationToRotationPinsRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Reconnect the **Branch** input execution pin to the output of the **Set Actor Rotation** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ReconnectDrawDebugLineRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Run the game and walk into the collision volume.  Now the spheres rotate and continue to face the center and now it looks pretty good.  Lets end it here.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Rotate4SpheresRotate.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. That's it for Room 11. Press **Save All** and update Github by **committing** and **pushing**1all the changes made.  Next up we will be polling inputs to control objects at run time.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GithubRm15.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____  

<br><br>

[<- Previous](Intro-To-Blueprints-11B.html)&nbsp;&nbsp;&nbsp;[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](Intro-To-Blueprints-12.html)
<br />  
<br />  
<br />  




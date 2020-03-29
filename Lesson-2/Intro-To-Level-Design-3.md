---
layout: default
title:  "UE4 Intro to Level Design 4"
---
 <br><br>

## Introduction to Level Design - Page 3

* Part 1 - Setting up 
1. [Getting Started](Intro-To-Level-Design-1.html#getting-started)
2. [Tuning Default Settings](Intro-To-Level-Design-1.html#tuning-default-settings)
3. [Clean Up Content Folder](Intro-To-Level-Design-1.html#clean-up-content-folder)
4. [Lock Down Physics](Intro-To-Level-Design-2.html#lock-down-physics)

* Part 2 - Creating The Grey Block
1. [Short Ramp](Intro-To-Level-Design-2.html#short-ramp)
2. [Center Platform](Intro-To-Level-Design-2.html#center-platform)
3. [**Second Ramp**](Intro-To-Level-Design-3.html#second-ramp)
4. [**Third Ramp**](Intro-To-Level-Design-3.html#third-ramp)
5. [**Fourth 45 Degree Ramp**](Intro-To-Level-Design-3.html#fourth-45-degree-ramp)
6. [Easy Jump Height](Intro-To-Level-Design-4.html#easy-jump-height)
7. [Intermediate &amp; Hard Jump Height](Intro-To-Level-Design-4.html#intermediate--hard-jump-height)
8. [Short Standing Jump Distance](Intro-To-Level-Design-4.html#short-standing-jump-distance)
9. [Short Running Jump Distance](Intro-To-Level-Design-5.html#short-running-jump-distance)
10. [Long Running Jump Distance](Intro-To-Level-Design-5.html#long-running-jump-distance)
11. [Moving Platform](Intro-To-Level-Design-5.html#moving-platform)
12. [Moving Platform Part II](Intro-To-Level-Design-6.html#moving-platform-part-ii)

* Part 3 - Adding Materials to Map 
1. [Adding Master Material](Intro-To-Level-Design-7.html#adding-master-material)

_____ 

### Second Ramp
Lets create a second ramp at the other end of the first one at a different angle.

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Duplicate the ramp by right clicking on **Small Ramp** and selecting **Edit \| Duplicate**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DuplicateSecondRamp.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Unlock this new BSP's Transform Movement.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/UnlockTransformMovement.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Move this new ramp to the other side of the center piece:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MoveRampToOppositeSide.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Rotate the ramp around 180 degrees then change to **Top** view and align the ramp and center section:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RotateAlignTopView.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Change to **Right** or **Left** view and adjust the side to align with the middle section:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AlignSide.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Test the game and make sure you can run up and down both ramps without getting hung up on a ledge. Now I notice that the player dissapears when going over the second ramp.  Lets fix that.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TwoRamps.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open **ThirdPresonCharacter** and select the **Camera Boom** component and raise the value in **Camera \| Target Offset Z** like so:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TargetOffsetLarger.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now select the **FollowCamera** component and tilt the camera to be pointing at the back of the player's head:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LowerAngleCamera.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Run the game and now the player does not get occluded when I run over the ramp.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AdjustedCameraTwoRamps.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back to the game and now lets make the ramp less steep.  Select the second ramp and change the **X** Brush Setting and make it `2000`.  This removes our edited ramp and it is rectangular again.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LengthenRamp.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go back to the editing mode and select the two far points while pressing the **Control** key and lower the ramp back to the bottom.  Press **Apply**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RecreateRamp.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back to the top view and make sure the platform is lines up on the edge of the center piece.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AlignFromTop.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Do the same thing lining up from a side view either **Right** or **Left**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LineUpRightView.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go back to the **Perspective** view and you should have two slopes of diffent angles.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TwoDifferentSlopedRamps.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Run the game and give it a shot!
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TwoRampsOneLong.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

## Third Ramp
Lets create another ramp perpendicular to the two we have made of yet another angle.

_____ 


{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Duplicate the last ramp you made.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DupeThirdRamp.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Make **Small Ramp Long** unmovable by locking its **Transform**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LockSmallRampLong.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Rotate the third ramp by 90 degrees and place it orthoginally to the other two ramps. Go to the **Top** view and align it from the top.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MoveRotateRamp3.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go into **Edit** mode and **Control** click the two end points.  Pull them out to make the ramp even longer!
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LengthenTirdLength.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Change to **Front** view and adjust the side to line up this new ramp and the center piece:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FrontViewEdit3Ramp.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 



{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go back to **Perspective** view and look at three ramps with different slopes.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ThreeRampsLS.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Play the game and make sure you don't get hung up on any of the ramps.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ThreeRamps.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Change the name of the third ramp to `Small Ramp Very Long`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/UpdateThirdRampName.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now lock the ability to alter the **Transform** of the third ramp.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LockThirdRamp.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

### Fourth 45 Degree Ramp
Add our final and fourth ramp that we will angle at 45 degrees.

_____ 
{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add another box and make the height and length the same so we have a 45 degree ramp:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FourtyFiveFourthRamp.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Edit both end points to make a ramp.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TurnIntoRamp.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go into **Top** and **Front** view to align the edges:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FourthRampFront.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Test all the ramps by running around them.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AllFourRamps.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go back to the world outliner and make any final changes to organize the data. Call the fourth ramp `Small Ramp Short`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CleanUpAssetsSecondTime.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Finish the ramps off by adding a **Text Render** and have it say `Ramps`.  Make it very large so you can see it anywhere in the test level:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RampsTextTitle.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Finally make final adjustements to your **Ramps** folder and name and organize these elements.  Add a **Ramps** folder and put all ramp BSP's in the subfolder. Press **Save All** and update Github by **committing** and **pushing** all the changes made. On the next page we will look at an easy single jump vertical height.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/OrganizeFolder.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Type `Text Render` in the modes panel to add a 2-D text to add on top of the ramps to identify it from afar.  Type in as the **Text** field: `Ramps`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddTextRender.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Make it really big and place it on top of the ramp:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ResizeCenterOverRamp.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Duplicate the text render and rotate it 90 degrees so you can see the text from all angles (as the text is not 3-D).
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RampTextDupe.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
<br><br>

[<- Previous](Intro-To-Level-Design-2.html)&nbsp;&nbsp;&nbsp;[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](Intro-To-Level-Design-4.html)
<br />  
<br />  
<br />  




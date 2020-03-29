---
layout: default
title:  "UE4 Intro to Level Design 1"
---
<br><br>
## Importing Models - Page 1

Lets now look at the pipeline of getting models from softare to Unreal Engine.

_____ 

## Index
_____ 

* Part 1 -  
1. [**What Makes a Good Real Time Model?**](Intro-To-Level-Design-1.html#what-makes-a-good-real-time-model)
2. [Scale]
2. [Levels, Props & Skeletons](Intro-To-Level-Design-1.html#tuning-default-settings)
4. [Materials](Intro-To-Level-Design-2.html#lock-down-physics)
1. [UV Mapping](Intro-To-Level-Design-2.html#short-ramp)
2. [LOD](Intro-To-Level-Design-2.html#center-platform)
3. [Collisions](Intro-To-Level-Design-3.html#second-ramp)
4. [Pivot Point](Intro-To-Level-Design-3.html#third-ramp)
5. [Fourth 45 Degree Ramp](Intro-To-Level-Design-3.html#fourth-45-degree-ramp)
6. [Easy Jump Height](Intro-To-Level-Design-4.html#easy-jump-height)
7. [Intermediate &amp; Hard Jump Height](Intro-To-Level-Design-4.html#intermediate--hard-jump-height)
8. [Short Standing Jump Distance](Intro-To-Level-Design-4.html#short-standing-jump-distance)
9. [Short Running Jump Distance](Intro-To-Level-Design-5.html#short-running-jump-distance)
10. [Long Running Jump Distance](Intro-To-Level-Design-5.html#long-running-jump-distance)
11. [Moving Platform](Intro-To-Level-Design-5.html#moving-platform)
12. [Moving Platform Part II](Intro-To-Level-Design-6.html#moving-platform-part-ii)

_____ 


## What you will need?

For this project you will need to be install [Unreal Engine 4.22.x](https://www.unrealengine.com/en-US/download) , have a [GitHub](https://github.com/) account (which is free of charge) as well as [GitHub Desktop](https://desktop.github.com). 

_____ 

### Getting Started
_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. If you are a student of mine in class you will have get a link on Moodle of this same repository and will view the invitation and press the **Accept this Assignment** button.  Once this process is complete open **Github Desktop** and press **File \| Clone Repository** and clone the `LSU-UE4-intro-to-animation` repository.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GithubClassrroomAssignment.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. If you are not part of the class you can login into github with your personal account and navigate to  [https://github.com/maubanel/UE4Blank](https://github.com/maubanel/UE4Blank) and in the top right corner press the fork button:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BlankGithubProject.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Navigate to the directory where you installed it.  You will have a **Source Files** folder with all the files you need.  There is a hidden .git folder that contains the database for all your files. There is a **LICENSE** file that declares the copyright and licensing terms.  You can look at this if you like.  The **README.md** file has temporary text that you need to keep updated.  You should fill it in with relevant content as you progress through this walk through. You will only see the `.git` folder if you have hidden folders turned on. All the rest of the files and folders are a default Unreal project.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NewBlankProjectFinder.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. What you are getting is Unreal's default third person template.  It would have been the same as running **Epic Launcher** and starting a New Project with Third Person selected.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ThirdPersonTemplate.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now double click on **LSU_Third_Person** to open the editor.  Now your screen should look like this:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ThirdPersonTempate.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Fill in the **Description** tab info in **Project Settings** while we are at it:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FillInDescriptionTab.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____  

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press play and lets see what we get? Run around using the **WASD** keys on the keyboard.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BaseTemplate.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

## Tuning Default Settings
Now we want to tune the default settings of this template on the Third Person Character blueprint. We will make it more like a platform game.

_____

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now open the **ThirdPersonCharacter** blueprint that you find in **Content \| ThirdPersonBP \| Blueprints \| ThirdPersonCharacter.uasset**. Make sure you are in the **Viewport** tab. Now click on the **Camera Boom** component.  It is the parent of the camera.  This acts as a spring so that when the camera collides with geometry it acts as a spring to keep the camera from going into geometry. This is represented with the **red** line in the editor.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CameraBoomUnreal.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Select the **Camera Boom** component.  Change the **Target Arm Length** to a number like `750`.  Then adjust the **Target Offset Z** value to a value like `218`. Now the camera is above and further away but is not rotated facing the player.  Lets fix that.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AdjustArmDistanceAndOffset.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now select the **FollowCamera** component and adjust the **Rotation Y** to `345`.  This will pitch the camera down 15 degrees pointing towards the back of the player's head.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RotateOnYAxis.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Run the game and run into the back wall to see that the spring arm stops (and the player sort of disappears).  We will fix that in a later lesson when we dig more into blueprints.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AdjustedCamAndSpring.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Run the game again and look how the arrow keys for left and right differ from the a and d key in the game.  The **AWSD** moves the player and on the arrow keys left and right move the camera.  Lets make them the same.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LeftRightWrong.gif "  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. The controls are defined in the project settings.  Select the **Settings** button and go to **Project Settings**.  Go to **Engine \| Input** and open up the arrow next to **Axis Mappings**.  Go to **Left** and **Right** under **TurnRate** and press the **X** to delete both of them.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ArrowTurnNotCam.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now press the **+** (plus symbol) button twice to add controls for left and right.  Add a **Right** keypress and set the **Scale** to `1.0` and a**Left** keypress with a **Scale** of `-1.0`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddLeftAndRight.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Run the game again and now the arrow keys act just like the **WASD** keys and we are at parity.  Try plugging in a controller to play it as well!
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ArrowsWork.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open up the **ThirdPersonCharacter** blueprint and select the **CharacterMovement** component.  This is where all the adjustments for player physics is held.  Let's first change the gravity.  We want a bit of moon like physics for **Gravity**. If you hover the cursor over **Gravity Scale** you will get a description of what it does.  The most common type of setting normalizes between a range of 0 and 1.  In this case 0 would be no gravity, 1 is earth gravity and anything larger than 1 will apply a greater gravitational force.  Let's make it more like the moon and set it to `.75`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AdjustGravity.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____  
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press the **Compile** button on the blueprint and run the game.  Now look at how the player's gravity changes and he float more.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LowGravity.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets make a few more changes.  Lets make our character run a bit faster.  In the blueprint chnage the **Character Movement: Walking \| Max Walk Speed** to `800`. Play the game and tune the numbers to your liking.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MakePlayerRunFaster.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____  

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now lets make the player jump higher and give the ability for the player to adjust his direction mid flight.  In **Character Movement: Jumping / Falling** change **Jump Z Velocity** to `600.0` and **Air Control** to `0.5`. Play the game and tune the numbers to your liking.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AdjustZVelocityAndAirControl.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____  
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We will make one final change and have very snappy turning speed.  We will adjust the **Character Movement (Rotation Settings) \| Rotation Rate Z** to `1000`. Play the game and tune the numbers to your liking.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AdjustRotation.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____  
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Play the game and make any changes to what I suggested.  Get the player to move the way you envision a player should move in an arcady third person game.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NewPhysics.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____  


## Clean Up Content Folder
Lets organize the content folder for our project.

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We have two **Meshes** (geometry) folders.  One in the **Third Person** folder and the other in the **Geometry** folder.  Lets move the meshes from **Third Person** to the **Geometry Meshes** folder.  Then delete the **Third Person** meshes folder.  Force the delete if needed.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MoveTPMeshes.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____  
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Move the **Blueprints** and **Maps** folder from **ThirdPerson** to the roon **Content** folder.  Then delete all the contents of the **Third Person** folder.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MoveBPMapsFolders.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____  


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Before we start a gray block level we need to create a test level to understand how our player moves and how high and far to make jumps.  We also want to create ramps for players to run up and down.  To do this we will create a test level just meant to test physics so we can get an understanding of how the player moves.  Select the **Maps**
 folder and press **File \| New Level**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NewLevel.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Call it `PhysicsTestLevel`:
 </div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PhysicsTestLevel.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____  
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. So we should end up with the **PhysicsTestLevel** in the **Maps** folder.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/EndUpWithTestMapInFolder.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>


_____  
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press **Settings \| Project Settings**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SettingsProjectSettings.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____  
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Change the **Editor Startup Map** and **Game Startup Map** to `PhysicsTestLevel`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AbilitiesTestMap.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____  

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now press play and we should have the character controls we had previously with all of its logic.  Press **Save All** and update Github by **committing** and **pushing** all the changes made. Next up we will start to figure out platform distances.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NewLevelPlayer.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____  

<br><br>

[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](Intro-To-Level-Design-2.html)
<br />  
<br />  
<br />  




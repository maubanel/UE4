---
layout: default
title:  "UE4 Intro to Animation 5"
---

<br><br>

_____ 

### Falling Animation
Lets add an animation for when the player is falling to our movement state machine for when the player falls off the edge of a surface.

_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets go back to [mixamo](https://www.mixamo.com/#/) and look for some more animations.  I am looking for a looping falling animation and for hitting the ground (after falling).  Select the character you are using then search for these two animations. First pick the looping falling and make the appropriate adjustments.  Click the **Download** button:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LoopingFalling.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Download just the animation with the default settings.  Set **Skin** to `Without Skin` to avoid bringing in any geometry. Press the **Download** button again.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DownloadJustAnimationFall.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. I also found an animtion from falling to hitting the ground.  I sped up the animation as I didn't want it to interupt gameplay too much so I cranked up the **Overdrive**.  On the next menu it should be the same settings as previously so you can verify this then press **Download** again.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FallingToLanding.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back to the game and go to the **AJ \| Animations** folder and press the **Import** button and select these two animations you just downloaded:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ImportFallingAnimation.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. In the **FBX Import Options** overlay, make sure you select the skeleton you have been using. Then press **Import All**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectSkeletonFallingAnims.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Preview the animations in the editor.  Name them accordingly.  I named them `Falling_Loop` and `Falling_To_Landing`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RenameAndPreviewAnims.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open the **aj_AnimBlueprint** animation blueprint and go to the **Anim Graph \| Core Locomotion** tab.  Right click on the area and add an **Add State** button:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddFallingState.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Call this new state `Falling`.  Right click again and add another state:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CallItFallingAddAnotherState.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Call this new state `Falling End`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FallingEnd.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we need a boolean to track when we are on the ground or in the air.  Add a new **Boolean** Variable and call it `bAreWeInAir`.  Make it **Private** and set the **Tooltip** to `True when player is not on the ground`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AreWeInAirBooleanDef.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go to the **Event Graph** tab and make some space between the **Is Valid** node and the **Get Velocity** node to check to see if we are in air.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MakeSpaceEventGraphAnimBP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off of the **Return Value** pin from the **Try Get Pawn Owner** node and select the **Get Movement Component** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GetMovementComponentAnimBP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off of the **Return Value** pin from the **Get Movement Component** and selecdt the **IsFalling** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/IsFallingVariableGet.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Drag the **Set Are We In Air** variable onto the graph:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetAreWeInAir.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the **Return Value** pin from the **Is Falling** node to the **Set Are We In Air?** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectAreWeInAirPins.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Hijack the execution pin from **Is Valid** node and send it to the **Set Are We In Air?** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/IsValidExecutionPin.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Take the output execution pin from **Set Are We in Air?** node to the **Set Speed** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ReconnectSetSpeedPin.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Select the new nodes and make a comment `Sets Whether Player Is In Air`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddCommnentIsPlayerInAir.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back to the **Anim Graph \| Core Locomotion** screen.  Connectd the **IdleWalkRun** state to the **Falling** state to the **Falling End** state back to the **IdleWalkRun**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectFallingStates.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Double click the transition from **IdleWalkRun** to **Falling**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConditionToFalling.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Drag and drop the **Get Are We In Air?** variable onto the graph.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AreWeInAirGetTransition.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Attach the two only pins in this graph.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AttachPinsForFalling.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets put the animation inside the falling state.  Double click the **Falling** state node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DoubleClickFallingState.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Drag and drop the **Falling_Loop** animation onto the graph.  Connect the animation pins together.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PlayFallingLoopAnim.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back to the **Anim Graph \| Core Locomotion** screen and double click the transition button between **Falling** and **Falling End** state nodes:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FallingToFallingEndTransition.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We switch to this animation when we hit the ground.  Drag a **Get Are We in Air?** node to the graph.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GetAreWeInAirNOT.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off of the **Are We in Air?** node and select a **NOT Boolean** node as we want to find out if the player is not in the air:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PullOffNOTBool.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the output of the **NOT** node to the **Result** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectNotToEnterTransition.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets assign the falling end animation.  Go back to the **Anim Graph \| Core Locomotiion** screen and double left-click on **Falling End**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DoubleClickFallingEnd.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Drag and drop the **Falling_To_Landing** animation onto the graph.  Connect the animation pin to the **Final Animation Pose**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FallingToLandingConnectAnim.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Double click on the transition button from **Falling End** to **IdleWalkRun**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DoubleClickTransitionToEnd.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We want this animation to play once then blend back to the **IdleWalkRun** state.  There is a node for this.  Right click on the graph and select a **Time Remaining (ratio)(Falling_To_Landing)** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TimeRemainingRatioFallEnd.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off of the **Return Value** pin from the **Time Remaining** node and select a **<=** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LessEqualTimeRemaining.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Set the bottom value for the **<=** node to `0.75`.  Then connect the output to the input of the **Result** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LessThanPointSevenFive.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back to the game editor and select the **Floor** objectd in the **World Outliner**.  Change its **Scale** to `10.0` on the **X** and **Y**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MakeFloorBigger.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a cube under the **Player Start** so that the player will land on the cube.  Scale the cube to a size that makes sense to you. Raise the **Player Start** so it is above this platform.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddCubeUnderPlayerStart.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Run the game and the player should fall on the cube. Walk off the cube and the player should fall on the floor.  We should have our states working correctly for falling. Press **Save All** and update Github by **committing** and **pushing** all the changes made.  Next up we will be adding jumping to the game:
</div>
</div>
<div class="col-12 col-lg-8">
<div class="embed-responsive embed-responsive-16by9">
<iframe class="embed-responsive-item" src="https://www.youtube.com/embed/9LLcN28yliU?autoplay=1&rel=0&controls=0&amp&showinfo=0&version=3&loop=1&playlist=9LLcN28yliU" frameborder="0" allowfullscreen></iframe>
</div>
</div>
</div>
_____ 
<br><br>

[<- Previous](Intro-To-Animation-4.html)&nbsp;&nbsp;&nbsp;[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](Intro-To-Animation-6.html)
<br />  
<br />  
<br />  




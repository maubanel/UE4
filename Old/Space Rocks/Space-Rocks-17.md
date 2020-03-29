---
layout: default
title:  "UE4 Space Rocks 17"
---

### Rock Medium Continued

_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now lets add a new track for our medium rock.  Press the **~+** button to add a new **Event** track.  Call it `Events Rock Medium`. Shift Left click on the graph and add a point that is set to **Time** to `5.0` and **Value** to `1`
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddRockMediumEvent.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a point to **Vertical** at **Time** `5.0` and **Value** to `0.0`. Add a point to **Horizontal** at **Time** `5.0` and **Value** to `0.5`. Add a point to **Angle** at **Time** `5.0` and **Value** to `10.0`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetFirstMedSizeRockValue.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now that we have the values set for our one small rock and one medium rock lets go back to the **Event Graph** tab and trigger then.  In the empty Rock Small Events comment box right click and call the **Spawn Rock** event node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SpawnRockEventGraph.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the timeline **Events Rock Small** execution pin and attach it to the **Spawn Rocks** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectRockSmallEventPins.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the **Horizontal**, **Vertical** and **Angle** pins to each other from the **Timeline** node to the **Spawn Rock** node.  Change the **Rock Radius Offset** to `40.0`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectThreePinsAndOffsetSmallRockLvlBP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press the **Select Class** button on the **Spawn Rock** node.  Notice that you only get the base parent class of **BP_Rock_Parent** as well as all the classes that inherit from it.  Select **BP_Rock_Small**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectClassSmallBP1.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Your node chart should look like the picture.  Now play the game and you should be back to where we started.  Phew!
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RockEventSmallFinalModeChart.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now lets launch our medium rock we have setup.  Higlight the comment and **Spawn Rock** node and copy and paste it below:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CopyAndPasterSmallLaunchForMEd.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Change the comment to `Rock Medium Events`.  Attach the output of the timeline **Events Rock Medium** to the **Spawn Rock** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectMediumRockSpawnerLvlBP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the **Horizontal**, **Vertical** and **Angle** pins to each other from the **Timeline** node to the **Spawn Rock** node.  Change the **Rock Radius Offset** to `75.0`.  Set the **Select Class** to `BP_Rock_Medium`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectMediumRockSpawnPinsLvlBp.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Wow, that was a long way to get here.  But finally we have two rocks of different sizes launching.  Now play the game and shoot the rocks.  You will notice tha the small rock works correctly but the medium rock doesn't respond to bullet fire. There are no events called when the bullet collides with the medium rock.  
</div>
</div>
<div class="col-12 col-lg-8">
<div class="embed-responsive embed-responsive-16by9">
<iframe class="embed-responsive-item" src="https://www.youtube.com/embed/w67zdFXfRxE?autoplay=1&rel=0&controls=0&amp&showinfo=0&version=3&loop=1&playlist=w67zdFXfRxE" frameborder="0" allowfullscreen></iframe>
</div>
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets go to our **Rock Parent** script to find out why?  Look at the **Rock Small** cast.  We have a bullet collision event.  But we only do something when we cast to Rock Small.  We need to on its fail (checks to see if this is Rock Small) then cast to rock medium.  Lets try this.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DontHandleMediumRockBulletCollision.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Take the output pin of **Cast Failed** and pull from it a **Cast To BP_Rock_Medium** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PullOffCastFailedBPCastMediumRockP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now it won't compile without an input in the **Object** input pin.  Attach the **Self** output to this new **Cast** node like so:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectSelfToMediumCastRockM.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets test this in game.  Add a **Print String** node with the **In String** `Rock Medium Hit`.  Attach the execution pins.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TestWorkByPrintingRockP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Play the game and fire at the medium rock.  You should see it print out once.  It doesn't more than once because if you remember we killed the collider before we called these nodes, so the rock will not cause any more collisions once it has been hit once.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RockMediumMessageWorksRockP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We have a good starting point with our nodes in the Destroy Rock Small function.  Right click on the **Destroy Rock Small** in the **My Blueprint** tab and select **Duplicate**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DupeDestroyRockSmallRockP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Rename it to `Destroy Rock Medium`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RenameDestroyRockMedium.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go to the level and in the **Content Browser** go to the **Textures \| Sprites** folder.  Look for the medium rock explosion.  Notice we have a generic two frames for both rocks.  Select the two (shift or cntrl clicking):
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LookForMediumExplosionSprites.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Right click on one of them and select **Create Flipbook**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RightClickAndCreateFlipbook.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open the destroy animation to view it.  Change the **Frames Per Second** to `5.0`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ReduceDeathToFiveRockP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we can't change the sprite in a paper sprite component to a flipbook. What we will need to do is add an empty flipbook to the rock and switch off the sprite frame and switch on the flipbook playback.  We can do this by reopening the **BP_Rock_Parent** and going to the **Viewport** tab. Press the **Add Component** button and add a **Paper Flipbook**.  Drag this element to be under **Paper Sprite** (this will inherit the rotations we need).  Remember to leave the **Source Flipbook** empty for now.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddFlipbookLeaveEmpty.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go back to the **Destroy Rock Medium** function tab.  In the **Set Sprite** selecdt `None`.  This will effectively stop rendering this sprite.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MediumDestroySetSpriteToNone.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Drag a reference to the new **Paper Flipbook component between the **Set Sprite** and **To Desotroy Rock** nodes.  Drag off of the pin and select a **Set Flipbook** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddSetPaperFlipbbokToDestroyMedRockP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Reconnect the execution pins so it goes from **Set Sprite** to **Set Flipbook** to **To Desotry Rock**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectExecutionPinsBetweenMedRockDestRockP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press the **New Flipbook** drop down menu on the **Set Flipbook** node and select the `FB_Rock_Medium_Explodes` animation.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NewFlipbookMediumExplodes.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now your node tree should look like:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CompleteDestroyRockMedium.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back to the **event Graph** and look for the **Cast To BP_Rock_Medium** node.  Pull from the execution pin and selecdt **Destroy Rock Medium** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CallDestroyRockMedium.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go into the game and try this out.  You shoot the medium size rock.  Yay, it gets destroyed and runs the explosion animation.  One problem though, it should spawn two small rocks.  Lets take care of that next.
</div>
</div>
<div class="col-12 col-lg-8">
<div class="embed-responsive embed-responsive-16by9">
<iframe class="embed-responsive-item" src="https://www.youtube.com/embed/jZwBz0OYd2U?autoplay=1&rel=0&controls=0&amp&showinfo=0&version=3&loop=1&playlist=jZwBz0OYd2U" frameborder="0" allowfullscreen></iframe>
</div>
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back the **Destroy Rock Medium** function tab.  Disconnect the execution pins between **Set Flipbook* and ** To Destroy Rock** nodes.  Add a large space in between to spawn two new small rocks.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddRoomAfterSetFlipbookDestRckMed.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Right click in between these two nodes and add a **Spawn Actor From Class** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SpawnActorFromClass.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press the **Class** drop down and select `BP_Rock_Small`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectClassBPRockSmallDstRckMed.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we will add the transform so its starting position, scale and rotation is the same as the rock that was just hit.  Add a **Get Actor Transform** node.  This gets the transform of the self target (which is the rock that was just hit by a bullet).  Attach the **Return Value** to the **Spawn Transform** input pin on **Spawn Actor BP_Rock_Small** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetTransformForSmallRockSpawnDstRkMed.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we want the angle to deflect so they both sort of spray out in different directions.  Lets create a variable to hold the **Rock Deflection** amount.  Create a new variable called `Rock Deflection` of type **Float** that is **Private**.  Set the **Category** to `Rock Collision` and **Tooltip** to `Angle in degrees for rock deflection when destroyed`.  Press the **Compile** button and set the **Defautl Value** to `30.0`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RockDeflectionVariableAssignment.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off the **Return Value** pin and select the **Set Direction and Speed** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetDirectionSpeedFirstDeflectedRockSRockP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off the **Return Value** pin again and select the **Get Speed** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ReturnValueSetFirstSpeedDeflection.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Drag the output pin from the **Speed** node and attach it to the input pin **Rock Speed** in the **Set Directino and Speed** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SpeedToRockSpeedDefletionRockSmall.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a **Get Direction Degrees** and **Get Rock Deflection** node to the chart:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DragRefToDirDegRckDefl.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a **float + float** node and add the **Direction Degrees** and **Rock Deflection** nodes together.  Grab the output of the **Addition** node and attach it to **Rock Angle** in the **Set Direction And Speed** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddDirDegRockDefl.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Make some more room to the right of these nodes.  Select all the nodes for spawning the small rock and copy and paste them.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CopyAndPasteDeflectionNodes.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. The chart should look like:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ShouldLookLikeCopies.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the output execution pin from the first **Set Direction and Speed** node to the input of the second **Spawn Actor To BP_Rock_Small** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectSecondRockDeflectction.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Delete the **Addition** node.  Add a **float - float** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ReplaceAdditionWSubtractionDefl.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Make sure you subtract **Rock Deflection** from **Direction Degrees**.  Send the **Subtraction** output to the **Rock Angle** input of the second **Set Direction and Speed** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CalcSSecondDeflRockAngle.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Reconnect the execution pin of **To Destroy Rock** node to the last **Set Direction And Speed** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ReconnectToDestroyRck.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. The whole function should look like:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AllNodesDestroyRckM.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Play the game and shoot the medium rock. It should spawn two rocks that span out 60 degrees from each other like. On the next page lets add some more rocks to our first wave here.
</div>
</div>
<div class="col-12 col-lg-8">
<div class="embed-responsive embed-responsive-16by9">
<iframe class="embed-responsive-item" src="https://www.youtube.com/embed/BUqjNvQBqdE?autoplay=1&rel=0&controls=0&amp&showinfo=0&version=3&loop=1&playlist=BUqjNvQBqdE" frameborder="0" allowfullscreen></iframe>
</div>
</div>
</div>
_____ 

<br><br>

[<- Previous](Space-Rocks-16.html)&nbsp;&nbsp;&nbsp;[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](Space-Rocks-18.html)
<br />  
<br />  
<br />  




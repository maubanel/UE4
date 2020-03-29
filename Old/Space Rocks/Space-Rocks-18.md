---
layout: default
title:  "UE4 Space Rocks 18"
---

### Add More Rock Waves
To better test our game lets add some more waves.  Lets do three small and three medium rocks over 15 seconds.  Lets get started.

_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open the **Main Game Timeline** tab on the level blueprint.  Change the **Event Rock Medium** `Time` from **5** to `10` seconds. Add two new keys one at  Add two new keys one at **Time** `13.0` and **Value** `1.0` and another at **Time** `15.0` and **Value** `1.0`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MoveEventRockMedTo10.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now lets add two more event triggers to the **Event Rock Small** graph. Add a **Time** `3.0` and **Value** `1.0` and another at **Time** `8.0` and **Value** `1.0`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddTwoSmallRockEventsToTmline.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now lets set the second rock small.  Add a node to the **Horizontal** with **Time** `3.0` and **Value** `0.4`. Add a second node to the **Vertical** with **Time** `3.0` and **Value** `0.0`. Add a final node to the **Angle** with **Time** `3.0` and **Value** `80.0`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Set3SecondNodesTmline.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now lets set the final rock small for now.  Add a node to the **Horizontal** with **Time** `8.0` and **Value** `0.8`. Add a second node to the **Vertical** with **Time** `8.0` and **Value** `1.0`. Add a final node to the **Angle** with **Time** `8.0` and **Value** `-100.0`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Set8SecondNodesTmline.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now lets set the first rock medium spawn.  Add a node to the **Horizontal** with **Time** `10.0` and **Value** `0.55`. Add a second node to the **Vertical** with **Time** `10.0` and **Value** `0.0`. Add a final node to the **Angle** with **Time** `10.0` and **Value** `95.0`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Set10SecondNodesTmline.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Now lets set the second rock medium spawn.  Add a node to the **Horizontal** with **Time** `13.0` and **Value** `1.0`. Add a second node to the **Vertical** with **Time** `13.0` and **Value** `0.3`. Add a final node to the **Angle** with **Time** `13.0` and **Value** `45.0`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Set13SecondNodesTmline.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Now lets set the last rock medium spawn.  Add a node to the **Horizontal** with **Time** `15.0` and **Value** `1.0`. Add a second node to the **Vertical** with **Time** `15.0` and **Value** `1.0`. Add a final node to the **Angle** with **Time** `15.0` and **Value** `-135.0`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Set15SecondNodesTmline.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Runt the game and shoot both small and medium rocks.  Run into both small and medium rocks.  You will notice a bug that when we hit the medium rock with the player ship that the rock doesn't get destroyed as it does when hitting the smaller rock.  Lets fix this issues.
</div>
</div>
<div class="col-12 col-lg-8">
<div class="embed-responsive embed-responsive-16by9">
<iframe class="embed-responsive-item" src="https://www.youtube.com/embed/6ughow0j0dA?autoplay=1&rel=0&controls=0&amp&showinfo=0&version=3&loop=1&playlist=6ughow0j0dA" frameborder="0" allowfullscreen></iframe>
</div>
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open **BP_Rock_Parent** and look for the **Player Hit By Rock** nodes.  Zoom into the end o these nodes.  You will notice that we just call the destroy function for the small rock.  Lets fix this.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LookForPlayerHitByRock.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off of the **Self** pin after the **Set Flipbook** node and select a **Cast To BP_Rock_Medium** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CastToBPMediumRockPlayerColl.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull from the **Cast To BP_Rock_Medium** node and add a **Destroy Rock Medium** node.  Attach the **As BP_Rock_Medium** node to **Target** in the **Destroy Rock Medium** node.  Make sure that the **Call Failed** node from **Cast To BP_Rock_Small** is connected to the input of **Cast To BP_Rock_Medium**
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CallSecondDestroyRockMd.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now play the game and run into the middle size rock.  You will see that it correctly splits into two!
</div>
</div>
<div class="col-12 col-lg-8">
<div class="embed-responsive embed-responsive-16by9">
<iframe class="embed-responsive-item" src="https://www.youtube.com/embed/2vf-2eKUTRg?autoplay=1&rel=0&controls=0&amp&showinfo=0&version=3&loop=1&playlist=2vf-2eKUTRg" frameborder="0" allowfullscreen></iframe>
</div>
</div>
</div>
_____ 

### Rock Rotation
Now the rocks don't move very realistically.  A computer unfortunately has a lot of symmetry by default in how we approach it.  Lets start the animation at a random angle, and rotate the rocks at random speeds.  

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add another Variable to **BP_Rock_Parent**.  Call it `Rotation Speed` and make it type **Float**.  Make it **Private** and set the **Category** to `Movement`.  Set the default to `30.0` so that we rotate 30 degrees per second. Add a **Tooltip** that state `Rotation speed in degrees per second`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddRotationSpeedAssignment.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go to the **Event Begin Play** node.  Add to the very right of the nodes connected to it a **Random Float in Range** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GoToEndOfBeginPlayRockP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a **Get Rotation Speed** node to the event graph.  Attach the ouput to the **Max** input in the **Random Float in Range**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddRotationSpeedToRandomInput.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets set the minimum rotation to be the negative equivalent.  Add a **float * float** node.  Pull the output of the **Rotation Speed** to the top input. Change the bottom input to `-1.0`.  Connect the output of the **Multiplicatio** node to the **Min** input on the **Random Float in Range** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NegtaiveOppositeRandom.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Drag a **Set Rotation Speed** node to the graph:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddSetRotationSpeedNode.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the output of **Set Gamemode Reference** execution pin to the input of the newly created **Set Rotation Speed** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectSetRotationSpeedExecPin.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add to the right of this another **Random Float in Range** node and a **Set Direction Degrees** node.  In the **Random** node set the **Min** to `0.0` and **Max** to `359.0`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RandomRotationAngleSetDirectionRockP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the **Return Value** from the **Random Float in Range** node to the **Set Direction Degrees** node.  Connect the execution pin from **Set Rotation Speed** to the **Set Direction Degrees** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectSetRotationSpeedWithSetAngle.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a comment `Start at a random facing angle` to these nodes.  Zoom out and you should now have three distinct operations in the **Event Begin Play** execution pin flow.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddedSetupNodesRockP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go to the **Move Rock to New Location** section that ends with a **Set Actor Location** node.  Make some room to the right of it and add a **Get Rotation Speed** node and a **Get World Delta Seconds** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RotationSpeedDeltaTimeRockP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Right click and select a **Set Actor Rotation** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetActorRotationRockP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Right click on the **New Rotation** pin and select **Split Struct Pin**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetRotationSplitPinRockP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a **Get Actor Rotation** node. Right click on the **Return Value** pin and select **Split Struct Pin**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GetActorRotationRockPSpli.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a **float + float** node. Connect the output of the **Multiplication** pin and the **Return Value Z(Yaw)** pin to the inputs of the **Addition** node.  Send the **Addition** node to the **New Rotation Z(Yaw)** in the **Set Actor Rotation** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FloatPlusFloatConnectRotateRockP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We are not changing **Rotation X** and **Rotation Y** so hook up the **X** and **Y** pins together from the **Get Actor Rotation** to the **Set Actor Rotation** pins.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LeaveXYUnchanged.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the output execution pin from **Set Actor Location** to the input pin in **Set Actor Rotation**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetActorToSetActorRotRockP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go and play the game.  You will notice that the rocks rotate at different speeds and start at different angles.  It looks a lot more organic - subtle but meaningful change.  Press **Save All** and update Github by **committing** and **pushing** all the changes made. Next up we will start building the HUD.
</div>
</div>
<div class="col-12 col-lg-8">
<div class="embed-responsive embed-responsive-16by9">
<iframe class="embed-responsive-item" src="https://www.youtube.com/embed/qyMK8x221Bg?autoplay=1&rel=0&controls=0&amp&showinfo=0&version=3&loop=1&playlist=qyMK8x221Bg" frameborder="0" allowfullscreen></iframe>
</div>
</div>
</div>
_____ 

## Part 5 - HUD and Front End
Now lets build a HUD.  The game starts with a prompt to start the game.  There is an in game HUD with score and lives.  There is an end game screen where you can restart the game.  Lets get started.

_____ 

### 10. [HUD Score
Lets start by building the score.  But before we build the widget, we need a genearl HUD class.  Lets start by creating this.
_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press the **Blueprints** button and select **GameMode: Edit... \| HUD HUD \| + Create \| HUD**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreateHUDBP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Call it `BP_Space_Rock_HUD`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CallItBPSpaceRockHUD.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go to **Project Settings** and **Maps and Modes**.  Look at the **Selected GameMode* and press the triangle to expand it. Check out the **HUD Class**.  Notice that it has already placed **BP_Space_Rocks_HUD** there based on how we created it through the menu.  We are good to start.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreatedItInPSGameSettings.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press the **Add New** button and select a new **User Interface \| Widget Blueprint** class. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddInGameScoreWidgetBP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Rename it to `BP_Ingame_Widget`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RenameInGameWidget.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open **BP_Ingame_Widget**.  Drag a **Text** from the **Palette** menu and drag it into the screen: 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddTextToIngameWidget.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Change the name to to `Score` in the **Hierarchy** tab.  Change the **Content \| Text** to `0`.  Change the **Font \| Size** to `45`.  Change the **Justification** to **Centered** text.  Fit the Green box around the text and center it on the top center of the screen.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SettingsForScoreTextIngameW.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press the **Anchor** button and select the top middle selection:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectTopCenterAnchorForScore.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Make final adjustments to the position of the Score text.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MakeFinalPositionAdjustments.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go back to **BP_Space_Rock_HUD** and create or alter the function and call it `Create In Game HUD`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreateInGameHudFunction.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off of the **Create In Game HUD** execution pin and select a **Create Widget** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreateWidget.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press the **Class** and select `BP_Ingame_Widget`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectBPInGameWidgetHUD.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off the **Return Value** pin and put a **Add to Viewport** node on the graph.  Connect the execution pins.  Add a comment `Adds Ingame HUD to Widget`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddToViewPortHUD.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We will activate this widget in the level blueprint.  Selecdt **Blueprints \| Level Blueprints**.  Go to the custom event **Restart Game**.  Make some space to the right of it.  Add a **Get Player Controller** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddToRestartGamePlayerCont.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off of the **Return Value** pin and select **Get HUD** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GetHUDRefLvlBP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Drag off the **Get HUD \| Return Value** pin and select a **Cast To BP_SPace_Rocks_HUD**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CastToSpaceRocksLvlBP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off the **As BP_Space_Rocks_HUD** pin and call the function you just created **Create Ingame HUD**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CallCreateInGameHUD.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Highjack the **Restart Game** node's executioon pin and send to **Cast to BP_Space_Rock_HUD** then **Create In Game HUD** then the **Timeline**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/HighjackExecutionPins.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Run the game and a score appears. Now it stays at zero as we are not adding up a score. On the next page we will create and update a variable for this.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RunGameScoreAppearsStaysAtZero.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

<br><br>

[<- Previous](Space-Rocks-17.html)&nbsp;&nbsp;&nbsp;[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](Space-Rocks-19.html)
<br />  
<br />  
<br />  




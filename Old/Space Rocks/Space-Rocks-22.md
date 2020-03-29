---
layout: default
title:  "UE4 Space Rocks 23"
---

### End Game Flow Continued

_____ 

{% assign num = 37 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back to **BP_Player_Pawn** to the end of the player dies section.  Disconnect **Call Restart Space Rock Game** exit execution pin.  It will no longer change back to the gameplay state.  Take the nodes that it is disconnected from and move it closer to the left top nodes where the player dies with lives left.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ChangePlayerDiesFlow.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Copy the **Gamemode Reference**, **Set Game Mode** and **Reset Player to Start Node** and paste them below to the right.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CopyAndPasteStateRestPlayer.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Change the **Set Game State** to `Pre Game`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetGameStateToPreGame.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the **Call Restart Space Rock Game** node to **Set Game State** execution pin.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectRockPinPlayer.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off the execution pin from **Reset Player to Start** and select the **Remove All Widgets** node to get rid of the huds.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RemoveAllWidgetsPlayer.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull from the **As BP_Space_Rocks_HUD** and pull all the way to an open spot on the right and select a **Create Pre Game HUD** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CastSpaceRocksToPreGameHUD.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Connect the output of the **Remove All Widgets** execution pin into the input of the **Create Pre Game HUD** pin.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectRemoveToPreGameHUDPin.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off of the **Create Pre Game HUD** node execution pin and select a **Set Actor Hidden In Game** node set **New Hidden** to `true`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PregameHudToHidePlayer.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Go back to the level blueprint.  Now we will not restart each game when this event is called, it will instead go to the pre game state. Disconnect the custom event **Begin To End** node's **Bind Event to Restart Space Rock Game** output execution node.  Move it to the **Begin Play** secdtion to the right of **Spawn Player In Center of Level** nodes:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MoveEventDispatcher.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Find the **Destroy Pre Game Rocks** nodes and copy them.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CopyPreGameRocks.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Paste the nodes after the Bind Event From Player Pawn nodes. Connect the execution pin from **Bind Event Restart Space Rock Game** to **Get All Actors Of Class**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PasteAfterBind.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off of the **For Each Loop Complete** pin and add a **Create Pre Game Rocks** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CompletedPreGameRocks.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}-4U
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Play the game and lose all three lives.  Now you will notice that it goes from game over to pre game just like we wanted to.  Now lets move to the final stage and implement some sound before we finish this exercise.
</div>
</div>
<div class="col-12 col-lg-8">
<div class="embed-responsive embed-responsive-16by9">
<iframe class="embed-responsive-item" src="https://www.youtube.com/embed/WARpbMUe-4U?autoplay=0&rel=0&controls=0&amp&showinfo=0&version=3&loop=0&playlist=WARpbMUe-4U" frameborder="0" allowfullscreen></iframe>
</div>
</div>
</div>
_____ 

## Part 6 

### Audio
Now the final portion of this execise is to add audio to the game.

_____ 
{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back to the main game tab.  Press the **Add New** button and add a folder called `Sounds`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddNewFolderSounds.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press the **Import** button and go to the **Source** folder and import all `.wav` files:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ImportAllWavs.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  You should end up with all the sounds you need for the game.  Don't be afraid to click on them and listen to them.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/EndUpWithSoundsInFolder.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets start with the shooting sound.  Now we don't want to play it raw.  We want to add a variety of tone and volume shifts to give it less repetitive repeating sound since it will play so much.  Right click on **S_Shoot** and select **Create Cue**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreateSoundCueShoot.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Rename this cue to `SC_Shoot`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RenameSCShoot.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Double click the **SC_Shoot** and get to the sound cue editor.  Looks very similar to blueprints and materials.  Right click in the graph and add a **Modulator** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SoundCueAddModulator.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Connect the **Modulate** node pins between the **Wave Player S_Shoot** and the **Output** nodes.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ModulateBetweenSoundAndOutput.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Play with different values in the modulator and listen to them.  For the game I am going to stick with the defaults.
</div>
</div>
<div class="col-12 col-lg-8">
<div class="embed-responsive embed-responsive-16by9">
<iframe class="embed-responsive-item" src="https://www.youtube.com/embed/k_9VN8AFcLI?autoplay=0&rel=0&controls=0&amp&showinfo=0&version=3&loop=0&playlist=k_9VN8AFcLI" frameborder="0" allowfullscreen></iframe>
</div>
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Go to the **BP_Player_Pawn** blueprint and zoom out.  Look for the shooting nodes:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LookForShootingInPawn.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go to the very end of those nodes.  Pull off of the **Reload** execution pin and look for the **Play Sound 2D** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PlaySound2D.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Click on the **Sound** dropdown and select the `SC_Shoot` sound cue.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ClickOnSoundSCShoot.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. So the graph should look like:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FinishedShootingSnd.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Now go to the game and play it.  Hit the shoot button and we should trigger the sound every time you shoot.
</div>
</div>
<div class="col-12 col-lg-8">
<div class="embed-responsive embed-responsive-16by9">
<iframe class="embed-responsive-item" src="https://www.youtube.com/embed/I8Pcw8Q2rnA?autoplay=0&rel=0&controls=0&amp&showinfo=0&version=3&loop=0&playlist=I8Pcw8Q2rnA" frameborder="0" allowfullscreen></iframe>
</div>
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go back to the **Sounds** folder and right click on **S_Hit_Rock_Small** and select **Create Cue**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreateCueRockSmall.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Call it `SC_Hit_Rock_Small`.  Repeat for **S_Hit_Rock_Medium** by right clicking and selecdting **Create Cue**.  Call this one `SC_Hit_Rock_Medium`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RepeatForMediumRockCue.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Double click the **SC_Hit_Rock_Medium** and add a **Modulator** node.  I played with the **Pitch Min** and **Pitch Max** and widened it a bit to my liking.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ScMediumModulatorSettings.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Repeat the exact same procedure for **SC_Hit_Rock_Small**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RepeatModulatorSCRockSmall.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open up **BP_Rock_Parent**.  Lets look for the best place to put this sound.  I think the functions where we destroy the rocks looks best as it will have past all the checks.  The sound should occur when the rock is destroyed as well.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GoToRockParentDestoryRockSm.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Go to the **Destroy Rock Small** tab (or double click the function to reopen the tab).  Go to the very end and pull off the **Set Score** execution pin and select another **Play Sound 2D** node.  Press **Sound** and select `SC_Hit_Rock_Small`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PlaySmallRockDestroySound.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. So your nodes should look like:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FinalHitRockSmall.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Go to the **Destroy Rock Medium** function and add a **Play Sound 2D** node at the end of it.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RepeatDestroyRockMd.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press **Sound** and select `SC_Hit_Rock_Medium`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectSoundRockMed.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  
</div>
</div>
<div class="col-12 col-lg-8">
<div class="embed-responsive embed-responsive-16by9">
<iframe class="embed-responsive-item" src="https://www.youtube.com/embed/amef4v-fWyI?autoplay=0&rel=0&controls=0&amp&showinfo=0&version=3&loop=0&playlist=amef4v-fWyI" frameborder="0" allowfullscreen></iframe>
</div>
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now lets make a thrust sound every time the player holds the thrust button.  Open **BP_Player_Pawn** and add some space beneath **Event Begin Play**.  In this space add a **Spawn Sound 2D** node.  We need a reference to this sounds as we will be turning it on and off.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MqkeRoomForThrustSound.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Pull off of the **Return Value** pin and select the **Promote to variable** option:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PromoteSoundReturnValueToVariable.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Call it `Thrust Target`.  Make it **Private** and add it to **Category** `Targets`.  Set the **Tooltip** to `Accesses thrust sound`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ThrustTargetAssign.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Now we don't want this sound to play so pull off of the **Set Thrust Target** output pin and selecdt **Set Active**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetInactdiveThrustSound.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the execution pins by connecting **Spawn Sound 2D** to **Set Gamemode Reference**. Add a comment around these nodes called `Get Thrust Sound Reference and Deactivate`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectThrustExecutionPins.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Click **Sound** on the **Spawn Sound 2D** node and select `S_Thrust`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectSThrustSound.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Zoom out on the blueprint and look for the three times we set the **Thrust Button Held** boolean.  We can use this to determine when the play these sounds.  Lets start with the Reset Thrust when Not In Gamemode and just turn the sounds off there.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ZoomOutThrustButtonHeld.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Drag a **Get Thrust Target** node to the right of **Set Thrust Button Held** (that is set to **false**). Pull off the pin and look for **Set Active**.  Lets continue adding the thrust sound on the next page.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ThrustTargetSetActiveForReset.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
<br><br>

[<- Previous](Space-Rocks-21.html)&nbsp;&nbsp;&nbsp;[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](Space-Rocks-23.html)
<br />  
<br />  
<br />  



---
layout: default
title:  "UE4 Space Rocks 20"
---

### HUD and Lives Continued

_____ 

{% assign num = 29 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the output pins from all four **Set** nodes to the **Return Node**.  Add a **Get Health Bar Amount** and attach it to the **Return Value** pin in the **Return Node**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FinishOffHealthHud.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Play the game and kill yourself.  Your lives should go down form 3, to 1 to 0.  Press **Save All** and update Github by **committing** and **pushing** all the changes made. Next up we will add the starting screens for the game.
</div>
</div>
<div class="col-12 col-lg-8">
<div class="embed-responsive embed-responsive-16by9">
<iframe class="embed-responsive-item" src="https://www.youtube.com/embed/MMTcVOEs3gI?autoplay=1&rel=0&controls=0&amp&showinfo=0&version=3&loop=1&playlist=MMTcVOEs3gI" frameborder="0" allowfullscreen></iframe>
</div>
</div>
</div>
_____ 

### Start Game Flow
Before finishing off the end of game flow, lets get the starting flow working.  You will start the game with a Start Game graphic and a hint to press enter.  Some rocks will be flying by behind tihs.  As soon as you press the enter button the game will start.  Lets add this to our flow.  Lets start by adding two more widgets one for end game and one for the pre game.

_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press the  **Add New** button and select the **User Interface \| Widget Blueprint** to create a new widget.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MakeSecondWidget.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Call it **BP_End_Game_Widget**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CallItGameOver.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Drag an **Image** from the **Palette** menu to the screen.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DragImageToPalette.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open the widget and select **Appearance \| Image** and set it to `SP_Game_Over_HUD` graphic.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AppearanceImageGameOverHud.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Change the **Size X** to `730.0` and **Size Y** to `132.0` and center the font in the game screen.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GameOverCenterResize.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Change the **Appearnace \| Tint** to light blue.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TintGameOverText.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back to the **Content Browser** and right click on **BP_Game_Over_Widget** and press **Duplicate**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DupeGameOver.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Rename the file to `BP_Pre_Gamne_Widget`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RenameToBPPreGameWid.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open up the **Widget** and change the **Image** to **BP_StartGame_A_HUD**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ChangeImageToStartGame.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. On the **Hierarchy** tab copy and paste (there is no duplicate) the image.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CopyPasteHieracrchyStartGame.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Change the **Image** to **BP_StartGame_B_HUD**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/StartGameBImage.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Position the **Start Game** and **Press Enter** text to your taste.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PositionStartTextToTaste.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we will need another button to trigger the start game.  So open **Edit \| Project Settings** and go to **Input** on the side menu.  Press the **+** button next to **Action Mapping** to add a third action:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddNewActionMappingInput.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Call the event `Start Game` and select the `Enter` button as the key to press.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/StartGameEnterButton.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We need to open the **BP_Space_Rocks_HUD** class and add a new **Function**.  Call it `Create Pre Game HUD`.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreatePreGameHUDFunc.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off the **Create Pre Game HUD** execution pin and select a **Create Widget** node.  Select **Class** `BP_Pre_Game_Widget`.  Pull off it its execution pin and select **Add to Viewport**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddPreGameToViewport.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the **Return Value** pin to the **Target** pin.  Add comment `Add Pre Game HUD to Widget`.  Press the **Compile** button.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ReturnToTargetCommentCompile.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now the game will start in the pre game state.  So lets activate this HUD in the **Construction Script** tab of the **BP_Space_Rocks_HUD** script.  Pull off the **Contruction Script** pin and select **Create Pre Game HUD**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CallCreateInGameHUDConstructorB.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now if you remember we set out default state in the **BP_SpaceRocks_Gamemode**.  Open this blueprint and select the variable **Global Game Settings \| Game State**.  Change its **Defualt Value** to `Pre Game`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ChangeStateToPreGame.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Currently we spawn the player right away but we don't want a player in the pre game state.  So go to the **Level Blueprint** an dlook for where we spawn the player then start the game.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LookForSpawnGameStartPlayernodes.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Disconnectd the **Sequence Then 1** pin from the **Spawn Actor BP_Player_Pawn** and move the two nodes off to the left for now.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DisconnectThePinDragToLeftLvlBP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Start the game and you should now see out title screen but nothing happens.  Lets add some rocks floating in the background then add the logic to start the game.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/StartGameTitleScreen.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. At the very top of the **Level Blueprint** choose a **Add Custom Event** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddCustomEventTopLevelBP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Call it `Create Pre Game Rocks`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RenameCreatePreGameRocks.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a **Spawn Rock** node to call this custom event.  Change **Horizontal** to `0.2`, **Vertical** to `0.7`, **Angle** to `30` and **Rock Radius Offset** to `70` and **Class Reference** to `BP_Rock_Medium`.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SpawnFirstPreGameRock.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Copy and paste this three times.  Select different rocks and different settings for the four rocks.  Daisy chain all the execution pins and create a comment called `Pre Game Rocks` which should explain what we are doing here.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreateThreeMoreConnectExecutePins.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back to the area where you disconnected the pins next to **Event Begin Play**.  Add a call to **Creat Pre Game Rocks**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GoBackToPreGameGapEventPlay.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a comment called `Launch Per Game Rocks`.  Why do this, it is a node and it is self exaplanatory.  The reason is that when zoomed out looking at all the nodes, the comments are all scaled.  It makes it much easier to find where you put things when looking to adjust a previous node or secdtion. Now it is critical that you change the order here. You need to highjack the **Sequence Ten 1** pin and send it to the **Cast** node in the Get Extents of Level.  We need these camera extents within the Spawn Rock function. The take the **Sequence Then 2** and send it to **Create Pre Game Rocks**. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ExecuteInCorrectOrderLaunchRocks.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Play the game and we should have the pre game title screen and rocks in the background. Notice that it always sorts the HUD widget in front of the game objects.  We didn't have to adjust this anywhere.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/StartWithRocks.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now lets create a trigger to start the game.  Remember we created an input action for this in the project settings.  Right click at the top of the **Level Blueprint** and select **Input \| Acdtion Events \| Start Game**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddStartGameEventInputAction.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a **Get Game Mode** node then cast it to our **BP_SpaceRocks_Gamemode**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddGetGameModeAndCast.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Select the output blue pin from the **Cast** node and select a **Get Game State** node.  We need to make sure we are actually in the **Pre Game** State before we perform the action.  We wouldn't want to restart the game while playing if we accidentally pressed the **Enter** button.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GetGameStateMode.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off of the **Game State** pin and select a **Equal (Enum)** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GameStateToEqualStartGameLvlBP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Change the Enum to `Pre Game`.  Then pull off the output pin and selectd a **Branch** node.  So the logic here is if the Game State is equal to **Pre Game** then the **Branch True** pin will execute when this event is called.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CheckPreGameThenBranchLvlBP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now pull from the output pin on the **SpaceRocks_Gamemode** node and add a **Set Game State** pin.  We will be changing the state to Gameplay.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetGameStateIngameLvlBP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the **Branch True** execution pin to the **Set Game State** node.  Select **Game State** `Gameplay`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectPinChangeStateGameplay.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull of the **Set Game State** execution pin and select the **Restart Game** node which is the custom event we created to include all the start game initializaiton.  Add a comment around all these nodes called `Start Game From Pre Game Screen`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RestartGameComment.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Zoom back out.  Look for the two disconnected nodes we marooned earlier.  The call to **Start Game Mode** can be deleted as we have put a new call to this in the correct spot.  The **Spawn** player node needs to be moved into the **Start Game** custom event flow:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DeleteStartGameMoveSpawnPlayer.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Make some space to the right of the **Restart Game** event and move the **Spawn Player** node and comment in the space like so:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MakeSpaceMoveSpawnPlayer.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We need to clean up the rocks we spawned in the pregame menu.  We need to destroy them.  So make some space between the **Restart Game** and the **Spawn** player nodes.  Right click in the middle and add a **Get Actors Of Class** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MakeRoomToDestroyPreGameRocks.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press **Actor Class** and select `BP_Rock_Parent`.  This will select ALL classes that inherit from it.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectRockParentInRockDestroyer.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Notice the output is an array.  We will need to loop through each one.  Pull from the **Out Actors** node and selecct **For Each Loop** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ForEachRockDestroyer.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off of the **Loop Body** execution pin and select a **Destroy Actor** node. Lets continue on the next page
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddDestroyActorRockDestroyer.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

<br><br>

[<- Previous](Space-Rocks-19.html)&nbsp;&nbsp;&nbsp;[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](Space-Rocks-21.html)
<br />  
<br />  
<br />  




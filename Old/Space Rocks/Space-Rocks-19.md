---
layout: default
title:  "UE4 Space Rocks 19"
---

### HUD Score Continues

_____ 

{% assign num = 20 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. The best place to store our global variables is in the game mode.  Open **BP_Spacerocks_Gamemode**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/OpenBPSpacerocksGamemodeHUD.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add an **Integer** variable type called `Score` in **Category** `Global Game Settings` with a tooltip `Tracks Score of Game`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ScoreIntAddGamemode.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back to **BP_Ingame_Widget** and seledt the **Score** text.  Press the **Bind** button and create a bind.  This will take you from the Designer view to the Graph view:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GraphViewBindWidgetGame.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. I dind't like the default name of the function so I renamed it to `Get_Score`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RenameToGetScore.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a **Get Game Mode** node. Pull off the **Return Value** pin and select a **Czst To BP_SpaceRocks_Gamemode** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddGetGameModeThenCastWidgInGame.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off the **As BP SpaceRocksGamemode** pin and select **Get Score**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GetScoreFromGamemodeWidget.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Take the output of **Score** and put it to the **Return Value**.  UE4 adds a **To Text** node to convert the format for us. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SendScoreToReturnWidget.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add comment to the nodes `Gets Score and sends to Widget`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddCommentToGetScore.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open **BP_Rock_Parent** and lets adjust the scores.  Open the **Destroy Rock Small** tab and go to the far right and make some room in the comment box. Add a **Get Gamemode Reference** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DestroyRockSmallAddScore.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off the **Gamemode Reference** pin and select a **Get Score** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GetScoreRefRockP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Add a **int + int** node to increment the score.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/IntPlusIntScoreRockP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the output pin from **Score** to the top in of the **Addition** node.  Set the bottom to `100`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Add100ToScore.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off **Gamemode Reference** and select the **Set Score** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetScoreRockSmall.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the output execution pin from **To Destroy Rock** to the **Set Score** node.  Attach the output of the **Addition** node to teh **Score** pin in the **Set** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectSetScore.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add comment `Adjust Score`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddAdjustScoreComment.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Select the adjust score nodes including the comment and press copy (cntl C).
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CopyAdjustScore.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go to tab **Destroy Rock Medium** and make room to the far right of the nodes.  Paste the adjusted score you just copied:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MakeRoomPasteRockM.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Connecdt the output execution pin from **To Destroy Rock** to the **Set Score** node
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectDestroyToScoreRockM.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Change the added score to `50` in the **Addition** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ChangeAddedScoreTo50.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Play the game and shoot rocks. The score should increase by 100 for small rocks and 50 for medium ones.   Press **Save All** and update Github by **committing** and **pushing** all the changes made. Next up we will implement lives to the HUD and game logic.
</div>
</div>
<div class="col-12 col-lg-8">
<div class="embed-responsive embed-responsive-16by9">
<iframe class="embed-responsive-item" src="https://www.youtube.com/embed/2XFk0bvMF2k?autoplay=1&rel=0&controls=0&amp&showinfo=0&version=3&loop=1&playlist=2XFk0bvMF2k" frameborder="0" allowfullscreen></iframe>
</div>
</div>
</div>
_____ 

### HUD and Lives

_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we will show our lives on the screen.  We will use the progress bar to show it.  Even though this is not continual health we can hide parts of a graphic with three lives to alter.  Open **BP_Ingame_Widget** and drag a **Progress Bar** into the top left corner of the sceen:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ProgressBarInGameWidget.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go to **Style \| Fill Image \| Image** and select `SP_Lives_HUD` that we created at the very begining of this exercise. Notice that this is covered by the background color.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FillImageSPLivesHUD.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Double click the **Background Color** and set the **Alpha** to `0.0`, making it transparent.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BackgroundAlphaZero.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Click the **Tint** under the **Fill Image**.  Select a light blue. Now we see the fill image and it is blue, but nothing shows up on screen.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TintFillImageHud.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. You don't see any graphics as it is set to 0.  Think of this as a health bar that is normalized where 0 is empty and 1 is 100%.  So change the **Progress \| Percent** to `1.0` and you now see the planes but they are squished.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ProgressBarPercentAt1.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. The images in the HUD don't get imported at scale.  Change the **Size X** to the original `128.0` and **Size Y** to `32.0` to get back to a 1:1 scale with the original artwork. Now it looks much better. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FixScaleHealth.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We will change this widget by having percent at `1.0` for three lives, `0.6` for 2, `0.3` for one life and `0` for when the game is over and no lives are left.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SwitchLivesByChangingPercent.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We need a variable to track lives. We will go to the same place we keep the score.  Open **BP_SpaceRock_Gamemode** and right click on **Score** and select **Duplicate**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/VariableForLives.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Change the name to `Lives` and **Tooltip** to `Track Lives in Game`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LivesAssignment.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open the **Level Blueprint** and make some room to the right of the **Event Restart Game** node.  Add a **Get Game Mode** node and pull off the **Return Value** pin and select a **Cast To BP_SpaceRocksGamemode** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GetGamemodeRefLvlBP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off the **As BP SpaceRocks_Gamemode** pin and select **Set Lives** node.  Highjack the execution pin from **Restart Game** send it to **Cast** then **Set** then to the final **Cast** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetLivesInLvlBP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. In the **Set Lives** node change the **Lives** to `3`.  Add a comment `Make sure score is set to 3 when game restarts` around these new nodes we just created.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetLivesToThree.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we need to subtract the lives by one when the player dies.  Zoom into the last portion of the Player Hit by Rock section in the **BP_Rock_Parent** Event Graph.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PlayerHitByRockMakeRoom.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add some room after the **Set Flipbbok** node. Add a **Get Gamemode Reference** node.  Pull of its pin and select a **Get Lives** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MakeRoomAddGetLivesToCountdownNode.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Right click on an empty areea and select an **integer - integer** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/IntMinusIntCalcLivesNode.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off the **Gamemode Reference** node again and select **Set Lives**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetLivesNode.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the output of **Lives** to the top input of the **Subtraction** node.  Leave the default to subtracing by `1`. Send the output to the **Set Lives** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectLivesPins.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Highjack the output execution pin from **Set Flipbook** and send it to **Set Lives** node then to the **Cast To BP_Rock_Small** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ExecutionPinsSetLives.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open the **BP_Ingame_Widget** and press the **Bind** button next to the **Percent** bar to allow us to affect its value.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BindProgressBarWidget.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Rename the function `Display Lives`.  Add a **Get Game Mode** node.  Pull off the **Return Value** and select a **Cast To BP_SpeedRocks_Gamemode** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DisplayLivesFunction.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off of the **As BP SpaceRocks_Gamemode** pin and add a **Get Lives** node: 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GetLivesWidget.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a **Equal (integer)** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddEqualIntPin.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Copy and paste the **Equal** node twice.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CopyAndPasteTwoMoreEqualNodes.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connet the output of the **Lives** pin into the top node of all three **Equal** nodes.  Set the top one to `3`, middle one to `2` and bottom one to `1` as the second value.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectLivesToEqualCountdown.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press the **+** button in **Variables** add a **Float** called `Health Bar Amount` with a tooltip of `A scale between 0 and 1`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddLifeSizeVariable.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off the first **Equal** node and add a **Branch** node.  Add a **Set Bar Amout** node.  Connect the **True** from **Branch** to the **Set Health Bar Amount** execution node.  Set the value to `1.0`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BranchSetBarAmountOne.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Copy and paste the **Branch** and **Set** nodes twice.  Connet **False** form the first **Branch** to the input of the second **Branch** node.  Set the middle value to `0.60`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TwoMoreSetNodes.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Daisy chain the **False** to input nodes below.  Change the bottom node to `0.30` and pull of the last **False** pin.  Select another **Set Health Bar Amount** node and set the value to `0.0`. We will finish this off on the next page.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetFourthNodeHealthAmount.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 



<br><br>

[<- Previous](Space-Rocks-18.html)&nbsp;&nbsp;&nbsp;[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](Space-Rocks-20.html)
<br />  
<br />  
<br />  




---
layout: default
title:  "UE4 Space Rocks 1"
---

## Space Rocks

We will be making our first game and putting all of what we practiced in Materials and Blueprints to work.  We will pick a very simple one level game with a full game cycle including audio. We will be doing a Asteroids like game that consists of a space ship that flies around and shoots rocks.  Lets get started!

_____ 

## Index
_____ 

* Part 1 - Setting up with Git/Github
1. [Starting New Git Repository](#starting-new-git-repository)
2. [Starting Blank Unreal Project](#starting-blank-unreal-project)

* Part 2 - Getting the Basics Set Up
1. [Starfield Background Part 1](#starfield-background-part-1)
2. [In Game Camera](Space-Rocks-2.html#in-game-camera)
3. [Starfield Background Part 2](Space-Rocks-2.html#starfield-background-part-2)
4. [Import Sprites](Space-Rocks-3.html#import-sprites)

* Part 3 - SpaceShip
1. [Getting BP Setup](Space-Rocks-3.html#getting-bp-setup)
2. [Create Space Ship Material](Space-Rocks-4.html#create-space-ship-material)
3. [Ship Rotation](Space-Rocks-5.html#ship-rotation)
4. [Ship Thrust](Space-Rocks-5.html#ship-thrust)
5. [Ship Friction](Space-Rocks-6.html#ship-friction)
6. [Screen Wrapping](Space-Rocks-7.html#screen-wrapping)
7. [Ship Maximum Velocity](Space-Rocks-9.html#ship-maximum-velocity)
8. [Firing Bullets](Space-Rocks-9.html#firing-bullets)

* Part 4 - Rocks
1. [Rock Parent](Space-Rocks-11.html#rock-parent)
2. [Rock Small](Space-Rocks-12.html#rock-small)
3. [Rock Spawner](Space-Rocks-12.html#rock-spawner)
4. [Rock Collisions](Space-Rocks-13.html#rock-collisions)
5. [Game State](Space-Rocks-14.html#game-state)
6. [Rock Killing Player](Space-Rocks-15.html#rock-killing-player)
7. [Rock Medium](Space-Rocks-16.html#rock-medium)
8. [Add More Rock Waves](Space-Rocks-18.html#add-more-rock-waves)
9. [Rock Rotation](Space-Rocks-18.html#rock-rotation)

* Part 5 - HUD and Front End
10. [HUD Score](Space-Rocks-18.html#hud-score)
11. [HUD and Lives](Space-Rocks-19.html#hud-and-lives)
12. [Start Game Flow](Space-Rocks-20.html#start-game-flow)
13. [End Game Flow](Space-Rocks-21.html#end-game-flow)

* Part 6 [Audio](Space-Rocks-23.html#Audio)

_____ 

## What you will need?

For this project you will need to be install [Unreal Engine 4.20.x](https://www.unrealengine.com/en-US/download) , have a [GitHub](https://github.com/) account (which is free of charge) as well as [GitHub Desktop](https://desktop.github.com). 

_____ 

### Starting New Git Repository
_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. If you are a student of mine in class you will have received an email of this same repository and will view the invitation and press the **Accept this Assignment** button.  Once this process is complete open **Github Desktop** and press **File \| Clone Repository** and clone the `LSU-UE4-UE4SpaceRocks` repository.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GithubClassroomInvite.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. If you are not part of the class you can login into github with your personal account and navigate to  [https://github.com/maubanel/UE4SpaceRocks](https://github.com/maubanel/UE4SpaceRocks) and in the top right corner press the fork button:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SpaceRocksGithubLink.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open up GitHub Desktop and select **File \| Clone repository**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CloneRepository.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Select the ue4-space-rocks project to clone.  Put it on a drive where you have lots of space.  Press the **Clone** button to complete the process:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectProjectToClone.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Navigate to the directory where you installed it.  You will have a **Source Files** folder with all the files you need.  There is a hidden .git folder that contains the database for all your files. There is a **LICENSE** file that declares the copyright and licensing terms.  You can look at this if you like.  The README.md file is blank.  You should fill it in with relevant content. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/EmptyInstall.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now I didn't provide you with the .gitignore.  Again this is SUPER important, it will stop the engine and temporary files from cluttering up space on your projects.  The .gitignore file can be found at [github](https://github.com/github/gitignore/blob/master/UnrealEngine.gitignore). In the future you can just google **.gitignore UE4** and it will link you to this project.  Click on the **Raw** button to make copying and pasting easier:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RawGitIgnore.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Select all the text and copy it (**Edit \| Copy** or _cntr C_).
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CopyGitIgnoreFileContents.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Fire up **Notepad** (do not use a word processor like Word) and paste the text into it.   
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CopyToNotepad.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Change the **Save as type:** to `All Files (*.*).  Call the file `.gitignore`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Gitignoredottxterror.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Select the directory with that you downloaded git to and press save:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/OpenCommandPromptStudio.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go back to the directory and you should see that is lost the extension.  I can't stress how **IMPORTANT** it is for the `.gitignore` file to be spelled correctly with no extension (sometimes windows hides the extension).  It will not work properly so be CAREFUL!
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/dotgitignorecorrected.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. If you see an empty file with no name you can go to **File Explorer \| View** and set **File name extensions** to `true`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CommandLineChangeName.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

## Starting Blank Unreal Project
Now we are ready to start a new Unreal project.  Now I would like to be able to create it right in this directory, but Unreal needs an empty folder name to install.  So we will install it in a temporary directory then manually move it.  Lets get started.

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now run the **Epic Launcher**.  Go to **Unreal Engine** tab and **Library**.  Launch versio00n 4.20.x by clicking on the button:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/UnrealLauncher.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. When the Unreal Project Browser finally loads - 1. Select the **New Project** tab. 2. Select the **Blueprint** tab underneath.  3. Select a **Blank** project.  4. Select a Console game with Maximum quality with No Starter Content.  5. Choose a temporary directory to place the files.  6.  Enter the name `SpaceRocks`.  7.  Press the **Create Project** button:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NewProject.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. You will be sent to the editor.  We will not start yet select **File \| Save All**.  When the project is saved press **File \| Exit** and exit the game engine.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SaveAllEditor.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Move all the files that were in the **SpaceRocks** folder where you put the project.  Select all the files within this folder and move it to the root of the **ue4-space-rocks** folder with the .gitignore files.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MoveFilesToGitFolder.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Double check that the project file is in the same directory as the .gitignore, or it won't work (Please not there should also be a **.git** folder in this directory).
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MoveToFinalSpot.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____  
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go to **GitHub Desktop** and commit and push the latest files with an appropriate message;
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SaveAndPushToGithubInitial.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

## Part 2 - Getting the Basics Set Up
Now we will get everything prepared to go.  Lets get a background starfield, a main game camera and input all of the **Paper 2D** sprites needed for the game.
_____ 

### Starfield Background Part 1
So we will have a starfield background for our game to make it look super fancy.  Lets create a Material for it, but first we need to set up the Level.
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Double click SpaceRocks.uproject and open the game.  Click on the arrow on the **Content Browser** to open up the folders.  Press the **Add New** button and select a **New Folder**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NewMapsFolder.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Name the folder `Maps`.  We will storing our one level game here.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CallItMaps.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press the **Add New** button and select a **Level**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddNewLevel.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Name it `Main Game Level`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MainGameLevelName.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Select **Edit \| Project Settings** and select the **Maps and Modes** tab under **Project** on the side menu.  Select `MainGameLevel` as the **Editor Startup map** and **Game Default Map** in the 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MapsAndModesDefaultLevels.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press the **Description** item under **Project Settings \| Project**.  Fill in the project information that you feel is important.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ProjectSettingDescription.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Double click **MainGameLevel** and it will ask you to save the level you are in.  Press **Don't Save** as we will not be using this level.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GoToMainGameLevelNoSave.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Since this is a 2-D game we don't need a 3-D view.  I am choosing to use the X & Y asis as this is quite common nomenclature in 2D games.  Press the **Top** button to change the view. It also switches to **Wireframe** view which we will leave:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ChangeViewToTop.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we will be placing the background on a simple plane.  We will be putting a star field in it with a custom **Material**.  Select **Modes**, **Basic** and drag a **Plane** into the scene.  We want to shape to be on the positive X, Y plane.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DragPlaneForBackground.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. So we want to have an HD size game play space.  For standard consumer High Def, that is 1920 x 1080 pixels.  We will change the **Scale** on **Plane** component to `19.20` on the **X** and `10.80` on the **Y** axis.  Move the Plane so the top left corner is on the `0,0` point in **X, Y** space:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AdjustSizeOfBackgroundPlane.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press the **Add New** button and select **New Folder**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NewFolderBlueprints.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Call the new folder `Materials` and press the **Add New** button and select **Material**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddNewMaterialForStars.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Call this new Material `M_Background_Stars`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NameItBgStars.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we will need three textures for this material. Two different star fields that we will animate differently and a color swatch to give a bit of color to the stars.  Add another **Folder** and call it **Textures**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddNewTexturesFolder.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press the **Import** button and change the folder to the source level where the uproject file is located.  Look for the **Source Files** folder and select **T_StarColorMap.tga**, **T_Stars_1.tga** and **T_Stars_2.tga**.  Press the **Open** button to import all three files into the Textures folder:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectTStars.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Double click **M_Background_Stars** to open the newly creaed **Material**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DoubleClickMBackgroundStars.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Right click on a blank area on the graph and select the **Texture Sample** node and select `T_Stars_1` as the **Texture** found in the **Etails** panel:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TStars1Text.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a **Multiplication** node to adjust brightness and connect the pins as shown:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MultiplyNodeForEmission.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Leff mouse click while holding the **1** _button_ and it will add a **Scalar** node.  Connect it to the **B** side of the input of the **Multiplication** node.  Send the output to the **Emissive** input in the main Material node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ScalarEmissive.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we will not use lights in the game so all of our shaders will be emissive.  Go to the **Details** panel and change the **Shading Model** to `Unlit`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/UnlitShadingStars.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. This is by no means finished.  We have a lot more to do but we want to be able to see it in game to tweak it.  Press the **Apply** button.  Press **Save All** and update Github by **committing** and **pushing** all the changes made. On the next page we will add an in game camera to preview this material:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PressApplyStage1Stars.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

<br><br>

[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](Space-Rocks-2.html)
<br />  
<br />  
<br />  




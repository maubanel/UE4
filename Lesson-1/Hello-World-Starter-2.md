---
layout: default
title:  "UE4 Hello World Starter"
---


# Hello World for Unreal Engine 4 - Page 2
_____ 

## Index
_____ 

* Part 1 - Setting up with Git/Github
1. [Starting New Git Repository](Hello-World-Starter-1.html#starting-new-git-repository)
2. [**Starting Unreal Engine 4**](Hello-World-Starter-2.html#starting-unreal-engine-4)
3. [Our First Addition to Git](Hello-World-Starter-3.html#our-first-addition-to-git)

* Part 2 - Static Meshes, Ligths & Materials
3. [Basic Plane](Hello-World-Starter-4.html#basic-plane)  
4. [Our First Light](Hello-World-Starter-5.html#our-first-light)  
5. [Our First Material](Hello-World-Starter-6.html#our-first-material)
6. [Skybox and Reflections](Hello-World-Starter-7.html#skybox-and-reflections)
6. [Buliding Blocks & Instanced Material](Hello-World-Starter-8.html#building-block-instanced-material)

_____ 



### Starting Unreal Engine 4
_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. The project we have is the equivalent of starting a new Unreal project as a blank **Blueprint** style project with no starter content with maximum quality for a desktop/console. Please do not do this step as I have provided the project for you already.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/EpicGamesLauncher.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
<img src="images/NewUE4Project.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Double click on UE4HelloWorld.uproject file to launch the game engine.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/OpenHWProject.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. If there is not a UE4 icon on the file then the operating system does not know what program to load it with.  Right click on **HelloWorld.uproject** in explorer:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RightClickUProject.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Select **Properties**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectProperties.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press the **Change** button then select the **More Apps** link:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ChangeMoreApps.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Unreal will not show up in the App list so scroll to the bottom and select the **Look for another app on this PC**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ScrollToBottomLookForOther.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go to **Epic Games \| 4.22** (the latest 4.2x version in your directory).
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/EpicGame420.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Then **Engine \| Binaries**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/EngineBinaries.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Then go to **Win64**.  You will select the program **UE4Editor.exe** as the program you want to run the `.uproject` file.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Win64UE4Editor.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now you should see in explorer that it opens UPROJECT File (.uproject) with Unreal Engine.  If it does press **Apply**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/UnrealEngineApply.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now when you go back to your folder you will see that your **HelloWorld.uproject** file has the UE4 icon next to it.  Run it by double clicking on it.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NowCanLoadByDoubleClick.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. When the game loads (it may take a while) press **File < New Level** to create a new blank level.  We don't want the default level as it has a lot going on that will be introduced slowly.  The VR level is not applicable in this non vr exercise.  So lets pick a blank level:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreateNewLevel.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. A level selection tool comes up.  Please pick the **Empty Level**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectEmptyLevel.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we want to save the level and add it to the **GitHub** repository. Before we do this we need to realize that UE4 puts all the game assets into the **Content** folder in the project directory.  Now this will be very crowded if we save everything to the root of this folder. So we want to organize different assets by folders.  Lets create a **Maps** folder.  Start by seeing the folder structure by pressing the yellow button next to the filter at the bottom left of the screen: 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ShowFolders.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press the green button that says **Add New** and select **New Folder**.  Add a folder called `Maps`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NewFolder.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go back to the top menu and select **File < Save Current** and save the level into the Maps folder,
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FileSaveCurrent.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Call the file `Test Map` and make sure it is in the `Maps` folder.

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TestMapInMaps.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now you will see Unreal give the new Map an icon and it should be in the correct folder.  This now saves our current map.  It has nothing in it so there is no work yet to review by running the game.  Since we have completed one measure of work and started the project we should look at adding this to the git database.

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TestMapIcon.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 



<br><br>

[<- Previous](Hello-World-Starter-1.html)&nbsp;&nbsp;&nbsp;[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](Hello-World-Starter-3.html)
<br />  
<br />  
<br />  




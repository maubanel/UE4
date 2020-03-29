---
layout: default
title:  "UE4 Intro to Models - Page 2"
---
<br><br>
## Intro To Models - Page 2

Lets now look at the pipeline of getting models from software to Unreal Engine.

_____ 

## Index
_____ 

1.  [Anatomy of a Model](Intro-To-Models-1.html#anatomy-to-models)
2. [**What Makes a Good Real Time Model?**](Intro-To-Models-2.html#what-makes-a-good-real-time-model)
3. [What Makes a Good Real Time Model Part II?](Intro-To-Models-3.html#what-makes-a-good-real-time-model-part-ii)
4. [Scale](Intro-To-Models-4.html#scale)
5. [Levels, Props & Skeletons](Intro-To-Models-4.html#levels-props--skeletons)
6. [Materials](Intro-To-Models-4.html#materials)
7. [UV Mapping](Intro-To-Models-5.html#uv-mapping)
8. [Bad UVs](Intro-To-Models-6.html#bad-uvs)
9. [LOD](Intro-To-Models-6.html#lod)
10. [Pivot Point](Intro-To-Models-7.html#pivot-point)
11. [Collisions](Intro-To-Models-7.html#collisions)

_____ 

### What Makes a Good Real Time Model?
So now we know the names of some of the components of a model that we will take to Unreal 4.  Lets look at what makes up a good model for Unreal (or any real time engine for that matter).

_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. A good model for a game needs to reasonable in terms of the number of vertices, edges and faces.  The more we have with the more textures and materials the slower the game will run.  Lets demonstrate this.  First create a new blueprint and add it to the **Blueprints** folder.  Make it of class **Actor**.  Call it `BP_HighPolySphere`
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BP_High_Poly_Sphere.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we want to spawn a whole bunch of the very high poly sphere in the scene.  To make it work harder lets make each sphere a different color.  To do this we need to dynamically adjust the color in the blueprint.  To do this we need to change the color into a dynamic parameter.  Lets right click on **Materials \| M_Rough** and select **Duplicate**.  Call this new Material `M_Rough_Dynamic`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DuplicateRoughMaterial.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Double click on **M_Rough_Dynamic** and right click on the color vector and select **Convert to Parameter**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConvertVectorToParameter.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Name this material **Parameter Name** `ColorParam`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ColorParam.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go back to **BP_HighPolySphere** and press the **Add Component** button and select a **Static Mesh**.  Assign the **SM_Very_High_Poly_Sphere** to the **Static Mesh** and the newly created **M_Rough_Dynamic** material to the mesh. Static Meshes default to having physics turned off which is fine for ground planes and walls.  But for this ball we want to turn **Physics \| Simulate Physics** to on.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddSMToSphereBP2.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we want the collisions to be more elastic (bouncy) so scroll down in the **Details** tab and find **Phy Mat Override** and select **PM_Ball**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddPMBall.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we want the color to be set in the editor se we will use the **Construction Script** tab.  Right click on the empty graph and add a **Create Dynamic Material Instance** from the **Static Mesh** and connect the execution pins.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreateDynamicMaterialInstance.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now click on **Source Material** and select the **M_Rough_Dynamic** material.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MRoughDynamicOnMat.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now pull off the **Return Value** pin and add a **Set Vector Parameter Value**.  Please note that the color parameter in the material was called Vector Parameter.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetVecParameterValue.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we want to adjust each color channel separately so we can randomly pick a color.  Right click on the **Set Vector Parameter Value**  node on its input **Value** pin and select **Split Structure Pin** option:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SplitValueStruct.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets set the **Red Channel** to `1.0`.  Now each color channel is normalized between `0` and `1`.  So 0 would be no color of that channel and 1 would be 100% of that channel.  This should generate a red sphere.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetRedToOne.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we could have multiple **Vector Parameter** values, so we have to click on **Parameter Name** and enter `ColorParam`.  It HAS to be the exact same way you spelled the name in the material you just created. Press the **Compile**
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetParamName.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Double click on **Maps \| BallPit** level.  Now drag an instance of **BP_HighPolySphere** blueprint into the level.  It should be red, proving that we can alter the color of the material dynamically in the blueprint.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GoToBallPitRoomAddRedBall.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we want to have a random color for each sphere.  This means we need three random floats between **0** and **1**.  Right click on the **Construction Script** of the bluepring and add a **Random Float** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddFirstRandomFloat.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Hover over the **Random Float** node and double check that the range of the returned value is a float between 0 and 1.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/KismetRandomTooltip.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add two more **Random Float** nodes for the three color channels.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ThreeFloats.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Attach the output of the three **Random Float** nodes and attach them to the **Value R**, **Value G** and **Value B** pins:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AttachFloatToRGB.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go to the game and drag a few copies of **BP_HighPolySphere** into the level.  They should all be different colors like so:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MultiColorBalls.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we want to have a blueprint that spawns many copies of this blueprint so we can check the framerate.  Create  a new **Actor Blueprint** and place it in the **Blueprints** folder.  Call it `BP_HighPoly_Ball_Spawner`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BallSpawnerBP.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press the **Add Component** button and select a **Box Collision** component. We will use this to calcluate where to create the spheres from.  This shape will be the spawn volume that we use.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BoxCollisionComponent.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Change the component name to `SpawnVolume` then in the **Details** panel change the **Shape \| Box Extent** values to `2500` in **X** and **Y** and `400` in **Z**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetShapeExtentSpawnVolume.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add **BP_HighPoly_Ball_Spawner** to the level.  Place it in the center and well above the floor so the balls can fall. You should see the volume with a yellow line that indicates where the spheres will be spawned from.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddSpawnerToMap.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back to **BP_HighPoly_Ball_Spawn** and drag a reference of the **SpawnVolume** component to the **Event Graph**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddSpawnVolumeRef.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull off the **Spawn Volume** pin and select a **Shape \|Get Box Extent** node. Right click on the output **Box Extent** pin and select **Split Struct Pin**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GetBoxExtentNode.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. So what is an extent?  It is like a radius of a sphere.  It is from the pivot point of the spawn volume which is in the center of the box volume.  There is then an orthoganal line drawn along the **X Y Z** axis until it hits the edge of the box.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ExtentFromOrigin.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now that we split the stucture, we got three floats representing the length of the three box extents.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/BoxExtentOfXYZ.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Grab the output pin **Box Extent X** then add a **Random Float in Range** node.  Reconnect it to the **Max** pin.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RandomFloatonX.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now that is the maximum number along the X axis.  What about the starting value.  Since the pivot point is in the center we can multiply this value by **-1** to find the left had side along the X axis as shown below:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MinimiumValue.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now add a **Float * Float** pin and multiply the output of **Box Extent X** by `-1.0` and connect it to the **Min** pin on the **Random Float in Range** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FloatByFloat.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Repeat this for the **Y** and **Z** extent.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectYAndZExtent.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now that we have the **XYX** random location for our spawn lets recombine it into a **Vector** struct.  Add a **Make Vector** node and connect the **XYZ** pins:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MakeVector.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we have a problem.  This extent is in local space relative to the **BP_HighPoly_Ball_Spawn** actor.  This means it see's its position as `0.0, 0.0, 0.0`.  But in the room in my game the actor static mesh is at: `185.0, -922.0, 1431.0`.  This is the **World Space** that the actor is in.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/WorldSpaceSpawner.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. To go from local space to world space we just need to add the two together.  This is the result of adding two vector's together.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/WorldToLocal.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. To get the world position of the actor we need to a **Get Actor Location** node.  In my case this will be `185.0, -922.0, 1431.0`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GetActorLocation.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a **Vector + Vector** node and connect the output of the **Make Vector** and **Get Actor Location** node.  This shifts the location from Local to World space.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddWorldLocalSpace.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now right click on the graph and add a **Spawn Actor From Class** node.  
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
{{ num }}. Now right click on the **Spawn Transform** pins and select **Split Struct Pin**.  We will not be touching the rotation of scale just the location which is why we need to separate the struct.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SplitStructPins.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now it doesn't know what to spawn.  Select the **Class** drop down and select the **BP_HighPolySphere** blueprint.  Now connect the output of the **Vector + Vector** pin and attach it to **Spawn Transform Location**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SpawnLocation.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets spawn one ball.  Connect the **Event BeginPlay** node execution pin to the **Spawn Actor BP High Poly Sphere** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SpawnOneBallBeginPlay.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go to the game and hit run.  Look around and you should see one sphere spawn in the world. On the next page we will do this a thousand times and drop more balls.  But first we will be adding comments to our blueprints.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SpawnOneHighResSphere.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

<br><br>

[<- Previous](Intro-To-Models-1.html)&nbsp;&nbsp;&nbsp;[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](Intro-To-Models-3.html)
<br />  
<br />  
<br />  




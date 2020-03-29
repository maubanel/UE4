---
layout: default
title:  "UE4 Intro to Materials 13"
---

# UE4 Intro To Materials - Page 13
_____ 

## Index
_____ 

* Part 1 - Getting Setup
1. [Getting Set Up](Intro-To-Materials-1#getting-set-up)
2. [Creating a Diffuse Map](Intro-To-Materials-2.html#creating-a-diffuse-map.html#starting-unreal-engine-4)


* Part 2 - Our First Material
1. [Diffuse Only Material](Intro-To-Materials-3.html#diffuse-only-material)
2. [Texture Coordinate](Intro-To-Materials-4.html#texture-coordinate)
3. [Normal Mapping](Intro-To-Materials-4.html#normal-mapping)
4. [Roughness and Metallic Constants](Intro-To-Materials-5.html#roughness-and-metallic-constants)

* Part 3 - Material Instances
1. [Material Instance Diffuse](Intro-To-Materials-5.html#material-instance-diffuse)
2. [Metallic and Roughness Parameters](Intro-To-Materials-6.html#metallic-and-roughness-parameters)
3. [Normal Map Parameter](Intro-To-Materials-6.html#normal-map-parameter)
4. [UV Parameters](Intro-To-Materials-6.html#uv-parameters)

* Part 4 - Masked and Transluscent Materials
1.  [Metallic Mask](Intro-To-Materials-7.html#metallic-mask)
2.  [Opacity Mask](Intro-To-Materials-7.html#opacity-mask)
4.  [Translucent Blend Mode](Intro-To-Materials-8.html#translucent-blend-mode)

* Part 5 - Illumination
1.  [Importing a Model](Intro-To-Materials-8.html#importing-a-model)
2.  [Bracket Material](Intro-To-Materials-8.html#bracket-material)
3.  [Lamp Material](Intro-To-Materials-9.html#lamp-material)

* Part 6 - More Material Concepts
1.  [Two Sided Material](Intro-To-Materials-10.html#two-sided-material)
2.  [Decals](Intro-To-Materials-10.html#decals)
3.  [Refraction and Fresnel](Intro-To-Materials-11.html#refraction-and-fresnel)
4. [World Aligned Materials](Intro-To-Materials-12.html#world-aligned-materials)
5.  [**Animation**](Intro-To-Materials-13.html#animation)

* Part 7 - A Practical Master Material
1.  [A Practical Master Material](Intro-To-Materials-14.html#a-practical-master-material)
2.  [A Practical Master Material Part II](Intro-To-Materials-15.html#a-practical-master-material-part-ii)
3.  [A Practical Master Material Part III](Intro-To-Materials-16.html#a-practical-master-material-part-iii)

_____ 

## Animation

_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  We can animate many parts of a material.  There are too many to get into in one exercise. We will do two techniques.  This first is to animate a Linear Interpolation (LERP).  This allows us to change between two input pints gradually over time based on whether it is `0` - pin A or `1` - pin B. Scoot the camera over to **Room 8** and add a **Sphere** to the level changing its scale to `3.0, 3.0, 3.0`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddSphereToRoom8.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Create a new **Material** in the **Materials Folder** called `M_Glow`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MGlow.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Add a **Constant 3** node and make it ice blue and plug the output to **Base Color**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Const3IceBlue.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Set Roughness to `0.0`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetRoughnessToZero.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a **LinearInterpolate** (LERP) node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddLinearInterpolateNode.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We are going to have no flashing glow at the B input so add a **Constant** node and leave it as its default 0 and place it in the B node of the LERP:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NoFlash0.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Add a **Const 3** node and make it yellow.  Feed it into the A input of a multiply node;
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Const3YellowMult.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Multiply this by a **Constant** node set to `4`.  Plug this into the A input of the LERP node.  Connect this to the **Emissive Color** of the main node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MultiplyBy4.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>


_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. So when the Alpha in the LERP node is set to `1` we get no glow as it selects the B input which sends 0 to the glow:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Alpha1NoGlow.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Change the Alpha to `0` and you get the A input which is a multiplied yellow glow:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Alpha0Glow.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. So if we go into the room we have a glowing sphere that doesn't animate. Wouldn't it be cool if we could slowly change that Alpha value from 0 to 1 then back to 0 to animate it?
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GlowingInRoom.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a comment to your Glow LERP.  Now to the left drop a **Time** node.  This will give us a ticking clock based on game time:

</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CommentTime.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Send the output of Time into a **Sine** node.  A sine will return a value between -1 and 1 depending on the input (Time):
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SendIntoSineNode.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Clamp the value between 0 and 1 (its default setting) by adding a Clamp Node. Then take the output and send it to the **Alpha** in the LERP.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ClampSendToLerpAlpha.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Comment this section and I called it `Animation`. Press the **Apply** button. Now go into the game and assign the **M_Glow** material to the sphere. Run the game. I find the blinking to be off too much.  That is because the sine function doesn't return a nice value between 0 and 1.  Lets invert the output.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CommentNode.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Invert the result by adding a **One Minus** node before the Clamp.  Run it in game and it is better.  But what if I want to control the speed?
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/OneMinusBeforeClamp.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>


_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We divide Time to make it smaller and slow the transition down.  Add a **Divide** and **Constant** node.  Make sure you DON'T DIVIDE BY 0!  Set the constant node to `4`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DivideTime.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Run it in game and you should see a nice flashing animation on the sphere glow:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GlowingBall.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now lets try another technique and animate the UV's.  Not only can these position the texture within the model but we can animate them.  Lets animate a Chevron like in a race track that lights the direction to move in.  Go to the **Textures** directory and press the **Import** button to get the textured called **Chevron_DandA.TGA**.  Rename it and add a `T_` prefix to the texture. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ChevronImport.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Create a new **Material** and put it in the **Materials Folder**.  Call it `M_Chevron`. Add a **Texture Sample** to the graph and assign the Chevron texture. Now we don't need all channels as this is a two tone image.  We can just grab the red channel as it is a two tone image and connect it to the **Base Color** input on the main Material node. Use the **plane** shape to preview as this is not supposed to be on a sphere:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RedPinBaseColor.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now black and white is not what we wanted, so lets multiply this by a green color. Add a **Constant 3** vector and make it bright green.  Multiply this into the existing texture which will leave black as black but change the white to green.  Add a comment to this group:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddGreenToChevron.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now this is great but it is supposed to be a lit sign. So it is an emissive surface.  Now we can use the same texture as our emissive filter as the entire white portion is emissive.  Add a **Multiply** and **Constant** Node set to `6`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Multiply6Constant.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now connect the output of the Mutliply Node in the texture to the input A of the newly created multiply node.  Put the constant 6 in the B channel.  Put the output into the **Emissive Color** node.  Add a comment to explain what this is doing.  Press the **Apply** button.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MultiplyEmission2.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go to the game and drop a **plane** into the level:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DropPlaneIntoLevel.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Rotate the plane 90 degrees so that it is facing you:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Rotate90.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Assign the M_Chevron material to the plane.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/2To1Ratio.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Rotate so arrows face the right.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RotateRight.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  I have squashed the texture's width by 50%.  So I expect this texture to be on a plane that is twice as wide as it is high.  So I adjusted my plane's scale to be larger in all dimensions but to have a 2:1 ratio as shown. I set **X Scale** to `4.0` and **Y Scale** to `2.0`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TwoToOneRatio.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a second Chevron and put the two planes in Room 8. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddSecondChevron.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now how do we animate it?  Open the Material and add a **Panner** node.  This will pan the UVs in both dimensions along the plane:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PannerNode.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the output of the Panner to the UV of the Texture Sample.  Also set the **Speed X** to `.3`.  Now go in game and look at the nice panning!
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PanOnXHardCoded.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. To change directions, change the sign on the UV animation.  You can now select either positive or negative based on what direction you want the sign to animate.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NegativePositive.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back to the material and we can have these as parameters that we can use in an instance material.  Since it requires two parameters, we will add two **Scalar Parameter** nodes and connect them to an **Append** node then send this to the **Speed** input in the **Panner**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TurnIntoParameters.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go into the game and press play.  Look at the nice animating UV's!
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AnimatingChevronInGame.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. In the final part of this room we will do the same thing but rotate the UV's as oppose to scrolling them.  Import **T_CircularLogo_M.png** to the **Textures** folder:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LoadLogo.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. I have two masks in two different channels in the PNG.  The outer ring in the Red channel and the inner ring in the green channel.  We can save space in the game by combining our masks as we have 4 channels available in an PNG or TGA.  Open the Texture and under **View** just turn on the red channel and you should see:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ViewRedOnly.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now look at the green channel.  It contains the inner ring:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GreenView.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Create a new **Material** called `M_CircleSign`. Add a **Texture Smaple** node and assign the downloaded texture.  Multiply the **red** channel by an Orange **Constant 3** node and send to the **Base Color** pin: 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MCircleSignMaterial.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a **Rotator** node and change the **Speed** to `-1` to turn clockwise.  The CenterX and Y should be find as is.  You can adjust those to pick a different point to rotate on.  Right now it is in the very center of the UV, which makes sense:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Rotator.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a comment then select the entire set of nodes and copy and paste them:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CommentAndCopy.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Make the inner ring a different color, and change the Texture pin from Red to Green.  Rename the inner ring to `Inner Ring Diffuse`:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ChangeColorAndPin.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Since these rings don't overlap we can simply add the two outputs together to add the inner and outer ring:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddTwoRings.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We have a black background that we want to be clear.  So lets change the **Blend Mode** to **Translucent** in the **Details** panel:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MakeMaterialBlendModeTranslucent.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add the green and red outputs of the SampleTextures and add them together placing the output in the **Opacity** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Hook Up Opacity.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Take the output of the add and multiply it by `7` and send it to the **Emissive Color** to make it glow like a neon sign:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddEmissiveToCircleLogo.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go into the game and add another plane above the Chevron.  Scale it to your liking, rotate it to face the camera and add the appropriate material.  Voila, rotation! I sped up the inner rotation so it would be a different speed from the outer ring.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AnimatingCirclesInGame.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. That's it for Room 8. Press **Save All** and update Github by **committing** and **pushing** all the changes made.  Next up Animating UVs:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SaveAndCommit.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

<br><br>



[<- Previous](Intro-To-Materials-12.html)&nbsp;&nbsp;&nbsp;[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](Intro-To-Materials-14.html)
<br />  
<br />  
<br />  




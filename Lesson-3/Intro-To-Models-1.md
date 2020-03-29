---
layout: default
title:  "UE4 Intro to Models - Page 1"
---
<br><br>
## Intro To Models - Page 1

Lets now look at the pipeline of getting models from softare to Unreal Engine.

_____ 

## Index
_____ 

1. [**Anatomy of a Model**](Intro-To-Models-1.html#anatomy-to-models)
2. [What Makes a Good Real Time Model?](Intro-To-Models-2.html#what-makes-a-good-real-time-model)
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


## What you will need?

For this project you will need to be install [Unreal Engine 4.22.x](https://www.unrealengine.com/en-US/download) , have a [GitHub](https://github.com/) account (which is free of charge) as well as [GitHub Desktop](https://desktop.github.com). 

_____ 

### Anatomy of a Model
Lets look at the some terminology and what it means for a 3-D Model.

_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. UE4's models need consist of [polygons](https://en.wikipedia.org/wiki/Polygon).  It will not take models that are made with NURBS or other surface types.  A polygon is a plane that has at least three lines that connect to form a closed shape.<br><br>The best format to take into Unreal is the **[FBX](https://en.wikipedia.org/wiki/FBX)** format. Most 3-D software will allow you to export your model as polygons in the **FBX** format.  This is a proprietary format that is used by most software but is owned by **Autodesk**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/fbx.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets look at the simplest polygon a face.  Here it is displayed in **Maya 2019**:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SinglePoloygonFace.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. A polygon is made up on vertices, edges and faces.  Lets look at a vertice.  It is an **X, Y, Z** point in 3-D Space. So a plane consists of 4 vertices.  They all connect to each other to form a closed shape.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/VerticesOnPlane.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. So this plane consists of 4 **Edges**.  Every pair of vertices contains one edge.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FourEdgesToPlane.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Every group of edges that form a closed polygon is called a face:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CloseFace.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now even on a single plane, it can contain multiple faces.  If we divide this one plane up into a 4 by 4 grid.  We get 16 planes. Make sure you have no faces made up of more than 4 lines.  These Ngons (**N** stands for any number greater than 4) will be problematic in Unreal.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SingleFace16SubD.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now lets look at some hidden attributes that you don't see but are very important to how surfaces are displayed.  Each **face** has a [normal](https://en.wikipedia.org/wiki/Normal_(geometry)) which is a perpendicular line to the tangent plane of the surface. The normal is used for determining the surface's orientation for lighting. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FaceNormals.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. A [vertex normal](https://en.wikipedia.org/wiki/Vertex_normal) has the normals from all adjacent faces.  This way the renderer can figure out where the edge lies for lighting and shading.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SharpEdgeNormals.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. These normals can be adjusted to behave differently without adding geometry to the model.  In 3D Studio Max is is called **Smoothing Groups**.  In Maya you can affect the surface normals by softening the edge of the vertex normals on a face.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SoftenEdge.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. This takes an average of the three vertex normals and softens the edge.  This will be exported and viewable in UE4. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SmoothingEdgeNormal.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Download the Unreal Engine project in GitHub Classroom.  The link can be found on Moodle. Clone the project using **GitHub Desktop** and open the new project you just created.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/IntroToModels.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. The game should boot up to the **Test** Map.  If not go to the **Maps** folder and double click on **Test**.  Go to the **Geometry \| Static Mesh \| Smooth Edge** folder.  You should see to static mesh models.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/StaticMeshesUE4SoftEdge.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Drag **SM_Hard_Edge** and **SM_Soft_Edge** into the level next to each other.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DragTwoCubesInGame.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Play the game and you should see a difference between the two edges.  If you look carefully it is not the same as a fully rounded edge (with additional geometry) but does "soften" the edge.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SmoothSharpEdge.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. There is another way of simulating geometric details that are not in the base model.  Lets look at these two objects.  Here is a low poly sphere with 144 faces:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LowPolySphere.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. The other model is made of 40,000 faces.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/HighPolySphere.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. The faces are so small that the ball looks perfectly round. So we see we have one model that is much smaller (and therefore faster in the engine) than the other.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/TwoSpheres.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. What we can do though is grab the normal's from the high poly spheres and use those normals to shade our low poly model. This is done by saving them as a texture as opposed to geometry.  What the **RGB** channel holds is **XYZ** data of a [vector](https://en.wikipedia.org/wiki/Euclidean_vector).  This uses the face normal on the high polygon model and encodes it in a pixel on a texture map.  The texture normal map of this sphere looks like this:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SpehereNormalMap.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. This texture matches the UV coordinates of the low poly sphere.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/UVsOfSphere.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. A [UV](https://en.wikipedia.org/wiki/UV_mapping) is a texture map that assigns pixels in the image to a face on the model. So this is what a sphere would look like with a map texture applied to the UVs.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/UVMapping.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. If you go to the game and double click **SM_Low_Poly** that is located in the **Geometry \| StaticMesh \| LowHiSPhere** folder.  Notice that it has 552 vertices.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LowPolyModel.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open up **SM_High_Poly** mesh by double clicking on it.  Notice that is uses 40,399 vertices. These were both generated from the model we saw above in Maya.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/HighPolySphere2.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Drag **SM_High_Poly** and **SM_Low_Poly** mesh into the scene.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DraghLowHighPolyInScene.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now lets see how we can use the normal map to get some of the benefits of the high polygon model with a reduced cost to processing time in the computer.  Go to the **Materials** folder and right click on **M_Rough** and select **Duplicate**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DuplicateMaterial.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Name the new material **M_Rough_Normal**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NameFileMRoughNormal.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go to the **Content Browser** and select **Textures \| T_Sphere_N**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectNormalMapInContent.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back to **M_Rough_Normal** material and right click on the empty graph.  Select a **Texture Sample** node.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ImportTextureSample.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now the material selects for you the texture you have selected in the engine.  If not you can change the textre and select **T_Sphere_N**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DefaultsToSelectedTexture.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we want to preview this material on our actual model. We can do this by returning to the **Content Browser** and selecting **Geometry \| Static Mesh \| LowHiSphere \| SM_Low_Poly**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectSMLowPoly.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now go back to **M_Rough_Normal** material and select the **Sets Preview Mesh** button to load that mesh in the previewer.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ResetPreviewMesh.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____  
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. You now see the low poly sphere in the preview window.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LowPolyInPreviewWindow.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____  

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the **RGB** pin from the **Texture Sample** node to the **Normal** pin on the material.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectNormalMapSmooth.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____  

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the **RGB** pin from the **Texture Sample** node to the **Normal** pin on the material.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectNormalMapSmooth.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____  

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Duplicate **SM_Low_Poly** mesh and call the new mesh `SM_Low_Poly_Norm`.  Assign the **M_Rough_Normal** to this new mesh.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DupeSMLowPoly.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____  

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Duplicate **SM_Low_Poly** mesh and call the new mesh `SM_Low_Poly_Norm`.  Assign the **M_Rough_Normal** to this new mesh.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DupeSMLowPoly.jpg"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____  
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add it to the game and go next to the sphere with and without the normal map.  Now it is clearly not as convincing as the high poly mesh.  We would have a higher polygonal model for a sphere in a real project, but I wanted to exaggerate the difference to demonstrate the use of normal maps. Now you can really tell the illusion when you look at the edges.  It only affects normals that are on the face, and the silhouette is identical on both models. The normals cannot project outside of the faces of the model. But the procedure of having a low poly mesh and applying the normals of a high poly mesh in software like ZBrush is a very common workflow in real time engines. Next up we will look at what makes a good game model.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NormalMapSphere.gif"  class= "img-fluid"  alt="Create new sprite with button">  
</div>
</div>
_____  




<br><br>

[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](Intro-To-Models-2.html)
<br />  
<br />  
<br />  




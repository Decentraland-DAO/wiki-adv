In this article you will learn **Drafting** pipeline required for 3D Modeling.

To follow this article, make sure to install **Blender** and **PureRef**. Additionally, it's important to read [[(Concept) Wearables]] article.

In this and next articles we will use **image reference** generated **with Stable Diffusion.**

*Reference*

[[/images/ip-adapter06.png]]

### PureRef
First of all, you will need to **import** reference image to PureRef. Right click on reference image above and select **copy**. Open PureRef press right click and select **paste**.

Now you will need to set PureRef mode to be always on top. 
**Right click -> Mode -> Always On Top**.

Then, save your PureRef project to be able to open it at any time without needs for repeatable steps with copy and paste of reference image. 
**Right click -> Save -> Save.**

If needed, you can export images from PureRef as images to any folder you want. 
**Right click -> Save -> Export -> All Images.**

### Blender
Before you will start doing things in Blender, you should import **Decentraland Avatar Base Mesh** and do some preparations for modeling. 

You can find **Decentraland Base Meshes** [here](https://drive.google.com/drive/u/1/folders/12hOVgZsLriBuutoqGkIYEByJF8bA-rAU) 

As we will work according to **reference image**, import **AvatarShape_A** base mesh.

Importing of Base Mesh required for several things:
- Usage of default body parts for your model, for example, hands.
- Parenting and weight painting final model to Base Mesh skeleton and export to Decentraland.
- Silhouette guideline and proper connections between Avatar parts.


It's not recommended to use default Avatar Base Mesh for modeling as topology of this model have reduced triangle count and triangulated for Decentraland. It's possible to use it for modeling, but you will encounter issues with topology and other steps required for creating high poly model.

### Step 1. Creating Base Mesh for High Poly Modeling
There are three ways from what to begin. 

First way is to adapt current Avatar Base Mesh model to be usable for high poly modeling. This way requires some topology cleaning, which may end up with loss of time and unexpected results for non-experienced user.

Second way is to create Base Mesh model from primitives and then polish it to have perfect topology ready for high poly modeling.

Third way is to download prepared Avatar Base Mesh from [here]() and move to **Step 2.**

**Modeling Base Mesh**
It's very important to create a base mesh with perfect topology, to be able to do any manipulations with it. With prepared base mesh, you will be able to use it for any cloth pieces and easily apply core modifiers (bevel, subdivision, multiresolution) without wrong distortion and future issues on baking.

There are few rules topology rules that you need to keep in mind, first of all, amount of sides (edges) for each part of body.

- 6-8 sides (edges) for Arms and connection
- 12 sides (edges) for Neck and connection
- 14 sides (edges) for Hips and connection
- 8 sides (edges) for Legs and connection

This numbers is base used in many many old and mobile games, which are restricted to low triangles count. Also, this amount of edges works very well for subdivision workflow, which then transforms to multiresolution for sculpting.

Pay attention to **topology, edges, loops, faces count** on images and examples provided below, make to follow and keep exact same topology for your **Base Mesh.** 

Create basic **Cylinder** with **8 sides** and **elbow/knee area**.

*Result*

[[/images/step01_arms01.png]]

*Result (Subdivision)*

[[/images/step01_arms02.png]]

Improve Cylinder and make it look like **Arm**, use **Decentraland Avatar Base Mesh** for shapes and silhouette reference. Make sure to **check your shapes** with **Subdivision modifier**.

*Result*

[[/images/step01_arms03.png]]

*Result (Subdivision)*

[[/images/step01_arms04.png]]

Duplicate Cylinder and prepare **Legs**, topology stays exactly the same as for Arms but some areas of legs should be wider. 

*Result*

[[/images/step01_legs01.png]]

*Result (Subdivision)*

[[/images/step01_legs02.png]]

Position created **Cylinders** to **Decentraland Avatar Base Mesh** Arms and **Legs**, **apply** **all transforms**, and then **add Mirror modifier**.

*Result (Subdivision)*

[[/images/step01_legs03.png]]

Create **Hip** **Area**, connect it with **Legs**, merge vertices between seams. 

*Hips Result*

[[/images/step01_hips01.png]]

[[/images/step01_hips02.png]]

*Hips Result (Subdivision)*

[[/images/step01_hips03.png]]

[[/images/step01_hips04.png]]

*Total Result*

[[/images/step01_total01.png]]

*Total Result (Subdivision)*

[[/images/step01_total02.png]]

Create **Torso**, connect it with **Hips** and **Arms** and then merge vertices between seams.

*Torso Result*

[[/images/step01_torso01.png]]

*Torso Result (Subdivision)*

[[/images/step01_torso02.png]]

*Total Result*

[[/images/step01_total03.png]]

*Total Result (Subdivision)*

[[/images/step01_total04.png]]

Now your **Body Base Mesh** is almost ready! Let's make topology smooth and clean. **Set Subdivision Level to 1** and **apply modifier**.

*Result*

[[/images/step01_topology01.png]]

As you may see, **topology looks very smooth** now, but **polygon count is huge**, and **mesh a bit thinner**, let's fix that. 

Add **Decimate** modifier to your Base Mesh, move to **Un-Subdivide** tab inside Decimate modifier, set **Iterations to 2** and **apply modifier**.

*Result*

[[/images/step01_topology02.png]]

As last part of polishing, **select all faces** in **Edit Mode** and apply **Shrink/Fatten tool (ALT+S)** with **0.02 offset.****
**
*Result*

[[/images/step01_topology03.png]]

Now your Body Base Mesh is ready! Any time you will start working on wearables, make sure to start your workflow from this base mesh. It's ready for high-poly modeling and sculpting.

Before moving to next step, make sure to check this timelapse of base mesh creation process.

[[base_mesh.mp4]]
### Step 2. Drafting Clothes
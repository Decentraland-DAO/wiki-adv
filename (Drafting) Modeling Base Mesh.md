In this article you will learn how to create **Avatar Base Mesh** required for future usage in wearables modeling.

To follow this article, make sure to install **Blender**. 

# Blender
Before you will start doing things in Blender, you should import **Decentraland Avatar Base Mesh** and do some preparations for modeling. 

You can find **Decentraland Base Meshes** [here](https://drive.google.com/drive/u/1/folders/12hOVgZsLriBuutoqGkIYEByJF8bA-rAU) 

As we will work according to **reference image**, import **AvatarShape_A** base mesh.

Importing of Base Mesh required for several things:
- Usage of default body parts for your model, for example, hands.
- Parenting and weight painting final model to Base Mesh skeleton and export to Decentraland.
- Silhouette guideline and proper connections between Avatar parts.

It's not recommended to use default Avatar Base Mesh for modeling as topology of this model have reduced triangle count and triangulated for Decentraland. It's possible to use it for modeling, but you will encounter issues with topology and other steps required for creating high poly model.

## Tools and Modifiers

You should know this tools and modifiers for modeling

### Mesh
- Plane 
- Cube
- UV Sphere
- Cylinder

### Tools
- Move, Rotate, Scale (if you have selection of one or more elements, you can move, rotate or scale them)
- Vertex Slide/Edge Slide (Transform a vertex or edges along one of its adjacent edges/faces)
- Delete/Dissolve (Delete will delete faces/vertices/edges, while dissolve will remove them without loss of geometry but with creating n-gons)
- Extrude (you will use this one a lot, extrudes polygons from other polygons, same for edges and vertices)
- Inset (takes the currently selected faces and creates an inset of them, with adjustable thickness and depth)
- Loop Cut (this tool splits a loop of faces by inserting new edge loops intersecting the chosen edge)
- Knife (useful to manually cut edge loops, useful when working with topology issues)
- Merge (merge selected vertices)
- Split (split selected faces from other face)
- Separate (separate selected faces to another mesh)

### Modifiers
- Mirror (save lots of time in creating mirrored cloth pieces)
- Solidify (adds thickness to your model)
- Bevel (makes model angles look smooth and beautiful, which is required for baking beautiful maps, segments amount should always stay on 3 or less, since more segments count is not actually useful/visible)
- Subdivision (smooth entire mesh and divide each polygon to 4)
- Array (creates an array of copies of the base object)
- Curve (simple but efficient method of deforming a mesh along a curve object)
- Simple Deform (do some deformations like Twist, Bend, Taper, Stretch)
- Weighted Normals (useful to correct some issues with normals shading without topology edits)

### Shade Smooth (Setting/Modifier)
Additional important setting that you should always use is Shade Smooth by Angle (or similar modifier)

Most common angle numbers: **30, 45, 60, 80, 180**
- Numbers higher than 45 should be used for soft cloth pieces that don't have any sharp corners. (Shirt)
- Numbers equal to 45 or lower should be used for cloth pieces that have sharp corners (Belts, Chains)
- In situations when cloth piece contains soft and sharp edges, you will need to manually set Sharp Edges in required areas.

For Drafting Step you can simply set angle 180, but for baking and final model you should always follow this rules, because it's required not only for visual look, but also for proper baking and engine rendering. 

# Modeling Base Mesh
There are three ways from what to begin. 

**First way** is to adapt or simply use default Avatar Base Mesh model for modeling. This way requires some topology cleaning, which may end up with loss of time and unexpected results for non-experienced user.

**Second way** is to create Base Mesh model from primitives and then polish it to have perfect topology ready for high poly modeling.

**Third way** is to download prepared Avatar Base Mesh from [here]() and move to [[(Drafting) Modeling Wearables]].

It's very important to create a base mesh with perfect topology, to be able to do any manipulations with it. With prepared base mesh, you will be able to use it for any cloth pieces and easily apply core modifiers (bevel, subdivision, multiresolution) without wrong distortion and future issues on baking.

There are few rules topology rules that you need to keep in mind, first of all, amount of sides (edges) for each part of body.

- 6-8 sides (edges) for Arms and connection
- 12 sides (edges) for Neck and connection
- 14 sides (edges) for Hips and connection
- 8 sides (edges) for Legs and connection

This numbers is base used in many many old and mobile games, which are restricted to low triangles count. Also, this amount of edges works very well for subdivision workflow, which then transforms to multiresolution for sculpting.

Pay attention to **topology, edges, loops, faces count** on images and examples provided below, follow and keep exact same topology for your **Base Mesh.** 

## Modeling Body

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

As last part of polishing, **select all faces** in **Edit Mode** and apply **Shrink/Fatten tool (ALT+S)** with **0.02 offset.**

*Result*

[[/images/step01_topology03.png]]

That's all the steps for avatar body base model. Any time you will start working on wearables, make sure to start your workflow from this base mesh. It's ready for high-poly modeling and sculpting.

If you encounter issues, please follow this video timelapse with steps explanation.

[[modeling_avatar.mp4]]

## Modeling Feet

to-do
## Modeling Hands 

to-do
## Modeling Head

to-do

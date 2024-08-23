In this article you will learn how to create **Avatar Base Mesh** required for future usage in wearables modeling.

To follow this article, make sure to install **Blender**. 

# Blender
Before you will start doing things in Blender, you should import **Decentraland Avatar Base Mesh** and do some preparations for modeling. 

You can find **Decentraland Base Meshes** [here](https://drive.google.com/drive/u/1/folders/12hOVgZsLriBuutoqGkIYEByJF8bA-rAU) 

As we will work according to **reference image**, import **AvatarShape_A** base mesh.

Base Mesh required for several things:
- Usage of default body parts for your model, for example, hands.
- Parenting and weight painting final model to Base Mesh skeleton and export to Decentraland.
- Silhouette guideline and proper connections between Avatar parts.

It's not recommended to use default Avatar Base Mesh for modeling because topology of this model have reduced triangle count and model is ready to-go to engine, rather than for modeling.

## Tools and Modifiers

You should know this tools and modifiers for modeling

### Mesh
- Plane 
- Cube
- UV Sphere
- Cylinder

Additional meshes/curves will be explained in next steps and articles.
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

Additional tools will be explained in next steps and articles.
### Modifiers
- Mirror (save lots of time in creating mirrored cloth pieces)
- Solidify (adds thickness to your model)
- Bevel (makes model angles look smooth and beautiful, which is required for baking beautiful maps, segments amount should always stay on 3 or less, since more segments count is not actually useful/visible)
- Subdivision (smooth entire mesh and divide each polygon to 4)
- Array (creates an array of copies of the base object)
- Curve (simple but efficient method of deforming a mesh along a curve object)
- Simple Deform (do some deformations like Twist, Bend, Taper, Stretch)
- Weighted Normals (useful to correct some issues with normals shading without topology edits)

Additional modifiers will be explained in next steps and articles.
### Shade Smooth
Additional important setting that you should always use is Shade Smooth by Angle (or similar modifier)

Most common angle numbers: **30, 45, 60, 80, 180**
- Numbers higher than 45 should be used for soft cloth pieces that don't have any sharp corners. (Shirt)
- Numbers equal to 45 or lower should be used for cloth pieces that have sharp corners (Belts, Chains)
- In situations when cloth piece contains soft and sharp edges, you will need to manually set Sharp Edges in required areas.

For Drafting Step you can simply set angle 180, but for baking and final model you should always follow this rules, because it's required not only for visual look, but also for proper baking and engine rendering. 

### Topology Cheat Sheet

image

## Collections

to-do 
# Modeling Base Mesh
There are three ways from what to begin. 

**First way** is to adapt or simply use default Avatar Base Mesh model for modeling. This way requires some topology cleaning, which may end up with loss of time and unexpected results for non-experienced user.

**Second way** is to create Base Mesh model from primitives and then polish it to have perfect topology ready for high poly modeling.

**Third way** is to download ready .blend from [here]() and move to [[(Drafting) Modeling Wearables]].

It's very important to create a base mesh with perfect topology, to be able to do any manipulations with it. With prepared base mesh, you will be able to use it for any cloth pieces and easily apply core modifiers (bevel, subdivision, multiresolution) without wrong distortion and future issues on baking.

There are few topology rules that you need to keep in mind, first of all, amount of sides (edges) for each part of body.

- 6-8 sides (edges) for Arms and connection
- 12 sides (edges) for Neck and connection
- 14 sides (edges) for Hips and connection
- 8 sides (edges) for Legs and connection

This numbers is base used in many old and new mobile games, which are restricted to low triangles count. Also, this amount of edges works very well for Subdivision workflow, which then transforms to Multiresolution for sculpting.

Most common mistake of beginners is to add model, move it away from (0, 0, 0) coordinates and start doing some things like extrude, adding modifiers, etc. As result, beginners end up messing with viewport navigation issues.

Always create new models, in 0,0,0 position and work on them here. As soon as model is ready, you can navigate it to right place on avatar. 

If you do adjustments or add additional pieces for clothes (by using separate tool), and feel uncomfortable with navigation or modeling, or anything else. Just use powerful isolate mode to isolate mesh and hide all the rest. 

Pay attention to **topology, edges, loops, faces count** on images and examples provided below, follow and keep exact same topology for your **Base Mesh.** 



## Modeling Body

As it was mentioned before, there are lots of troubles with default Decentraland body model. It's triangulated and ready to-go to engine. But for modeling wearables it's very bad. You won't be able to use core modifiers like Bevel, Subdivision, Multiresolution with it. That means, that you won't be able to create good wearables ready for sculpting and future baking with it.

### Arms and Legs

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

### Hips
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

### Torso

Create **Torso**, connect it with **Hips** and **Arms** and then merge vertices between seams.

*Torso Result*

[[/images/step01_torso01.png]]

*Torso Result (Subdivision)*

[[/images/step01_torso02.png]]

*Total Result*

[[/images/step01_total03.png]]

*Total Result (Subdivision)*

[[/images/step01_total04.png]]

### Clean Topology
To make topology smooth and clean. **Set Subdivision Level to 1** and **apply modifier**.

*Result*

[[/images/step01_topology01.png]]

Topology looks very smooth now, but polygon count is huge, and mesh a bit thinner, let's fix that. 

Add **Decimate** modifier to your Base Mesh, move to **Un-Subdivide** tab inside Decimate modifier, set **Iterations to 2** and **apply modifier**.

*Result*

[[/images/step01_topology02.png]]

**Select all faces** in **Edit Mode** and apply **Shrink/Fatten tool (ALT+S)** with **0.02 offset.**

*Result*

[[/images/step01_topology03.png]]

If you encounter issues, please follow this video timelapse with steps explanation.

[[modeling_avatar.mp4]]

### Result

## Modeling Hands 

It's very challenging to do good handwear models with default Decentraland hands model. Bad triangulated topology, wrong edge loops for fingers bending (required for good weight painting and animations). Lack of nails. 

### Hand and Fingers
Create basic **Cube** and **Add Subdivision Modifier**

image

Remove bottom face of cube and apply subdivision modifier, this is front part of finger.

image

Move, Rotate, Scale cube to cover index finger of avatar base mesh

image

Extrude faces 2 times from edge loops

image

Shrink/Fatten middle edge loop

image

Repeat same steps to achieve full length of index finger, orient on **Decentraland Avatar Base Mesh** shapes and silhouette. Make sure to **check your shapes** with **Subdivision modifier**.

image

Duplicate finger and adjust it to fit other finger, repeat this step for all fingers 

image

Fingers should start from same line

image

Join all fingers and merge vertices as on image

image

Extrude more edge loops 

image

Delete 4 faces, select hole edge loops and thumb finger edge loops, bridge them. 

image

Adjust topology to match default avatar hand shapes and silhouette. 

image

For now you have a lot of edge loops in connection between hand and arms, this is not good and needs to be adjusted. If you want, you can ignore this topology for now, because it's good to go for sculpting and modeling handwear wearables (connections will be fixed on final low-poly model). 

image

But if you want to create skin wearable, you will need to achieve right connection (8 edge loops) to connect hands with body. To do that, you will need to adjust topology transitions from high dense to low.

Merge 3 vertices of pinky and middle finger to get 4 triangles.

image

Delete edge loops between triangles and move vertices a bit.

image

Delete two unnecessary edge loops and then edge loops of appeared triangles.

image

image

Repeat steps for bottom side of hand.

image

Delete faces near connection between hand and arm on top and bottom side.

image

Merge three vertices of hole on top and bottom.

image

Delete edge loop and edge loops of triangles that appear.

image

image

Merge vertices of arm and hand connection on top and bottom side.

image

Delete faces near connection between hand thumb finger.

image

Merge three vertices of hole on top and bottom.

image

image

Delete edge loop and edge loops of triangles that appear.

image

image

Merge vertices of arm and hand connection on top and bottom side.

image

image

If you made everything right, now hand connection should have 8 edge loops and can be easily connected to arms.

image

### Clean Toplogy

Make topology smooth and clean. **Set Subdivision Level to 1** and **apply modifier**.

image

Add **Decimate** modifier to your Base Mesh, move to **Un-Subdivide** tab inside Decimate modifier, set **Iterations to 2** and **apply modifier**.

image

As last part of polishing, **select all faces** in **Edit Mode** and apply **Shrink/Fatten tool (ALT+S)** with **0.02 offset** and add mirror modifier

image

Apply all transforms and add mirror modifier

image

Connect hands and body, and merge vertices.

image

### Nails

Select 4 faces of each finger, use inset and move new faces a bit inside of fingers

image

Duplicate faces and separate them

image

Add solidify modifier and set offset to 1

image

Preview result with Subdivision Modifier

image

For future modeling and baking you can add bevel modifier with 3 segments, low amount value (0.005), and 80 degrees angle before Subdivision modifier

image

Move vertices a bit to achieve smooth corners

image

Add Subdivision modifier (Level 1) to body. Move vertices to bottom a bit, to achieve smooth transition between fingers and nails. 

image

### Result

image

If you encounter issues, please follow this video timelapse with steps explanation.

**modeling_hands.mp4**

## Modeling Feet

Default avatar feets don't have all fingers, and same as hands, there are lack of nails. As usual, topology is triangulated and ready to go engine, rather than modeling.

### Feet and Fingers

Create basic **Cube** and **Add Subdivision Modifier**

image

Remove bottom face of cube and apply subdivision modifier, this is front part of finger.

image

Move, Rotate, Scale cube to cover thumb finger of avatar feets

image

Extrude additional faces from edge loop

image

In edit mode, duplicate 4 additional fingers, change their scale and extrude additional faces from their edge loops

image

Fingers should start from same line

image

Join all fingers and merge vertices as on image

image

Extrude additional faces from edge loop

image

Select bottom edge loops and hide them

image

image

Select all bottom faces and flatten them with scale

image

Unhide edge loops

image

If you will continue working with this topology, you will end up with mess and huge polygon count. Same as with hands, it's possible to continue with that high dense, but it's not really necessary for feet model and better to do transition. 

Delete faces between thumb and index finger

image

Bridge edge from thumb to index finger

image

Delete faces between index and middle finger

image

Bridge edge from middle to index finger

image

Delete faces between pinky and ring finger

image

Bridge edge from pinky to ring finger

image

Delete faces between ring and middle finger

image

Bridge edge from middle to ring finger

image

Merge vertices 

image

Repeat all steps to bottom side of foot

image

Extrude faces from edge loop

image

Add cylinder with 8 sides and scale/position it to connection of default avatar feet and legs. Join cylinder to foot model. Delete top and bottom faces of cylinder.

image

Extrude back side edge loops of cylinder to create heel

image

Bridge heel and foot faces

image

Adjust topology to match default avatar default foot shapes and silhouette. 

image

Merge 3 vertices and delete triangles edge loop on bottom of foot

image

image

Bridge bottom heel and foot edge loops

image

Loop Cut additional edge loop

image

Merge vertices

image

### Nails

Select 4 faces of each finger, use inset and move new faces a bit inside of fingers

image

Duplicate faces and separate them

image

Add solidify modifier and set offset to 1

image

Preview result with Subdivision Modifier

image

For future modeling and baking you can add bevel modifier with 3 segments, low amount value (0.005), and 80 degrees angle before Subdivision modifier

image

Move vertices a bit to achieve smooth corners

image

Add Subdivision modifier (Level 1) to body. Move vertices to bottom a bit, to achieve smooth transition between fingers and nails. 

image

### Result

image

If you encounter issues, please follow this video timelapse with steps explanation.

**modeling_feet.mp4**


## Modeling Head

to-do

# Summary
That's all the steps for creating avatar base model. Any time you will start working on wearables, make sure to start your workflow from this prepared base models. It's ready to go for high-poly modeling and sculpting.

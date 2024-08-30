In this article, you will learn how to create a useful base mesh that will be used for modeling wearables.

To follow this article, make sure to install **Blender** and adjust Blender settings according to the [[Software Settings]].

# Blender
Before you start working in Blender, you should import the **Avatar Models** from **Decentraland**. You will use it as a reference for creating your own avatar base mesh ready for high-poly modeling.

You can find **Decentraland Avatar Models** [here](https://drive.google.com/drive/u/1/folders/12hOVgZsLriBuutoqGkIYEByJF8bA-rAU) 

They are required for several purposes:

- Using default body parts for your model, such as hands.
- Parenting and weight painting the final model to the Armature of avatar and exporting it to Decentraland.
- Providing silhouette guidelines and ensuring proper connections between avatar parts.

It's not recommended to use the default avatar models as the base mesh for modeling wearables because the topology of these models has a reduced triangle count and is optimized for direct use in the engine, rather than for modeling purposes.

## Tools and Modifiers
For modeling, you should be familiar with these tools and modifiers.
### Mesh
- Plane 
- Cube
- UV Sphere
- Cylinder
### Tools
- Move, Rotate, Scale (if you have a selection of one or more elements, you can move, rotate, or scale them)
- Vertex Slide/Edge Slide (transform a vertex or edges along one of its adjacent edges/faces)
- Delete/Dissolve (delete will delete faces/vertices/edges, while dissolve will remove them without loss of geometry but will create n-gons)
- Extrude (you will use this one a lot, it extrudes polygons from other polygons, the same for edges and vertices)
- Inset (takes the currently selected faces and creates an inset of them, with adjustable thickness and depth)
- Loop Cut (this tool splits a loop of faces by inserting new edge loops intersecting the chosen edge)
- Knife (useful for manually cutting edge loops, useful when working with topology issues)
- Merge (merge selected vertices)
- Split (split selected faces from other faces)
- Separate (separate selected faces into another mesh)
### Modifiers
- Mirror (saves lots of time when creating mirrored cloth pieces)
- Solidify (adds thickness to your model)
- Bevel (makes model angles look smooth and beautiful, which is required for baking beautiful maps. The segments amount should always stay at 3 or less, as having more segments is not actually useful or visible)
- Subdivision (smooths the entire mesh and divides each polygon into 4)
- Array (creates an array of copies of the base object)
- Curve (a simple but efficient method of deforming a mesh along a curve object)
- Simple Deform (allows for deformations like Twist, Bend, Taper, and Stretch)
- Weighted Normals (useful for correcting some issues with normal shading without topology edits)
### Shade Smooth
Additional important setting that you should always use is "Shade Smooth" or "Shade Smooth by Angle" (Blender 4.2+).

The most common angle numbers are: **30, 45, 60, 80, 180.**
- Numbers higher than 45 should be used for soft cloth pieces that don't have any sharp corners (e.g., a shirt).
- Numbers equal to 45 or lower should be used for cloth pieces that have sharp corners (e.g., belts, chains).
- In situations where a cloth piece contains both soft and sharp edges, you will need to manually set sharp edges in the required areas.

[[/images/blender_shade_smooth.png]]

Using "Shade Smooth" is necessary not only for visual appearance but also required for future baking and proper rendering inside the game engine.

# Decentraland Models (Import)
guide how to import decentraland models

# Preparing Collections
work with collections
# Modeling Base Mesh
You can begin with one of three ways:

1. Adapt or simply use the default Decentraland avatar models for modeling. This approach requires some topology cleaning, which may result in a loss of time and unexpected outcomes for inexperienced users.
2. Create a base mesh model from primitives and then refine it to achieve perfect topology suitable for high-poly modeling.
3. Download the ready .blend file from [here]() and proceed to [[(Drafting) Modeling Wearables]].

The next steps of this article will focus on creating a base mesh with ready-to-use topology.
### Topology Tips
#### Number of Edges
There are a few topology tips that you need to keep in mind. First and foremost is the number of sides (edges) for each part of the body.

- 6-8 sides (edges) for Arms
- 12 sides (edges) for Neck
- 14 sides (edges) for Hips
- 8 sides (edges) for Legs

These numbers are the base used in many old and new mobile games, which are restricted to a low triangle count. Additionally, this amount of edges works very well for a Subdivision workflow, which can then be transformed into Multiresolution for sculpting.
#### Common Mistake
The most common mistake beginners make is to add a model, move it away from the (0, 0, 0) coordinates, and start performing actions like extruding, adding modifiers, etc. As a result, beginners often encounter viewport navigation issues.

Always create new models at the 0, 0, 0 position and work on them there. Once the model is ready, you can then position it correctly on the avatar.

If you make adjustments or add additional pieces for clothes using a separate tool and feel uncomfortable with navigation or modeling, simply use the powerful isolate mode to isolate the mesh and hide everything else.

Pay attention to the **topology, edges, loops,** and **face count** on the images and examples provided below. Follow and maintain the exact same topology for your base mesh.


## Modeling Body
### Arms and Legs

Create a basic cylinder with 8 sides for the elbow/knee area.

*Result*

[[/images/step01_arms01.png]]

*Result (Subdivision)*

[[/images/step01_arms02.png]]

Improve the cylinder to look like an arm, use the avatar model as a reference for shapes and silhouette. Make sure to verify your shapes with the Subdivision modifier.

*Result*

[[/images/step01_arms03.png]]

*Result (Subdivision)*

[[/images/step01_arms04.png]]

Duplicate the cylinder to prepare the legs, the topology remains exactly the same as for the arms, but some areas of the legs should be wider.

*Result*

[[/images/step01_legs01.png]]

*Result (Subdivision)*

[[/images/step01_legs02.png]]

Position the cylinders to match the avatar model arms and legs, apply all transforms, and then add a Mirror modifier.

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

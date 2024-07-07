In this article you will learn how to use **Avatar Base Mesh** and create wearables base meshes with it.

Additionally, it's important to read [[(Concept) Wearables]] article, because in this and next articles we will use **reference image** generated **with Stable Diffusion.** 

For next steps, you should use **Avatar Base Mesh** **.blend** file, you can find download link in [[(Drafting) Modeling Base Mesh]] article.

*Reference*

[[/images/ip-adapter06.png]]

To follow this article, make sure to install **PureRef**. 

### PureRef
First of all, you will need to **import** reference image to **PureRef**. Right click on reference image above and select **copy**. Open **PureRef** press right click and select **paste**.

Now you will need to set **PureRef** mode to be always on top. 
**Right click -> Mode -> Always On Top**.

Then, save your PureRef project to be able to open it at any time without needs for repeatable steps with copy and paste of reference image. 
**Right click -> Save -> Save.**

If needed, you can export images from **PureRef** to any folder that you want. 
**Right click -> Save -> Export -> All Images.**

### Drafting Pipeline
Drafting is first step in modeling, artist create models and define their basic shapes and silhouette. 

- **Keep it Simple.** Start with simple shapes and gradually add details. Avoid adding unnecessary complexity at the beginning. This will help you maintain a clean and organized model that is easier to work with.
- **Maintain Good Topology**. Topology refers to the arrangement of vertices, edges, and faces in a 3D model. It is important to have clean and efficient topology to ensure smooth deformations and proper shading when rendering. Avoid triangles and ngons (faces with more than 4 sides) as much as possible, this is very important for Sculpting and Subdivision modeling.
- **Work with Proper Scale.** Always model with real-world scale in mind. This is important for accurate dimensions and interactions with other elements in a scene. Make sure to set the units correctly in your 3D modeling software and reference real-world measurements when needed.
- **Organize Your Scene.** Keep your scene well-organized by using layers, groups, or naming conventions to easily identify and select different parts of your model. This will make it easier to work on specific elements and maintain a clear overview of your project.

It's very important to start with Avatar Base Mesh. It's already prepared and have good topology ready for Sculpting and Subdivision modeling. Most of times, when you will do cloth pieces, you will separate them from base mesh. This workflow reduce amount of time for topology adjustments, instead of doing all cloth pieces manually from scratch.
### Tools and Modifiers

List of most common modifiers and tools that you should know for preparing wearables base models:

**Modifiers**
- Mirror (save lots of time in creating mirrored cloth pieces)
- Solidify (adds thickness to your model)
- Bevel (makes model angles look smooth and beautiful, which is required for baking beautiful maps, segments amount should always stay on 3 or less, since more segments count is not actually useful/visible)

**Tools**
- Extrude (you will use this one a lot, extrudes polygons from other polygons, same for edges and vertices)
- Inset (takes the currently selected faces and creates an inset of them, with adjustable thickness and depth)
- Loop Cut (this tool splits a loop of faces by inserting new edge loops intersecting the chosen edge)
- Merge (merge selected vertices)
- Split (split selected faces from other face)

**Shade Smooth**
Additional important setting that you should always use is Shade Smooth by Angle (or similar modifier)

Most common angle numbers: **30, 45, 60, 80, 180**
- Numbers higher than 45 should be used for soft cloth pieces that don't have any sharp corners. (Shirt)
- Numbers equal to 45 or lower should be used for cloth pieces that have sharp corners (Belts, Chains)
- In situations when cloth piece contains soft and sharp edges, you will need to manually set Sharp Edges in required areas.

For Drafting Step you can simply set angle 180, but for baking and final model you should always follow this rules, because it's required not only for visual look, but also for proper baking and engine rendering. 


### Modeling Shirt
For shirt model work with ubody model from Avatar Base Mesh .blend file.

image

As you may see on reference, both sides of shirt looks very similar. First of all, delete half part of ubody model and apply mirror modifier. 

image

In mirror modifier properties, make sure to turn on bisect and flip, otherwise you won't see your mesh.

image

Extrude neck and adjust Vertices according reference image.

image

Delete unnecessary polygons in arms area

image 

Make visible Female Base Mesh in Female Avatar Base Mesh collection, starting from here, you will use it as main shape and silhouette for wearables. In proccess you can make it visible or invisible as you want.

image

Now Shrink/Fatten your Shirt model to make it cover on top Female Base Mesh, there should be gap between female base mesh and shirt.

image

Adjust forearms according to reference image.

image

Add Solidify Modifier, set Offset to 0 and Thickness to 0.9, if you want to see topology in edit mode, make sure to turn on **On Cage** property.

image

Add additional Edge Loops for zip-up, later we will select and split them to achieve zip-up lines from reference image. 

image 

Before next steps, make sure that your model follows shapes and silhouette of Avatar Base Mesh and reference image.

Select Arm, Sleeve, Neck, Zip-Up polygons and split them in areas as on reference image

image

Add Bevel Modifier, set Angle to 80, Segments to 3. If bevels looks too huge or too small, you can adjust amount setting.  

image

Select zip-up polygons and separate them to unique mesh. Apply mirror modifier and adjust topology according to reference image. 

image

Add additional Edge Loop in Neck Area and Split polygons

image

As you may see, there is a connection line on back of shirt and neck which you don't really need. 

Separate Neck and Shirt to two unique meshes. 

image

Turn on Merge setting in Neck and Shirt mirror modifier and adjust value a bit until connection line disappear

image

That's all the steps required to create shirt model. If you feel that shapes, solidify or bevels is weird, you can play with values in modifier settings. Your result should look almost same as result in article.

If you encounter issues, please follow this video timelapse with steps explanation.

drafting_shirt.mp4

### Modeling Jumpsuit
For jumpsuit model work with lbody model from Avatar Base Mesh .blend file.

image 

Most of steps for jumpsuit are same as for shirt.
- Start with lbody base mesh
- Delete half part of base mesh 
- Add mirror modifier without merge setting
- Add Shrink/Fatten to cover female base mesh
- Define silhouette and shapes
- Use Solidify and Bevel Modifiers
- Split parts (belt area, front and back of pants)

**Jumpsuit Fly** 
Select faces in fly area, duplicate them, separate to unique mesh and then apply symmetry modifier and delete left side of fly.

image

It may feel strange, but in real life, fly part is not symmetrical and usually located on right side of pants.

image

Set Solidify offset to 1 and polish fly shapes according to reference image.

By default you can set solidify offset maximum to 1, but if you will manually write any number higher than 1 and hit enter, it will work. This trick works on almost any value settings on any tools and modifiers.

If you feel that fly thickness or offset is too small, you can play with values as you want.

Add subdivision modifier (level 1), to smooth right bottom corner of fly

image

**Jumpsuit Straps**
Select some amount of belt edges and extrude them.

image

Repeat extrude several times to achieve straps result just like on image, to connect faces use bridge tool.

image

After that, define main shape and silhouette of straps according to reference image. 

**Jumpsuit Clips**

Add plane object to scene, scale it a bit to achieve silhouette of clip from reference image. It's very important to **Apply Scale** after adjustments to follow next steps.

image

Add this modifiers to your plane
- Mirror (Bisect, Flip, Merge), 
- Solidify (Offset 0, Thickness 0.5) 
- Bevel (Amount 0.1, Segments 3, Angle 80) 

image

Insert one vertical and two horizontal loop cuts

image

Split new horizontal areas, use inset tool and then delete faces. This will be handles for jumpsuit straps.

image

Use Knife tool to create clips connection and then split it

image

Separate clips connection and one of handles. After that reduce solidify thickness.

image

Add more loop cuts to clips handles and adjust silhouette to achieve more interesting handles shape. 

image

Use knife tool to fix topology. Remember, your model should avoid n-gons and triangles. 

image

If bevels looks weird somewhere, simply adjust bevel amount in modifier properties.

image

Select clips and locate it to strap as on reference image.

image

Add Empty object to scene and then add mirror modifier to all clips pieces. Select empty in mirror object setting. 

image

**Jumpsuit Belt Loops**

Add plane object to scene, scale it a bit to achieve silhouette of belt loop from reference image.

image

Add this modifiers to your plane
- Solidify (Offset 0, Thickness 0.5) 
- Bevel (Amount 0.1, Segments 3, Angle 80) 

image

Use inset tool to inset some faces, and then delete them to achieve hole.

image

Separate belt from jumpsuit, turn on merge in mirror modifier, and then add horizontal loop cut in middle of belt.

image

Select fresh loop cut, duplicate it, separate it to unique mesh, apply mirror modifier and then remove rest modifiers. After that convert mesh to curve.

Select belt loop model, add array and curve modifiers. In curve modifier select curve that you created from belt loop cut.

image

Adjust scale and rotation of belt loop. In array modifier adjust count and relative offset settings. Add mirror modifier to achieve better array.  Use curve as mirror object.

image 

Usually Array and Curve is a bit buggy, this happens because of many different reasons. If you encounter issues on this step, make sure to follow step by step video with explanations.

image

**Jumpsuit Pockets** 

Select your jumpsuit mesh and define pocket topology according to reference image.

image

Select left side faces, separate them and change solidify offset to -1. 

image

If your pocket seems too flat, you can inset additional loop cuts and then adjust shape.

image

### Modeling Cap
First of all, you will need to create sphere model. 

There are several ways to create sphere, first one is to add uv sphere model from add menu.  Second way is to add cube and apply subdivision modifier (level 1-3). In most cases you should use subdivided cube, instead of uv sphere, because it have clean quad topology. 

But in situation with cap, uv sphere works much better and easier to be prepared for sculpting. 

Add uv sphere, make sure that sphere cap with triangles located at top and not at left or right side.

image

Delete bottom part of sphere, you don't need that for cap model.

image

As usual, define shape and silhouette. Apply Mirror, Solidify and Bevel Modifiers.

image

Extrude front part of cap, split it and define shape and silhouette. 

image

On reference image, you can see additional bow part on top of cap. Duplicate your cap sphere, delete everything except 2 middle loops, and then adjust Solidify modifier settings (Offset and Thickness). 

image

On back side of cap, delete and split some faces in bottom area, that way you will create hole for ponytail.

image

Extrude two straps from edges in ponytail hole and separate them. 

image

If straps topology is too low, add additional edge loops.

image

Add Subdivision Modifier (Level 1) on top of all other modifiers. Now define straps shape and silhouette.

image

Select all faces of front strap and use inset modifier.

image

Add additional horizontal edge loop at middle of strap.

image

Use bevel tool to split this edge loop and move it to front and bottom of strap, make sure to keep middle faces look like quads.

image

Select middle faces and use inset tool with individual option, after that split faces

image

Apply Subdivision Modifier and now in edit mode fix left and right part of strap, for better shape.

image

Follow all the same steps for back strap, except inset and split of rivets, you don't need this ones on back strap, because you already have imitation of connection on front strap. 

image

If you encounter issues, please follow this video timelapse with steps explanation.

drafting_cap.mp4

### Modeling Sneakers
Modeling sneakers requires all the same steps explained in previous cloth pieces. Explanation of sneakers pipeline may contain lot's of repeatable text, which is unnecessary. 

Instead, follow this video timelapse with steps explanation.

drafting_sneakers.mp4

### Summary
Drafting steps are over. Now you should have better understanding of patterns that used for creating base models and move forward to high-poly modeling and sculpting. 

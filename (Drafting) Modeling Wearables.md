In this article you will learn how to use **Avatar Base Mesh** and create wearables base meshes with it.

Additionally, it's important to read [[(Concept) Wearables]] article, because in this and next articles we will use **reference image** generated **with Stable Diffusion.** 

For next steps, you should use **Avatar Base Mesh** **.blend** file, you can find download link in [[(Drafting) Modeling Base Mesh]] article.

*Reference*

[[/images/ip-adapter06.png]]

To follow this article, make sure to install **PureRef**. 

# PureRef
First of all, you will need to **import** reference image to **PureRef**. Right click on reference image above and select **copy**. Open **PureRef** press right click and select **paste**.

Now you will need to set **PureRef** mode to be always on top. 
**Right click -> Mode -> Always On Top**.

Then, save your PureRef project to be able to open it at any time without needs for repeatable steps with copy and paste of reference image. 
**Right click -> Save -> Save.**

If needed, you can export images from **PureRef** to any folder that you want. 
**Right click -> Save -> Export -> All Images.**

# Drafting
Drafting is first step in 3d modeling, artist create models and define their basic shapes and silhouette. 

- **Keep it Simple.** Start with simple shapes and gradually add details. Avoid adding unnecessary complexity at the beginning. This will help you maintain a clean and organized model that is easier to work with.
- **Maintain Good Topology**. Topology refers to the arrangement of vertices, edges, and faces in a 3D model. It is important to have clean and efficient topology to ensure smooth deformations and proper shading when rendering. Avoid triangles and ngons (faces with more than 4 sides) as much as possible, this is very important for Sculpting and Subdivision modeling.
- **Work with Proper Scale.** Always model with real-world scale in mind. This is important for accurate dimensions and interactions with other elements in a scene. Make sure to set the units correctly in your 3D modeling software and reference real-world measurements when needed.
- **Organize Your Scene.** Keep your scene well-organized by using layers, groups, or naming conventions to easily identify and select different parts of your model. This will make it easier to work on specific elements and maintain a clear overview of your project.

It's very important to start with Avatar Base Mesh. It's already prepared and have good topology ready for Sculpting and Subdivision modeling. Most of times, when you will do cloth pieces, you will separate them from base mesh. This workflow reduce amount of time for topology adjustments, instead of doing all cloth pieces manually from scratch.

## Modeling Shirt
For Shirt model you should duplicate **ubody_base** model, then create **shirt_base** collection in outliner, move **ubody_base** duplicate here and make sure that all your shirt pieces will be created inside this collection. 

image

As you may see on reference, both sides of shirt looks very similar. First of all, delete half part of ubody model and apply mirror modifier. 

image

In mirror modifier properties, make sure to turn on bisect and flip, otherwise you won't see your mesh.

image

Extrude neck and adjust Vertices according reference image.

image

Delete unnecessary polygons in arms area

image 

(visible invisible explanation)

image

Now Shrink/Fatten shirt model. It should cover female base, and should have  gap between female base mesh and shirt.

image

Adjust forearms according to reference image.

image

Add Solidify Modifier, set Offset to 0 and Thickness to 0.9, if you want to see topology in edit mode, make sure to turn on **On Cage** property.

image

Add additional Edge Loops for zip-up, later we will select and split them to achieve zip-up lines from reference image. 

image 

Before next steps make sure to correct shapes/silhouette according to reference image.

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

That's all the steps for shirt model. If you feel that something wrong, you can play with shapes/silhouette and modifiers values.

If you encounter issues, please follow this video timelapse with steps explanation.

**modeling_shirt.mp4**

## Modeling Overalls
For overalls model you should duplicate **lbody_base** model, then create **overalls_base** collection in outliner, move **lbody_base** duplicate here and make sure that all your overalls pieces will be created inside this collection. 

image 

Most of steps for overalls are same as for shirt.
- Start with lbody_base mesh
- Delete half part of base mesh 
- Add mirror modifier without merge setting
- Add Shrink/Fatten to cover female base mesh
- Define silhouette and shapes
- Use Solidify and Bevel Modifiers
- Split parts (belt area, front and back of pants)

### Overalls Fly
Select faces in fly area, duplicate them, separate to unique mesh and then apply symmetry modifier and delete left side of fly.

image

It may feel strange, but in real life, fly part is not symmetrical and usually located on right side of pants.

image

Set Solidify offset to 1 and polish fly shapes according to reference image.

By default you can set solidify offset maximum to 1, but if you will manually write any number higher than 1 and hit enter, it will work. This trick works on almost any value settings on any tools and modifiers.

If you feel that fly thickness or offset is too small, you can play with values as you want.

Add subdivision modifier (level 1), to smooth right bottom corner of fly

image

### Overalls Straps
Select some amount of belt edges and extrude them.

image

Repeat extrude several times to achieve straps result just like on image, to connect faces use bridge tool.

image

After that, correct shapes/silhouette of straps according to reference image. 

### Overalls Clips

Add plane object to scene, scale it a bit to achieve silhouette of clip from reference image. It's very important to **Apply Scale** after adjustments to follow next steps.

image

Add this modifiers to your plane
- Mirror (Bisect, Flip, Merge), 
- Solidify (Offset 0, Thickness 0.5) 
- Bevel (Amount 0.1, Segments 3, Angle 80) 

image

Insert one vertical and two horizontal loop cuts

image

Split new horizontal areas, use inset tool and then delete faces. This will be handles for overalls straps.

image

Use Knife tool to create clips connection and then split it

image

Separate clips connection and one of handles. After that reduce solidify thickness.

image

Add more loop cuts to clips handles and correct them to achieve more interesting result. 

image

Use knife tool to fix topology. Remember, your model should avoid n-gons and triangles. 

image

If bevels looks weird somewhere, simply adjust bevel amount in modifier properties.

image

Select clips and move it to strap as on reference image.

image

Add Empty object **clips_mirror** to scene and then add mirror modifier to all clips pieces. Select empty in mirror object setting. 

image

### Overalls Belt Loops

Add plane object to scene, scale it a bit to achieve silhouette of belt loop from reference image.

image

Add this modifiers to your plane
- Solidify (Offset 0, Thickness 0.5) 
- Bevel (Amount 0.1, Segments 3, Angle 80) 

image

Use inset tool to inset some faces, and then delete them to achieve hole.

image

Separate belt from overalls, turn on merge in mirror modifier, and then add horizontal loop cut in middle of belt.

image

Select fresh loop cut, duplicate it, separate it to unique mesh, apply mirror modifier and then remove rest modifiers. After that convert mesh to curve.

Select belt loop model, add array and curve modifiers. In curve modifier select curve that you created from belt loop cut.

image

Adjust scale and rotation of belt loop. In array modifier adjust count and relative offset settings. Add mirror modifier to achieve better array.  Use curve as mirror object.

image 

Usually Array and Curve is a bit buggy, this happens because of many different reasons. If you encounter issues on this step, make sure to follow step by step video with explanations.

image

### Overalls Pockets

Select your overalls mesh and adjust topology in pocket area according to reference image.

image

Select left side faces, separate them and change solidify offset to -1. 

image

If your pocket seems too flat, you can inset additional loop cuts and then adjust shape.

image

That's all the steps for overalls model. If you feel that something wrong, you can play with shapes/silhouette and modifiers values.

If you encounter issues, please follow this video timelapse with steps explanation.

**modeling_overalls.mp4**

## Modeling Bag

to-do

## Modeling Gloves

to-do

## Modeling Cap
Create **cap_base** collection in outliner and make sure that all your cap pieces will be created inside this collection. 

image

First of all, you will need to create sphere model. 

There are several ways to create sphere. Most common is to add UV Sphere from Add menu. UV Sphere is perfect for modeling cap, because it works very well with subdivision modifier, easy for sculpting and easy to work with topology.

Add **UV Sphere** with **12 segments** and **8 rings**. 

image

Extrude edges from sphere top and downscale them (this step is important for Subdivision Modifier).

image

Delete top middle vertex, right and bottom half of sphere.

image

As usual, add Mirror, Solidify, Bevel modifiers.

image

Define sphere shape and silhouette to look more like cap from reference image.

image

Select front edges and extrude front part of cap, after that correct shapes/silhouette of front part. Then select front part pieces and separate them.

image

Hide front part corners to achieve better connection look.

image

Select middle faces of cap, duplicate and separate them. Set Solidify offset to 1.

image

Correct topology and then modifiers settings to achieve bow shape as on reference image.

image

Adjust cap shapes, to achieve dent effect in middle

image

### Cap Straps
There are a lot of ways how to make straps. Some are dirty, some a bit complex, but result is better.

For learning purposes, it's better to continue with complex one.

Delete few faces on back side of cap to create hole for straps. Correct shapes/silhouette of hole area.

image 

Add Plane model then use inset tool with thickness value 0.15 two times. Split middle face. As usual, add Solidify and Bevel modifiers.

image

Add Subdivision modifier (level 1) on top of all other modifiers.

image

Add Array modifier on top of all other modifiers, set count to 5 and enable merge option. 

image

Add Weighted Normal modifier (this modifier is very useful in situations when you want to fix model shading without topology edits and works very well on flat surfaces)

image

Apply Array and Subdivison modifier.

image 

Select first rivet area, merge vertices, remove edge loops and straighten side.

image

image

Duplicate strap, merge vertices, remove all rivets edge loops except one on left corner.

image

Rotate strap without rivets to 180 degrees and move it below strap with rivets

image (top view)

image (side view)

Select both straps and join them. Set origin to center of mass, clear straps location and then apply rotation.

image

Add Simple Deform modifier, select Bend option, set angle to 90 degrees and set Z axis. Add new Empty **cap_base_bend** to scene select it in Simple Deform modifier Origin.

image

Rotate Empty to 90 or -90 degrees to achieve expected bend result

Select straps together with empty and move them properly to cap hole. When you will rotate and move straps, make sure that you selected both straps and empty. Adjust bend number if needed to achieve right connection with cap.

image

Add new empty **cap_base_root**, select all cap pieces and parent them to new empty. Select empty and now move, rotate and scale it on top of avatar head. This is right way to move several objects pieces all together without any issues with modifiers. 

image

That's all the steps for cap model. If you feel that something wrong, you can play with shapes/silhouette and modifier values.

If you encounter issues, please follow this video timelapse with steps explanation.

**modeling_cap.mp4**

## Modeling Sneakers
Create **sneakers_base** collection in outliner and make sure that all your sneakers pieces will be created inside this collection. 

There are two ways how to start modeling sneakers, most common is to create sole first. But, doing sneakers this way, you will end up with dealing topology issues. Instead, you will learn way with creating sneakers from uv sphere.

### Sneakers Base
Add **UV Sphere** with **12 segments** and **8 rings**

image

Delete bottom and left half of sphere

image

Move sphere a bit forward

image

Duplicate sphere and rotate it on 180 degrees, move it back, this will be back side of sneakers.

image

Join spheres together and use bridge edge loops tool to connect them

image

Add Mirror, Solidify, Bevel modifiers as usual

image

Inset additional edge loops in bridge area, and then define better sneakers shape/silhouette

image

Extrude bottom edge loops and split created faces to achieve sole

image

Extrude and fill top edge loops of front sneakers piece

image

Select front piece faces and split them

image

### Sneakers Tongue
Extrude top edge loops again for several times to create tongue

image

Separate tongue part and set solidify offset to -1

Extrude top back edge loops to create heel part

image

Separate heel part and set solidify offset to -1

image

Adjust shapes/silhouette and modifiers values to achieve sneakers result as on reference image

image

As you may see, reference image generated some bad areas on tongue area, you can ignore this issues and add something from your mind. It's seem good idea to add velcro part in tongue area, to hide bad area.

Duplicate tongue and heel, join them and change solidify offset to-0.1

image

Select two edges and fill holes

image

Delete unnecessary faces and adjust shapes/silhouette.

image

Duplicate clips created for Overalls and locate it on velcro part

image

### Sneakers Sole

Duplicate sole and correct shapes to achieve orange part as on reference image

image

Use knife tool to cut some additional edge loops according to shape of brown part on sneakers sole 

image

Separate brown part faces

image

Adjust bevel amount value for better results

image

Select white part of sneaker sole and move bottom edges a bit to top, use fill and then split faces 

image


Duplicate and separate bottom faces, apply mirror modifier and then connect vertices by using Connect Vertex Path tool

image

Now split any faces that you want and change solidify offset to 0.25 or 1. You can also scale them in edit mode with Individual Origins option in Transform Pivot Point window. You can edit faces as you want to achieve interesting results.

You can also add any additional interesting objects like cylinders, later all this details will be baked on simple flat plane and results will look great.

image



### Sneakers Laces

Before doing sneaker laces, you will need to prepare area with laces holes and as it looks on reference image. 

Select faces in collar/laces area, split them and adjust shapes/silhouette to achieve result as on reference image

image

Inset edge loop on heel part, and split faces

image

You can create laces with different ways, for more realistic look you will need to create holes in collars and use curves and customs shapes with manual placement. 

For more stylized look (as on reference image) you can use dirty way by extruding edges from collars and splitting them, or use more clean and smooth way by creating plane with simple deform (bend) modifier, curve and array modifier. 

Add plane, change it's shape to rectangle and then apply all transforms

image

Add additional edge loops

image

Add Solidify and Bevel modifier

image

Add Simple Deform modifier with Bend option, if Bend works wrong, rotate plane on 90 degrees in edit mode, and then back to 90 degrees in object mode.

image

Select sneakers tongue, in edit mode select middle edge loop, duplicate and separate it. 

Remove all modifiers from separated edge loop and convert it to curve

image

Select lace and add array, curve modifiers, in curve modifier select curve that you separated from sneakers tongue. 

Now downscale your lace, move it and change bend value to achieve result as on image

image

Set Array count to 4 and change relative offset from Factor X to Z -1 or -1.5 (choose good value)

image

If you experience issues, you can adjust curve points and radius of each point in edit mode of curve.

If you want to avoid array and curve modifiers, you can manually duplicate and place lace on top of tongue. But result with array and curve looks more clean.

image

Add new empty **sneakers_base_root**, select all sneakers pieces and parent them to new empty. Select empty and now move, rotate and scale it to properly locate them on avatar feet. This is right way to move several objects pieces all together without any issues with modifiers. 

Add new empty **mirror**, select any sneaker part, add mirror modifier and select mirror empty as mirror object. Now select this part and all  sneakers parts, click on arrow in mirror modifier and select **Copy to Selected** this option will copy mirror modifier to all pieces. 

image

That's all the steps for sneakers model. If you feel that something wrong, you can play with shapes/silhouette and modifiers values.

If you encounter issues, please follow this video timelapse with steps explanation.

**modeling_sneakers.mp4**

# Summary
That's all steps for creating base wearable models. Now you should have better understanding of repeatable patterns (tools and modifiers) used for creating base models. You can move forward to high-poly modeling and sculpting. 

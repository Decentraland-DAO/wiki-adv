In this article you will learn how to prepare wearable models for uv unwrap, baking, texturing. 

It's important to follow [[(High-Poly) Sculpting Wearables]] article, because this article requires knowledge and usage of models from previous article. 

# Low-Poly from High-Poly
If you followed all previous articles as intended and used prepared models instead of sculpting from scratch, now all you need to do, is to take models that you used for sculpting and prepare them for UVs and Baking. 

By doing that, you will avoid manual retopology of your high-poly models. Keep in mind that this will work only for models made from base meshes. If you made your high-poly model by sculpting it from scratch, you will need to follow retopology guide that you can find below in this article. 

Make sure to work with models that you made before sculpting, sculpted models will be used only for baking. 

Overall preparations requires removal of most modifiers, merging back separated pieces, and removal of unnecessary geometry.
## Preparing Shirt
Remove Subdivision and Bevel modifier on all shirt parts.  

image

Select all parts and then select all faces in edit mode, merge all vertices by distance. By doing that you will remove unnecessary lines made only for baking, if some of the areas were not merged properly, adjust merge by distance value a bit, or manually merge vertices in problem area.

image

Turn on Only Rim option in Solidify modifier on all shirt parts except neck and zipper. 

image

Apply solidify modifier and remove inner faces between body, arms, neck.

image

Select body, neck, arms mesh and join them together, after that select all faces in edit mode and use merge by distance. As result body, neck, and arms should became one base mesh. 

image

Set shade smooth to 80, make sure that with shade smooth tool all hard edges shades properly. This thing is required for doing UVs, you will use hard edges to automatically mark UVs seams in future.

image

Remove bottom faces on neck and shirt. 

image

image

Before applying mirror modifier, make sure remove faces in back middle connection of shirt.

image

image

Select forearm edge loop and merge it at center, move center vertex a bit inside of forearm.

image

image

Apply mirror modifier.

image

Bridge edge loops from left to right side in zipper area.

image

Select edge loop inside of neck, extrude it and merge vertices at center

image

Remove zipper faces that's not visible and overlaps with shirt. This is unnecessary geometry that eats triangles.

image

Check all areas and make sure that there are no problems with geometry. In Blender 4.2 shade smooth tool use modifier instead of option, make sure to apply this modifier on all shirt parts too. 

If shade smooth modifier ignores some shard edges parts, manually mark them in edit mode. 

image

Now your model is read for UVs and baking, keep zipper and shirt as separate objects, this is important for future baking. 

### Reducing Triangles
Overall topology of Shirt looks good, but there are some areas with unnecessary triangles that you will need to remove. Reducing triangles is very important step, because you should follow triangles limitation limit required for publishing wearables. 

Keep in mind, that during reducing triangles step, you should avoid huge changes of shapes and silhouette, otherwise mesh density will not be enough for good bakes, you will encounter with issues like weird wavy curves, and other things. 

Additionally, you should keep some edge loops for proper weight painting and deformations with avatar animations.

If you want to save some time, you can add back mirror modifier and apply it later, after you will reduce required amount of triangles. Make sure to turn on bisect option in mirror modifier, to avoid overlapping issues.

It's also important to reduce triangles before doing UVs, it's doable and sometimes needed to reduce triangles after UVs (for example you can do that for loops that are not UV seams), but you should keep in mind that doing any adjustments to model with UVs will cause distortions on textures and sometimes edits can broke some UV areas.  

Remove one edge loop on neck, it's not really necessary and wont have issues with deformations on animations.

image

Front part of shirt looks good, but back and side areas have some unnecessary edge loops. 

Merge them according to image

image

image

Additionally, you can merge some vertices in shoulders area

image

image

Take a look at triangles count in statistics window, your shirt model should stay around 400-600 triangles, this is more than enough for such simple model. 

Always work with cleaning your model, unnecessary edge loops and big triangle count in situations when it's not needed, will struggle you with lots of problems during weight painting step. It's very important to keep model topology clean. 

### Result 

image

If you encounter issues, please follow this video timelapse with steps explanation.

**preparing_shirt.mp4

## Preparing Overalls
Most of steps for overalls are same as for shirt.
- Remove Subdivision and Bevel modifier
- Merge connections between unnecessary lines
- Join pockets, remove middle edge loop and merge vertices by distance
- Merge problem vertices manually
- Turn on only Rim on Solidify modifier
- Apply Solidify Modifier
- Before applying mirror modifier, make sure to remove faces in middle connection of left and right part of pants
- Connect edge loops in bottom area of calf, move vertice a bit inside for better look
- Remove faces on top of pants, they're unnecessary and eat triangles.
- Use Shade Smooth, mark sharp edges manually, if needed, and apply all modifiers

image

### Overalls Fly
For overalls fly you will need to do few similar steps. 
- Remove Subdivision and Bevel modifier
- Turn on Only Rim and apply Solidify
- Merge connections between unnecessary lines 
- Use Shade Smooth and apply all modifiers

image
### Overalls Belt and Belt Loops
Instead of removing subdivision modifier for belt, you will need to apply it. The reason for that is curves that will appear on baking, because belt shape will be too low if you will remove subdivision modifier. 

- Apply Mirror and Subdivision modifier
- Turn on Only Rim and apply Solidify
- Close top and bottom hole with merge by distance
- Use Shade Smooth and apply all modifiers

image

For belt loops simply remove bevel modifier, use shade smooth and apply all modifiers. Remove unnecessary faces.

image

image
### Overalls Straps
- Remove Subdivision and Bevel modifier
- Use Shade Smooth and apply all modifiers
- Remove bottom faces that overlaps with belt, they eat triangles and unnecessary
### Overalls Clips
- Remove Bevel modifier\
- Remove hidden faces, they eat triangles.
- Use Shade Smooth and apply all modifiers
### Reducing Triangles
Overall process is same as for shirt, just look for unnecessary edge loops and remove them or merge some of vertices. 
#### Overalls
Your overalls (without belt, clips, straps, etc) should stay around 400-600 triangles, there are no reasons to have more, unless you have a lot of complex details, such as detailed pockets, or anything else. 

If you followed articles as intended, there are no needs to reduce triangles for overalls.

#### Overalls Belt and Belt Loops
For belt, simply remove middle edge loops, you can keep one for any animations deformations in belt area.

image

What about belt loops, they don't have any unnecessary edge loops and their triangle count is ok. Same as belt, add middle edge loop on all belt loops, to avoid issues with animations deformations
#### Overalls Straps
to-do, steps issue in polishing article

#### Overalls Clips
For overalls clips you will need to remove edges that don't affect shapes.
If needed use Rotate Edge CW tool located in Edge tab in viewport header, this tool will rotate edges, sometimes it's faster to use this tool instead of doing things manually.

image

image

image

image

### Result

image

If you encounter issues, please follow this video timelapse with steps explanation.

**preparing_overalls.mp4

## Preparing Bag
to-do
## Preparing Gloves
to-do
## Preparing Cap
Same as with belt, you will need to apply subdivision modifier first, to keep shapes for baking. After that, remove bevel modifier and use shade smooth.

Before you will apply subdivision modifier, make sure to add additional edge loop in bottom of cap. This loop is important, to avoid rounded angles that will appear in strap area, if you will apply modifier without additional edge loop.

image

image

Don't apply all modifiers for now, if you will take a look at cap topology, it's too high now, because you applied subdivision modifier. You will need to reduce triangles in next steps.

Also, don't forget to mark Sharp Edges manually, this is needed for doing UVs.

### Top Part
Same steps as for other small pieces.
- Remove Bevel Modifier
- Turn on Only Rim and apply Solidify modifier
- Use Shade Smooth and apply all modifiers

Remove middle unnecessary edge loop.

image

image

### Cap Straps
Select all faces in edit mode and merge vertices by distance.

image

image

Remove Bevel modifier and apply Simple Deform and remove Weighted Normal modifier. 

image

Remove unnecessary edge loops. 

image

image

Turn on Only Rim and apply Solidify modifier.

image

Use Shade Smooth and apply all modifiers. 

image

Remove unnecessary hidden faces and merge vertices, your straps should be as one mesh.

image

### Reducing Triangles
Overall process is same as for other parts, just look for unnecessary edge loops and remove them or merge some of vertices. 

As final result, your cap model should have around 400-500 triangles, this is perfect amount of triangles for such simple model. Keep in mind that overall triangles limitation for hair model with hat is around 2000 triangles, so it's better to leave extra triangles for high quality hair, rather than cap. 

And 400-500 triangles is perfect If you're planning to publish your cap model as hat category, without hair.

#### Cap
Remove all edge loops that won't change much cap shape after removal. 

image

image

image

image

Merge at center top hole edge loop. 

image

image

Start manually merging vertices, the idea here is to remove huge amount of edge loops, but keep shapes on cap corners. 

image

image

Use Shade Smooth and apply all modifiers.

image

You can reduce more triangles at bottom area of cap, it won't be visible because of hair. Good recommendation here it to not simply delete faces here, but keep them at minimum. Avoid leaving holes for any cap or hair models, unless it's intended. 

Select and merge vertices and center.

image

Manually merge some other vertices.

image

image

#### Cap Straps
Remove all edge loops that won't change much straps shape after removal. 

image

image

Remove middle edge loop. 

image

image

You can adjust edge loops a bit with Edge Slide tool. 

image

image

### Result

image

If you encounter issues, please follow this video timelapse with steps explanation.

**preparing_cap.mp4**
## Preparing Sneakers
From first view it's seems complex, but everything is same and simple as it was with previous parts. A lot of repeatable steps.

- Remove Subdivision and Bevel modifiers
- Select all faces in edit mode and merge vertices by distance
- Manually solve problem areas by removing unnecessary edge loops and merging vertices
- Join shapes that have lines for baking and merge vertices
- Remove sole details, they will be baked on flat plane as texture
- For sneakers clips you can copy prepared clips from overalls model
- Remove hidden faces, they eat triangles.
- Don't forget to mark Sharp Edges manually, if Shade Smooth works incorrectly in some areas

Limitations for any shoes wearables is 1500 triangles, so for one sneaker you can have 750 triangles maximum. You can orient on this number when you will reduce triangles count. 

### Sneakers Base
Remove unnecessary copy of sole, move vertices of sneakers base to bottom, to close hole.

image

image

Turn on Only Rim on Solidify and apply all modifiers.

image

Remove hidden faces, they're unnecessary and eats triangles.

image

Bridge faces in laces area and move them inside to avoid overlaps with laces and tongue. 

image

image

Select top hole edge loop, extrude edges and merge them at center, move it down a bit for natural look.

image

image

Edge slide unnecessary edge loops. 

image

image

### Sneakers Tongue
Apply all modifiers and remove hidden faces. 

image

image

For velcro part use Solidify with Only Rim and apply all modifiers, after that close holes by merging edge loops at center

image

image



### Sneakers Sole
Turn on Only Rim on Solidify and apply all modifiers. 

image

Merge at center bottom edge loop.

image

Remove unnecessary edge loops.

image

image

### Sneakers Laces 
Turn on Only Rim on Solidify and apply all modifiers. 

image

Remove hidden faces.

image

image

### Reducing Triangles
For now you should have model with around 900 triangles, that above limitation and you will need to reduce a lot of triangles. 

You will need to delete unnecessary edge loops, merge vertices, and and the same time keep shapes for baking. This might be challenging, but it's always possible.

image

### Result
After you prepared all models, make sure to apply all transforms and convert visual geometry to mesh, by doing that your models will be finally ready for doing UVs.

image

If you encounter issues, please follow this video timelapse with steps explanation.

**preparing_sneakers.mp4**


# Retopology
to-do 
## Summary
Now you should know how to adapt and clean models that you used for sculpting, to be ready to go for doing UVs and baking. As well as how to use retopology in situations when you made decision to do sculpt models from scratch.  

As final result, your low-poly models should have proper triangles count (as low as possible), but keep overall shapes for clean baking, without modifiers and unnecessary geometry. 
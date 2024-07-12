In this article you will learn how to polish base wearable models. 

It's important to follow [[(Drafting) Modeling Wearables]] article, because this article requires knowledge and usage of models from previous article. 

On previous article you should end with this result

image

# High-Poly 
On this step you will work with Subdivision Modifier and adjust models topology to prepare them for future sculpting and baking.

Most of models that you made in previous article require small amount of topology solutions and will use same modifier settings. Overall, when you will create any stylized models for Decentraland, you will end up with fixing small issues. 

Most of job, such as adding patterns, noise, dirt, small details, will be done on painting step in Substance Painter.

This article focus more on explaining modifiers and common solutions for topology issues. Models preparations here required only for doing some sculpting to enhance overall quality of models.

## Bevel Modifier

Bevel modifier adds smoothing on sharp edges and edges that have different angles. 

Nowadays, artists that work on stylized models, prefer to use only Bevel modifier or use Bevel shader to bake bevels on models edges. This saves lots of time, while overall quality of baked maps is near quality of models created with subdivision modifier.

Workflow with Bevel works very well for creating stylized textures for simple objects. If you want to achieve great results at creating PBR textures, especially on very complex models, it's better to learn modeling with Subdivision Modifier.


## Subdivision and Multiresolution Modifier 
Subdivision Surface uniformly subdivides the mesh for a smoother appearance, whereas the Multiresolution modifier provides a more flexible workflow for sculpting and detailing on different levels of resolution without affecting the base mesh. Each modifier has its strengths and is used based on the specific requirements of the modeling or sculpting process.

If you won't adjust model topology to work with both modifiers, you will encounter with huge amount of issues on baking and sculpting.  

Decentraland use models with stylized textures. This textures imitate all details from baked maps by combining them to one base color texture.

When you will start doing stylized textures in Substance Painter, all this textures will be created with generators that use baked maps. That means if your baking results have issues, all this issues will appear on your stylized textures. 

### When you can skip subdivision modifier?
You can skip subdivision modifier for very simple objects created from simple shapes.

- Models that don't require sculpting and requires huge triangle limitations on final model (clips, belt, fly, pockets, cap, any other simple shapes).

Mostly, you should use Bevel modifier. Using this modifier is more than enough for creating stylized textures.

### When you can't skip subdivision modifier?
Mostly subdivision modifier with topology adjustments required for very complex models with lots of details, holes, transitions in topology (for example, futuristic, sci-fi, weapon models). 

Additionally, If you want to do some sculpting on your model, then your model should work perfectly with subdivision modifier. If it works good with subdivision modifier, then it automatically works perfectly with Multiresolution modifier.

- Models for sculpting (clothes, trees, stones, leather, etc)
- Complex models for AAA games (weapons, sci-fi models, etc)
- Models with PBR textures

For some models you will need to use Bevel modifier in pair with Subdivision modifier to achieve perfect result. You already encountered with that on drafting step.

## Edge Loops and Creases 
Models that use subdivision modifier requires additional edge loops to avoid wrong smoothing on corners and other situations. 

Ways to add support edge loops. 
- manually with loop cut and knife tools. (manually add two edge loops near  wrong area and manually slide this edge loops to control subdivision smoothing, this method requires topology edits)

image

- automatically with creases (With this method you select wrong edges and define crease weight to them, solving smoothing issues. Just like with manual loop cut method, but without any topology edits)

image

- automatically with bevel modifier and proper settings (With this method you add edge loops automatically to all edges, adjust their weight, and correct which edges affected by setting angle limitation)

image

Core idea of this ways is to control subdivision modifier smoothing results and correct them in wrong areas. Each method depends on situation, you can use all of them at once, but usually it's more recommended to stick to one that you prefer more in exact situations. 

## Common Topology Issues

to-do

bevel arc option
applying subdivision and fixing topology
moving vertices

## Polishing Shirt
As you will sculpt folds in future pipelines, shirt should work perfectly with Multiresolution modifier.

Select shirt and all shirt pieces, add subdivision modifier (level 3) to them. Usually you should keep subdivision modifier at level 3 for testing purposes. 

There are no needs to increase level higher than 3, because you won't really see any changes on smoothing, while performance of Blender will go down and down with higher levels. 

You can use higher levels only if your base model looks very low poly even on level 3.

As you may see, there some issues appeared.

image

In this case, the best way to solve this issues is to adjust bevel modifier settings that you added to shirt pieces on drafting stage.

Select shirt and change bevel width type to absolute. Change bevel angle from 80 to 60 and adjust value of amount setting as you prefer. Repeat same steps for all shirt pieces. 

image

Now your shirt model is ready for sculpting. 

If you encounter any issues, take a look at this video timelapse with explanations

**polishing_shirt.mp4**

## Polishing Overalls 
Same as shirt, overalls should work perfectly with Multiresolution modifier. 

Some overalls parts (clips, belt loops), don't need any adjustments and they're ready to go for baking. Don't add any additional modifiers to them, this will cause bad baking results due to difference in triangles count. 

Select overalls, belt, straps and pockets, apply subdivision modifier (level 3). As it was with shirt, overalls have several issues with that needs to be fixed

image

Select overalls and change bevel width type to absolute. Change bevel angle from 80 to 60 and adjust value of amount setting as you prefer. Repeat same steps for straps and pockets. 

image

There are several issues because of bevel. For example front part of overalls legs have some weird beveled lines. To solve this type of issues, simply move vertices deeper to change angle of edges, until result will be smoothed. 

image

Another issue appeared in overalls pocket area. Some holes appeared and overalls parts connection line is too smooth. Luckily, overalls pants model is simple and you can fix this issues by moving vertices. There are no reasons to fix topology and insert any additional edge loops.

image

Next important thing is connection lines of overalls pieces, that may look thinner and thicker in different places especially in middle connection of mirrored parts. Manually fix all this lines by moving vertices, to achieve perfect look. This connections lines will be baked on texture, which will reflect more realistic and the same time stylized look.

image

Take a look at straps, from first view they look normal, but pay attention to rounded angles, due to low topology, they look like a bit deep/inside out. 

image

There are two ways how you can fix issues like this, first way is to simply select all faces and inset them a bit.

image

Second way is to apply subdivision modifier (level 1), fix topology, shape and silhouette, then add new subdivision modifier or keep model in mid-poly state. 

image

Also, if you don't like how knees and elbows area looks, you can remove their edge loops for now. This parts topology more important for final low poly model, for better bend during animations, rather than for sculpting.

image

image

Take a look at all parts of overalls and shirt. If you see any holes or issues, make sure to move vertices, edit any of modifier settings, for example solidify thickness, or value of bevel amount, to achieve clean model with perfect shapes, silhouette.

image

Now your overalls model is ready for sculpting.

If you encounter any issues, take a look at video timelapse with explanations,

**polishing_overalls.mp4**


## Polishing Cap
You can keep cap model as it is, it's more than enough for baking and painting stylized textures.

If you want improve overall quality of cap, then you should sculpt folds and add other small details. Same as shirt and overalls, prepare cap for multiresolution modifier.

Cap model is very simple and requires similar modifier settings explained before. Add subdivision modifier (level 3), change bevel type to absolute (you can keep default type on this and future steps if result looks well) and limit angle to 60. 

image

If you will notice some small issues, you can manually fix them by changing modifiers settings or by moving vertices.

Don't add any additional modifiers to straps and bow, they will be baked as it is to achieve good results. If you will add subdivision modifier to them, then high-poly will bake to low poly with additional shadows and curves, this will cause bad baking results due to lack of details on low poly models.

If you encounter any issues, take a look at video timelapse with explanations,

**polishing_cap.mp4**

## Polishing Sneakers
Same as cap, you can keep sneakers as it is. Baking results will look good and it's more than enough for painting stylized textures.

As well, if you want to add some folds, you should prepare sneakers for multiresolution modifier.

You can keep all parts except base, tongue and heels as it is.

Add subdivision modifier (level 3), change bevel type to absolute and limit angle to 60 to sneakers base, tongue and heels.

image

If you encounter any issues, take a look at video timelapse with explanations,

**polishing_sneakers.mp4**

# Summary
That's all steps for creating high-poly wearable models. For creating stylized models, high-poly modeling steps requires only few adjustments and is not that complex as for creating very high quality models.

Now you should have better understanding of repeatable patterns (tools and modifiers) used for creating high-poly models. You can move forward to sculpting. 

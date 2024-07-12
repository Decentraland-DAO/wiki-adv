In this article you will learn how to polish base wearable models. 

It's important to check [[(Drafting) Modeling Wearables]] article, because this article requires knowledge and usage of models from previous article. 

Result from previous article

image

# High-Poly 
On this step you will add Subdivision Modifier and adjust models topology to prepare them for future sculpting and baking.

## Subdivision and Multiresolution Modifier 
Subdivision Surface uniformly subdivides the mesh for a smoother appearance, whereas the Multiresolution modifier provides a more flexible workflow for sculpting and detailing on different levels of resolution without affecting the base mesh. Each modifier has its strengths and is used based on the specific requirements of the modeling or sculpting process.

If you won't adjust model topology to work with subdivision modifier, you will encounter with huge amount of issues on baking and sculpting.  

Decentraland use models with stylized textures. This textures imitate all details from baked maps by combining them to one base color texture.

When you will start doing stylized textures in Substance Painter, all of this textures will be created with generators that use baked maps. That means if your baking results have issues, all this issues will appear on your stylized textures. Knowing that fact, it's impossible to avoid subdivision modifier in some situations.

### When you can skip subdivision modifier?
You can skip subdivision modifier for shapes created from simple objects.

- Models that don't require sculpting and requires huge triangle limitations on final model (clips, belt, fly, pockets, cap, any other simple shapes).

### When you can't skip subdivision modifier?
Mostly subdivision modifier with topology adjustments used for very complex models with lots of details, holes, complex transitions in topology (for example, futuristic, sci-fi, weapon models). 

Additionally, If you want to do some sculpting on your model, then your model should work perfectly with subdivision modifier. If it works good with subdivision modifier, then it automatically works perfectly with Multiresolution modifier.

- Models for sculpting (clothes, trees, stones, leather, etc)
- Complex models for AAA games (weapons, sci-fi models, etc)
- Models with PBR textures

For some models you will need to use Bevel modifier in pair with Subdivision modifier to achieve perfect result. You already encountered with that, when you was doing straps and rivets on back side of cap.

## Edge Loops and Creases 
Bevel modifier smooth edges without issues on many many simple models. But, models that use subdivision modifier requires additional edge loops to avoid wrong smoothing on corners and other situations. 

Ways to add support edge loops. 
- manually with loop cut and knife tools. (manually add two edge loops near  wrong area and manually slide this edge loops to control subdivision smoothing, this method requires topology edits)

image

- automatically with creases (With this method you select wrong edges and define crease weight to them, solving smoothing issues. Just like with manual loop cut method, but without any topology edits)

image

- automatically with bevel modifier and proper settings (With this method you add edge loops automatically to all edges, adjust their weight, and correct which edges affected by setting angle limitation)

image

Core idea of this ways is to control subdivision modifier smoothing results and correct them in wrong areas. Each method depends on situation, you can use all of them at once, but usually it's more recommended to stick to one that you prefer more in exact situation. 

## Common Topology Solutions

bevel arc option
applying subdivision and fixing topology
moving vertices

## Polishing Shirt
As you will sculpt folds in future pipelines, shirt requires preparations to work perfectly with Multiresolution modifier.

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

polishing_shirt.mp4

## Polishing Overalls 
Same as shirt, overalls requires preparations to work perfectly with Multiresolution modifier. 

Some overalls parts (clips, belt loops), don't need any adjustments and they're ready to go for baking. Don't add any modifiers like subdivision to them, this will cause bad baking results due to difference in triangles count. 

Select overalls, belt, straps and pockets, apply subdivision modifier (level 3). As it was with shirt, overalls have several issues with that needs to be fixed

image

Select overalls and change bevel width type to absolute. Change bevel angle from 80 to 60 and adjust value of amount setting as you prefer. Repeat same steps for straps and pockets. 

image

There are several issues because of bevel. For example front part of overalls legs have some weird beveled lines. To solve this type of issues, simply move vertices deeper to change angle of edges, until result will be smoothed. 

image

Another issue that appeared is pockets and overalls pocket area. Some holes appeared and overalls parts connection line is too smooth. Luckily, overalls pants model is simple and you can fix this issues by moving vertices. There are no reasons to fix topology and insert any additional edge loops.

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

polishing_overalls.mp4


## Polishing Cap
You can keep cap as it is, it's more than enough for baking and simple textures.

If you want to sculpt folds and add other small details, you will need to prepare cap for Multiresolution modifier.

Cap model is very simple and requires similar modifier settings as shirt or overalls parts. Add subdivision modifier (level 3), change bevel type to absolute and limit angle to 60. 

If you will notice some small issues, you can manually fix them by changing modifiers settings or by moving vertices.

Don't add any additional modifiers to straps and bow, they will be baked as it is to achieve good results. If you will add subdivision modifier to them, then high-poly will bake to low poly with additional shadows and curves, this will cause bad baking results due to lack of details on low poly models.

## Polishing Sneakers
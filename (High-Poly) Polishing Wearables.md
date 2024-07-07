In this article you will learn how to polish base wearable models. 

It's important to check [[(Drafting) Modeling Wearables]] article, because this article requires knowledge and usage of models from previous article. 

Result from previous article

image

### High-Poly Pipeline
High-Poly modeling is second step in modeling. This step requires a lot of topology adjustments and repeatable usage of Subdivision Modifier.

Additionally, artist works on small and complex details, then polish model for future sculpting and baking. 

### Subdivision and Multiresolution Modifier 
Subdivision Surface uniformly subdivides the mesh for a smoother appearance, whereas the Multiresolution modifier provides a more flexible workflow for sculpting and detailing on different levels of resolution without affecting the base mesh. Each modifier has its strengths and is used based on the specific requirements of the modeling or sculpting process.

Mostly subdivision modifier with topology adjustments required for very complex models with lots of details, holes, complex transitions in topology. Good example is futuristic, sci-fi, mechanical robot models. This modifier also required for baking smooth PBR textures.

If you won't prepare model topology to work with subdivision modifier, you will encounter with huge amount of issues on baking and sculpting, because your model will be too low poly for this kind of this. 

Decentraland use stylized models with stylized textures that imitate all details and use only one base color. Knowing that fact, you can skip subdivision modifier and save your time, using bevel modifier for baking instead, which is more than enough and modifier itself don't require a lot of manual work with topology. 

Examples when you can skip subdivision modifier:

- Models that don't require sculpting and requires triangle limitations on final model (clips, belt, fly, pockets, cap, cylinders, etc).

However, as usual, there are exceptions. If you want to use sculpting and add a lot of details that way, your model should be prepared and work perfectly with subdivision modifier, which means that model will be automatically prepared for multiresolution modifier. 

Examples when you can't skip subdivision modifier
- Cloth models that require sculpting of folds, cracks, stitches (shirt, pants, jumpsuit, skirt, etc).

For some models you will need to use Bevel modifier in pair with Subdivision modifier to achieve perfect result. You already encountered with that, when you were modeling straps with rivets on back side of cap.

In some situations it's impossible to create high-poly model without subdivision modifier. 

### Edge Loops and Creases 
Bevel modifier smooth edges without issues on many many simple models. But, models that use subdivision modifier requires additional edge loops to avoid wrong smoothing on corners and other situations. 

Ways to add support edge loops. 
- manually with loop cut and knife tools. (manually add two edge loops near  wrong area and manually slide this edge loops to control subdivision smoothing, this method requires topology edits)

image

- automatically with creases (With this method you select wrong edges and define crease weight to them, solving smoothing issues. Just like with manual loop cut method, but without any topology edits)

image

- automatically with bevel modifier and proper settings (With this method you add edge loops automatically to all edges, adjust their weight, and correct which edges affected by setting angle limitation)

image

Core idea of this ways is to control subdivision modifier smoothing results and correct them in wrong areas. Each method depends on situation, you can use all of them at once, but usually it's more recommended to stick to one that you prefer more in exact situation. 

### Topology Solutions

bevel arc option
applying subdivision and fixing topology
moving vertices

### Polishing Shirt
As you will sculpt folds in future pipelines, Shirt requires preparations to work perfectly with Multiresolution modifier.

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

### Polishing Jumpsuit
Same as shirt, jumpsuit requires preparations to work perfectly with Multiresolution modifier. However, some jumpsuit parts (clips, belt, belt loops, fly), don't really need any adjustments and they're ready to go for baking. 

Select jumpsuit, belt, straps and pockets, apply subdivision modifier (level 3). As it was with shirt, jumpsuit have several issues with that needs to be fixed

image

Select jumpsuit and change bevel width type to absolute. Change bevel angle from 80 to 60 and adjust value of amount setting as you prefer. Repeat same steps for straps and pockets. 

image

There are several issues because of bevel. For example front part of jumpsuit legs have some weird beveled lines. To solve this type of issues, simply move vertices deeper to change angle of edges, until result will be smoothed. 

image

Another issue that appeared is pockets and jumpsuit pocket area. Some holes appeared and jumpsuit parts connection line is too smooth. Luckily, jumpsuit pants model is simple and you can fix this issues by moving vertices. There are no reasons to fix topology and insert any additional edge loops.

image

Next important thing is connection lines of jumpsuit pieces, that may look thinner and thicker in different places especially in middle connection of mirrored parts. Manually fix all this lines by moving vertices, to achieve perfect look. This connections lines will be baked on texture, which will reflect more realistic and the same time stylized look.

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

Take a look at all parts of jumpsuit and shirt. If you see any holes or issues, make sure to move vertices, edit any of modifier settings, for example solidify thickness, or value of bevel amount, to achieve clean model with perfect shapes, silhouette.

image

Now your jumpsuit model is ready for sculpting.

If you encounter any issues, take a look at video timelapse with explanations,

polishing_jumpsuit.mp4


### Polishing Cap
You can keep cap as it is, it's more than enough for baking, if you want to keep simple style. Just make sure to polish shapes and silhouette.

If you wish to add folds and sculpt some stitches and any other details, you will need to prepare cap for Multiresolution modifier.

Cap requires similar modifier settings as shirt or jumpsuit parts. Add subdivision modifier (level 3), change bevel type to absolute and limit angle to 60.


In this article you will learn how to improve wearable models with sculpting. 

It's important to follow [[(High-Poly) Polishing Wearables]] article, because this article requires knowledge and usage of models from previous article. 

# Sculpting
On this step you will work in Sculpt Mode with Multiresolution Modifier and default or custom tools for sculpting.

Before you will start sculpting folds and others details, duplicate collection with models prepared for subdivision modifier and then remove subdivision modifier on them. Apply all other modifiers and then add multiresolution modifier.

## Multiresolution Modifier
There are few things that you should know about subdivision levels in Multiresolution modifier. 

### High Subdivision Levels
The global mistake of all beginners is to use high subdivision levels on simple/stylized models. 

Usually, high subdivision levels are used for baking very high density details on realistic characters, or for creating high quality renders.

You don't need that for simple stylized model, the basic rule is to stay away from subdivision levels that increase face count higher than 3 millions, everything else is good and usable.

### Mid and Low Subdivision Levels
This is from where you will start, before sculpting things. 

To determine good subdivision levels, you should orient on how big or how small your object and how topology density will change with subdivision levels. 

For example if object have medium size, like gloves, couple of thousands or 1-2 hundred of faces will be enough to get high density topology ready for sculpting. 

image

The same thing with big objects, for them it's not enough to have couple of thousands faces, usually good density starts around 5 hundred or 1 million of faces.

image



### Switching Levels
Sometimes, it's good to switch subdivision levels from higher to lower and back to higher. 

Here is couple examples when this trick is useful:
- change folds position on lower level and then get back to sculpting on higher level.
- easier to fix or remove bad details with smooth tool on 1-2 levels lower and then get back to higher level.

## Mouse and Pen Tablet 
While most of senior 3d artists use pen tablet or pen displays for drawing and sculpting details, it's not the thing that should block beginners from sculpting things. 

You can easily use mouse for sculpting simple things, especially on simple stylized models.

The one major minus of mouse is lack of pressure, all lines will have same thickness no matter how hard you press on your mouse. Because of that, you will need to use Pinch brush a lot to imitate pen pressure. 

image

image

If you're planning to use mouse, you can also turn on Stabilize Stroke and adjust it's settings, this option located in Sculpt Mode, Stroke tab. 

image

## Sculpting Brushes
To sculpt folds, cracks, stiches and any other details on your models, you will need to use default brushes and know how to setup custom brushes. 
### Default Brushes
You should know all this brushes for sculpting things, this brushes are must have for different common situations.

- Draw (sculpting realistic folds)
- Draw Sharp (sculpting cracks, lines, stitches)
- Clay (most common tool for sculpting characters with round shape clay)
- Clay Strips (most common tool for sculpting characters with square shape clay)
- Inflate (useful for changing realistic folds thickness)
- Crease (good for sculpting stylized folds, cracks, lines)
- Smooth (smoothing or fixing some areas for achieving better results)
- Flatten (flatten uneven surfaces)
- Fill (fill holes, for example hole between two folds)
- Scrape (good for sculpting damaged areas on hard surface objects)
- Pinch (useful changing lines thickness)
- Grab (tool for moving small details on model)
- Elastic Deform (tool for moving huge areas of model)
- Snake Hook (tool for moving areas of model with some kind of extrusion)
- Mask (tool for sculpting only on masked areas)

### Custom Brushes
To important custom brushes, you will need to find and download them somewhere. [Here](https://stylizedstation.gumroad.com/l/zMJlJ) you can find very famous and free to use **Orb Brush Pack** created by **Michael Vicente - Orb**, converted for Blender. 

Originally, pack was created for Zbrush and use format that Blender don't support. If you want to support original creator, follow this [link](https://orb.gumroad.com/l/nOkHw)

Archive includes guidelines how to install this brushes to Blender to be able to use them in any project, follow this guidelines if needed. 

Let's take a look how to prepare and use any brush psd file as brush in current project.

Select draw brush, navigate to Tool tab in Properties panel, duplicate draw brush and rename it as you want. 

image

image

Change stroke method to anchored, with this method you will be able to draw details like scratches.

image

Navigate to Texture tab in Properties panel, create new texture and select psd file. 

image

image 

image

Navigate back to Tool tab and reduce or increase sample bias, this will help to avoid drawing of additional circle around brush.

image

Now your custom brush is ready to use

image

You can switch brush back to default one in brushes tab

image



## Core Sculpting Tools
Mostly, you will just sculpt couple of folds and other details with default and custom brushes on top of base mesh prepared with methods from previous articles.

Base mesh with couple of folds on top don't require manual retopology and will end up with almost ready to go low poly model adapted from base mesh. 

But, if you want to sculpt additional complex shapes, or sculpt model from scratch, then you will need to work a lot with default brushes.

### Remesh and Dyntopo
If you're looking for sculpting models from scratch, you will need to use this tools to keep density for new shapes and details, this tools don't work with subdivision/multiresolution modifier workflow and requires work with manual retopology for creating ready to bake low-poly. 

Using this tools you don't need to care about perfect quad topology, because this topology anyways will be recalculated to triangles/voxels. 

#### Remesh
This tool recalculates topology density on object according to pre-defined voxel size setting. Remeshing also closes all holes and merges overlapping shapes together. 

For example, if you made character draft from couple of spheres and now want to start sculpting, you will need to merge all spheres into one mesh and then use Remesh tool in Sculpt Mode to recalculate topology properly.

If you're going to use single mesh, for example sphere, you can skip Remeshing and start sculpting with Dyntopo.

#### Dyntopo 
This tool automatically recalculates topology density on areas and new shapes that you will sculpt. That means that you can deform your mesh as much as you want and you will always be able to sculpt things on it, because topology will be automatically recalculated to keep good enough density. 

You should always use Remesh and turn on Dyntopo on all things that you're going to sculpt from scratch. This is important on drafting stage, when you sculpt main shapes and define silhouette. 

#### Quad Remesh
This is additional option in Remesh tool, that recalculates topology with quads, instead of voxels. 

You should use Quad Remesh as soon as you sculpted all main shapes and silhouette with Remesh and Dyntopo, because thats required for future usage of Multiresolution modifier to be able to sculpt more small details, and for preparing final, polished, high-poly model ready for baking.

### Clay and Clay Strips Brush
That's the core brushes used for sculpting new shapes and for sculpting characters from sphere, from scratch.

You can use any of them, there are no strict rule which one is right and which one is wrong. Sculpting things with Clay brush feels smooth, sculpting with Clay Strips brush feels more strict and noisy. Just like in real life, some sculptors sculpt things with a lot of small and strict pieces of clay and leave them as it is, while other sculptors do all the same but in the end smooth clay for more natural result.

There is one thing required for both of this brushes and that's the low strength setting. Overall approach for sculpting things is to draw "layers" of clay and then smooth them. Low strength of brush gives sculptor a lot of flexibility and reduce amount of mistakes that's hard to remove with smooth brush.

image

image

By default strength is 0.5, that's a lot. Keep strength of your brushes around 0.15 - 0.25. Feeling of strength also depends on density of your mesh, so if you feel that strength is very low, or very high, change numbers until you will feel good. 

#### Smooth Brush
Core brush used for smoothing results and fixing mistakes, the thing about strength applies on this brush too.

#### Mask and Face Sets
With mask brush you can mark areas that you want to sculpt without affecting the rest of areas.

Additionally, mask brush used for extracting new shapes from masked areas, for example if you want to draw complex ornament, the easiest way is to draw it with mask and then extract mask to new mesh and then adjust this mesh to achieve smooth results.

If you want to smooth or sharpen mask you can find this settings in mask tab located in viewport header.

image

You can also convert your masks to Face Sets.

Face sets are used to group your mesh into differently colored faces, which can then be quickly hidden or shown. This is very handy tool used a lot, especially when sculpting models from scratch.

### Grab and Elastic Deform
Both of this brushes are used a lot to define core shapes and silhouette of object. In pair with Dyntopo and Remesh, you will never encounter lack of density issue. 

For example, you can easily create interesting scratches and deformations with mask and grab/elastic deform.

image


## Sculpting Folds
If you want to achieve great results at sculpting folds, you should know how to use combination of several brushes and common folds patterns

### Stylized Folds
To draw stylized folds use Crease brush in combination with Inflate and Smooth brushes. If you feel that strength of your brushes are low or high, you can change their strength setting in tool tab or in viewport header.

image

image

To achieve more stylized look of folds, you can change pinch setting of crease brush, you can find this setting in tool tab or in brush tab at viewport header. 

image

image

Draw couple of folds with Crease brush and then change their thickness with Inflate brush, smooth some areas for better transitions if needed. 

image

You can improve holes between folds with Inflate brush, this is very useful for creating folds like on puffer jacket. You will need to hold CTRL or switch direction mode in tool tab or in viewport header.

image 

image

### Folds Patterns
From first view, most of folds, especially on jackets or pants, looks very complex and strange. But, actually, there is nothing complex. 

If you will take a look on folds from different angles, you will notice patterns,  the most common one is when folds looks like "Y" character, that have different length and angle. 

image

Complex folds are combination between "X", "Y", "Z" characters merged together, for example, you can notice this folds pattern on jacket forearms. 

image


## Sculpting Wearables
As you're following approach with base mesh and Multiresolution modifier, instead of sculpting models from scratch, you can simply draw couple of stylized folds with crease brush on all cloth parts and then move to next article.

Here is result that you should achieve by sculpting couple of stylized folds.

image

image

Instead of reading repeatable text and images about sculpting all the same folds, just take a look at video timelapse with explanations.

**sculpting_wearables.mp4**

## Summary
That's all steps you should know for sculpting. Now you should have better understanding, when it's good to sculpt things from scratch, and when it's good to use prepared models. 
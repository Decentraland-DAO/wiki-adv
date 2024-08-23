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

## Computer Mouse and Pen Tablet 
While most of senior 3d artists use pen tablet or pen displays for drawing and sculpting details, it's not the thing that should block beginners from sculpting things. 

You can easily use computer mouse for sculpting simple things, especially on simple stylized models.

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

## Sculpting Details
## Sculpting Wearables

## Summary
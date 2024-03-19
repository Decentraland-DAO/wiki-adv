Addons that you will need for advanced documentation pipelines.
- [Blender](https://github.com/the-ankou/advanced-documentation/wiki/Addons#blender)
	- [TheAnkou's Scripts and Pie Menu Editor (Scripts)](https://github.com/the-ankou/advanced-documentation/wiki/Addons#theankous-scripts-and-pie-menu-editor-scripts)
	 - [TheAnkou's Hair Nodes or Stylized Hair PRO v3 (Modeling)](https://github.com/the-ankou/advanced-documentation/wiki/Addons#theankous-hair-nodes-or-stylized-hair-pro-v3-modeling)
	 - [Friendly Pivot (Modeling)](https://github.com/the-ankou/advanced-documentation/wiki/Addons#friendly-pivot-modeling)
	 - [LoopTools (Modeling)](https://github.com/the-ankou/advanced-documentation/wiki/Addons#looptools-modeling)
	 - [Rigify (Rigging)](https://github.com/the-ankou/advanced-documentation/wiki/Addons#rigify-rigging)
	 - [Easy Weights (Weight Painting)](https://github.com/the-ankou/advanced-documentation/wiki/Addons#easy-weights-weight-painting)
	 - [Lazy Weight Tool (Weight Painting)](https://github.com/the-ankou/advanced-documentation/wiki/Addons#lazy-weight-tool-weight-painting)
	 - [Voxel Heat Diffuse Skinning (Weight Painting)](https://github.com/the-ankou/advanced-documentation/wiki/Addons#voxel-heat-diffuse-skinning-weight-painting)
	 - [SJ Phaser (Animation)](https://github.com/the-ankou/advanced-documentation/wiki/Addons#sj-phaser-animation)
# Blender
### TheAnkou's Scripts and [Pie Menu Editor](https://blendermarket.com/products/pie-menu-editor) (Scripts)
**TheAnkou's Scripts** handy scripts created with ChatGPT. With **Pie Menu Editor** addon, you will be able to use this scripts as panel with buttons in **N** menu tab   in Blender.

You can't CTRL+Z most of these scripts, so be careful and save your project before using them.
- **Import Texture** instead of manually creating material and doing things in nodes as well as manually selecting textures. This script will assign roughness 1 material and selected texture just in one click. 

- **Bones Default and Symmetry Name** scripts switch Decentraland avatar bone names to ones that will work with weight paint symmetry and back to default ones.

- **Remove Modifiers, Remove Materials, Remove Vertex Groups** scripts remove all modifiers, materials or vertex groups from selected meshes. 
- **UVName -> UVMap** usually, when you work with imported meshes from different software, sometimes their uv maps have different names, this cause issues when you want to merge two meshes into one. This script change name of all uv maps on selected objects to default UVMap name, without needs for manual renaming. With this script you can merge meshes without worries that uv maps will dissapear. 

- **Roughness Material** script applies roughness to 1 and metallic, specular and some other settings to 0 (except alpha and emission) on all materials of selected meshes. 

- **Reload Textures** script reloads all textures used in project.
- **Purge ALL** removes all unused things from project. 

**Pie Menu Editor Setup** 
Go to Blender **Preferences -> Add-ons** and search for **Pie Menu Editor**, open Pie Menu Editor tab and under **Preferences** window you can setup **N** menu tab with buttons.

[[/images/pie_menu_editor01.png]]

Press **Add an item** and select **Panel Group** and **Popup Dialog**

[[/images/pie_menu_editor02.png]]

[[/images/pie_menu_editor03.png]]

In left area you will need to select **Panel Group** that appeared, then press **add panel** button and select **Popup Dialog**. Also, here you can search for **My Category** word and change it to anything you want. That will be the name of tab in **N** panel.

[[/images/pie_menu_editor04.png]]

 Now select **Popup Dialog** that appeared and in right area you can now add buttons and select scripts that buttons will run.

[[/images/pie_menu_editor05.png]]

Click on **Button 1** and **Edit Slot**, now you will need to press on three horizontal stripes button and select **Call External Script**, select python script that you want and press **open script**, after that change button **name** and press **OK**.

[[/images/pie_menu_editor06.png]]

[[/images/pie_menu_editor07.png]]

[[/images/pie_menu_editor08.png]]

That method will work for all python scripts except **Import Texture**.
To create **Import Texture** button instead of call external script you will need to select **Call Operator** and add **Run Python File**

[[/images/pie_menu_editor09.png]]

[[/images/pie_menu_editor10.png]]

Click on folder icon and select **Import Texture** python script. 

[[/images/pie_menu_editor11.png]]

Press **Apply**, change button name and then press **OK**

[[/images/pie_menu_editor12.png]]

### TheAnkou's Hair Nodes or [Stylized Hair PRO v3](https://deanzarkov.gumroad.com/l/stylized_hair_pro) (Modeling)
**TheAnkou's Hair Nodes** or **Stylized Hair PRO v3** tools made from Blender geometry nodes, for creating any type of hairs, with curves and flexible settings just in few steps. 


### [Friendly Pivot](https://blendermarket.com/products/friendly-pivot) (Modeling)
**Friendly Pivot** small addon for fast manipulations with pivot point in Blender.
### [LoopTools](https://docs.blender.org/manual/en/latest/addons/mesh/looptools.html) (Modeling)
**LoopTools** allows to adjust mesh vertices to different shapes. Usually it's used for squared holes that needs to be changed to rounded.
### [Rigify](https://docs.blender.org/manual/en/2.81/addons/rigging/rigify.html#activation) (Rigging) 
**Rigify** complex but very useful addon for creating skeleton with constraints for animations. Skeleton created with this addon will require a lot of properties adjustments, to make it ready to use in Decentraland, but it's worth of it.
### [Easy Weights](https://studio.blender.org/pipeline/addons/easy_weights) (Weight Painting)
**Easy Weights** handy addon with couple of useful tools required for weight painting. You will need to use it with **Lazy Weight Tool.**
### [Lazy Weight Tool](https://blendermarket.com/products/lazy-weight-tool) (Weight Painting)
**Lazy Weight Tool** core addon for weight painting. It copies a lot of things from 3ds Max and Maya, and makes weight painting process more simple.
### [Voxel Heat Diffuse Skinning](https://blendermarket.com/products/voxel-heat-diffuse-skinning) (Weight Painting)
**Voxel Heat Diffuse Skinning** calculates weights with voxel method, just like in 3ds Max or Maya. It's must have to use this addon, because it makes simple auto weight painting for mesh with a lot of individual parts and allows to bake smooth corrective modifier.
### [SJ Phaser](https://captainhansode.gumroad.com/l/EVhEq) (Animation)
**SJ Phaser**  addon creates and bakes spring animation for bones. Very useful for creating simple wings, cloak, ears, tail animations. Just in one click and game ready.

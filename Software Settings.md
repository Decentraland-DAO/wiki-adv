List of recommended settings for tools, this settings will speed-up process of creating models, and will make UI of some tools more user-friendly.
- [Blender](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#blender)
	- [Import/Export Settings](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#importexport-settings)
- [Marmoset Toolbag 4](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#marmoset-toolbag-4)
- [Adobe Substance 3D Painter](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#adobe-substance-3d-painter)
# Blender
### Navigation Settings 
On first start after installation, you will see welcome window with hotkey and navigation settings, keep navigation and hotkey settings by default. It's not recommended to switch them to Maya or anything else. There will be issues with hotkeys on modes like "Weight Painting". 

### Viewport Denoising and Color Management
**Viewport Denoising** - setting reduce noise and smooth character animation preview in viewport. It's sounds as good feature, but on practice it adds more noise, than denoise. It's highly recommended to **turn off** this setting, to achieve clear and smooth animation results, that will look exactly like in game engine. 

*Visual Comparison*


[[viewport_denoising.mp4]]

**Color Management** -  is another Blender setting that manages colors inside Blender viewport. By default View Transform setting, located in Color Management tab is set to Filmic or anything else, but not Standard. As result, this setting cause any textures, look a bit different, than they look in Substance Painter or in game engine. It's highly recommended to change View Transform setting from Filmic to **Standard**. Standard setting will display textures right way.

*Visual Comparison*

[[/images/color_management.png]]

*Settings Location*

[[/images/render_properties.png]]

### Frame Rate
By default Blender **Frame Rate** is 24, which is good for movies. It's highly recommended to change Frame Rate to **30**, which is standard for games and this setting is important for creating game-ready character animations. 

*Settings Location*

[[/images/frame_rate.png]]

### Face Orientation
**Face Orientation** - display orientation of face normals. This setting allow creators to detect all inverted normals on a model. it's highly recommended to keep this setting always on. 

By default, when you turn on Face Orientation setting, "right" normals on model shown as blue color, and "wrong" inverted normals as red color, which cause creators to turn this setting on and off time from time to check if everything is good. 

With right settings in Blender preferences, you can hide display of "right" normals and keep display only "wrong" normals. That way you're able to keep Face Orientation setting always on by default and always see what's right and what's wrong without need to always turn this setting on and off. 

*Visual Comparison*

[[/images/face_orientation_preview.png]]

*Settings Location*

[[/images/face_orientation.png]]

[[/images/face_orientation_preferences.png]]
 




### Save Settings and UI Setup
It's recommended to move Blender outliner from right side to left side of window, that way UI will be more friendly and will look like basic windows "explorer", and will be familiar to navigation in other tools like Maya, Marmoset, and rest. This setup saves huge amount of time on work and reduce amount of mouse clicks between tabs and windows.

Additionally, we will add small UV editor window on left side, which we will use for fast access to UV. 

For animations it's useful to keep two timelines, default one, but closed. For frame range setup, record and play buttons. Second one Dope Sheet with actions, will be used for work. 

*Save Settings*

[[default_settings.mp4]]

*UI Setup*

[[ui_setup.mp4]]

### Import/Export Settings

You can save export settings as presets and use it in future without needs for manual adjustments.

**Recommended import/export to FBX settings**

**Export settings:** All settings should be default, in our pipelines you will use FBX export for RizomUV, Marmoset and Substance Painter. The only setting that you will need to change sometimes is **Selected Objects, ** **Apply Modifiers** and **Triangulate Faces**

**Import Settings:** Default.

**Recommended GLTF/GLB import settings**
- **Pack Images:** by default is enabled, It's recommended to keep that setting enabled. 
- On import you will need to enable option **"Merge Vertices"**.  When you export any object from Blender to GLB, mesh vertices will split as UV shells. That means that if you will import object back to Blender, your mesh will look exactly the same, but if you will start edit it and move vertices, you will notice that in some areas there are 2 vertices in located and the same place. 
- **Shading:** Use Normal Data
- **Bone Dir:** by default it's **Blender**, but sometimes you will need to change this setting to **Temperance**, for example, when you will import **Decentraland avatars** to Blender, with **Bone Dir: Blender**, you won't see bones. Temperance setting solve this issue. 


**Recommended export to GLTF/GLB settings.**

**Wearables** - for wearables it's recommended to use .glb, because textures will be packed inside .glb file, which is handy for easy upload to builder
- Use **Selected** or **Visible** objects setting in include section.
- **Only UVs and Normals** should be enabled in mesh section, sometimes you will need to use **Apply Modifiers** additionally. Avoid all other options, like Vertex Colors. This option, for example, will split materials with alpha, which will cause increase of .glb total size and loss of source material if you will import .glb back to Blender. 
- If you experience issues with .glb size, you can use **export to jpg** option inside material section. Usually it's better to manually export all textures to jpg, with proper compression, to achieve best quality and small size for each textures. But if you're looking for fast solution, just use automatic method that's implement in export settings. 
- **Shape Keys** should be disabled.
- In armature section enable **use rest position** and **export deformation bones** only.
- If you experience issues with .glb size, you can try to use **compression setting**, by default level of compression set to 6, which cause small glb files be empty and crash in game. It's recommended  to try different compression levels starting from 1, and detect the one that works and decrease size. This option is very handy for animations and environment objects. It's not recommended to touch other compression settings, except compression level.
- **Animation** section should be disabled.

**Assets** - export option here depends on situation. If you you're looking for fast export, use .glb. If you're looking for more optimized way and you're the one who will build whole scene through builder/visual studio code/blender, then it's better to use .gltf with separated "textures" folder. For assets you can use  same settings like for wearables. Here is additional settings that you will need to use for assets with animations:
- **Skinning**, if you use bone animation, then you will need to use this setting, otherwise, disable it.
- **Animation** section should be enabled.
- **Animation mode** depends on situation, usually you will use **NLA tracks** and **Scene** mode. If your model use many actions like (stand, walk, idle) convert them to NLA tracks. If your model use one infinite animation (for example: elevator), then use Scene mode. It's not recommended to use other modes. 
- **Rest & Ranges** usually default.
- **Shape Keys Animation** should be disabled.
- **Sampling Animation** and **Sampling Rate** by default is 1. Sometimes it's useful to use higher levels for better animation optimization. But be careful with this setting, because it's functional is to delete keyframes. Animation will look very choppy if you will set very high level of sampling rate.
- **Optimize Animations** by default is enabled, but sometimes disabling this setting will reduce total size of .glb, this depends on situation, it's better to always try to export animated objects with and without this option.

**Environment** - if you're building whole environment from assets in Blender, and planning to export each asset as separated file, it's highly recommended to use .gltf with separated "textures" folder. That way objects that you used many times, won't have individual materials with duplicated textures and that way you're able to use one same texture on different objects. Settings here are same as for wearables, or as for assets, depends on situation. It's recommended to use "Texture or Textures" folder name, for .gltf with textures. 

*Wearables and Assets*

[[/images/wearables_export.png]]

*NLA Tracks*

[[/images/nla_tracks.png]]

*Scene Animation*

[[/images/scene_animation.png]]

*Export to JPG*

[[/images/export_to_jpg.png]]

*Compression*

[[/images/compression_setting.png]]

# Marmoset Toolbag 4
### Output Settings
On first bakes and cage setup, it's recommended to use the lowest settings as possible to save bake time and speed up baking workflow. As soon as everything bakes well, you can increase settings to maximum and bake final maps.

- **Samples:** Minimum 4

- **Format: Always 16 Bits/Channel**, don't bake 8 and 32 bit maps. The reason for that is very low gradient quality on 8 bit maps (which will cause artifacts on texture painting and final textures), what about 32 bit maps it's not really important and only required for very high quality meshes, for example - 3d scans.

- **Soften:** Always 1
- **Padding:** Custom
- **Padding Size:** 8px

By default padding size is moderate, but It's recommended to change it to custom and set padding size to 8px, because we will bake only 1024x1024 textures.

On baking stage it's better to keep exact padding for exact texture size, later, in Substance Painter, we will export final textures with moderate padding that will fill all empty areas. 

It's not recommended to keep moderate setting. Later, in game engine, you will encounter with issues like wrong padding which in result cause mipmaps work with artifacts, and as result in game you will see white lines between UV shells on models.
 
 You can learn more information about padding and mipmaps 
 [here](http://wiki.polycount.com/wiki/Edge_padding) 

We will always bake all this maps, for future usage in Substance Painter:
- **Normals**
- **Normals (Object)**
- **Height**
- **Position**
- **Curvature**
- **Convexity**
- **Cavity**
- **Thickness**
- **Bent Normals**
- **Ambient Occlusion**
- **Material ID**

All this maps have their own settings, It's recommended to set **Ray Count** on some of this maps to **1024** and keep the rest settings in default state. 

*Settings Preview*

[[/images/bake_settings.png]]

If you're looking for more information about maps that we will bake, you can find it [here](https://marmoset.co/posts/toolbag-baking-tutorial/) and [here](https://docs.marmoset.co/docs/map-types/)
# Adobe Substance 3D Painter
### New Project Settings
- **Template:** just leave as is "Select template...", 
there are many templates, but we won't use them.

- **Document Resolution:** 1024 (1024x1024 textures)

- **Normal Map Format:** OpenGL (Blender, Marmoset, Decentraland (Unity) use OpenGL)

- **UV Tile Settings (UDIM's):** It's highly recommended to use UV tile workflow and preserve UV tile layout per material. This setting is very important for UDIMs workflow and fast work with models in process of creating (painting) textures. 

It's not recommended to create any projects without UV tile workflow. You will encounter issues, bugs, and freezes. It also requires creation of many materials for your models, which make process of preparations for texturing very complex. Just use UDIM's (UV tile workflow), it's faster and better. 

- **Import Cameras:** OFF

- **Auto-Unwrap:** OFF

Other settings should stay default

*Recommended Settings*

[[/images/spp_project_settings.png]]

### Import Textures Settings
Select all maps in explorer, drag and drop them to **Assets** window in **Substance Painter**. 

**Import resources** window will appear. Click on area with list of imported maps, press **CTRL+A** and then change **undefined** to **texture**

Change **import your resources to:**  from **current session** to **project "your project name here"**. 

Current session will keep maps only until you will close Substance Painter. Project will keep maps in project that you saved. Library will keep your assets in Substance Painter forever, no matter what project you open. For maps it's recommended to use **Project**.

[[/images/import_resources.png]]

### Export  Textures Settings
- **Output Template** by default it's **Document channels + Normal + AO (No Alpha)** but sometimes you will need to use the same template but **with alpha**. You can also create your own template, but it's recommended to use default ones. There is another one popular template - **2D View**, this template export 2D View of current texture and light state in Substance Painter scene, sometimes it's handy, but results are dirty. Advanced Documentation pipelines will cover better and more professional way that use filters for baked lights.
- **File type:** by default it's PNG 8 bits, it's recommended to use **PNG 16 bits** and then optimize to JPG with clear and smooth results in **Adobe Photoshop**. PNG 8 bits decrease gradients quality, while PNG 16 bits keeps all gradients as clear as possible.
- **Size:** 1024
- **Padding:** Dilation Infinite. Other settings required for manual adjustments in Adobe Photoshop or for other individual situations.

You will need to export only **Base Color** maps which will be used in all pipelines. It's not recommended to use other maps in Decentraland, because they don't work as they should. You may try to experiment with Normal, Metallic and Roughness maps, but all this maps require a lot of manual adjustments for clear results.

You can select only **Base Color** maps on each material in Global Settings window

*Export Settings*

[[/images/export_templates.png]]

*Required Maps*

[[/images/global_settings.png]]
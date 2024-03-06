List of recommended settings for tools, this settings will speed-up process of creating models, and will make UI of some tools more user-friendly.
- [Blender](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#blender)
	- [Navigation Settings](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#navigation-settings)
	- [Viewport Denoising and Color Management](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#viewport-denoising-and-color-management)
	- [Frame Rate](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#frame-rate)
	- [Face Orientation](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#face-orientation)
	- [Save Settings and UI Setup](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#save-settings-and-ui-setup)
	- [Import/Export Settings](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#importexport-settings)
- [RizomUV](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#rizomuv)
	- [Texel Density](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#texel-density)
	- [Margin and Padding](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#margin-and-padding)
	- [UV Packing Settings](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#uv-packing-settings)
- [Marmoset Toolbag 4](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#marmoset-toolbag-4)
	- [Output Settings](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#output-settings)
- [Adobe Substance 3D Painter](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#adobe-substance-3d-painter)
	- [New Project Settings](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#new-project-settings)
	- [UI Setup](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#ui-setup)
	- [Import Textures Settings](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#import-textures-settings)
	- [Export Textures Settings](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#export--textures-settings)
	- [Custom Templates](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#custom-templates)
- [Adobe Photoshop](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#adobe-photoshop)
- [Stable Diffusion (AUTOMATIC1111)](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#stable-diffusion-automatic1111)
	 - [Required Models](https://github.com/the-ankou/advanced-documentation/wiki/Software-Settings#required-models)
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
It's recommended to move Blender outliner from right side to left side of window, that way UI will be more friendly and will look like basic windows explorer, and will be familiar to navigation in other tools like Maya, Marmoset, and rest. This setup saves huge amount of time on work and reduce amount of mouse clicks between tabs and windows.

Additionally, we will add small UV editor window on left side, which we will use for fast access to UV. 

For animations it's useful to keep two timelines, default one, but closed. For frame range setup, record and play buttons. Second one Dope Sheet with actions, will be used for work. 

*Save Settings*

[[default_settings.mp4]]

*UI Setup*

[[blender_ui_setup.mp4]]

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

# RizomUV
### Texel Density
**Texel Density** - is global scaling setting for each UV island. Final textures result strictly depends on right texel density. You can learn more about texel density and it's calculations [here](https://www.beyondextent.com/deep-dives/deepdive-texeldensity#)

In-depth information about texel density usually sounds very complex and confusing, but on practice everything is simple.

Before doing UV unwrapping, it's very important to export from Blender object with right, final, dimensions. For example, if you will create desk with wrong dimensions, UV shells will be very big according to texel density, and as result, you will need to use two or more textures for one object, to achieve clear textures quality. You don't need 2 or more textures for desk, unless desk was supposed to be very big.

Here is basic texel density numbers for common textures. It's not recommended to use number less than listed below, but you can use higher numbers, if your UV square have enough of space for that. 

- **10.24** for **2048**
- **5.12** for **1024**
- **2.56** for **512**
- **1.28** for **256**

As example, number 5.12 will be used for jacket UV islands, and higher numbers will be used for small objects islands like buttons, pockets, chains on that jacket. That way quality of small details will be increased and as result whole model will look clean.

By default RizomUV Texel Density is 10.24 and texture size is 2048. This is a good start if you wish to create 2048x2048 textures for your model.

For Decentraland, it's recommended to use only 1024 or 512 textures. Most of creators use 1024. There are no reasons to use higher textures, because Decentraland client downscale all textures higher than 1024, sometimes even 1024 is downscaled to 512. Also higher textures affect on client optimization, fps, and scene loading times.

One more note about dimensions. If you made small object, with right texel density and right texture size. Keep in mind, that if you need, you can decrease object size when you build scene. But, you can't increase object size without loss in quality. If you made a small soda can, made all UVs and final textures, and then decide to make it very big in scene, model will look blurry because there are not enough texel density on UV. In that case, you will need to do new UV with right texel density and then redo textures.

### Margin and Padding 
**Margin** - UV islands distance from corners of UV square. 

Here is a minimal margin numbers for each texture size.
- **8** for **2048**
- **4** for **1024**
- **2** for **512**
- **1-2** for **256** (0 not recommended)

It's very important to use this setting, to avoid any UV overlapping issues in game engine. 

As we will create only 1024 textures, it's recommended to use margin 4.


**Padding** - distance between each UV island. This is very important thing that you should always keep in mind. Padding strongly connected with Mip Maps. Here you can learn more about [Padding](http://wiki.polycount.com/wiki/Edge_padding) and [Mip Mapping](http://wiki.polycount.com/wiki/Mip_mapping)

Here is a minimal padding numbers for each texture size.

- **16** for **2048**
- **8** for **1024**
- **4** for **512**
- **2** for **256**

It's very important to use this setting, to avoid any UV overlapping issues in game engine. 

As we will create only 1024 textures, it's recommended to use padding 8.



### UV Packing Settings 
It's strongly recommended to manually set Texel Density for each UV island and manually pack each island in UV square. But, if you wish to achieve fast result, you can use tools for UV auto packing.

Here is settings that's required for manual packing:

Texture Type to should be **Checker**. With checker you will be able to visually determine if UVs unwrapped well and texel density is good for all parts.

[[/images/rizom_checker.png]]

It's recommended to turn off all **scale optimization** settings in **packing properties** tab, if you will do packing manually.

[[/images/packing_properties.png]]

For automatic packing, you can keep default settings, but keep in mind, that texel scaling optimization will change texel density numbers for all UV islands.

When you will do manual packing, you will use distribute space setting lots of times. It's recommended to change space number according to number of padding. Change from available to pixel and set number to 8.

[[/images/distribute_space.png]]

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

### UI Setup
You can keep default UI if needed. But for advanced documentation pipelines it's better to use UI from video, it's more flexible, less complex, requires less clicks between tabs, and covers less space on screen.

*UI Setup*

[[spp_ui_setup.mp4]]

If you messed up with UI, you can always reset it in **Window** tab.

[[/images/spp_reset_ui.png]]

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

Make sure to set **Base color** bits to **RGB16** on channels in general properties tab, otherwise textures will be exported in 8 bits, even if setting in export textures window set to 16.

*Base Color RGB16*

[[/images/channels_bits.png]]

You will need to export only **Base Color** maps which will be used in all pipelines. It's not recommended to use other maps in Decentraland, because they don't work as they should. You may try to experiment with Normal, Metallic and Roughness maps, but all this maps require a lot of manual adjustments for clear results.

You can select only **Base Color** maps on each material in Global Settings window

After you will click export, you will see window with process of exporting. As soon as export is finished you can click **"Open output directory"** to see folder with your maps.

*Export Settings*

[[/images/export_templates.png]]

*Required Maps*

[[/images/global_settings.png]]

*Finished Export*

[[/images/exported_assets.png]]

### Custom Templates
In **Export textures** window, go to **output templates** tab. Here you can create your export textures template.

To create **Base Color** only template, you will need to duplicate **PBR Metallic Roughness** template and delete all output maps except BaseColor. Since we will use UDIMs in process of creating models, in some cases, you will need to remove dot in (.$udim) name. If you will keep dot, Blender will determine all UDIMs as UDIMs and later that may cause some issues on export. It's not very important thing and usually works fine, but if needed, just remove dot.

*Custom Templates Example*

[[custom_templates.mp4]]

Actually, it's better to use default **Document channels + Normal + AO (No Alpha)**, but if you want something special, you can always create custom template.

# Adobe Photoshop
wip import export
# Stable Diffusion (AUTOMATIC1111)
### Required Models
**Automatic1111** works well on latest GPU cards, however, if your pc don't match latest specs, you still can use this tool with very low settings and achieve good results. If that's impossible for you, then you can try alternatives from web. But they're not flexible as Stable Diffusion and might be expensive.

The most important tool that you will need is **ControlNet** (Canny, IP-Adapter), **LORA**, and any **model** (anime or realistic) that you want from [here](https://civitai.com/). In pipelines you will need to use [ManmaruMix v3.0](https://civitai.com/models/86277/manmaru-mix) model, but you can experiment with any model you want. We won't use SDXL models in pipelines. You will need to put files in "sd.webui\webui\models\stable-diffusion" folder.

**LORA** - small model file that was created from 5-15 reference images. It's used as part of positive prompt. With it you can generate any characters from anime, or any persona in any style that you want, for example - realistic. You can also do enhancement to your images, like adding details. It's also very simple to train your own lora and requires small amount of time.

One of additional **LORA** models that you will need is [Detail Tweaker LoRA](https://civitai.com/models/58390/detail-tweaker-lora-lora), this one seems to be best at adding details for generated images. You will need to put files in "sd.webui\webui\models\lora"

To install **ControlNet** you will need to download it from [here](https://github.com/Mikubill/sd-webui-controlnet) and follow installation [guide](https://github.com/Mikubill/sd-webui-controlnet#installation).

Download ControlNet **Canny** optimized model from [here](https://huggingface.co/webui/ControlNet-modules-safetensors/tree/main) (control_canny-fp16.safetensors) and put it in ControlNet models folder. If you want to get original models, you can get them from [here](https://huggingface.co/lllyasviel/ControlNet-v1-1/tree/main), you will need to download only .pth files and put them in ControlNet models folder. You can learn more about it [here](https://github.com/Mikubill/sd-webui-controlnet#download-models)

Download ControlNet **IP-Adapter** model from [here](https://huggingface.co/h94/IP-Adapter/tree/main/models) (ip-adapter-plus_sd15.safetensors) and put it in ControlNet models folder. You will use IP-Adapter to mimic style of any picture from internet, and generate new images in that style. This model saves a lot of time on writing prompts, and can generate results with unique and unusual things (like clothes) just in one click, according to reference image and mixing it.

To achieve better results at image generations, you will need to download few textual inversions and put them in "sd.webui\webui\embeddings". This inversions will save you time on writing negative prompts, and will solve issues with low image quality results.
- [badhandv4](https://civitai.com/models/16993/badhandv4-animeillustdiffusion)
- [EasyNegative](https://civitai.com/models/7808?modelVersionId=9208)
- [veryBadImageNegative_v1.3](https://civitai.com/models/11772?modelVersionId=25820)

Additionally, you will need to download VAE model, to achieve images with clean color. For different models, different VAEs. For ManmaruMix model, [this](https://huggingface.co/stabilityai/sd-vae-ft-mse-original/tree/main) VAE fits very well. Download and put it in "sd.webui\webui\models\VAE"

Once everything is installed and downloaded, you can generate your first image. Here is a basic settings and prompts setup to achieve even result.

*Prompt and Settings*

[[/images/stable_diffusion.png]]

If you want to achieve exact same image, you will need to copy all settings and press generate. If result is different, you can write this number 2803890072 in seed option and that way you will generate exact same image. 

If your pc have low specs, it's recommended to generate images only with 768x768, 512x512 or less resolution, higher resolutions like 1024x1024 will crash with out of memory error. 
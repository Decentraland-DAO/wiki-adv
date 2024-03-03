List of recommended settings for tools, this settings will speed-up process of creating models, and will make UI of some tools more user-friendly.

# Blender
### Navigation Settings 
On first start-up after installation, keep navigation and hotkey settings by default. It's not recommended to switch them to Maya or anything else. There will be issues with hotkeys on modes like "Weight Painting". 

### Viewport Denoising and Color Management
Viewport Denoising setting reduce noise and smooth character animation preview in viewport. It's sounds as good feature, but on practice it adds more noise, than denoise. It's highly recommended to turn off this setting, to achieve clear and smooth animation results, that will look exactly like in game engine. 

*Visual Comparison*



Color Management is another Blender setting that manages colors inside Blender viewport. By default View Transform setting, located in Color Management tab is set to Filmic or anything else, but not Standard. As result, this setting cause any textures, look a bit different, than they look in Substance Painter or in game engine. It's highly recommended to change View Transform setting from Filmic to Standard. Standard setting will display textures right way.

*Visual Comparison*

[[/images/color_management.png]]

*Settings Location*

[[/images/render_properties.png]]

### Frame Rate
By default Blender Frame Rate is 24, which is industry standard for movies. It's highly recommended to change Frame Rate to 30, which is standard for games and this setting is important for creating game-ready character animations. 

*Settings Location*

[[/images/frame_rate.png]]

### Face Orientation
Face Orientation display orientation of face normals. This setting allow creators to detect all inverted normals on a model. it's highly recommended to keep this setting always on. 

By default, when you turn on Face Orientation setting, "right" normals on model shown as blue color, and "wrong" inverted normals as red color, which cause creators to turn this setting on and off time from time to check if everything is good. 

With right settings in Blender preferences, you can hide display of "right" normals and keep display only "wrong" normals. That way you're able to keep Face Orientation setting always on by default and always see what's right and what's wrong without need to always turn this setting on and off. 

*Visual Comparison*

[[/images/face_orientation_preview.png]]

*Settings Location*

[[/images/face_orientation.png]]

[[/images/face_orientation_preferences.png]]
 


### Workspace, UI, and Set Settings as Default
It's recommended to move Blender outliner from right side to left side of window, that way UI will be more friendly and will look like basic windows "explorer", and will be familiar to navigation in other tools like Maya, Marmoset, and rest. This setup saves huge amount of time on work and reduce amount of mouse clicks between tabs and windows.

Additionally, we will add small UV editor window on left side, which we will use for fast access to UV. 

For animations it's useful to keep two timelines, default one, but closed. For frame range setup, record and play buttons. Second one we will use for work - Dope Sheet with actions. 


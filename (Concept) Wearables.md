In this article you will learn pipeline for generating reference wearables images  with **Stable Diffusion**.

To follow this article, make sure to install Stable Diffusion. download all needed models, and use base generation settings from here [[Software Settings]].

*Generation Settings*

[[/images/stable_diffusion.png]]

Use [Pinterest](https://pinterest.com/) for ideas and references.

You can learn prompts writing workflow [here](https://education.civitai.com/civitais-prompt-crafting-guide-part-1-basics/)
# Option 1. Generating images with prompts
Generate images with prompts, textual inversion and LORA.

In most cases you will need to use this words to generate image of character in any type of clothes. Make sure to write this words in exact same order. Influence of words in prompt lowers according to order.

## Positive Prompt Structure

- extreme quality (optional)
- 1boy or 1girl (character type)
- fullbody (character on image will be generated in full length)
- stand pose (optional)
- clothes (for example: cap, hoodie, joggers)
- concept sheet (optional, draws the same character in front, back, side view)
- white background (removes any background details and draws only character in most cases)
- look at camera (optional, character will look at us in most cases)

To achieve better result in details, use lora **detail tweaker** mentioned in [[Software Settings]].
- <<lora:add_detail:1>> or <<lora:add_detail:0.75>> or less/higher

## Negative Prompt Structure

Usually you will need to use only **textual inversions** mentioned in [[Software Settings]]. By using them, you will save a lot of time and will never write negative prompts except unusual situations.

- badhandv4 
- easynegative 
- verybadimagenegative_v1.3

Here is few basic words that you can use, if you don't want to use textual inversions.
- bad quality
- low quality
- worst quality
- ugly hands
- ugly face

If you're looking for more negative or positive prompts you can copy them from images on [civitai](https://civitai.com/images)

You can also **change any word influence** in prompt by adding word inside () and setting number of influence, **example: (white background:1.5)**

### prompt example with concept sheet word

**positive:** 1girl, fullbody, stand pose, cap, hoodie, joggers, concept sheet, white background, look at camera, <<lora:add_detail:0.8>>

**negative:** badhandv4 easynegative verybadimagenegative_v1.3

*Result, Seed: 3912979637*

[[/images/prompt_example01.png]]

### prompt example without concept sheet word

**positive:** 1girl, fullbody, stand pose, cap, hoodie, joggers, white background, look at camera, <<lora:add_detail:0.8>>

**negative:** badhandv4 easynegative verybadimagenegative_v1.3

*Result, Seed: 1304235324*

[[/images/prompt_example02.png]]

### prompt example copied from civitai

**positive:** a 1980s pop art style portrait of Marylin Monroe, punk, pop art, stylized, bold colors, photo and illustration hybrid

**negative:**  badhandv4 easynegative verybadimagenegative_v1.3

*Result, Seed: 466431685*

[[/images/prompt_example03.png]]

### prompt mix example

**positive:** 1girl, fullbody, stand pose, look at camera, concept sheet, a 1980s pop art style portrait of Marylin Monroe, punk, pop art, stylized, bold colors, photo and illustration hybrid,  white background, <<lora:add_detail:0.8>>

**negative:**  badhandv4 easynegative verybadimagenegative_v1.3

*Result, Seed: 4233230048*

[[/images/prompt_example04.png]]


# Option 2. Generating images with IP-Adapter
Generate images with **IP-Adapter** and reference images from **Pinterest**. **IP-Adapter** option generates images in style that you want. With additional prompts you will be to achieve interesting and inspiration results. 

This method works in-pair with prompts and other settings from **Option 1**. 

Enable **ControlNet** and select **IP-Adapter**. 

Make sure that **preprocessor** set to **ip-adapter-clip_sd15** and **model** to **ip-adapter-plus_sd15**.

After that, select any image that you want to use as reference. 

[[/images/ip-adapter01.png]]

It's recommended to use square type images. But if your image is different, you can play with **resize mode** setting to achieve different results. 

It's very important to play with **Control Weight** and **Ending Control Step** settings. If you want to achieve very close result to reference image, **set Control Weight to 0.6 - 0.8**. If you notice that influence of image is too high, you can play with lower numbers **0.3 - 0.4**. This is recommended numbers, but, usually, numbers depends from image that used as reference. **Ending Control Step** is rarely used, but might be helpful too, you can play with this numbers of this setting too.

## Example with IP-Adapter and prompt 

**positive:** 1girl, fullbody, stand pose, cap, hoodie, joggers, (white background:1.5), look at camera, <<lora:add_detail:0.8>>

**negative:** badhandv4 easynegative verybadimagenegative_v1.3

*Reference image*

[[/images/ip-adapter02.png]]

*Result* (Control Weight 0.6)

[[/images/ip-adapter03.png]]

*Result* (Control Weight 0.4)

[[/images/ip-adapter04.png]]

## Example with IP-Adapter and empty prompt 

**positive:** <<lora:add_detail:0.8>>

**negative:** badhandv4 easynegative verybadimagenegative_v1.3

*Result* (Control Weight 0.6)

[[/images/ip-adapter05.png]]

As you may see, generated images have almost same style and details. Even without prompts. This is very useful for generating concepts from inspiration references and achieve **random** (without prompts and small control weight) or  **restricted** (with prompts and medium-high control weight) results.

# Enhancing with Hires. Fix
As you may see results in **Option 1**  and **Option 2** methods, both of them lacks of quality and looks very blurry. To fix that, you will need to use **Hires. Fix** option. 

As soon as you generated image that you like, **set image seed** with **green arrows button**

[[/images/prompt_hires01.png]]

Now **enable Hires. Fix** option, set upscaler to **R-ESRGAN 4x+ Anime6B** (best upscaler for anime stable diffusion models) and **Denoising Strength** to **0,45** or less. If you want to achieve more random results, you can play with denoising strength numbers. Higher numbers might change source image completely.

Keep **upscale by** setting on **2**, higher numbers may give out of memory error, depends on your pc. 

Now you can press **Generate** button to get final **1024x1024** image. 

[[/images/prompt_hires02.png]]


*Result without Hires. Fix*

[[/images/prompt_example04.png]]

*Result with Hires. Fix*

[[/images/prompt_hires03.png]]

This is recommended image generation way for users with **low-end pc**. If you use **high-end pc**, you can generate images with always enabled **Hires. Fix**.

# Final Result

Follow this video with generation process for better understanding of workflow. 
Image reference result from this video will be used in next modeling steps.

*Generation process*

[[concept_wearables.mp4]]

*Reference image*

[[/images/ip-adapter07.png]]

*Result*

[[/images/ip-adapter06.png]]


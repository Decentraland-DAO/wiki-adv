In this article you will learn pipeline for generating reference wearables images  with **Stable Diffusion**.

To follow this article, make sure to install Stable Diffusion. download all needed models, and use base generation settings from here [[Software Settings]].

*Generation Settings*

[[/images/stable_diffusion.png]]

Use [Pinterest](https://pinterest.com/) for ideas and references.

You can learn prompt writing basics [here](https://education.civitai.com/civitais-prompt-crafting-guide-part-1-basics/)
### Option 1. Generating images with prompt
Generate images with prompts, textual inversion and LORA.

In most cases you will need to use this words to generate image of character in any type of clothes. Make sure to write this words in exact same order. Influence of words in prompt lowers according to order.

**Positive Prompt Structure**

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

**Negative Prompt Structure**

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

**prompt example with concept sheet word:** 

**positive:** 1girl, fullbody, stand pose, cap, hoodie, joggers, concept sheet, white background, look at camera, <<lora:add_detail:0.8>>

**negative:** badhandv4 easynegative verybadimagenegative_v1.3

*Result, Seed: 3912979637*

[[/images/prompt_example01.png]]

**prompt example without concept sheet word:** 

**positive:** 1girl, fullbody, stand pose, cap, hoodie, joggers, white background, look at camera, <<lora:add_detail:0.8>>

**negative:** badhandv4 easynegative verybadimagenegative_v1.3

*Result, Seed: 1304235324*

[[/images/prompt_example02.png]]

**prompt example copied from civitai:**

**positive:** a 1980s pop art style portrait of Marylin Monroe, punk, pop art, stylized, bold colors, photo and illustration hybrid

**negative:**  badhandv4 easynegative verybadimagenegative_v1.3

*Result, Seed: 466431685*

[[/images/prompt_example03.png]]

**prompt mix example:**

**positive:** 1girl, fullbody, stand pose, look at camera, concept sheet, a 1980s pop art style portrait of Marylin Monroe, punk, pop art, stylized, bold colors, photo and illustration hybrid,  white background, <<lora:add_detail:0.8>>

**negative:**  badhandv4 easynegative verybadimagenegative_v1.3

*Result, Seed: 4233230048*

[[/images/prompt_example04.png]]


### Option 2. Generating images with IPAdapter
Generate images in combination of **IPAdapter** and reference images from **Pinterest**, this option generates images in style that you want, copy and adapt details from image, and doesn't require writing thousands of words in prompt.

### Enhancing with Hires. Fix
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

This is recommended image generation way for users with **low-end pc**. If you use **high-end pc** , you can generate images with always enabled **Hires. Fix**.
In this article you will learn how to generate reference images with **Stable Diffusion**.

To follow this article, make sure to install Stable Diffusion, download all necessary models, and use the base generation settings. You can find all the information in the [[Software Settings]].

*Generation Settings*

[[/images/stable_diffusion.png]]

For ideas and references dive in [Pinterest](https://pinterest.com/) 
You can learn more information about writing prompts [here](https://education.civitai.com/civitais-prompt-crafting-guide-part-1-basics/)
# Generating with Prompts 
With this method, you can generate images using prompts, textual inversions, and LORA.
One important thing to keep in mind is that the influence of words in prompts decreases according to their order.

To generate images, follow the structures explained below. These structures are useful for generating character images
## Positive Prompt
That's the structure you should follow in most cases, with the exact same order, to generate characters in full length, neutral pose, and a white background.

- extreme quality (optional)
- 1boy or 1girl (character type)
- fullbody (character will be generated in full length)
- stand pose (optional)
- clothes (for example: cap, hoodie, joggers)
- concept sheet (optional, generates character in front, back, side view, works better with horizontal images)
- white background (generates images with white background)
- look at camera (optional, generates characters that look at camera)

To achieve better results in details, use the **detail tweaker** lora mentioned in [[Software Settings]].

- <<lora:add_detail:1>> or <<lora:add_detail:0.75>> or less/higher
## Negative Prompt
Usually, you will need to use **textual inversions** mentioned in the [[Software Settings]]. By using them, you will save a lot of time and will write less negative prompts.

- badhandv4 
- easynegative 
- verybadimagenegative_v1.3

Here are a few basic words that you can use if you don't want to use textual inversions.

- bad quality
- low quality
- worst quality
- ugly hands
- ugly face

If you're looking for more negative or positive prompts, you can copy them from images on [civitai](https://civitai.com/images)

You can also change the influence of words in the prompt by enclosing them in parentheses() and setting the number of influence. For example: **(white background: 1.5)**
## Generations 
Below, you can take a look at the generation results with different prompts.
### Result (With Concept Sheet)

**positive:** 1girl, fullbody, stand pose, cap, hoodie, joggers, concept sheet, white background, look at camera, <<lora:add_detail:0.8>>

**negative:** badhandv4 easynegative verybadimagenegative_v1.3

*Result, Seed: 3912979637*

[[/images/prompt_example01.png]]

### Result (Without Concept Sheet)

**positive:** 1girl, fullbody, stand pose, cap, hoodie, joggers, white background, look at camera, <<lora:add_detail:0.8>>

**negative:** badhandv4 easynegative verybadimagenegative_v1.3

*Result, Seed: 1304235324*

[[/images/prompt_example02.png]]

### Result (Prompt from Civitai)

**positive:** a 1980s pop art style portrait of Marylin Monroe, punk, pop art, stylized, bold colors, photo and illustration hybrid

**negative:**  badhandv4 easynegative verybadimagenegative_v1.3

*Result, Seed: 466431685*

[[/images/prompt_example03.png]]

### Result (Mix of Prompts)

**positive:** 1girl, fullbody, stand pose, look at camera, concept sheet, a 1980s pop art style portrait of Marylin Monroe, punk, pop art, stylized, bold colors, photo and illustration hybrid,  white background, <<lora:add_detail:0.8>>

**negative:**  badhandv4 easynegative verybadimagenegative_v1.3

*Result, Seed: 4233230048*

[[/images/prompt_example04.png]]

# Generating with IP-Adapter 
With **IP-Adapter**, you can generate images by copying style, shapes, and details from reference images.

This method is more user-friendly and a bit more flexible because you don't need to write a huge amount of words in your prompts to achieve expected results. At the same time, you can use additional words in your prompts to maintain style, but, for example, change clothes.

Enable **ControlNet** and select **IP-Adapter**. 

Make sure that **preprocessor** set to **ip-adapter-clip_sd15** and **model** to **ip-adapter-plus_sd15**.

After that, select any image that you want to use as a reference.

[[/images/ip-adapter01.png]]

It's very important to adjust the **Control Weight** and **Ending Control Step** settings. If you want to achieve a result very close to the reference image, set the Control Weight to **0.6 - 0.8**. If you notice that the influence of the image is too high, you can try lower numbers like **0.3 - 0.4**. These are recommended numbers, but usually, the numbers depend on the image used as a reference. The **Ending Control Step** is rarely used but may also be helpful; you can experiment with the numbers for this setting as well.

Keep in mind that for better generation results, you should work with higher vertical resolutions (**256x512, 512x768, 512x1024**), as these resolutions generate characters more effectively, with fewer anomalies and unnecessary objects, compared to square images.
## Generations
### Result (IP-Adapter + Prompt)

**positive:** 1girl, fullbody, stand pose, cap, hoodie, joggers, (white background:1.5), look at camera, <<lora:add_detail:0.8>>

**negative:** badhandv4 easynegative verybadimagenegative_v1.3

*Reference image*

[[/images/ip-adapter02.png]]

*Result (Control Weight 0.6)*

[[/images/ip-adapter03.png]]

*Result (Control Weight 0.4)*

[[/images/ip-adapter04.png]]

### Result (IP-Adapter + Empty Prompt)

**positive:** <<lora:add_detail:0.8>>

**negative:** badhandv4 easynegative verybadimagenegative_v1.3

*Result (Control Weight 0.6)*

[[/images/ip-adapter05.png]]

As you see, generated images have almost same style and details. Even without prompts. This is very useful for generating concepts from inspiration references and achieve **random** (without prompts and small control weight) or  **restricted** (with prompts and medium-high control weight) results.

# Upscaling with Hires. Fix
To complete your generated image and achieve best quality, you will need to use **Hires. Fix** upscaler. 

 Set image **seed** with **green arrows button**

[[/images/prompt_hires01.png]]

Now **turn on Hires. Fix** option, set upscaler to **R-ESRGAN 4x+ Anime6B** (best upscaler for anime stable diffusion models) and **Denoising Strength** to **0,45** or less. If you want to achieve more random results, you can play with denoising strength numbers. Higher numbers might change source image completely.

Keep **upscale by** setting on **2** or lower, higher numbers may give out of memory error, depends on your GPU. 

Now you can press **Generate** button to get final **1024x1024** image. 

[[/images/prompt_hires02.png]]


*Result without Hires. Fix*

[[/images/prompt_example04.png]]

*Result with Hires. Fix*

[[/images/prompt_hires03.png]]

This is recommended image generation way for users with **low-end pc**. If you use **high-end pc**, you can generate images with always enabled **Hires. Fix**.

# Result
Follow this video to understand the generation process better. The image reference result from this video will be used in the next modeling steps.

*Generation process*

[[concept_wearables.mp4]]

*Reference image*

[[/images/ip-adapter07.png]]

*Result*

[[/images/ip-adapter06.png]]

# Summary
Those are all the steps required for generating a character reference image with **Stable Diffusion**. By now, you should have a better understanding of how to use prompts effectively, how to write them properly, and how to utilize **IP-Adapter** and **Hires. Fix**. 

Remember to use these generation methods whenever you seek inspiration from images.

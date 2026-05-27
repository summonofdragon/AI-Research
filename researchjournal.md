# AI Research Journal

## Week [2] — [Not All Feelings Are the Same]

### This Week's Method
This week's method is applying comparative analysis. By the examples of detection over emotions with different models and values of detecting emotions, the same image/text is imputed and results were compared to find differences or similarities in the results. 

### How I Applied It
I applied the analysis by using different models and emotion categories to test a sample sentence. For example, I would choose AI spaces like [Binary Image](https://huggingface.co/spaces/profplate/image-binary) or [Feelings Image](https://huggingface.co/spaces/profplate/image-color-mood-analyzer) and upload some pictures of basic elements.

### What I Expected
I expect most AI to give similar "tones" with the results; for example, based on the color, object or phrasing sequence, they may decide what is "happy" or "sad". They couldn't identify it as in knowing it, but based on details they are able to tell most. However, there would be some difficulties especially in hidden messages, like sarcasm or such.

### What I Found
In basic pictures like my school's grassy areas in spring, the pictures were identified mostly as "Harmonious" or "Positive". When I switched to hand drawn figures with messier layout and deep colorings, though, the different systems refused to agree and one gave "Negative" whereas we also have a "Tranquil".

### Why I Think This Happened
My basic understanding is that they analyze over different training models and ways to identify; for example, the Binary model is based on what BLIP sees, so I assume it assigns things like tokens while trying to identify objects, and it certainly has difficulties in identifying cartoonish images. The other is based on color, and it is more reliable in such case; yet, when I assign weird colors, it appears to be different again.

### Limitations
Again, the testing limit here would be based on the amount of training and the idea of "hidden messages", so I find it useful to try and combine two models. However that is not within my range of abilities currently, so I would have to improve my skills; otherwise, the machine should focus on what it cannnot tell, or the problem itself is one built with the model.

### What I Want to Try Next
I want to try creating movements with models, but first I should still work on my skills. For example, I would try and fix small parameters within a space and try creating my own zero-shot AIs with a given template?


## Week [3]

### Update

Accepts a user-written prompt describing a cinematic world.
Uses a language model to generate a structured scene script.
Analyzes the script for emotional and environmental cues.
Converts those cues into visual parameters.
Renders a 15-second animated scene as an MP4 video.

The output consists of:

A generated cinematic script
A procedurally rendered animated scene featuring a tall solitary figure

Uses Models:
HuggingFaceTB/SmolLM2-360M-Instruct
distilgpt2

Problems:
Visuals often create problems, generating long blocks only to cope with "abstractness".
Often shows wrong output



## Week [4]

### Update

Tried to make image less abstract, didn't work.
Tried to file out problems.

## My Space 1

Name:AnimationwithMoods
URL: (https://huggingface.co/spaces/Silverwind101/AnimationwithMoods)

What it can do: Build basic text descriptions and draw simple shapes.

What I wanted it to do next: Split items into scenes interrelated to each other. Less abstract models

The Space is currently broken. The error is: Runtime + Coding error. 

My best guess about the cause: Code contains error on format (copied old code: failure. Could be fixed in 2nd space.)

The next fix I will try: Formatting formally and give the image more shape.

## Week [5]

### Update

Started 2nd space, and fixed the formatting problems. However, the code still did not work.

I asked AI for help, and it says the code contains a keyword-only identifying part. Fixed a little of that, but the API is still a cause for being unable to change the shapes. Unable to fix for now... 

I changed the project so the visual generation system no longer depends only on direct keyword matching. Originally, the program looked for exact words like “rain,” “fog,” or “anger” to determine the environment and mood of the scene. This was very limited because the AI could only react when those specific words appeared. I replaced this approach with a semantic analysis system using the transformer model facebook/bart-large-mnli through Hugging Face’s zero-shot classification pipeline.

I also expanded the rendering system so the environment changes more dynamically based on the script’s meaning. The updated code can now classify settings such as cities, forests, deserts, industrial areas, oceans, and mountains. Different moods like calm, mysterious, melancholic, or intense also affect the lighting and sky color palettes. Weather systems were improved with effects for rain, fog, and snow, while the background generation became more scene-specific instead of using the same generic structures every time.

## My Space 2

Name:MoodAnimation2
URL: (https://huggingface.co/spaces/Silverwind101/MoodAnimation2)

Seems like I have to fix the video part because it doesn't influence the idea at all and is a distraction for the code, as it takes a long run-time.

## Week [6]

### Update

For this project update, I transitioned the Cinematic World Engine from a procedural graphics system into a full AI-driven trailer generation pipeline. Previously, the system relied heavily on manually drawn shapes and keyword-based effects, which made the output repetitive and visually limited.

The new version of the system generates a structured trailer script using a small language model (such as SmolLM2-360M-Instruct or distilgpt2).The script is split into five distinct trailer beats (hook, introduction, rising tension, climax, and resolution). Each scene is then translated into a detailed image prompt that includes emotional tone, environment, and cinematic style. These prompts are sent to a free image generation API (Hugging Face Stable Diffusion XL), which produces real images instead of abstract shapes.

The generated images are assembled into a short video to create a trailer. While the system is still limited in areas like character consistency and smooth motion, it represents a major shift from procedural rendering to AI-assisted cinematic generation.


## Week [7]

### Update


System was significantly optimized to solve performance and issues that were present in the previous version. The earlier followed a multi-scene image generation pipeline, where each scene in the script triggered a separate scene. While this produced detailed and varied visuals, it also caused major slowdowns on Hugging Face Spaces, often leading to long execution times and timeouts due to repetition.

Redesigned around a single-image cinematic synthesis approach. Instead of generating multiple images per scene, the system now produces a structured 5-beat script using a lightweight language model, then the entire narrative is changed to a single coherent cinematic prompt. Emotional analysis is still included, but it is now used only to influence environmental tone descriptors (such as spatial openness, lighting behavior, and composition style). I disliked how it now affects the entire image, so I kept pushing it off.

The final process was simplified to one call, followed by frame repetition and synthetic camera motion to create movement. This change dramatically improved execution speed and eliminated previous timeout issues while preserving emotional and narrative depth. However, the code gets into bugs sometimes, and I'd have to fix it entirely.


## Week [8]

### Update

With CPU running problems, I had to remove the rendering part. No more video in mind, because now the code cannot even run properly. Earlier versions attempted to generate cinematic visuals and animated scenes, but these approaches caused long execution times, crashes, and unreliable outputs because image diffusion models required GPU acceleration. Now I'd focus on text only, which somehow didn't match the title anymore.

The updated system now functions as a mood-driven cinematic direction engine. Instead of generating placeholder templates or static visual slides, the AI expands prompts into trailer-like sequences with detailed environmental storytelling, pacing, sound design, camera direction, and lighting descriptions. A new mood system was added that strongly influences the writing style and atmosphere of each generated scene. 

The final implementation uses the HuggingFaceTB/SmolLM2-360M-Instruct language model through the Transformers pipeline and integrates randomized cinematic enhancement systems for camera framing, transitions, lighting, and sound design. I focused more on the seperate aspects for the system.

## Week [9]

### Update

Earlier versions of the system generated disconnected scenes where characters, environments, and story elements changed randomly between outputs. For example, a story about a dog could unexpectedly shift into human narration. To solve this issue, the architecture was modified so the AI generates scenes one at a time.

A major improvement added in this version was the mood-based cinematic writing system. Instead of simply generating neutral descriptions, the engine now uses emotional directives such as fear, dread, wonder, sadness, anger, and hope to influence the scenes. For example, fear-based scenes use confined environments, unstable movement, and tense sensory descriptions, while wonder-based scenes focus on scale, discovery, and atmospheric beauty.

Visual rendering systems and diffusion-based image generation were completely removed due to severe instability and performance limitations on CPU-only Hugging Face Spaces still since the problem remains unsolved. I have fully shifted the focus on the item, and for better purposed the models of distil gpt was changed into others such as Qwen, which provides better fluent descriptions without random interrupts.

The wall is now how to connect it and the runtime, which I probably may not solve.

## Week [10]

## My Space 3

Name:Final-Space_Scene-Creator
URL: (https://huggingface.co/spaces/Silverwind101/Final-Space_Scene-Creator)

What it can do: Generate sperate scenes to create a story board only on text.

What I wanted it to do next: Be faster?

Problem: I put some updates on the 2nd one. But it doesn't matter!

### Update

Runtime is slow as always, taking up to hundreds of seconds, but it was the best I could achieve.

Input example: 
A dog called Abby runs happily around its sweet home as it remembers its owner and how he used to play with it.


Processing Time: 500+ seconds

Output:
============================================================
SCENE 1
============================================================

**Scene Title: The Sweet Home**
*The screen opens onto an expansive backyard adorned in vibrant greenery.*
*A gentle breeze carries through the trees.*
*CUT TO*
ENVIRONMENT:
Backyard of Abby's Happy Haven - A cozy wooden fence surrounds her small cottage made entirely out of recycled materials; inside is filled with toys she loves playing with daily—kittens cuddling together under blankets while watching TV shows about their favorite cartoon characters (a catnip mouse chase).
ACTION:
Abby wags her tail energetically towards the open door where her human friend stands outside gazing lovingly at his pet.
*CAMERA:*
Wide shot capturing the entire family living room which has been transformed into a sanctuary for dogs by adding soft lighting fixtures that glow warmly without being harsh or glaring directly at anyone’s eyes.
*LIGHTING*:

CAMERA DIRECTION:
Wide establishing shot

LIGHTING STYLE:
dim indoor lighting

SOUND DESIGN:
faint room ambience

TRANSITION STYLE:
Slow fade.


============================================================
SCENE 2
============================================================

**Environment:**
The Backyard of Abby's Happy Haven
*Moonlight filters down gently over the lush garden.*
*Bright sunlight streams through gaps between leaves.*
**Action**:
Abby bounds across the grassy expanse, her joyful barks echoing softly against the backdrop of chirping birds. Her paws leave trails behind them, leaving tiny ripples in the dew-kissed soil.
**Camera Shot & Movement**:
Pan rightward along the length of the house, focusing on Abby running past several windowsills before reaching one particular window. She pauses momentarily beside this frame, then leaps up excitedly within seconds.
**Lighting Style**:
Soft ambient light filtering through large glass panes above the ground level area surrounding the backdoor leading into the main structure.
*SFX*:
Sound effects include subtle rustles of nearby plants moving slightly due to wind currents combined with

CAMERA DIRECTION:
Over-the-shoulder shot

LIGHTING STYLE:
cold morning light

SOUND DESIGN:
quiet footsteps

TRANSITION STYLE:
Soft dissolve.


============================================================
SCENE 3
============================================================

SCENE III
**Title:** **Moonlit Meadow**
Environment: The backyard of Abby’s Happy Haven
**Background Music**: Soft strains of nature sounds—birds singing quietly among tall trees that line the edge of the meadow; distant waves crashing at an ocean shore or gentle breezes blowing away golden wheat fields.
**Sunset Glow**: A warm amber hue slowly fades out while soft blue hues begin to fill the sky—a perfect twilight transition for capturing moments under moonlight.
#### Action:
Abby dashes joyfully towards the open doorway where she has been watching eagerly since dawn ended yesterday evening. As if sensing his return, she stops just outside the threshold, looking directly inside the room filled with familiar sights—the living room furniture still arranged exactly like they were when last seen together earlier today.
Her eyes sparkle mischievously as though daring him by being there first after

CAMERA DIRECTION:
Slow push-in shot

LIGHTING STYLE:
rain-soaked reflections

SOUND DESIGN:
quiet mechanical noise

TRANSITION STYLE:
Linger before cutting.


============================================================
SCENE 4
============================================================

SCENE IV
**Title:** **Echoes in Twilight**
The camera pulls back slightly into the cozy interior of the cottage's kitchen window frame. Moonlight filters through cracks between wooden panels, casting long shadows across bare shelves lined with books and decorative items.
In one corner stands Abby, her tail wagging gently against the cool wood floorboards beneath her paws. Her brown fur gleams softly, reflecting the silver glow emanating from within. She looks up expectantly, nose twitching toward something unseen but unmistakably dear.
Suddenly, footsteps echo faintly down the hallway leading to their bedroom door. They stop abruptly behind Abby, who turns sharply to face them fully once more. This time, however, instead of returning shyly, her expression is now full of determination mixed with unshed tears.
“Daddy?” whispers Abby hoarsely, breaking free of whatever hold


(note: over here is broken. possible fix)
CAMERA DIRECTION:
Low-angle medium shot

LIGHTING STYLE:
soft fog diffusion

SOUND DESIGN:
soft rain

TRANSITION STYLE:
Abrupt cut.


============================================================
SCENE 5
============================================================

**Scene V**
**Environment:**
As dawn breaks over the horizon outside the small farmhouse where they live together—pastures stretching endlessly beyond golden fields; birdsong fills the air like an old melody being played by nature itself—a gentle breeze carries fresh scents that seem almost magical after weeks spent inside darkened rooms filled mostly with silence.
*Action:*
Abby bounds out onto the porch steps, each step landing lightly upon soft grass carpeted underfoot. The sun begins creeping above the treetops at just this moment, painting everything amber before slowly transitioning towards orange hues climbing higher skyward.
*Suddenly,* she stops short mid-step near the front doorway. Eyes wide open yet still fixed firmly forward gaze directed straight ahead despite having paused momentarily there for what feels longer than mere seconds until...
*A sudden noise.* A rustling sound coming closer... Then—
She whimpers low-p

CAMERA DIRECTION:
Low-angle medium shot

LIGHTING STYLE:
rain-soaked reflections

SOUND DESIGN:
distant wind

TRANSITION STYLE:
Hard cut.


Note: the theme here seems slightly different, but it did a good job on narrating.

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

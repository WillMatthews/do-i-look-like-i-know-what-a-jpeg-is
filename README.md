## What?
I'm sure we are all familiar with JPEG loss, it makes images look absolutely shit and I love it.

JPEG encodes images by splitting the image into 8x8 pixel blocks, and compressing each block.
Compression happens through determining the weights of factors in a 2D-DCT matrix, and then pruning non-important ones.

We can see 8x8 pixel blocks in this image, and how they contain relatively few frequency components:
![image](https://github.com/user-attachments/assets/f3f82aaa-16f1-4a6d-ac32-20687fcb6bd5)

In the modern age, people copy and paste images a lot, sometimes cropping / editing them in between.
I want the answer the question - what does this mean for JPEG?

My initial thoughts were that if an image is shifted and re-encoded, all hell will break loose - we have a discontinuity
between pixels, which will add frequency terms that are not present in the image beforehand.
To test this hypothesis I made this repo.

## Why?
## How?
I've drawn up a plan.

### The Plan:

1. For each q \in 1..step..100 (q being the kpeg quality): 
    1. Encode the image as a JPEG with quality q
    2. For each n \in 1..k (k being jpeg block size): (do for x and y shifts)
        1. Measure information loss as a function of shift and how compressed an image is (for all qualities possible)

2. Determine trends in infromation loss as a function of pre-shift compression factor and shift itself.
3. ???
4. Profit! (Sigbovik paper?)


## How far I've gotten
I've got the data (the notebook will generate it, it just needs a hot minute to do so).
I just need to figure out how to nicely plot it, as it's a 5D dataset (pre-shift quality, 2xshift dimension, post-shift quality, loss).


# The Plan

1. Encode a jpeg
2. Measure information loss
3. For each q \in 1..step..100 (q being the kpeg quality): 
    1. Encode the image as a JPEG with quality q
    2. For each n \in 1..k (k being jpeg block size): (do for x and y shifts)
        1. Measure information loss as a function of shift and how compressed an image is (for all qualities possible)

4. Determine trends in infromation loss as a function of pre-shift compression factor and shift itself.
5. ???
6. Profit! (Sigbovik paper?)


## How far I've gotten
I've got the data (the notebook will generate it, it just needs a hot minute to do so).
I just need to figure out how to nicely plot it, as it's a 5D dataset (pre-shift quality, 2xshift dimension, post-shift quality, loss).

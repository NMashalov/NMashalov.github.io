---
layout: post
title: 3dModels
---

Types:
- inpainting
- strokes


## Style2Paints

Popular tool for colorisation of line art
https://lllyasviel.github.io/Style2PaintsResearch/


Despite v4 version used classical methods, v5 now use stable diffusion for colorization.

## Tracking 

https://ttwong12.github.io/papers/toontrack/toontrack.html


## Sceletionization

https://lllyasviel.github.io/DanbooRegion/paper/paper.pdf
```python
from tricks import *
from skimage.morphology import skeletonize, dilation

def get_skeleton(region_map):
    Xp = np.pad(region_map, [[0, 1], [0, 0], [0, 0]], 'symmetric').astype(np.float32)
    Yp = np.pad(region_map, [[0, 0], [0, 1], [0, 0]], 'symmetric').astype(np.float32)
    X = np.sum((Xp[1:, :, :] - Xp[:-1, :, :]) ** 2.0, axis=2) ** 0.5
    Y = np.sum((Yp[:, 1:, :] - Yp[:, :-1, :]) ** 2.0, axis=2) ** 0.5
    edge = np.zeros_like(region_map)[:, :, 0]
    edge[X > 0] = 255
    edge[Y > 0] = 255
    edge[0, :] = 255
    edge[-1, :] = 255
    edge[:, 0] = 255
    edge[:, -1] = 255
    skeleton = 1.0 - dilation(edge.astype(np.float32) / 255.0)
    skeleton = skeletonize(skeleton)
    skeleton = (skeleton * 255.0).clip(0, 255).astype(np.uint8)
    field = np.random.uniform(low=0.0, high=255.0, size=edge.shape).clip(0, 255).astype(np.uint8)
    field[skeleton > 0] = 255
    field[edge > 0] = 0
    filter = np.array([
        [0, 1, 0],
        [1, 1, 1],
        [0, 1, 0]],
        dtype=np.float32) / 5.0
    height = np.random.uniform(low=0.0, high=255.0, size=field.shape).astype(np.float32)
    for _ in range(512):
        height = cv2.filter2D(height, cv2.CV_32F, filter)
        height[skeleton > 0] = 255.0
        height[edge > 0] = 0.0
    return height.clip(0, 255).astype(np.uint8)


if __name__=='__main__':
    import sys
    region_map = cv2.imread(sys.argv[1])
    cv2.imshow('vis', get_skeleton(region_map))
    cv2.waitKey(0)
```
## Datasets

Main source of dataset is Danbooru provided by [Gwern](https://gwern.net/).,

Dataset preparation:

https://github.com/lllyasviel/DanbooRegion/tree/master?tab=readme-ov-file


https://gwern.net/doc/ai/anime/danbooru/2023-kim.pdf
https://lllyasviel.github.io/SplitFilling/


## Edgar Simo-Serra
Collections of work on morphological coloring of pictures.
https://esslab.jp/


Start from scetch infilling

- Scetch Simplification 
- Mastering Sketching https://arxiv.org/pdf/1703.08966.pdf

Dataset

| ![drawing.jpg](/assets/img/posts/drawing/Simo-Serra/drawing.png) | 
|:--:| 
| *Sketch Simplification* |




## Notable work
https://github.com/moellenh/flatgan
https://dl.acm.org/doi/10.1145/3581783.3613788

https://github.com/houseofsecrets/SdPaint
Skeletonize



https://github.com/ermongroup/SDEdit
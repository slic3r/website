---
title: "Tip: handling large models"
date: 2013-05-05
author: Alessandro Ranellucci
---

Let's see some things you can do to avoid problems or even crashes when trying to print large, detailed, heavy models. Detailed models contain a lot of vertices and Slic3r will use more memory to handle them; sometimes such needed memory is more than your physical system memory.

**First off, make sure you're using Slic3r 0.9.10 or newer**, as their memory usage was reduced enormously.

The first thing you can to is to **reduce the number of vertices/facts** in your model: if your file has more than 300k facets, it's very likely way more detailed than you can achieve using your printer. You can then use Meshlab to perform such simplification: it's a very easy task, just [follow this tutorial](http://www.shapeways.com/tutorials/polygon_reduction_with_meshlab).

The next thing you can do is to **use the resolution option** in Slic3r: it will perform a simplification on the XY plane after the model is sliced. You can set the resolution option to a value like 0.01mm. If you leave resolution to zero, no simplification will happen in Slic3r and the output G-code will reflect the full resolution of the original model.

Finally, you can **reduce the number of threads**. Due to the way Slic3r is currently written, each threads will reserve its memory space and duplicate most of the geometric data. This means that using 4 threads will reduce the processing time but will use about 4x the memory. You might want to revert to a single thread for very memory-consuming models.

Of course each Slic3r version includes optimizations and things will improve on this side, so expect these hints to be less needed in the future.

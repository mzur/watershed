# Watershed

A simple (but not very fast) Python implementation of [Determining watersheds in digital pictures via flooding simulations](http://dx.doi.org/10.1117/12.24211).

![source image](ex.png) ![labelled image](ws.png)

In contrast to [`skimage.morphology.watershed`](http://scikit-image.org/docs/dev/api/skimage.morphology.html#skimage.morphology.watershed) and [`cv2.watershed`](https://opencv-python-tutroals.readthedocs.io/en/latest/py_tutorials/py_imgproc/py_watershed/py_watershed.html) this implementation does not use marker seeds.

## Usage

```python
import numpy as np
from Watershed import Watershed
from PIL import Image
import matplotlib.pyplot as plt

w = Watershed()
image = np.array(Image.open('ex.png'))
labels = w.apply(image)
plt.imshow(labels, cmap='Paired', interpolation='nearest')
plt.show()
```

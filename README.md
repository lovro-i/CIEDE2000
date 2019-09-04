# Python CIEDE2000  
**Python implementation of the CIEDE2000 color difference algorithm**

A Python function for calculating how similar two colors are, based on the paper [The CIEDE2000 Color-Difference Formula: Implementation Notes, Supplementary Test Data, and Mathematical Observations](http://www.ece.rochester.edu/~gsharma/ciede2000/), by Gaurav Sharma, Wencheng Wu, and Edul N. Dalal.

### Usage

```
from ciede2000 import CIEDE2000

print(CIEDE2000((50, 2.6772, -79.7751), (50, 0.0000, -82.7485)))
print(CIEDE2000((50, 0, 0), (50.0000, -1, 2)))
print(CIEDE2000((50, 2.5, 0), (73, 25, -18)))
```

In order to use the function, you must first transform the colors into CIE L\*a\*b\* color space. That can be done using OpenCV, for example. Here's how to convert the whole image (and then you can pick colors from it):

```
import cv2

image = cv2.imread("./some_image.jpeg")
image = np.float32(image)
image *= 1./255
Lab = cv2.cvtColor(image, cv2.COLOR_BGR2Lab)
L, a, b = cv2.split(Lab)
```

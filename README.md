# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the required libraries.

### Step2
Read the image by using imread().

### Step3
Apply the required filters for the image separately.

### Step4
Plot the original and filtered image by using matplotlib.pyplot.

### Step5
End the program.

## Program:
### Developed By   : Aadhithya.M
### Register Number: 212222100001

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("avimage.jpg")
img1 = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
kernal = np.ones((11,11),np.float32)/121
img2 = cv2.filter2D(img1,-1,kernal)

plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(img1)
plt.title('original')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(img2)
plt.title('Filtered')
plt.axis('off')
```
ii) Using Weighted Averaging Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("avimage.jpg")
img1 = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
kernal2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
img2 = cv2.filter2D(img1,-1,kernal2)

plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(img1)
plt.title('original')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(img2)
plt.title('Filtered')
plt.axis('off')
```
iii) Using Gaussian Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("avimage.jpg")
img1 = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
gaussian_blur =  cv2.GaussianBlur(src=img1,ksize=(11,11),sigmaX=0,sigmaY=0)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(img1)
plt.title('original')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title('Filtered')
plt.axis('off')
```

iv) Using Median Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("avimage.jpg")
img1 = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
median = cv2.medianBlur(src=img1,ksize=11)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(img1)
plt.title('original')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(median)
plt.title('Filtered')
plt.axis('off')
```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("avimage.jpg")
img1 = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
kernal3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
img3 = cv2.filter2D(img1,-1,kernal3)

plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(img1)
plt.title('original')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(img3)
plt.title('Filtered')
plt.axis('off')
```
ii) Using Laplacian Operator
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("avimage.jpg")
img1 = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
kernal3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
img3 = cv2.filter2D(img1,-1,kernal3)
new_img = cv2.Laplacian(img1,cv2.CV_64F)

plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(img1)
plt.title('original')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(new_img)
plt.title('Filtered')
plt.axis('off')
```

## OUTPUT:
### 1. Smoothing Filters
</br>

i) Using Averaging Filter
![image](https://github.com/Abburehan/Implementation-of-filter/assets/138849336/f4354279-0695-4a70-91d9-eadfa2ec675c)


ii) Using Weighted Averaging Filter
![image](https://github.com/Abburehan/Implementation-of-filter/assets/138849336/2797719f-c03f-4b7e-bbf8-5d7836588e82)


iii) Using Gaussian Filter
![image](https://github.com/Abburehan/Implementation-of-filter/assets/138849336/abaa1115-4b55-4f66-b686-746f91f047c8)


iv) Using Median Filter
![image](https://github.com/Abburehan/Implementation-of-filter/assets/138849336/785a67a6-c36b-4d2f-9af2-7c1c2d341f3c)


### 2. Sharpening Filters
i) Using Laplacian Kernal
![image](https://github.com/Abburehan/Implementation-of-filter/assets/138849336/594c8ed0-0eb7-4cdc-8b32-703627134227)


ii) Using Laplacian Operator
![image](https://github.com/Abburehan/Implementation-of-filter/assets/138849336/1ff876a3-cc38-494c-833f-8808d718f2c5)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.

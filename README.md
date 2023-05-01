# <p align="center">Thresholding of Images</p>
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step 1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale.

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image.

### Step 6:
Display the results.

</br>
</br>

## Program

### Import Libraries & Define Functions
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
    
def plot(name,img):
    plt.axis("off")
    plt.imshow(img,cmap="gray")
    plt.title(name)
```
### Convert Image to GraySacle
```py
img = cv2.imread("gojo.png",1)
plot("Original Image",img)

img_gray = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
plot("Gray Image",img_gray)
```
### Gloabl Thresholding
#### Binary
```py
ret,t_b   = cv2.threshold(img_gray,200,300,cv2.THRESH_BINARY)
plot("Thershold - Binary",t_b)
```
#### Binary - Inverse
```py
ret,t_b_i = cv2.threshold(img_gray,200,300,cv2.THRESH_BINARY_INV)
plot("Thershold - Binary Inverse",t_b_i)
```
#### Truncate
```py
ret,t_t = cv2.threshold(img_gray,200,300,cv2.THRESH_TRUNC)
plot("Thershold - Truncate",t_t)
```

</br></br></br>

#### To Zero
```py
ret,t_tz =cv2.threshold(img_gray,86,255,cv2.THRESH_TOZERO)
plot("Thershold-To Zero",t_tz)
```
#### To Zero - Inverse
```py
ret,t_tz_i =cv2.threshold(img_gray,86,255,cv2.THRESH_TOZERO_INV)
plot("Thershold to Zero - Inverse",t_tz_i)
```
### Adaptive Thresholding
#### Mean
```py
amt = cv2.adaptiveThreshold(img_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
plot("Adaptive Mean Thersholding",amt)
```
#### Gaussian
```py
ag=cv2.adaptiveThreshold(img_g,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
plot("Adaptive Gaussian Thersholding",ag)
```
### Otsu's Thersholding
```py
ret,otsu = cv2.threshold(img_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
plot("Otsu Thersholding",otsu)
```
## Output
| Original 																										|  Gray Image	|
|    :-:    																									|     :-:  		|
| ![img](https://user-images.githubusercontent.com/93427237/235441441-5caee33c-c614-44e3-a99f-c2c30fffd412.png) |   ![img_gray](https://user-images.githubusercontent.com/93427237/235441346-2ed16d04-5fb7-4e8e-abed-dbb0a05caa8e.png)|

### Global Thresholding

| Gray Image 																										|  Binary Thersholding	|
|    :-:    																									|     :-:  		|
| ![img_gray](https://user-images.githubusercontent.com/93427237/235441346-2ed16d04-5fb7-4e8e-abed-dbb0a05caa8e.png) | ![t_b](https://user-images.githubusercontent.com/93427237/235441598-bf4f1d3b-2c62-46ff-9f1a-bd9585dd067d.png)  |
|**Binary Thersholding - Inverse|Truncate Thresholding|
|![t_b_i](https://user-images.githubusercontent.com/93427237/235441669-61af114a-b766-4c6d-ae59-1f2154576de4.png)|![t_t](https://user-images.githubusercontent.com/93427237/235441677-0274fd69-22a5-47e1-962e-62a059f14f14.png)|
|To Zero Thersholding - Inverse|To Zero Thresholding - Inverse|
|![t_tz](https://user-images.githubusercontent.com/93427237/235441735-7bf4dbe0-3e4f-4278-b855-73dcddbbffd1.png) |![t_tz_i](https://user-images.githubusercontent.com/93427237/235441741-26e8046f-862d-4121-9a1e-c639915ddc64.png) |

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

### Adaptive Thresholding

| Adaptive Thresholding - Mean |  Adaptive Thresholding - Gaussian	|
|    :-:    			|     :-:  		|
|![amt](https://user-images.githubusercontent.com/93427237/235442021-92472c29-4208-4109-9551-0c4e149ada30.png) | ![agt](https://user-images.githubusercontent.com/93427237/235442017-758a35ad-3845-4c12-8a8a-2cde31900a61.png)|

### Otsu's Thresholding

| Gray Image |  Otsu's	|
|    :-:    			|     :-:  		|
|![img_gray](https://user-images.githubusercontent.com/93427237/235441346-2ed16d04-5fb7-4e8e-abed-dbb0a05caa8e.png) |![otsu](https://user-images.githubusercontent.com/93427237/235442131-f0cb7f30-0707-4dd3-ab0c-746d2e1c8784.png) |


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

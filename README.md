### EX NO : 09
### DATE  : 26.05.2022
# <p align="center">Thresholding</p>
## AIM:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## SOFTWARE REQUIRED:
1. Anaconda - Python 3.7
2. OpenCV

## ALGORITHM:

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
<br/>
<br/>

## PROGRAM:
```python

# Developed By: Aishree Ramesh
# Register Number: 212220230003

import cv2
import numpy as np
import matplotlib.pyplot as plt
image=cv2.imread("anya.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("anya.jpg",0)
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(5,5))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```


## OUTPUT:

### Original Image and Grayscale Image

![image](https://user-images.githubusercontent.com/70213227/169489869-4db178fc-7cae-40c2-b54a-76728f731590.png)

### Global Thresholding
![image](https://user-images.githubusercontent.com/70213227/169490398-08904106-a03a-429c-aafc-f828135bef57.png)
![image](https://user-images.githubusercontent.com/70213227/169490457-e753c45c-07b7-4edf-8529-56a2b1709cec.png)
![image](https://user-images.githubusercontent.com/70213227/169490496-5ae83203-0849-40b4-981e-7091aa8733de.png)
![image](https://user-images.githubusercontent.com/70213227/169490536-70abdd05-c85d-4007-9ff8-8f2d1d03b658.png)
![image](https://user-images.githubusercontent.com/70213227/169490573-43993450-9125-4924-acb6-c4106fa54808.png)

<br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/>

### Adaptive Thresholding
![image](https://user-images.githubusercontent.com/70213227/169490676-9af1d272-06b5-4754-9c19-95043fae5ce0.png)
![image](https://user-images.githubusercontent.com/70213227/169490718-3929ca38-051a-4164-8360-33ec8a3b34b8.png)



### Optimum Global Thesholding using Otsu's Method
![image](https://user-images.githubusercontent.com/70213227/169490758-66d0871d-5ab5-4b7f-85be-6ee1576e1aa1.png)


## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

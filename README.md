# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Load the necessary packages.
### Step2:
Read the Image and convert to grayscale.
### Step3:
Use Global thresholding to segment the image.
### Step4:
Use Adaptive thresholding to segment the image.
### Step5:
Use Otsu's method to segment the image and display the results.

## Program
### Developed By :VAISHALI BALAMURUGAN
### Register Number : 212222230164
```python
# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2
# Read the Image and convert to grayscale

image = cv2.imread('lap.jpeg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('lap.jpeg',0)

# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
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
## Output

### Original Image
![download](https://github.com/divakar618/Thresholdingg/assets/121932143/bcdb7e11-1fd5-4675-8301-3523a3e1bf20)

### Global Thresholding
![download](https://github.com/divakar618/Thresholdingg/assets/121932143/fbd613c5-3cd2-4ea1-98b6-67b4e9d0e835)
![download](https://github.com/divakar618/Thresholdingg/assets/121932143/70a39f1d-5c92-4bcf-8052-dc4c8963fba0)
![download](https://github.com/divakar618/Thresholdingg/assets/121932143/1cbef3ec-4ad3-491f-b2f7-402b68f0eb8f)
![download](https://github.com/divakar618/Thresholdingg/assets/121932143/c6ac5f38-3144-40be-b9f0-896326d7caf1)
![download](https://github.com/divakar618/Thresholdingg/assets/121932143/a6f12774-9d33-407a-9e3e-87616b0827d2)

### Adaptive Thresholding
![download](https://github.com/divakar618/Thresholdingg/assets/121932143/e294dbbb-fb6a-4aa5-b06d-236ae54d7899)
![download](https://github.com/divakar618/Thresholdingg/assets/121932143/c3b14460-1843-4f48-a744-baa5cd5ba3a8)

### Optimum Global Thesholding using Otsu's Method
![download](https://github.com/divakar618/Thresholdingg/assets/121932143/1883bd75-cd58-4241-8642-fb34c11b6c18)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

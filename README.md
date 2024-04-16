# EX-08 THRESHOLDING
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
```
DEVELOPED BY: SATHISH R
REGISTER NO: 212222240138
```
### Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```python
image = cv2.imread("me.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("me.jpg",0)
```
### Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C
            ,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C
            ,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```python
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)"
       ,"Threshold Image (To Zero)","Threshold Image (To Zero-Inverse)"
       ,"Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)"
       ,"Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3
       ,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
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
![dipt-ex-8-1](https://github.com/r-sathish-02/THRESHOLDING-/assets/118787261/4deb48ac-6422-4dba-ae6a-db6d3877b419)


### Global Thresholding
![dipt_exp_8-2](https://github.com/r-sathish-02/THRESHOLDING-/assets/118787261/ba8db646-d71e-4832-8679-005bb41b2ab3)
![dipt-ex-8-3](https://github.com/r-sathish-02/THRESHOLDING-/assets/118787261/eace1834-d9ed-4c22-855a-dcdbd3eec487)
![dipt-exp-8-4](https://github.com/r-sathish-02/THRESHOLDING-/assets/118787261/8a8d0b4f-958e-40e4-ac15-9045d4c71fc8)
![dipt-ex-8-5](https://github.com/r-sathish-02/THRESHOLDING-/assets/118787261/52663d0a-05f0-4272-afcb-87877d014978)
![dipt-exp-8-6](https://github.com/r-sathish-02/THRESHOLDING-/assets/118787261/ee723e75-dac5-47f3-917c-4b50b80bcece)




### Adaptive Thresholding
![dipt-exp-8-7](https://github.com/r-sathish-02/THRESHOLDING-/assets/118787261/80694b93-6cae-49c2-a852-6cc56c2bfcb2)
![dipt-exp-8-8](https://github.com/r-sathish-02/THRESHOLDING-/assets/118787261/7d6c32f9-8606-474e-bd42-c46cdbbb53df)



### Optimum Global Thesholding using Otsu's Method
![dipt-exp-8-9](https://github.com/r-sathish-02/THRESHOLDING-/assets/118787261/99a10eba-728e-4b30-a4cb-f7d8a0e3f22a)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

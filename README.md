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
### Developed by: Krithick Vivekananda 
### Register no: 212223240075
#### Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
#### Read the Image and convert to grayscale
```python
image = cv2.imread('falcon.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('falcon.jpg',0)
```
#### Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
#### Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
#### Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
#### Display the results
```python
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

## Output:
![image](https://github.com/user-attachments/assets/d655f99b-98ab-48d3-a641-6279682c4f89)
### Original Image and Gray Image
![image](https://github.com/user-attachments/assets/8a28c6a2-e415-4460-a62f-3691a94932a8)
### Global Thresholding
![image](https://github.com/user-attachments/assets/3699e02c-0203-4b0e-9389-308c2fabe895)
![image](https://github.com/user-attachments/assets/e49de2de-3630-42bf-b479-b98c29e1ed52)
![image](https://github.com/user-attachments/assets/afbb0ab3-afa5-4f57-a76a-efbff35b52ab)
![image](https://github.com/user-attachments/assets/c0cf507e-92bf-495d-a8c5-4db9f5155217)
![image](https://github.com/user-attachments/assets/6acea4b9-77b3-4816-9414-625304e34a4a)
### Adaptive Thresholding
![image](https://github.com/user-attachments/assets/7f407075-31b6-4824-9271-2d33ff110779)
![image](https://github.com/user-attachments/assets/a15fb46e-04eb-4217-8efe-dc4db883825d)
### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/user-attachments/assets/b832a681-c2b2-42a1-b283-a1a1f8c5674c)
## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

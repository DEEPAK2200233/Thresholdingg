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
```
Developed by:DEEPAK RAJ S

Register number:212222240023

```

```
# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale
image = cv2.imread('kamal2.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('kamal2.jpg',0)


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

![image](https://github.com/user-attachments/assets/4aaae13d-859c-4f4b-b63d-3378346239ef)

### Global Thresholding

![image](https://github.com/user-attachments/assets/b14fce74-37dc-4aa4-9a10-bff3d47a8681)

![image](https://github.com/user-attachments/assets/3cd94afb-1052-4bcc-b43f-ec960678ed45)

![image](https://github.com/user-attachments/assets/22fd02d5-78d0-4389-97aa-f6829733cc07)

![image](https://github.com/user-attachments/assets/db5463e9-76bc-413f-a18d-26625a876385)

![image](https://github.com/user-attachments/assets/a7b49a0b-00ef-4514-bacb-f921371d9be2)

### Adaptive Thresholding

![image](https://github.com/user-attachments/assets/0d02c371-71ca-4217-8af6-9a0d1d1af2a8)

![image](https://github.com/user-attachments/assets/ebf6f777-4e6c-4be7-b214-9e1d5aa88fea)

![image](https://github.com/user-attachments/assets/c8fc7bfd-a92d-4ccd-8a77-fe781388793e)

### Optimum Global Thesholding using Otsu's Method

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

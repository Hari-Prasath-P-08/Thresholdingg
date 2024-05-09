# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program
### Developed by: Hari Prasath. P
### Reg. No: 212223230070
# Load the necessary packages

# Load the necessary packages

```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

# Read the Image and convert to grayscale

```python
image = cv2.imread('peacock.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('peacock.jpg',0)
```

# Use Global thresholding to segment the image

```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```

# Use Adaptive thresholding to segment the image

```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```

# Use Otsu's method to segment the image 

```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```

# Display the results

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

## Output

### Original Image

![Chotta Bheem](https://github.com/Hari-Prasath-P-08/Thresholdingg/assets/139455593/228e6c75-1db2-4be4-9b2b-6b3c01e25aac)

### Global Thresholding

![Screenshot 2024-05-09 072743](https://github.com/Hari-Prasath-P-08/Thresholdingg/assets/139455593/461ad09f-47fa-4efa-884e-256c51d587b0)

### Adaptive Thresholding

![Screenshot 2024-05-09 072929](https://github.com/Hari-Prasath-P-08/Thresholdingg/assets/139455593/4681dfd1-1011-4561-80bb-7dfd96a2be0a)

### Optimum Global Thesholding using Otsu's Method

![Screenshot 2024-05-09 072941](https://github.com/Hari-Prasath-P-08/Thresholdingg/assets/139455593/fb4c4af2-652e-4ef1-a822-b377912c7b73)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

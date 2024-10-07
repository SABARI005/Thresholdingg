# Thresholding

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

#### Name : SABARI S
#### Register no : 212222240085

### Load the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

### Read and show the Original image
```
image = cv2.imread('spiderman.jpeg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')
plt.show()
```
### Output:

![{3F828A74-2BA1-4A4B-836B-08EA0B40F5CE}](https://github.com/user-attachments/assets/0b659bbf-b2f1-44ed-a521-1ab0ff0a5db9)

### Convert the image to grayscale
```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.xticks([]), plt.yticks([])
plt.show()
```
### Output:

![{947A59DA-BE20-4FA0-86BB-B1AC30B79101}](https://github.com/user-attachments/assets/d46b9510-f6ad-4451-9160-661d0e108096)

### Use Global thresholding to segment the image
```
# Global thresholding
ret_global, th_global = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Display the global thresholding result
plt.imshow(th_global, cmap='gray')
plt.title('Global Thresholding (v=127)')
plt.xticks([]), plt.yticks([])
plt.show()
```
### Output:

![{9023DCBA-BB4B-43AE-A7F3-703C47C5F16B}](https://github.com/user-attachments/assets/ae4d276b-4922-4fe4-8b68-3086a271baa3)

### Use Adaptive thresholding to segment the image
```
# Adaptive thresholding (Gaussian)
th_adaptive = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
                                    cv2.THRESH_BINARY, 11, 2)

# Display the adaptive thresholding result
plt.imshow(th_adaptive, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.xticks([]), plt.yticks([])
plt.show()
```
### Output:

![{57794174-7D66-4097-95C8-6A059A46FED9}](https://github.com/user-attachments/assets/574db367-cddf-44e8-8f71-b261b6da00ac)

### Use Otsu's method to segment the image 
```
# Otsu's thresholding
ret_otsu, th_otsu = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Display the Otsu thresholding result
plt.imshow(th_otsu, cmap='gray')
plt.title("Otsu's Thresholding")
plt.xticks([]), plt.yticks([])
plt.show()
```
### Output:

![{56C173D1-8625-4BBC-AF42-AC7DE5BDCFC0}](https://github.com/user-attachments/assets/33a68e03-e1fd-48d4-a959-eaae3cff3d38)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

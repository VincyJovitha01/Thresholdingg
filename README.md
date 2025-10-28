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

```python
#Developed by : VINCY JOVITHA V
#Register No: 212223230242

# Load the necessary packages

import cv2
import numpy as np
import matplotlib.pyplot as plt



# Read the Image and convert to grayscale
image = cv2.imread('dog.png')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')



# Use Global thresholding to segment the image
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)



# Use Adaptive thresholding to segment the image

adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)


# Use Otsu's method to segment the image 

_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)


# Display the results
# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()


```
## Output

### Original Image
<img width="171" height="256" alt="image" src="https://github.com/user-attachments/assets/573bd7aa-26ca-4a40-85d8-c9170f504139" />


### Global Thresholding

<img width="291" height="287" alt="image" src="https://github.com/user-attachments/assets/bd0db8ec-cea1-4c50-b36f-b1e7452cd158" />

### Adaptive Thresholding

<img width="274" height="314" alt="image" src="https://github.com/user-attachments/assets/bdb85b3f-2999-4fa8-8b0c-99a5b95ab7ca" />

### Optimum Global Thesholding using Otsu's Method

<img width="199" height="292" alt="image" src="https://github.com/user-attachments/assets/178c9617-ff08-4f0c-bf5f-10bdceaa0ee1" />

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

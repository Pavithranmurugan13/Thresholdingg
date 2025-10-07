# EXP 8 :THRESHOLDING
# NAME: PAVITHRAN MJ
# REG NO:212223240112 
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
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 2: Read the image and convert to grayscale
image = cv2.imread('111.JPG')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
# Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')

# Step 3: Use Global Thresholding to segment the image
# Apply global thresholding with a threshold value of 127
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Step 4: Use Adaptive Thresholding to segment the image
# Apply adaptive thresholding using Gaussian method
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

# Step 5: Use Otsu's method to segment the image
# Apply Otsu's method for optimal thresholding
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)



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

## Original Image
<img width="146" height="210" alt="download" src="https://github.com/user-attachments/assets/65275d7c-19e9-4c51-953d-28d862491db5" />

## Global Thresholding
<img width="226" height="289" alt="Screenshot 2025-10-07 160321" src="https://github.com/user-attachments/assets/68f95e0a-ae55-457e-9ec8-dd5ef85641c3" />

## Adaptive Thresholding
<img width="257" height="305" alt="Screenshot 2025-10-07 160334" src="https://github.com/user-attachments/assets/73098431-6798-4d68-9bdf-c1586d405bca" />

## Optimum Global Thesholding using Otsu's Method
<img width="234" height="299" alt="Screenshot 2025-10-07 160327" src="https://github.com/user-attachments/assets/ef979c4b-a60e-4aa9-9fe3-e6f96bebe9ac" />

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

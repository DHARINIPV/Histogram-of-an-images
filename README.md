# Histogram-of-an-images
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()
### Step2:
Print the image using imshow().
### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.
### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.
### Step5:
The Histogram of gray scale image and color image is shown.

## Program:
### Developed By: Dharini PV
### Register Number: 212222240024
### Input Grayscale Image 
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
gray_image = cv2.imread('agray.jpg', cv2.IMREAD_GRAYSCALE)
plt.title("Grayscale Image")
plt.imshow(gray_image, cmap='gray')
plt.axis('off')
```
## Output:
![image](https://github.com/user-attachments/assets/fa0c51bc-81af-418a-9c88-01269a0d3903)

### Histogram of Grayscale Image
```python
plt.title("Histogram of Grayscale Image")
plt.hist(gray_image.ravel(), bins=256, color='black', alpha=0.6)
plt.xlim(0, 255)
plt.tight_layout()
plt.show()
```
## Output:
![image](https://github.com/user-attachments/assets/68bc5432-663f-49e3-be7d-9833745b2007)

### Histogram Equalization of Grayscale Image.
```python
equalized_gray_image = cv2.equalizeHist(gray_image)
plt.title("Histogram of Equalized Grayscale Image")
plt.hist(equalized_gray_image.ravel(), bins=256, color='black', alpha=0.6)
plt.xlim(0, 255)
plt.title("Enhanced Grayscale Image")
plt.imshow(equalized_gray_image, cmap='gray')
plt.axis('off')
```
## Output:
![image](https://github.com/user-attachments/assets/fb0cf19a-271c-4ca6-84d2-d3d4533c7b9e)
![image](https://github.com/user-attachments/assets/635d304c-3673-433f-82ac-8b7026ee47ea)

### Input of color image
```python
color_image = cv2.imread('vcolor.jpg')
plt.title("Input Color Image")
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.axis('off')
```
### Output:
![image](https://github.com/user-attachments/assets/bb3325bb-9754-43b1-9400-b2350894b13d)

### Histogram of Color Image
```python
hist_b = cv2.calcHist([color_image], [0], None, [256], [0, 256])
hist_g = cv2.calcHist([color_image], [1], None, [256], [0, 256])
hist_r = cv2.calcHist([color_image], [2], None, [256], [0, 256])
plt.title("Histogram of Input Color Image")
plt.plot(hist_b, color='blue', label='Blue channel')
plt.plot(hist_g, color='green', label='Green channel')
plt.plot(hist_r, color='red', label='Red channel')
plt.show()
```
### Output:
![image](https://github.com/user-attachments/assets/0fcf2fa3-3884-407f-8362-a163fb28f98c)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.

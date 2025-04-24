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
```python
# Developed By: Cynthia Mehul
# Register Number: 212223240020

import cv2
import numpy as np
import matplotlib.pyplot as plt

grey_img = cv2.imread('dark mickey.webp',cv2.IMREAD_GRAYSCALE)

plt.title("Grey Mickey")
plt.imshow(grey_img,cmap='gray')
plt.axis('off')

plt.title("Histogram of Grey Mickey")
plt.hist(grey_img.ravel(),bins=256,color='black',alpha=0.6)
plt.xlim(0,255)
plt.tight_layout()
plt.show()

equalized_grey_img = cv2.equalizeHist(grey_img)

plt.title("Equalized Hist of Grey Mickey")
plt.hist(equalized_grey_img.ravel(),bins=256,color='black',alpha=0.6)
plt.xlim(0,255)
plt.tight_layout()
plt.show()

plt.title("Enhanced Image")
plt.imshow(equalized_grey_img,cmap='gray')
plt.axis('off')

color_img=cv2.imread('donald.webp')

plt.title("Color Image")
plt.imshow(cv2.cvtColor(color_img,cv2.COLOR_BGR2RGB))
plt.axis('off')

hist_b=cv2.calcHist([color_img],[0],None,[256],[0,256])
hist_g=cv2.calcHist([color_img], [1], None, [256], [0, 256])
hist_r=cv2.calcHist([color_img], [2], None, [256], [0, 256])

plt.title("Hist of color image")
plt.plot(hist_b,color='blue',label='Blue')
plt.plot(hist_g,color='green',label='Green')
plt.plot(hist_r,color='red',label='Red')

blue_channel_eq = cv2.equalizeHist(color_img[:, :, 0])
green_channel_eq = cv2.equalizeHist(color_img[:, :, 1])
red_channel_eq = cv2.equalizeHist(color_img[:, :, 2])

equalized_color_img = cv2.merge([blue_channel_eq, green_channel_eq, red_channel_eq])

plt.imshow(equalized_color_img)

```
## Output:
### Input Grayscale Image and Color Image
![image](https://github.com/user-attachments/assets/24daac50-19c2-4136-8f6c-19397d92577a)

![image](https://github.com/user-attachments/assets/0ec9089c-47fb-4119-a517-4228f4761ff3)

### Histogram of Grayscale Image and any channel of Color Image
![image](https://github.com/user-attachments/assets/0f0636f4-e7b2-48db-a5ff-a40c3c734c0d)

![image](https://github.com/user-attachments/assets/5e983d2c-e9ed-4b6c-9f6c-5ada4d858bae)

### Histogram Equalization of Grayscale Image.

![image](https://github.com/user-attachments/assets/9e68cdb5-a5f3-497b-8d81-daa588a8b5af)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.

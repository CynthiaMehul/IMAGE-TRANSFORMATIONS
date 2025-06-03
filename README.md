# IMAGE-TRANSFORMATIONS
## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the required libraries and images for the experiment

### Step2:
Translate the image using wrapAffine and the same can be used for Shearing the image

### Step3:
Use cv2.resize() to scale the image

### Step4:
use cv2.flip(img,2) to get the reflected image

### Step5:
Crop the image by using slicing

## Program:
```python
Developed By: Cynthia Mehul
Register Number: 212223240020

i)Image Translation

import cv2
import numpy as np
import matplotlib.pyplot as plt

img=cv2.imread('cologne.jpg')
colonge_img=cv2.cvtColor(img,cv2.COLOR_BGR2RGB)
plt.imshow(colonge_img)
plt.title("cologne Cathedral")  
plt.axis('off')
plt.show()

tx, ty = 100, 50
M_translation = np.float32([[2, 0, tx], [0, 2, ty]])  
translated_img = cv2.warpAffine(img, M_translation, (img.shape[1], img.shape[0]))
translated_img=cv2.cvtColor(translated_img, cv2.COLOR_BGR2RGB)
plt.imshow(translated_img)  
plt.axis('off')
plt.show()

ii) Image Scaling

fx, fy = 5.0, 2.0  
scaled_img = cv2.resize(img, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
scaled_img = cv2.cvtColor(scaled_img, cv2.COLOR_BGR2RGB)
plt.imshow(scaled_img)  
plt.title("Scaled img")  
plt.axis('off')
plt.show()

iii)Image shearing
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])
sheared_img = cv2.warpAffine(img, shear_matrix, (img.shape[1], img.shape[0]))
sheared_img = cv2.cvtColor(sheared_img, cv2.COLOR_BGR2RGB)
plt.imshow(sheared_img)  
plt.title("Sheared img") 
plt.axis('off')
plt.show()


iv)Image Reflection

reflected_img = cv2.flip(img, 2)
reflected_img = cv2.cvtColor(reflected_img, cv2.COLOR_BGR2RGB)
plt.imshow(reflected_img) 
plt.title("Reflected img")  
plt.axis('off')
plt.show()

v)Image Rotation

(height, width) = img.shape[:2]  
angle = 45  
center = (width // 2, height // 2)  
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  

rotated_img = cv2.warpAffine(img, M_rotation, (width, height))
rotated_img = cv2.cvtColor(rotated_img, cv2.COLOR_BGR2RGB)
plt.imshow(rotated_img) 
plt.title("Rotated img")  
plt.axis('off')
plt.show()

vi)Image Cropping

x, y, w, h = 500, 1600, 700, 850  
cropped_img = img[y:y+h, x:x+w]
cropped_img = cv2.cvtColor(cropped_img, cv2.COLOR_BGR2RGB)
plt.imshow(cropped_img)  
plt.title("Cropped img")  
plt.axis('off')
plt.show()

```
## Output:
### i)Image Translation

![image](https://github.com/user-attachments/assets/39a1b193-7b4c-4b06-9467-8a84f153dbc6)

### ii) Image Scaling

![image](https://github.com/user-attachments/assets/582c4a97-3b00-49cc-adb8-6197184ff613)

### iii)Image shearing

![image](https://github.com/user-attachments/assets/ad14d2e1-2082-4e46-bb1b-cb3bcb2df51a)

### iv)Image Reflection

![image](https://github.com/user-attachments/assets/ecb7f100-9844-4283-ac3f-95a2564fe38d)

### v)Image Rotation

![image](https://github.com/user-attachments/assets/ebb15a20-d53f-4d82-881f-dfe72faffea2)

### vi)Image Cropping

![image](https://github.com/user-attachments/assets/1ece29dc-dd1e-49b2-8e2c-1b545fe48a44)


## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.

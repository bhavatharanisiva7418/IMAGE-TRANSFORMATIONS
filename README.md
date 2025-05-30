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
## Developed By:BHAVATHARANI S
## Register Number:212223230032
```
i)Image Translation

import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('eagle.png')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB) 
plt.imshow(image_rgb)
plt.title("Original Image")

rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
```

ii) Image Scaling
```
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR) 
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')
```


iii)Image shearing
```
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
```


iv)Image Reflection
```
reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')
```



v)Image Rotation
```
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')
```



vi)Image Cropping
```
 x, y, w, h = 100, 100, 200, 150 
cropped_image = image[y:y+h, x:x+w]
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB)) 
plt.title("Cropped Image")  
plt.axis('off')
```
## Output:
### i)Image Translation
![image](https://github.com/user-attachments/assets/6e14e386-f0c4-44f5-b4ce-80aa569a3a6c)


### ii) Image Scaling

![image](https://github.com/user-attachments/assets/ac73281d-95f9-44c0-9e41-bd29ede8c954)

### iii)Image shearing
![image](https://github.com/user-attachments/assets/5555224a-005d-440b-84cf-9b2a00e90dfc)


### iv)Image Reflection
![image](https://github.com/user-attachments/assets/527a6c9c-8715-491e-9e22-762d3146de0a)



### v)Image Rotation
![image](https://github.com/user-attachments/assets/3ee8134e-9838-43ce-9263-0839d7529ba0)



### vi)Image Cropping
![image](https://github.com/user-attachments/assets/b128e62d-6219-4a3c-af7b-f5c5b63a3dfe)


## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.

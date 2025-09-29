# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:
Import all the necessary modules 
### Step 2:
Choose an image and save it as filename.jpg
### Step 3:
Use imread to read the image
### Step 4:
Use cv2.warpPerspective(image,M,(cols,rows)) to translation the image
### Step 5:
Use cv2.warpPerspective(image,M,(cols2,rows2)) to scale the image
### Step 6:
Use cv2.warpPerspective(image,M,(int(cols1.5),int(rows1.5))) for x and y axis to shear the image
### Step 7:
Use cv2.warpPerspective(image,M,(int(cols),int(rows))) for x and y axis to reflect the image
### Step 8:
Use cv2.warpPerspective(image,M,(int(cols),int(rows))) to rotate the image
### Step 9:
Crop the image to remove unwanted areas from an image
### Step 10:
Use cv2.imshow to show the image
### Step 11: End the program


## Program:
```python
Developed By: Tanushree A
Register Number: 212223100057

import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('/content/flower.jpg')
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis('off')
```
i)Image Translation
```
tx, ty = 100, 50
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])
# [1, 0, tx] - Horizontal shift by tx
# [0, 1, ty] - Vertical shift by ty
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))
plt.title("Translated Image")
plt.axis('off')
```

ii) Image Scaling
```
fx, fy = 5.0, 2.0 # Scaling factors (1.5x scaling for both width and height)
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB)) # Display the scaled image
plt.title("Scaled Image") # Set title
plt.axis('off')
```

iii)Image shearing
```
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]]) # Shearing matrix
# The matrix shears the image by a factor of 0.5 in both x and y directions
# [1, 0.5, 0] - Shear along the x-axis (horizontal)
# [0.5, 1, 0] - Shear along the y-axis (vertical)
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB)) # Display the sheared image
plt.title("Sheared Image") # Set title
plt.axis('off')
```


iv)Image Reflection
```
reflected_image = cv2.flip(image, 2)
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB)) # Display the reflected image
plt.title("Reflected Image") # Set title
plt.axis('off')
```



v)Image Rotation

```
(height, width) = image.shape[:2] # Get the image height and width
angle = 45 # Rotation angle in degrees (rotate by 45 degrees)
center = (width // 2, height // 2) # Set the center of rotation to the image center
M_rotation = cv2.getRotationMatrix2D(center, angle, 1) # Get the rotation matrix
# getRotationMatrix2D: Takes the center of rotation, angle, and scale factor (1 means no scaling
rotated_image = cv2.warpAffine(image, M_rotation, (width, height)) # Apply rotation
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB)) # Display the rotated image
plt.title("Rotated Image") # Set title
plt.axis('off')
```


vi)Image Cropping

```
x, y, w, h = 100, 100, 200, 150 # Define the top-left corner (x, y) and the width (w) and heigh
# Cropping the image from coordinates (x, y) to (x+w, y+h)
cropped_image = image[y:y+h, x:x+w]
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB)) # Display the cropped image
plt.title("Cropped Image") # Set title
plt.axis('off')


```

## Output:
### i)Image Translation
<img width="786" height="540" alt="image" src="https://github.com/user-attachments/assets/ea6ca97a-d39d-4905-93ee-b791fdd9dc7e" />


### ii) Image Scaling
<img width="795" height="285" alt="image" src="https://github.com/user-attachments/assets/9d7923b1-2d56-412e-b6a5-8292037a4bc7" />



### iii)Image shearing
<img width="887" height="603" alt="image" src="https://github.com/user-attachments/assets/c52d8e87-18c6-4ad0-8140-7a754d179946" />


### iv)Image Reflection
<img width="872" height="549" alt="image" src="https://github.com/user-attachments/assets/7823b17e-0ecc-4dc4-ba1b-e9e02035aa4e" />



### v)Image Rotation
<img width="899" height="546" alt="image" src="https://github.com/user-attachments/assets/88154771-401e-4cba-972c-0bdb661125e7" />



### vi)Image Cropping
<img width="756" height="479" alt="image" src="https://github.com/user-attachments/assets/a7a3dbb0-def9-4bc5-bdc6-8792202d8843" />



## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.

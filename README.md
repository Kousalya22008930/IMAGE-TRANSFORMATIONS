# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:
Read the input image using cv2.imread() and store it in a variable for further processing.

### Step3:
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

Translation moves the image along the x or y-axis.
Scaling resizes the image by scaling factors.
Shearing distorts the image along one axis.
Reflection flips the image horizontally or vertically.
Rotation rotates the image by a given angle.

### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.

## Program:
### Developed By: KOUSALYA A.
### Register Number: 212222230068

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('bb.jpeg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)  # Convert BGR to RGB for Matplotlib

# Plot the original image
plt.figure(figsize=(7,3))
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')
```
### Output
![ori](https://github.com/user-attachments/assets/94255ee8-7922-4626-a976-54065d709d16)

### i)Image Translation
```python
rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  # Translate by (50, 100) pixels
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))

plt.figure(figsize=(7,3))
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
```
### Output
![trans](https://github.com/user-attachments/assets/0a52b307-4a44-42fc-b24e-72e7168372ad)

### ii) Image Scaling
```python
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR)  # Scale by 1.5x

plt.figure(figsize=(7,3))
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')
```
### Output
![sca](https://github.com/user-attachments/assets/a7a9ae85-662e-454e-944d-09755a1b4586)

### iii)Image shearing
```python
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))

plt.figure(figsize=(7,3))
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
```
### Output
![sear](https://github.com/user-attachments/assets/1e1ea5d2-9f2f-4898-8c1d-f2abd769de89)


### iv)Image Reflection
```python
reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)

plt.figure(figsize=(7,3))
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')
```
### Output
![ref](https://github.com/user-attachments/assets/83b7b138-c3cd-4ba1-86e1-69f94cbdda49)

### v)Image Rotation
```python
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 150, 1)  # Rotate by 150 degrees
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))

plt.figure(figsize=(7,3))
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')
```
### Output
![rot](https://github.com/user-attachments/assets/ee94f7d3-461f-4ae2-b28b-e4bbd30c8840)

### vi)Image Cropping
```python
cropped_image = image_rgb[50:300, 100:400]  # Crop a portion of the image

# Plot cropped image separately as its aspect ratio may be different
plt.figure(figsize=(7, 3))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()
```
### Output
![crop](https://github.com/user-attachments/assets/4b77c669-3615-43a3-a211-79a4c39b5ee9)

## Result: 
Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.

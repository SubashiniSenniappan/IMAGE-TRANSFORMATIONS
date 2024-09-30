# IMAGE-TRANSFORMATIONS
## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary libraries and read the original image and save it as a image variable.

### Step2:
Use cv2.warpAffine() to perform the Translation of the image

### Step3:
Define a scaling matrix to enlarge the image by a factor and apply scaling using cv2.warpAffine().

### Step4:
Use shearing matrices for both x-axis and y-axis transformations and reflection matrices for horizontal and vertical reflections.

### Step5:
Create a rotation matrix to rotate the image by a specified angle, then apply cropping by selecting a region of the image.

## Program:
```python
Developed By: SUBASHINI S
Register Number: 212222240106
```
## i)Original Image:
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
input_img = cv2.imread("shrine.jpg")
# cv2.imshow("image webp",input_img)
input_img = cv2.cvtColor(input_img, cv2.COLOR_BGR2RGB)
plt.axis('off')
plt.imshow(input_img)
plt.show()
```
## ii)Image Translation
```
rows,cols,dim=input_img.shape
M=np.float32([[1,0,50],  [0,1,100],  [0,0,1]])
translated_image=cv2.warpPerspective(input_img,M,(cols,rows))
plt.axis('off')
plt.imshow(translated_image)
plt.show()
```
## iii) Image Scaling
```
scale_factor = 1.5
M_scale = np.float32([[scale_factor, 0, 0],
                      [0, scale_factor, 0],
                      [0, 0, 1]])

scaled_img = cv2.warpAffine(input_img, M[:2], (int(cols*scale_factor), int(rows*scale_factor)))
plt.axis('off')
plt.imshow(scaled_img)
plt.show()
```
## iv)Image shearing
```
M_x = np.float32([[1, 0.2, 0],
                  [0, 1, 0],
                  [0, 0, 1]])

sheared_img_xaxis = cv2.warpAffine(input_img, M_x[:2], (cols, rows))
plt.axis('off')
plt.imshow(sheared_img_xaxis)
plt.show()
M_y = np.float32([[1, 0, 0],
                  [0.2, 1, 0],
                  [0, 0, 1]])

sheared_img_yaxis = cv2.warpAffine(input_img, M_y[:2], (cols, rows))
plt.axis('off')
plt.imshow(sheared_img_yaxis)
plt.show()
```
## v)Image Reflection
```
M_x = np.float32([[-1, 0, cols],
                  [0, 1, 0],
                  [0, 0, 1]])

reflected_img_xaxis = cv2.warpAffine(input_img, M_x[:2], (cols, rows))

plt.axis("off")
plt.imshow(reflected_img_xaxis)
plt.show()

M_y = np.float32([[1, 0, 0],
                  [0, -1, rows],
                  [0, 0, 1]])

reflected_img_yaxis = cv2.warpAffine(input_img, M_y[:2], (cols, rows))

plt.axis("off")
plt.imshow(reflected_img_yaxis)
plt.show()
```
## vi)Image Rotation
```
angle = np.radians(-60)
M = np.float32([[np.cos(angle), -np.sin(angle), 0],
                [np.sin(angle), np.cos(angle), 0]])
center = (cols // 2, rows // 2)
M = cv2.getRotationMatrix2D(center, -60, 1.0)
rotated_img = cv2.warpAffine(input_img, M, (cols, rows))

plt.axis('off')
plt.imshow(rotated_img)
plt.show()
```
## vii)Image Cropping
```
cropped_img = input_img[50:200, 200:400]
plt.axis('off')
plt.imshow(cropped_img)
plt.show()
```
## Output:
### i)Original image:

![Screenshot 2024-09-30 161101](https://github.com/user-attachments/assets/9c0a6386-65b3-45bd-8bcb-ec59c5b9dafe)

### ii)Image Translation

![Screenshot 2024-09-30 161116](https://github.com/user-attachments/assets/480d89d7-214f-4c7c-b234-18d9b665f393)


### iii) Image Scaling

![Screenshot 2024-09-30 161130](https://github.com/user-attachments/assets/b008e55e-3ad0-41c0-9b07-8393b88455dd)


### iv)Image shearing

![Screenshot 2024-09-30 161147](https://github.com/user-attachments/assets/669bcb2d-a7d3-443b-a9ef-984aac0fe4d0)


### v)Image Reflection

![Screenshot 2024-09-30 161204](https://github.com/user-attachments/assets/799bbb62-0433-48f3-87c5-b6260cc08734)

### vi)Image Rotation

![Screenshot 2024-09-30 161219](https://github.com/user-attachments/assets/b60ed0a5-18b5-4b89-b831-8738c3f8ccb3)

### vii)Image Cropping

![Screenshot 2024-09-30 161244](https://github.com/user-attachments/assets/35de7ca7-4683-41fe-8d5f-66ca5d5188d2)

## Result: 
Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.

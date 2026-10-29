# Exp3-RECORD-HISTOGRAM-PROCESSING

## Aim:
To obtain a histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255. Also, write a Python program using OpenCV to perform histogram equalization.

## Software Required
```
Anaconda - Python 3.7
OpenCV
NumPy
Matplotlib
```
## Algorithm
- Step 1
Read the grayscale and color images using the cv2.imread() function.

- Step 2
Display the grayscale and color images using the imshow() function.

- Step 3
Use the cv2.calcHist() function to calculate the frequency of pixel intensities in the grayscale image.

- Step 4
Use the cv2.calcHist() function to calculate the histograms of the Blue, Green, and Red channels of the color image.

- Step 5
Plot and display the histograms of the grayscale image and color image.

## Program
Developed By: RITHIKA K

Register Number: 212225040343
```  
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
```
img = cv2.imread('Rithi.jpeg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```
```
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
```
img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
```
```
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```
```
img = cv2.imread('Rithi.jpeg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
```
```
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
```
```
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```
```
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```
## Output
### Input Grayscale Image

<img width="465" height="542" alt="image" src="https://github.com/user-attachments/assets/44e254ef-cb7e-4741-a4ac-d2f8f60cf0a2" />

### Input Grayscale Image Range

<img width="745" height="552" alt="image" src="https://github.com/user-attachments/assets/75296992-102b-4c91-99f2-e8dc27cc1474" />

### Input Grayscale Image Equalized Histogram

<img width="712" height="540" alt="image" src="https://github.com/user-attachments/assets/5b802ebc-a29e-46fc-bfa9-04cd7517fb98" />

### Histogram of Grayscale Image and Color Image Channels
Original Image

<img width="547" height="626" alt="image" src="https://github.com/user-attachments/assets/5de8bb96-656c-48bb-bacb-82dd3f988fca" />

### Equalized Image

<img width="486" height="542" alt="image" src="https://github.com/user-attachments/assets/09c956f6-9ab8-46e0-a49d-e31b3bd0d5a4" />

### Equalized Histogram

<img width="737" height="542" alt="image" src="https://github.com/user-attachments/assets/722c4a43-de00-4417-8593-bb4b54fdb206" />

### Final Output of Original Image and Equalized Image

<img width="776" height="265" alt="image" src="https://github.com/user-attachments/assets/a0ea1536-4df9-4811-b7c7-c3e07250024a" />

### Final Output of Original Image and its Histogram Equalized

<img width="770" height="231" alt="image" src="https://github.com/user-attachments/assets/3d5fc16c-b9d4-45ae-8d00-e893f4082111" />

## Result:

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.

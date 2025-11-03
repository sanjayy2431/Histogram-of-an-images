# Histogram-of-an-images
# Name: SANJAY V
# Reg no:212223230188
# Date : 3/11/25
## Aim :
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required :
Anaconda - Python 3.7

## Algorithm :
### Step 1 :
Read the gray and color image using imread()

### Step 2 :
Print the image using imshow().

### Step 3 :
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step 4 :
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step 5 :
The Histogram of gray scale image and color image is shown.


## Program :
```
Developed By: Sanjay V
Register Number: 212223230188
```
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
from google.colab.patches import cv2_imshow

gray_image = cv2.imread("grayscaleimg.jpg", cv2.IMREAD_GRAYSCALE)
color_image = cv2.imread("colourimg.jpg")

cv2_imshow(gray_image)
cv2_imshow(color_image)

gray_hist = cv2.calcHist([gray_image], [0], None, [256], [0, 256])
green_channel = color_image[:, :, 1]
color_hist = cv2.calcHist([green_channel], [0], None, [256], [0, 256])
```
#### Plot grayscale histogram
```
plt.figure()
plt.title("Histogram of Grayscale Image")
plt.xlabel("Intensity Value")
plt.ylabel("Pixel Count")
plt.stem(np.arange(256), gray_hist.flatten())
plt.show()
```
#### Convert BGR to RGB for correct color display in matplotlib
```
plt.figure()
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.title("Color Image")
plt.axis("off")
plt.show()
```
#### Plot histogram of the green channel of the color image
```
plt.figure()
plt.title("Histogram of Color Image - Green Channel")
plt.xlabel("Intensity Value")
plt.ylabel("Pixel Count")
plt.stem(np.arange(256), color_hist.flatten())
plt.show()
```
```
equ = cv2.equalizeHist(gray_image)
cv2_imshow(equ)
```

## Output :
#### i. Input Grayscale Image and Color Image :
<img width="2048" height="1365" alt="image" src="https://github.com/user-attachments/assets/a9973234-80f4-4b2e-aa5b-d582b07c88d6" />
<img width="1280" height="847" alt="image" src="https://github.com/user-attachments/assets/930d05a0-4b16-4cfc-a5be-1c0612ca583c" />

#### ii. Histogram of Grayscale Image and any channel of Color Image :
<img width="597" height="455" alt="image" src="https://github.com/user-attachments/assets/c85e1ecf-171d-4ff6-b240-afa5fa730fca" />
<img width="589" height="455" alt="image" src="https://github.com/user-attachments/assets/f9143072-16cd-4daf-8861-f771f60e3f87" />

#### iii. Histogram Equalization of Grayscale Image :
<img width="2048" height="1365" alt="image" src="https://github.com/user-attachments/assets/e88cbf73-a588-4e4e-b63d-645642fa75b4" />

## Result : 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.

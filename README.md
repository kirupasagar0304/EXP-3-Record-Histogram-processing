# NAME: Kirupasagar S
# REG.No: 212224230126

# EXP-3:Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---

## Program


1.Import Neccessary Libraies
~~~
import cv2
import numpy as np
import matplotlib.pyplot as plt
~~~
2.Read the image file and display it
~~~
img = cv2.imread('image,jpg',cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('original_image')
plt.show()
~~~
3.Read and display the image in grayscale format
~~~
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
~~~
4. Perform histogram equalization
~~~
img_eq = cv2.equalizeHist(img)
~~~
5. Display [1] the Original Image (Gray Image) and its Histogram, and [2] the Enhanced Image and its Histogram using a 2×2 layout in Matplotlib.
~~~
plt.hist(img_eq.ravel(), 256, range = [0, 256]); 
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('original image')
plt.show()
~~~
6. Read the colorgiven eagle.jpeg image.
~~~
img = cv2.imread('eagle.jpeg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
~~~
7.Convert to HSV.
~~~
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
~~~
8.Perform histogram equalization
~~~
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
~~~
9.Convert back to BGR format and display it
~~~
plt.subplot(121); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(122); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')

plt.figure(figsize = [12,10])
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.subplot(223); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(224); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
~~~
##  Output
<img width="561" height="401" alt="bc959ce4-487f-4daa-9b60-f9fce78c9322" src="https://github.com/user-attachments/assets/2cc1ba2b-6d9d-4355-aea4-b11cb5348027" />
<img width="556" height="434" alt="3ed9afce-9deb-427e-85c4-c02f79f042ac" src="https://github.com/user-attachments/assets/d453a63d-5b5f-4289-a443-b8884f426a76" />
<img width="556" height="434" alt="6793daa6-184a-4b9b-9018-8f8bb25df56d" src="https://github.com/user-attachments/assets/1dbab9e3-91b3-42d4-b324-06daa91f0746" />
<img width="561" height="401" alt="3d5c2113-3f8e-437d-bb34-ccbf5aa8d7d9" src="https://github.com/user-attachments/assets/ead8c205-a984-4513-8f73-6dfba9d76355" />
<img width="561" height="401" alt="f2e48b6b-9767-4a1c-95b0-6ae69bba6739" src="https://github.com/user-attachments/assets/ad245e73-31e6-4c5d-94bf-91e746abde7b" />
<img width="547" height="434" alt="92449d08-3008-44a2-8f5e-4a616a4d2671" src="https://github.com/user-attachments/assets/85523f7d-9cbd-48c8-b9ed-a5c99f8e2ab8" />
<img width="547" height="434" alt="76c102c6-82cd-409a-bc93-250844a98609" src="https://github.com/user-attachments/assets/701a424f-8e6e-4338-a582-b6ddff222e3e" />

### Grayscale Histogram Equalization

- Original grayscale image is displayed  
- Histogram of original grayscale image is plotted  
- Enhanced image after histogram equalization is displayed  
- Histogram of enhanced grayscale image shows improved contrast  

### Color Image Histogram Equalization

- Original color image is displayed  
- Histogram of B, G, R channels is plotted  
- Enhanced image after HSV-based equalization is displayed  
- Histogram of enhanced image shows better intensity distribution  

---

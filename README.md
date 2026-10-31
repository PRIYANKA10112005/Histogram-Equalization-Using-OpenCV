# Histogram Equalization Using OpenCV (Grayscale & Color Images)

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
```PY
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread("parrot.jpg.jpeg", cv2.IMREAD_GRAYSCALE)
img.shape
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
img = cv2.imread('parrot.jpg.jpeg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
```

### Developed By:
**Name:** PRIYANKA P

### Register No:
212224230212
---

##  Output

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

### Original Grayscale Image
<img width="763" height="497" alt="image" src="https://github.com/user-attachments/assets/edf65353-edee-494a-9f44-7638665be3a2" />


### Histogram of Original Grayscale Image
<img width="863" height="548" alt="image" src="https://github.com/user-attachments/assets/a4f895fb-7089-422e-8449-20ae58f24634" />


### Histogram Equalization
<img width="783" height="528" alt="image" src="https://github.com/user-attachments/assets/b4566e34-28f2-4612-9a47-85dd6f94a5b6" />


### Equalized Grayscale Image
<img width="756" height="500" alt="image" src="https://github.com/user-attachments/assets/0e5826d4-14fc-481f-8520-1a7ca996c7d6" />


### Original Color Image
<img width="743" height="502" alt="image" src="https://github.com/user-attachments/assets/d0fbb20e-630a-4061-947d-7490c02bf4f7" />

### Histogram Equalized Color Image
<img width="736" height="492" alt="image" src="https://github.com/user-attachments/assets/183500de-3d80-49ef-b9c9-9f1f4f2a03b6" />

### Histogram of Equalized Color Image
<img width="757" height="525" alt="image" src="https://github.com/user-attachments/assets/98dbd056-cc08-4a88-b5f0-c91a68c090f1" />


---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.

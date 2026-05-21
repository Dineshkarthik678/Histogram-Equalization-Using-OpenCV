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

### Developed By:
**Name:** Dinesh Karthik R 

### Register No:
212224230068
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread('pa.jpeg',cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('original_image')
plt.show()

# Read the image in grayscale format
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

# Perform histogram equalization
img_eq = cv2.equalizeHist(img)

# Display [1] the Original Image (Gray Image) and its Histogram, and [2] the Enhanced Image and its Histogram using a 2×2 layout in Matplotlib.

plt.hist(img_eq.ravel(), 256, range = [0, 256]); 
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('original image')
plt.show()

# Read the colorgiven parrot.jpg image.

img = cv2.imread('pa.jepg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

# Convert to HSV.
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])

# Perform histogram equalization

img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

# Convert back to BGR format

plt.subplot(121); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(122); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')

plt.figure(figsize = [12,10])
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.subplot(223); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(224); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

---

##  Output
## ORIGINAL IMAGE
<img width="1046" height="607" alt="image" src="https://github.com/user-attachments/assets/cdb75a1a-8a8b-484f-a4c9-9b043daebf2c" />
<img width="1239" height="636" alt="image" src="https://github.com/user-attachments/assets/ff69f85d-eaa6-40cd-907c-3caea5181c16" />


## Equalised Histogram
<img width="1161" height="588" alt="image" src="https://github.com/user-attachments/assets/d544936c-f063-4a8f-8b4a-daf63a68348a" />
<img width="1365" height="617" alt="image" src="https://github.com/user-attachments/assets/8f2862e8-4b0d-4c03-be16-ed2daf73da15" />
<img width="1070" height="501" alt="image" src="https://github.com/user-attachments/assets/ca19e62c-7ec3-4cb2-be36-b3494e76baf8" />
<img width="1230" height="595" alt="image" src="https://github.com/user-attachments/assets/58ba95c4-be50-4920-b737-8007ffe7f94b" />




##  Histogram of Grayscale Image and any channel of Color Image
<img width="1551" height="531" alt="image" src="https://github.com/user-attachments/assets/45aa1ccc-e53d-40bc-99d9-607927a178a2" />

##  Histogram Equalization of Grayscale Image.
<img width="1508" height="464" alt="image" src="https://github.com/user-attachments/assets/9a7ecadf-999a-4bde-9549-70ef172fe350" />


---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.

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
img = cv2.imread('dk.jpg',cv2.IMREAD_GRAYSCALE)
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

img = cv2.imread('dk.jpg', cv2.IMREAD_COLOR)

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
<img width="1256" height="694" alt="image" src="https://github.com/user-attachments/assets/dbf35f16-07f4-4a75-bd10-301d197cbddb" />
<img width="985" height="726" alt="image" src="https://github.com/user-attachments/assets/b8c5f59e-e0f2-4866-bbfe-0d18a13581ad" />

## Equalised Histogram

<img width="938" height="589" alt="image" src="https://github.com/user-attachments/assets/9d6a1292-69eb-4a68-8bce-c7dd78ab0136" />
<img width="987" height="645" alt="image" src="https://github.com/user-attachments/assets/e7b27d5a-7077-45e7-9f18-9d69e7b9fbb4" />

<img width="993" height="650" alt="image" src="https://github.com/user-attachments/assets/7f627ff4-114b-4253-a5e5-f2c48ae61f1c" />
<img width="1005" height="606" alt="image" src="https://github.com/user-attachments/assets/ef4264d7-e0b8-4b48-b3ee-f57696ff5a4c" />

##  Histogram of Grayscale Image and any channel of Color Image
<img width="1000" height="473" alt="image" src="https://github.com/user-attachments/assets/21a222b0-083b-4a1b-8c84-60291c7f098c" />

##  Histogram Equalization of Grayscale Image.
<img width="999" height="415" alt="image" src="https://github.com/user-attachments/assets/5f8c2bfc-d422-44f8-b676-222e9e952e02" />


---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.

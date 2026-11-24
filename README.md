<img width="705" height="550" alt="image" src="https://github.com/user-attachments/assets/dae8c09f-af24-4d59-bfc9-63870f400842" /># EXPERIMENT 8

# IMAGE SEGMENTATION USING THRESHOLDING TECHNIQUES IN OPENCV

## AIM

To segment an image using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques using Python and OpenCV.

The program performs the following operations:

- Global Thresholding
- Adaptive Thresholding
- Otsu's Thresholding

## SOFTWARE USED

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## ALGORITHM

### Step 1: Import Libraries

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2: Load the Input Image

Read the input image using OpenCV.

### Step 3: Convert to Grayscale

Convert the input image into grayscale format.

### Step 4: Global Thresholding

- Select a fixed threshold value.
- Apply thresholding to separate foreground and background pixels.
- Display the thresholded image.

### Step 5: Adaptive Thresholding

- Compute threshold values for small regions of the image.
- Apply Adaptive Mean Thresholding.
- Apply Adaptive Gaussian Thresholding.
- Display the segmented images.

### Step 6: Otsu's Thresholding

- Automatically determine the optimal threshold value.
- Apply Otsu's thresholding technique.
- Display the segmented image.

### Step 7: Compare Results

Compare the results obtained from Global, Adaptive, and Otsu's thresholding methods.

## PROGRAM

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the input image
img = cv2.imread("flower.jpg")

if img is None:
    raise FileNotFoundError("Image not found!")

# Convert image to grayscale
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

# Display Original Grayscale Image
plt.figure(figsize=(6, 5))
plt.imshow(gray, cmap="gray")
plt.title("Original Grayscale Image")
plt.axis("off")
plt.show()

# Global Thresholding
_, global_thresh = cv2.threshold(gray, 127, 255, cv2.THRESH_BINARY)

plt.figure(figsize=(10, 5))
plt.subplot(1, 2, 1)
plt.imshow(gray, cmap="gray")
plt.title("Original Grayscale")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(global_thresh, cmap="gray")
plt.title("Global Thresholding")
plt.axis("off")
plt.tight_layout()
plt.show()

# Adaptive Mean Thresholding
adaptive_mean = cv2.adaptiveThreshold(
    gray, 255,
    cv2.ADAPTIVE_THRESH_MEAN_C,
    cv2.THRESH_BINARY,
    11, 2
)

# Adaptive Gaussian Thresholding
adaptive_gaussian = cv2.adaptiveThreshold(
    gray, 255,
    cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY,
    11, 2
)

plt.figure(figsize=(12, 5))
plt.subplot(1, 3, 1)
plt.imshow(gray, cmap="gray")
plt.title("Original Grayscale")
plt.axis("off")

plt.subplot(1, 3, 2)
plt.imshow(adaptive_mean, cmap="gray")
plt.title("Adaptive Mean Thresholding")
plt.axis("off")

plt.subplot(1, 3, 3)
plt.imshow(adaptive_gaussian, cmap="gray")
plt.title("Adaptive Gaussian Thresholding")
plt.axis("off")

plt.tight_layout()
plt.show()

# Otsu's Thresholding
otsu_value, otsu_thresh = cv2.threshold(
    gray, 0, 255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)

print("Otsu Threshold Value:", otsu_value)

plt.figure(figsize=(10, 5))
plt.subplot(1, 2, 1)
plt.imshow(gray, cmap="gray")
plt.title("Original Grayscale")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(otsu_thresh, cmap="gray")
plt.title("Otsu's Thresholding")
plt.axis("off")

plt.tight_layout()
plt.show()

# Comparison of all thresholding techniques
images = [
    gray,
    global_thresh,
    adaptive_mean,
    adaptive_gaussian,
    otsu_thresh
]

titles = [
    "Original Grayscale",
    "Global Thresholding",
    "Adaptive Mean",
    "Adaptive Gaussian",
    "Otsu's Thresholding"
]

plt.figure(figsize=(15, 8))

for i in range(len(images)):
    plt.subplot(2, 3, i + 1)
    plt.imshow(images[i], cmap="gray")
    plt.title(titles[i])
    plt.axis("off")

plt.tight_layout()
plt.show()
```

## DEVELOPED BY

**Name:** Mohammed Ameer F

**Register No:** 212225040248

## OUTPUT

### 1. Original Grayscale Image

- The grayscale version of the input image is displayed.
  <img width="717" height="547" alt="image" src="https://github.com/user-attachments/assets/40f43b4b-3ee7-41d2-ba72-1a46c6c1a047" />

  

### 2. Global Thresholding

- Original image is displayed.
  <img width="735" height="506" alt="image" src="https://github.com/user-attachments/assets/3ca046de-9353-4830-9621-f3de71be592f" />

- Thresholded image is displayed.
  <img width="855" height="567" alt="image" src="https://github.com/user-attachments/assets/92137139-66cf-4b2a-955c-292ff8596ae2" />


### 3. Adaptive Thresholding

- Original image is displayed.
  <img width="562" height="582" alt="image" src="https://github.com/user-attachments/assets/a65e6bd9-0c5f-436e-81b5-c22a4f4e6aa8" />

- Adaptive Mean Thresholded image is displayed.
  <img width="652" height="548" alt="image" src="https://github.com/user-attachments/assets/d7a08262-2140-4e30-b118-21b49b04bc48" />

- Adaptive Gaussian Thresholded image is displayed.
  <img width="705" height="550" alt="image" src="https://github.com/user-attachments/assets/b5597357-f0e0-4a52-91ca-c32eb30541f6" />



### 4. Otsu's Thresholding

- Original image is displayed.

<img width="562" height="582" alt="image" src="https://github.com/user-attachments/assets/46551681-6e99-4279-859c-10df043ff110" />

- Otsu segmented image is displayed.
  <img width="792" height="600" alt="image" src="https://github.com/user-attachments/assets/e36fd5b1-140f-4ce7-afa8-b8e1c74da8b6" />


### 5. Comparison Output

- All thresholding techniques are displayed together
  <img width="1587" height="738" alt="image" src="https://github.com/user-attachments/assets/bd35843f-b414-4a80-9786-da0f202881f1" />



## RESULT

Thus, image segmentation is successfully performed using **Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding** techniques in OpenCV.

# EXPERIMENT – 5

# Image Smoothing and Sharpening Using OpenCV

---

## Aim

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, and Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result along with the original image for comparison.

---

## Objective

To understand the effect of various smoothing and sharpening techniques in Digital Image Processing using OpenCV.

---

## Software Used

- Python 3.7+
- Jupyter Notebook
- OpenCV (cv2)
- NumPy
- Matplotlib

---

## Filters Implemented

### Smoothing Filters
- Averaging Filter
- Weighted Averaging Filter
- Gaussian Blur
- Median Blur

### Sharpening Filters
- Laplacian Kernel
- Laplacian Operator

---

## Algorithm

### Step 1
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2
Load the input image using `cv2.imread()`.

### Step 3
Convert the image from BGR format to RGB format for proper display.

### Step 4
Apply the Averaging Filter using `cv2.filter2D()` with an averaging kernel.

### Step 5
Apply the Weighted Averaging Filter using a weighted kernel and `cv2.filter2D()`.

### Step 6
Apply Gaussian Blur using `cv2.GaussianBlur()`.

### Step 7
Apply Median Blur using `cv2.medianBlur()`.

### Step 8
Apply Laplacian Sharpening using a custom Laplacian kernel.

### Step 9
Apply the Laplacian Operator using `cv2.Laplacian()`.

### Step 10
Display the original and processed images for comparison.

---

# Program

### NAME
**DEEPAK SUDHARSHAN B**

### REG. NO.
**212225230045**

---

## Import Required Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

---

## Step 1 – Read the Input Image

```python
image1 = cv2.imread("myimage.jpeg")
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)
```

### Output

<img width="930" height="391" alt="image" src="https://github.com/user-attachments/assets/cde03800-fce1-4aef-a8cd-d9f0c6ee1c91" />

---

## Step 2 – Averaging Filter

```python
kernel = np.ones((11,11), np.float32) / 169

image3 = cv2.filter2D(image2, -1, kernel)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter")
plt.axis("off")

plt.show()
```

### Output

<img width="460" height="402" alt="image" src="https://github.com/user-attachments/assets/48d8b378-a286-4cf4-9624-c28a7a2e2d31" />


---

## Step 3 – Weighted Averaging Filter

```python
kernel1 = np.array([[1,2,1],
                    [2,4,2],
                    [1,2,1]]) / 16

image3 = cv2.filter2D(image2, -1, kernel1)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter")
plt.show()
```

### Output

<<img width="658" height="287" alt="image" src="https://github.com/user-attachments/assets/e1173ac1-179f-415e-96a0-e5ad506fa245" />


---

## Step 4 – Gaussian Blur

```python
gaussian_blur = cv2.GaussianBlur(image2, (33,33), 0)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")

plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")

plt.show()
```

### Output

****<img width="642" height="287" alt="image" src="https://github.com/user-attachments/assets/8e6578cb-9b70-4ad3-a10c-514efc0d1928" />


---

## Step 5 – Median Blur

```python
median = cv2.medianBlur(image2, 13)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")

plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")

plt.show()
```

### Output

<img width="891" height="401" alt="image" src="https://github.com/user-attachments/assets/2dc39777-4f45-45fb-85df-e73f5733e88a" />


---

## Step 6 – Laplacian Kernel

```python
kernel2 = np.array([
    [-1,-1,-1],
    [ 2,-2, 1],
    [ 2, 1,-1]
])

image3 = cv2.filter2D(image2, -1, kernel2)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")

plt.show()
```

### Output

<img width="653" height="315" alt="image" src="https://github.com/user-attachments/assets/ffb1fd08-6e9a-4a76-b38e-de6a900c1005" />


---

## Step 7 – Laplacian Operator

```python
laplacian = cv2.Laplacian(image2, cv2.CV_64F)

plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")

plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")

plt.show()
```

### Output

<img width="663" height="295" alt="image" src="https://github.com/user-attachments/assets/208e3cf5-4ecc-44b2-86a6-365256cb3cdf" />


---

## Applications

- Noise Reduction
- Medical Image Processing
- Satellite Image Enhancement
- Computer Vision
- Face Recognition
- Image Restoration
- Edge Detection
- Object Detection
- Image Preprocessing for Machine Learning

---

## Result

Thus, image smoothing and sharpening operations were successfully implemented using OpenCV. The smoothing filters effectively reduced image noise while preserving important features, and the sharpening filters enhanced edges and fine details, making the images more suitable for further image processing and computer vision applications.

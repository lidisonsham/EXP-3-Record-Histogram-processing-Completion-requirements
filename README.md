# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image.
- Plot histogram of the grayscale image.
- Apply histogram equalization on the grayscale image.
- Read and display a color image.
- Convert the image to HSV color space.
- Apply histogram equalization on the Value (V) channel.
- Convert the enhanced image back to BGR format.
- Display original and enhanced images along with their histograms.

---

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook
- OpenCV (`cv2`)
- NumPy
- Matplotlib

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image in grayscale mode.

### Step 3:
Display the grayscale image.

### Step 4:
Plot the histogram of the grayscale image.

### Step 5:
Apply histogram equalization using `cv2.equalizeHist()`.

### Step 6:
Display the equalized histogram and enhanced grayscale image.

### Step 7:
Read the same image in color mode.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization to the V (Value) channel.

### Step 10:
Convert the enhanced HSV image back to BGR format.

### Step 11:
Display the original color image, equalized image, and their histograms.

---

# Program

### Developed By:
**Name:** LIDISON SHAM M

### Register No:
**212224040171**

---

## 1. Import the required libraries and read the grayscale image.

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('parrot.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```

---

## 2. Plot the histogram of the grayscale image.

```python
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Image Histogram')
plt.show()
```

---

## 3. Apply histogram equalization.

```python
img_eq = cv2.equalizeHist(img)
```

---

## 4. Display the histogram of the equalized image.

```python
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Equalized Histogram')
plt.show()
```

---

## 5. Display the equalized grayscale image.

```python
plt.imshow(img_eq, cmap='gray')
plt.title('Equalized Image')
plt.show()
```

---

## 6. Read the image in color mode and convert to HSV.

```python
img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
```

---

## 7. Apply histogram equalization to the V channel.

```python
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])
```

---

## 8. Convert the enhanced HSV image back to BGR.

```python
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
```

---

## 9. Display the original and equalized color images.

```python
plt.subplot(121)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(122)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.show()
```

---

## 10. Display the original and equalized images along with their histograms.

```python
plt.figure(figsize=[12,10])

plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.subplot(223)
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Histogram')

plt.subplot(224)
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Histogram Equalized')

plt.show()
```

---

## Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed.
<img width="392" height="532" alt="image" src="https://github.com/user-attachments/assets/bf6f3e8c-63b3-4cf6-910e-812bf2602455" />


- Histogram of the original grayscale image is plotted.
<img width="837" height="586" alt="image" src="https://github.com/user-attachments/assets/ac02a7e7-0dc3-44f1-8c69-c16918566fab" />

- Histogram of the equalized image shows improved contrast.
<img width="888" height="597" alt="image" src="https://github.com/user-attachments/assets/110808fa-6c00-4caa-841c-8ae545124816" />

### Color Image Histogram Equalization
<img width="857" height="521" alt="image" src="https://github.com/user-attachments/assets/872f15e1-8abd-4766-b97f-075fab7d3af6" />

## Result

Thus, histogram equalization was successfully performed on both grayscale and color images using OpenCV. The contrast of the images was enhanced, improving the overall visual quality.

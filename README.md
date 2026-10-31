# EX.No-6-EDGE-DETECTION
# Developed By: BUSHPIAK C
# Register Number: 212225230038


## Aim

To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Import all the necessary modules for the program.

### Step 2
Load an image using the `cv2.imread()` function.

### Step 3
Convert the image into grayscale using `cv2.cvtColor()`.

### Step 4
Use the Sobel operator from OpenCV to detect the edges of the image in the horizontal and vertical directions.

### Step 5
Use the Laplacian operator to detect edges based on second-order derivatives.

### Step 6
Use the Canny operator to detect edges in the image.

### Step 7
Display the edge-detected images using Matplotlib.

## Program

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('bushpika.jpeg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('on')

sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('on')

laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('on')

canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('on')  
```

## Output

### Input Image 

<img width="366" height="497" alt="image" src="https://github.com/user-attachments/assets/25d96597-1882-460f-9c66-9d975ebbe425" />


### 1. Sobel Edge Detector


<img width="386" height="492" alt="image" src="https://github.com/user-attachments/assets/a4a5efa6-899a-4850-a6ef-2a104fbc3b04" />



### 2. Laplacian Edge Detector


<img width="351" height="487" alt="image" src="https://github.com/user-attachments/assets/32d0743a-4c2d-45ae-8f69-0fc5858881b2" />



### 3. Canny Edge Detector

<img width="372" height="496" alt="image" src="https://github.com/user-attachments/assets/78f6aa05-a29d-460b-aea3-e7bf31ddd24e" />



## Result

Thus, the edges of the image were detected successfully using Sobel, Laplacian, and Canny edge detectors with OpenCV and Python.

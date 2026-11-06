# EXPERIMENT 6 – EDGE DETECTION

# Name:Raha Priya Dharshini M
# Reg no: 212224240124


## Aim
To perform edge detection on an image using Sobel, Laplacian and Canny edge detection techniques with OpenCV.

## Software Requirements
- Python
- OpenCV
- NumPy
- Matplotlib
- Jupyter Notebook

## Procedure
1. Import the required libraries.
2. Read the input image and convert it into grayscale.
3. Apply Sobel edge detection in both X and Y directions.
4. Combine the Sobel results to obtain the detected edges.
5. Apply Laplacian edge detection to identify edges in the image.
6. Apply Canny edge detection using threshold values of 50 and 150.
7. Display the results of all three edge detection techniques.

## Code 
```

import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('tiger.jpeg')

if image is None:
    raise FileNotFoundError("tiger.jpeg not found")

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.figure(figsize=(8, 6))
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
plt.show()

sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)
sobel_combined = cv2.magnitude(sobel_x, sobel_y)

plt.figure(figsize=(8, 6))
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
plt.show()

laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)

plt.figure(figsize=(8, 6))
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
plt.show()

canny_edges = cv2.Canny(gray_image, 50, 150)

plt.figure(figsize=(8, 6))
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
plt.show()
```

## Output

### 1. Original Image
<img width="1337" height="516" alt="image" src="https://github.com/user-attachments/assets/5e9aa394-4afb-4892-9234-79d07a1a0fed" />


### 2. Sobel Edge Detection
<img width="1346" height="522" alt="image" src="https://github.com/user-attachments/assets/969d8997-40cb-450d-9dce-80ece390d407" />


### 3. Laplacian Edge Detection
<img width="1350" height="506" alt="image" src="https://github.com/user-attachments/assets/7d992415-4847-4b0a-9de0-bfa72c24e23a" />


### 4. Canny Edge Detection
<img width="1360" height="527" alt="image" src="https://github.com/user-attachments/assets/85906c26-7af4-4ebb-a28a-09d53b0e5abf" />


## Result
Thus, edge detection was successfully performed using Sobel, Laplacian and Canny techniques in Python with OpenCV.

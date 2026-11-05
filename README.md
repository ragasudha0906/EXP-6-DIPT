# EXP 06 - Record-EDGE DETECTION
## NAME: RAGASUDHA R
## REG NO: 212224230215

## AIM

To implement edge detection techniques such as Sobel, Laplacian, and Canny using OpenCV and Python to identify the edges in an image.

## PROCEDURE

1. Import the required libraries such as OpenCV, NumPy, and Matplotlib.

2. Read the input image using cv2.imread().

3. Convert the original image into a grayscale image using cv2.cvtColor().

4. Apply the Sobel operator in the X and Y directions to detect edges.

5. Combine both Sobel outputs using cv2.magnitude().

6. Apply the Laplacian operator to detect edges in the image.

7. Apply the Canny edge detection technique using cv2.Canny().

8. Display the original image and the detected edges using Matplotlib.

## CODE
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('photo.jpeg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
```
## OUTPUT
<img width="1092" height="562" alt="image" src="https://github.com/user-attachments/assets/33aba55e-aa32-4596-991c-bd1e3a4213d0" />
<img width="1152" height="552" alt="image" src="https://github.com/user-attachments/assets/25feae8d-5ac5-4d5d-88dc-de9812499c58" />
<img width="1172" height="561" alt="image" src="https://github.com/user-attachments/assets/a39469f4-7612-4959-9ad8-123fca0504cc" />
<img width="1137" height="560" alt="image" src="https://github.com/user-attachments/assets/5f40b0eb-7db3-4435-95cf-31e15a058ba5" />

## RESULT
Thus, the edge detection techniques such as Sobel, Laplacian, and Canny were successfully implemented using OpenCV and Python. The edges of the input image were detected and displayed successfully.

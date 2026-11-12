# EX.NO:06 - edge-detection-opencv

## Aim

To perform edge detection using Sobel, Roberts, Prewitt, Laplacian, and Canny edge detectors.

---

## Software Required

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

## ⚙️ Algorithm

### Step 1:
Import all the necessary modules for the program.

### Step 2:
Load an image using `cv2.imread()`.

### Step 3:
Convert the image to grayscale.

### Step 4:
Apply **Sobel operator** using OpenCV to detect edges.

### Step 5:
Apply **Prewitt operator** using custom kernels.

### Step 6:
Apply **Roberts operator** using custom kernels.

### Step 7:
Apply **Laplacian operator** using OpenCV.

### Step 8:
Apply **Canny edge detector** using OpenCV.

### Step 9:
Display all edge-detected images for comparison.

---

## Program & Output:

## Developed By

- **Name:** Sanjai R 
- **Register No:** 212223040180


```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('me.jpg')  # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
```

<img width="306" height="410" alt="50dd1c5c-668a-4ac8-9711-a6fc053effc9" src="https://github.com/user-attachments/assets/89f1ac79-8e0e-4737-8c92-d3e20e823a87" />


```
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
```

<img width="306" height="410" alt="516ef069-c477-4ce6-a052-746976b3f0ba" src="https://github.com/user-attachments/assets/325fc80c-d50a-4ab8-85c6-756d9b477bab" />


```
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
```

<img width="306" height="410" alt="12037cd2-302d-4d99-a222-34ceb1872cf3" src="https://github.com/user-attachments/assets/8080a49f-1038-49c5-8301-f4e90612ada9" />



```
canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')  
```

<img width="306" height="410" alt="292ad6f4-2c13-4e91-99f4-5e7da0351386" src="https://github.com/user-attachments/assets/1b7f567e-dddf-4236-bf4d-528c8eeacedd" />


---


## Result

Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.

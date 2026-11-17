# edge-detection-opencv

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

## Developed By

- **Name:** Hemalatha.A
- **Register No:** 212224240056

---

## Output

```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('Qn6_.tif') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
```
<img width="700" height="543" alt="image" src="https://github.com/user-attachments/assets/cfb3e832-59d2-41d4-b18c-c75d533142d9" />

###  Sobel Edge Detector
```
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
```
<img width="701" height="537" alt="image" src="https://github.com/user-attachments/assets/97159ebd-4694-4d27-8573-868bb9941640" />

###  Prewitt Edge Detector
```
image = cv2.imread("Qn6_.tif")

gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
prewitt_x = np.array([[1, 0, -1],
                      [1, 0, -1],
                      [1, 0, -1]])

prewitt_y = np.array([[1, 1, 1],
                      [0, 0, 0],
                      [-1, -1, -1]])

prewitt_x_edge = cv2.filter2D(gray, -1, prewitt_x)
prewitt_y_edge = cv2.filter2D(gray, -1, prewitt_y)
prewitt = cv2.magnitude(prewitt_x_edge.astype(np.float32),
                        prewitt_y_edge.astype(np.float32))

plt.imshow(Canny_edges, cmap='gray')
plt.title('Prewitt Edge Detection')
plt.axis('off')
```
<img width="680" height="548" alt="image" src="https://github.com/user-attachments/assets/e987cea8-dae8-46c8-bc0e-8c032d8ff336" />

###  Roberts Edge Detector
 ```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Roberts masks
roberts_x = np.array([[1, 0],
                      [0, -1]])

roberts_y = np.array([[0, 1],
                      [-1, 0]])

# Apply Roberts operator
edge_x = cv2.filter2D(gray_image, cv2.CV_64F, roberts_x)
edge_y = cv2.filter2D(gray_image, cv2.CV_64F, roberts_y)

# Combine edges
roberts_combined = cv2.magnitude(edge_x, edge_y)

# Display output
plt.imshow(roberts_combined, cmap='gray')
plt.title('Roberts Edge Detection')
plt.axis('off')
plt.show()
 ```
<img width="732" height="518" alt="image" src="https://github.com/user-attachments/assets/4abf15b8-4ab7-4fef-bae3-9bb01dcbfd95" />

###  Laplacian Edge Detector
```
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)

plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
plt.show()
```
<img width="651" height="511" alt="image" src="https://github.com/user-attachments/assets/86237685-af54-4586-bb3c-b35cfa43b333" />


###  Canny Edge Detector
```
Canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(Canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
```
<img width="676" height="535" alt="image" src="https://github.com/user-attachments/assets/4e2fd1c4-6fe3-4113-82d1-58041d97bd6c" />


---

## Result

Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.

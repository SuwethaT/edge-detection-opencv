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

- **Name: Suwetha T
- **Register No: 212225040446
---
### Program

1) Displaying Original Image
---
import cv2

import numpy as np

import matplotlib.pyplot as plt

img = cv2.imread('duck.jpg')

if img is None:
    raise FileNotFoundError("Image not found! Check the image filename.")

img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

plt.figure(figsize=(6,6))

plt.imshow(img_rgb)

plt.title("Original Image")

plt.axis("off")

plt.show()
---
2) Sobel edge detection
---
import cv2

import numpy as np

import matplotlib.pyplot as plt

img = cv2.imread('duck.jpg')

if img is None:
    raise FileNotFoundError("Image not found!")

gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

sobel_x = cv2.Sobel(gray, cv2.CV_64F, 1, 0, ksize=3)

sobel_y = cv2.Sobel(gray, cv2.CV_64F, 0, 1, ksize=3)

sobel = cv2.magnitude(sobel_x, sobel_y)

sobel = cv2.convertScaleAbs(sobel)

plt.figure(figsize=(12,5))

plt.subplot(1,3,1)

plt.imshow(gray, cmap='gray')

plt.title("Grayscale Image")

plt.axis("off")

plt.subplot(1,3,2)

plt.imshow(sobel_x, cmap='gray')

plt.title("Sobel X")

plt.axis("off")

plt.subplot(1,3,3)

plt.imshow(sobel_y, cmap='gray')

plt.title("Sobel Y")

plt.axis("off")

plt.show()

plt.figure(figsize=(6,6))

plt.imshow(sobel, cmap='gray')

plt.title("Sobel Edge Detection")

plt.axis("off")

plt.show()
---
3) Laplacian Edge detection
---
import cv2

import numpy as np

import matplotlib.pyplot as plt

img = cv2.imread('duck.jpg')

if img is None:
    raise FileNotFoundError("Image not found!")

gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

laplacian = cv2.Laplacian(gray, cv2.CV_64F)

laplacian = cv2.convertScaleAbs(laplacian)

plt.figure(figsize=(10,5))

plt.subplot(1,2,1)

plt.imshow(gray, cmap='gray')

plt.title("Original Grayscale Image")

plt.axis("off")

plt.subplot(1,2,2)

plt.imshow(laplacian, cmap='gray')

plt.title("Laplacian Edge Detection")

plt.axis("off")

plt.show()
---
4) Canny edge detection
---
import cv2

import matplotlib.pyplot as plt

img = cv2.imread('duck.jpg')

if img is None:
    raise FileNotFoundError("Image not found!")

gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

blur = cv2.GaussianBlur(gray, (5,5), 0)

canny = cv2.Canny(blur, 100, 200)

plt.figure(figsize=(10,5))

plt.subplot(1,2,1)

plt.imshow(gray, cmap='gray')

plt.title("Original Grayscale Image")

plt.axis("off")

plt.subplot(1,2,2)

plt.imshow(canny, cmap='gray')

plt.title("Canny Edge Detection")

plt.axis("off")

plt.show()
---
## Output
---
<img width="393" height="697" alt="image" src="https://github.com/user-attachments/assets/75824e22-2c6b-4f3e-8eab-933f462c27e8" />

<img width="477" height="683" alt="image" src="https://github.com/user-attachments/assets/2e995835-301b-4bf7-826f-307cfff9bff8" />

<img width="1332" height="611" alt="image" src="https://github.com/user-attachments/assets/c7579ef1-57f5-489b-9b05-8d84237323aa" />

<img width="1008" height="571" alt="image" src="https://github.com/user-attachments/assets/5a681e99-bbe9-4a2e-8bb1-afa52fb955e7" />

###  Sobel Edge Detector
- Detects edges in horizontal and vertical directions  
- Produces gradient-based edge map  

###  Prewitt Edge Detector
- Similar to Sobel but simpler kernel  
- Detects directional edges  

###  Roberts Edge Detector
- Detects edges using diagonal gradients  
- Sensitive to noise  

###  Laplacian Edge Detector
- Detects edges using second-order derivatives  
- Highlights rapid intensity changes  

###  Canny Edge Detector
- Multi-stage edge detection  
- Produces clean and thin edges  

---

## Result

Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.

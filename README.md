# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import required libraries Use OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2
Read input image Load the image in grayscale or color depending on the filter requirements. 

### Step3
Apply smoothing filters Use averaging, weighted averaging, Gaussian, and median filters to reduce noise.

### Step4
Apply sharpening filters Use Laplacian kernel and Laplacian operator to enhance edges and fine details

### Step5
Display results Show original and filtered images side by side using Matplotlib for comparison.

## Program:
### Developed By   : T.Kajenderan
### Register Number:212225040163


### 1. Smoothing Filters

i) Using Averaging Filter
```Python
import cv2
import matplotlib.pyplot as plt

# Load the image
img = cv2.imread("korako waguri.jpg")

# Check whether image was loaded
if img is None:
    print("Error: Image not found. Check the file name/path.")
else:
    # Apply Averaging Filter
    avg_filter = cv2.blur(img, (5, 5))

    # Display the filtered image
    plt.imshow(cv2.cvtColor(avg_filter, cv2.COLOR_BGR2RGB))
    plt.title("Averaging Filter")
    plt.axis("off")
    plt.show()



```
ii) Using Weighted Averaging Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Weighted Averaging Filter
kernel = np.ones((5, 5), np.float32) / 25
weighted_filter = cv2.filter2D(img, -1, kernel)

# Display the filtered image
plt.imshow(cv2.cvtColor(weighted_filter, cv2.COLOR_BGR2RGB))
plt.title("Weighted Averaging Filter")
plt.axis("off")
plt.show()




```
iii) Using Gaussian Filter
```Python
import cv2
import matplotlib.pyplot as plt

# Load image
img = cv2.imread("korako waguri.jpg")

# Gaussian Filter
gaussian_filter = cv2.GaussianBlur(img, (5, 5), 0)

# Display result
plt.imshow(cv2.cvtColor(gaussian_filter, cv2.COLOR_BGR2RGB))
plt.title("Gaussian Filter")
plt.axis("off")
plt.show()




```
iv)Using Median Filter
```Python
import cv2
import matplotlib.pyplot as plt

# Load image
img = cv2.imread("korako waguri.jpg")

# Median Filter
median_filter = cv2.medianBlur(img, 5)

# Display result
plt.imshow(cv2.cvtColor(median_filter, cv2.COLOR_BGR2RGB))
plt.title("Median Filter")
plt.axis("off")
plt.show()




```

### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load image
img = cv2.imread("korako waguri.jpg")

# Laplacian Kernel (Sharpening)
laplacian_kernel = np.array([
    [0, -1, 0],
    [-1, 5, -1],
    [0, -1, 0]
])

laplacian_kernel_output = cv2.filter2D(img, -1, laplacian_kernel)

# Display result
plt.imshow(cv2.cvtColor(laplacian_kernel_output, cv2.COLOR_BGR2RGB))
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()




```
ii) Using Laplacian Operator
```Python
# Laplacian Operator
laplacian_operator = cv2.Laplacian(img, cv2.CV_64F)

# Convert back to uint8 for display
laplacian_operator = cv2.convertScaleAbs(laplacian_operator)

# Display result
plt.imshow(cv2.cvtColor(laplacian_operator, cv2.COLOR_BGR2RGB))
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()



```

## OUTPUT:
### 1. Smoothing Filters

i) Using Averaging Filter
<img width="298" height="408" alt="image" src="https://github.com/user-attachments/assets/fb7b658a-99dc-4daa-bf9c-257ba2abf35b" />


ii)Using Weighted Averaging Filter
<img width="293" height="406" alt="image" src="https://github.com/user-attachments/assets/9465f619-3ec8-454d-a81d-839c42711c2d" />


iii)Using Gaussian Filter
<img width="283" height="416" alt="image" src="https://github.com/user-attachments/assets/acc300a2-f8c4-4d49-9638-1b182eb3409f" />


iv) Using Median Filter
<img width="304" height="423" alt="image" src="https://github.com/user-attachments/assets/d16fce38-dee3-48af-b475-02ff016a1866" />


### 2. Sharpening Filters


i) Using Laplacian Kernal

<img width="261" height="422" alt="image" src="https://github.com/user-attachments/assets/0703549a-c1a0-4278-bee6-4e720dc8c592" />


ii) Using Laplacian Operator

<img width="271" height="413" alt="image" src="https://github.com/user-attachments/assets/e631c943-ec0d-48c1-b933-7004063d4555" />


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.

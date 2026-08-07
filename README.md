# EX-5-Image-Smoothing-and-Sharpening-Using-OpenCV
## Aim
To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

## The program performs the following operations:
Read and display an input image
Apply Averaging filter
Apply Weighted Averaging filter
Apply Gaussian filter
Apply Median filter
Apply Laplacian sharpening using kernel
Apply Laplacian operator
Display all outputs for comparison
## Software Used
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib
## Algorithm
Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2:
Read the input image (e.g., image.jpg).

Step 3:
Convert the image from BGR to RGB format for display.

Step 4:
Apply Averaging Filter using cv2.blur().

Step 5:
Apply Weighted Averaging Filter using a custom kernel with cv2.filter2D().

Step 6:
Apply Gaussian Filter using cv2.GaussianBlur().

Step 7:
Apply Median Filter using cv2.medianBlur().

Step 8:
Apply Laplacian Sharpening using Kernel with cv2.filter2D().

Step 9:
Convert image to grayscale and apply Laplacian Operator using cv2.Laplacian().

Step 10:
Display all filtered images using a grid layout for comparison.

## Developed By
**Name:Mageshwaran T.A
Register No: 212224230146
## Program
```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("batman.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```
<img width="1002" height="462" alt="image" src="https://github.com/user-attachments/assets/b4dd6faa-3e03-43d2-9f2e-64c8c33aaf46" />


```
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()

```
<img width="607" height="532" alt="image" src="https://github.com/user-attachments/assets/b8c2c021-f4c7-4170-bbc9-97f80af6a9bd" />

```
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()

```

<img width="575" height="532" alt="image" src="https://github.com/user-attachments/assets/b1e0d9f8-f073-427c-af72-70b5c3d372aa" />

```

median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()

```

<img width="1027" height="475" alt="image" src="https://github.com/user-attachments/assets/a421a5e7-2569-40f7-9f07-7cd317c76c82" />

```

kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()

```

<img width="667" height="525" alt="image" src="https://github.com/user-attachments/assets/e07481ac-27d9-4fe5-9883-5e15ee5e350e" />

```

laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()

```

<img width="622" height="525" alt="image" src="https://github.com/user-attachments/assets/6bf506aa-8ab5-4be3-b58c-dc535f174ab6" />


## Smoothing Filters
Averaging filter produces blurred image
Weighted averaging provides smoother result with less distortion
Gaussian filter preserves edges better while reducing noise
Median filter removes salt-and-pepper noise effectively
## Sharpening Filters
Laplacian kernel enhances edges and fine details
Laplacian operator detects edges clearly in grayscale
## Result
Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.

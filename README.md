# EXP -8 - Image Segmentation Using Thresholding Techniques in OpenCV

## Developed By : Vignesh S

## Register No: 212223230240

## Aim

To segment an image using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques using Python and OpenCV.

The program performs the following operations:

- Global Thresholding
- Adaptive Thresholding
- Otsu's Thresholding

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Load the input image using OpenCV.

### Step 3:

Convert the input image into grayscale format.

### Step 4: Global Thresholding

- Select a fixed threshold value.
- Apply thresholding to separate foreground and background pixels.
- Display the thresholded image.

### Step 5: Adaptive Thresholding

- Compute threshold values for small regions of the image.
- Apply Adaptive Mean Thresholding.
- Apply Adaptive Gaussian Thresholding.
- Display the segmented images.

### Step 6: Otsu's Thresholding

- Automatically determine the optimal threshold value.
- Apply Otsu's thresholding technique.
- Display the segmented image.

### Step 7:

Compare the results obtained from Global, Adaptive, and Otsu's thresholding methods.


## Program


```
import cv2
import matplotlib.pyplot as plt
img = cv2.imread("highway lane.jpg")
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis("off")
plt.show()
```
```
import cv2
import matplotlib.pyplot as plt
img = cv2.imread("highway lane.jpg", cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap="gray")
plt.title("Original Grayscale Image")
plt.axis("off")
plt.show()
```
```
import cv2
import matplotlib.pyplot as plt
img = cv2.imread("highway lane.jpg", cv2.IMREAD_GRAYSCALE)
_, result = cv2.threshold(img, 127, 255, cv2.THRESH_BINARY)
plt.imshow(result, cmap="gray")
plt.title("Global Thresholding")
plt.axis("off")
plt.show()
```
```
import cv2
import matplotlib.pyplot as plt
img = cv2.imread("highway lane.jpg", cv2.IMREAD_GRAYSCALE)
result = cv2.adaptiveThreshold(
    img, 255,
    cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY,
    11, 2
)
plt.imshow(result, cmap="gray")
plt.title("Adaptive Thresholding")
plt.axis("off")
plt.show()
```
```
import cv2
import matplotlib.pyplot as plt
img = cv2.imread("highway lane.jpg", cv2.IMREAD_GRAYSCALE)
_, result = cv2.threshold(
    img, 0, 255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)
plt.imshow(result, cmap="gray")
plt.title("Otsu's Thresholding")
plt.axis("off")
plt.show()

```
## Output
## Original Image
<img width="516" height="381" alt="image" src="https://github.com/user-attachments/assets/46b799eb-9e8c-49ec-9446-f3d142e9ea4e" />

### Original Grayscale Image

- The grayscale version of the input image is displayed.
- Serves as the input for thresholding operations.

<img width="516" height="381" alt="image" src="https://github.com/user-attachments/assets/df4cfb8c-7519-4ffb-be94-58dc01d7718e" />


### Thresholded Image

- Original image is displayed.
- Thresholded image is displayed.
- A fixed threshold value is used for segmentation.
- Pixels are classified as foreground or background.

<img width="640" height="466" alt="image" src="https://github.com/user-attachments/assets/42c4add3-4f3d-4d31-9eba-b0a6c0d621bc" />

### ROI Masked Image

- Original image is displayed.
- Adaptive Mean Thresholded image is displayed.
- Adaptive Gaussian Thresholded image is displayed.
- Threshold values vary across different regions of the image.
- Suitable for images with uneven illumination.


<img width="640" height="466" alt="image" src="https://github.com/user-attachments/assets/feb9b6cd-4835-4cea-9a58-493bc06bf12d" />


### Otsu's Thresholding / Result of Hough Transform

- Original image is displayed.
- Otsu segmented image is displayed.
- Optimal threshold value is calculated automatically.
- Produces improved segmentation for bimodal histograms.


<img width="516" height="381" alt="image" src="https://github.com/user-attachments/assets/755c038c-b402-4dcd-bba9-a5de6451ad4a" />

<img width="640" height="466" alt="image" src="https://github.com/user-attachments/assets/61b843b4-866f-44ef-89da-78155a1b8890" />

### Result of Hough Transform

<img width="516" height="381" alt="image" src="https://github.com/user-attachments/assets/f21e4834-8ebd-4a4a-a3fd-d0dfbe6c49c2" />

## Result

Thus, image segmentation is successfully performed using **Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding** techniques in OpenCV. 

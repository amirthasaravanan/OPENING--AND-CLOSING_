# OPENING--AND-CLOSING
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm:
### Step1: Read the Image

Load the input color image from a specified path.

### Step2: Convert to Grayscale

Transform the color image into a grayscale format for easier processing.

### Step3: Edge Detection

Apply an edge detection technique to identify the prominent edges in the grayscale image.

### Step4: Create Structuring Element

Define a kernel (structuring element) for use in morphological operations, typically a matrix of ones.

### Step5: Morphological Operations

Perform morphological operations:
Opening: Remove small objects from the edges to clean up the image.
Closing: Fill small holes in the detected edges to enhance the structure.

 
## Program:
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
```PYTHON
# Create a blank image
image = np.zeros((500, 500, 3), dtype=np.uint8)
```
```PYTHON
# Add text on the image using cv2.putText
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, 'Open and Close', (100, 250), font, 1, (255, 255, 255), 2, cv2.LINE_AA)
```
```PYTHON
# Create a simple square kernel (3x3)
kernel = np.ones((3, 3), np.uint8)
```
```PYTHON
# Display the input image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for displaying
plt.title("Input Image with Text")
plt.axis('off')

```
```PYTHON
# Opening is erosion followed by dilation
opened_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)
```
```PYTHON
# Display the result of Opening
plt.imshow(cv2.cvtColor(opened_image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB
plt.title("Opening Operation")
plt.axis('off')
```
```PYTHON
# Closing is dilation followed by erosion
closed_image = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)
```
## Output:

### Display the input Image


<img width="389" height="411" alt="download" src="https://github.com/user-attachments/assets/18924bfd-3b12-4f21-9a39-9ae36fcab4e6" />


### Display the result of Opening


<img width="389" height="411" alt="download" src="https://github.com/user-attachments/assets/2f0dea8d-6377-4472-b866-f6c0329616b2" />




### Display the result of Closing


<img width="389" height="411" alt="download" src="https://github.com/user-attachments/assets/51393a0a-269c-4ed9-8381-7947734152b6" />




## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.

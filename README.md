# Opening and Closing Operations Using OpenCV

Developed By
Name: Yuuvasri R

Register No: 212225230313

# Aim
To write a Python program using OpenCV to perform morphological Opening and Closing operations on an image.

The program performs the following operations:

Morphological Opening
Morphological Closing
Software Used
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib

# Algorithm
Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2:
Create or load an input image containing foreground objects.

Step 3:
Display the original image.

Step 4:
Create a structuring element (kernel) of suitable size.

Step 5: Opening Operation
Apply the Opening operation using the structuring element.
Opening consists of Erosion followed by Dilation.
Remove small foreground noises while preserving the shape of larger objects.
Display the opened image.
Step 6: Closing Operation
Apply the Closing operation using the structuring element.
Closing consists of Dilation followed by Erosion.
Fill small holes and gaps within foreground objects.
Display the closed image.
Step 7:
Compare the original, opened, and closed images.

# Program:

```

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 1: Create a blank black image
image = np.zeros((300, 500), dtype=np.uint8)

# Step 2: Insert white text
cv2.putText(
    image, "MORPHOLOGY", (30, 150),
    cv2.FONT_HERSHEY_SIMPLEX, 1.5, 255, 5
)

# Step 3: Create structuring element (kernel)
kernel = np.ones((5, 5), np.uint8)

# Step 4: Apply Opening Operation
opening = cv2.morphologyEx(
    image, cv2.MORPH_OPEN, kernel
)

# Step 5: Apply Closing Operation
closing = cv2.morphologyEx(
    image, cv2.MORPH_CLOSE, kernel
)

# Step 6: Display all three images
plt.figure(figsize=(15, 5))

plt.subplot(1, 3, 1)
plt.imshow(image, cmap="gray")
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 3, 2)
plt.imshow(opening, cmap="gray")
plt.title("Opening Operation")
plt.axis("off")

plt.subplot(1, 3, 3)
plt.imshow(closing, cmap="gray")
plt.title("Closing Operation")
plt.axis("off")

plt.tight_layout()
plt.show()

```
# OUTPUT:

<img width="1136" height="252" alt="image" src="https://github.com/user-attachments/assets/358f6a1d-dda5-4fcb-b467-0890294f2293" />

# Result
Thus, the morphological operations Opening and Closing are successfully implemented using OpenCV.

# Exp-7-Record-HOUGH-TRANSFORM
# Lane Detection

## Aim

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

---

## Learning Objective

* Understand each stage of image processing
* Learn how to build a complete computer vision pipeline
* Practice writing code in guided sections

**Important Instruction:**
👉 Write code **ONLY in places marked as `# Your Code Here`**
👉 Do NOT modify any other part of the code

---

## Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

---

## Algorithm & Explanation

---

### Step 1: Import Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
Step 2: Read the Image
# Read the image using OpenCV

###
# Your Code Here
###

image = cv2.imread('saveetha.jpg')
Step 3: Convert to Grayscale
# Convert to grayscale.

###
# Your Code Here
###

gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
Step 4: Display Images
plt.figure(figsize=(10,5))

###
# Your Code Here
###

plt.subplot(1, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")

plt.show()
Step 5: Thresholding
# Apply thresholding

threshold = 
###
# Your Code Here
###

threshold = cv2.threshold(
    gray,
    127,
    255,
    cv2.THRESH_BINARY
)[1]
Step 6: Region of Interest (ROI)
# ROI masking already provided
# (Do not modify)
Step 7: Edge Detection (Canny)
# Perform Edge Detection

###
# Your Code Here
###

edges = cv2.Canny(
    gray,
    50,
    150
)

plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detection")
plt.axis("off")
plt.show()
Step 8: Gaussian Blur
# Apply Gaussian Blur

###
# Your Code Here
###

blurred = cv2.GaussianBlur(
    edges,
    (5, 5),
    0
)

plt.imshow(blurred, cmap='gray')
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
Step 9: Hough Transform
# Detect lines using Hough Transform

###
# Your Code Here
###

lines = cv2.HoughLinesP(
    blurred,
    1,
    np.pi / 180,
    threshold=50,
    minLineLength=50,
    maxLineGap=100
)

line_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]

        cv2.line(
            line_image,
            (x1, y1),
            (x2, y2),
            (0, 255, 0),
            3
        )

plt.imshow(
    cv2.cvtColor(
        line_image,
        cv2.COLOR_BGR2RGB
    )
)

plt.title("Detected Lane Lines")
plt.axis("off")
plt.show()
Step 10: Lane Detection Logic
# Already implemented
# (Do not modify)
Expected Output
Original image
Grayscale image
Thresholded image
ROI masked image
Edge detected image
Smoothed image
Detected lines
Final lane detection output
Instructions
Fill ONLY in # Your Code Here sections
Do NOT change existing code
Run step-by-step
Verify outputs
Result
```

OUTPUT : 

<img width="302" height="284" alt="image" src="https://github.com/user-attachments/assets/f9e545b2-485b-4714-97f2-9014a76ca50e" />
<img width="299" height="263" alt="image" src="https://github.com/user-attachments/assets/95bd75fa-ce47-406c-b54d-1838ac67123b" />
<img width="303" height="284" alt="image" src="https://github.com/user-attachments/assets/a2757a66-71a1-4526-a6ac-b5adb4bac3d4" />
<img width="323" height="280" alt="image" src="https://github.com/user-attachments/assets/d4f953a1-e607-469a-a0b3-ba774000b302" />
<img width="303" height="278" alt="image" src="https://github.com/user-attachments/assets/2e098d6e-3e8f-4565-bf33-76036efd76f7" />





Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.

Developed By
Name: CJ ROHIT
Register No: 212224243005

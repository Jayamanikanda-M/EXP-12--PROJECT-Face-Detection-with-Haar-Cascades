# EXP-12--PROJECT-Face-Detection-with-Haar-Cascades

# Aim
To write a Python program using OpenCV to perform the following image manipulations: i) Extract ROI from an image. ii) Perform face detection using Haar Cascades in static images. iii) Perform eye detection in images. iv) Perform face detection with label in real-time video from webcam.

# Software Required
1.Anaconda - Python 3.7 or above 2.OpenCV library (opencv-python) 3.Matplotlib library (matplotlib) 4.Jupyter Notebook or any Python IDE (e.g., VS Code, PyCharm)

# Algorithm
I. ROI Extraction

1.Import OpenCV, NumPy, and Matplotlib.

2.Read the input image using cv2.imread().

3.Select the required Region of Interest (ROI) using image coordinates.

4.Create a black mask using np.zeros_like().

5.Place the selected ROI on the mask.

6.Apply cv2.bitwise_and() to segment the ROI.

7.Display the segmented ROI using Matplotlib.

II. Face Detection

1.Read the input image.

2.Convert the image from BGR to grayscale.

3.Load the Haar Cascade face classifier.

4.Detect faces using detectMultiScale().

5.Draw rectangles around the detected faces.

6.Display the face-detected image.

III. Eye Detection

1.Read the input image and convert it to grayscale.

2.Load the Haar Cascade eye classifier.

3.Detect eyes using detectMultiScale().

4.Draw rectangles around the detected eyes.

5.Display the resulting image.

IV. Real-Time Face Detection

1.Access the webcam using cv2.VideoCapture(0).

2.Capture frames continuously.

3.Convert each frame to grayscale.

4.Detect faces using the Haar Cascade classifier.

5.Draw rectangles around detected faces.

6.Display the label "Face" on the detected region.

7.Continue until the ESC key is pressed.

8.Release the webcam and close all windows.

# Program:
Developed by JAYAMANIKANDA M REG NO:- 212225230113
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("litya .jpeg")

if image is None:
    print("Image not found")
    exit()

# Extract ROI
roi = image[50:250, 50:250]

# Convert BGR to RGB
image = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
roi = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)

plt.subplot(1, 2, 1)
plt.imshow(image)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(roi)
plt.title("ROI")
plt.axis("off")

plt.show()
roi = image[100:420, 200:550]
mask = np.zeros_like(image)
mask[100:420, 200:550] = roi
segmented = cv2.bitwise_and(image, mask)
plt.imshow(cv2.cvtColor(segmented, cv2.COLOR_BGR2RGB))
plt.title("Segmented ROI")
plt.axis('off')
plt.show()
image = cv2.imread('litya .jpeg')
if image is None:
    print("Error: dhoni.jpeg not found")
    exit()
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
blur = cv2.GaussianBlur(gray, (5, 5), 0)
edges = cv2.Canny(blur, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detection")
plt.axis('off')
plt.show()
contours, _ = cv2.findContours(edges, cv2.RETR_EXTERNAL, cv2.CHAIN_APPROX_SIMPLE)
result = image.copy()
for c in contours:
    if cv2.contourArea(c) > 50:
        x, y, w, h = cv2.boundingRect(c)
        cv2.rectangle(result, (x, y), (x+w, y+h), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(result, cv2.COLOR_BGR2RGB))
plt.title("Contour Detection")
plt.axis('off')
plt.show()
```

# output
<img width="327" height="410" alt="ex12(1)" src="https://github.com/user-attachments/assets/e67afdce-76b5-4379-b138-4c88285e2576" />


<img width="299" height="397" alt="ex12(2)" src="https://github.com/user-attachments/assets/5bb81e96-a1f4-4b20-95dd-f918e5f445a5" />


<img width="302" height="401" alt="ex12(3)" src="https://github.com/user-attachments/assets/5cc962c9-05b9-4127-bc49-5c6b1d18ddf3" />


<img width="301" height="403" alt="ex12(4)" src="https://github.com/user-attachments/assets/5576cc68-791f-44f7-8e1e-220144d5eaa7" />


# Result
Thus, the Python program for ROI extraction, face detection, eye detection, and real-time face detection using Haar Cascade classifiers was successfully implemented using OpenCV and Matplotlib.

..

..

..

...

..

.. . .. .

.. ..

..

.. .. ..

..

..

..

..

..

..

...

..

.. . .. .

.. ..

..

.. .. ..

..

..

..

..

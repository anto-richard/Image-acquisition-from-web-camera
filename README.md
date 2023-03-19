# Image-Acquisition-from-Web-Camera...

## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.

i) Write the frame as JPG. 

ii) Display the video. 

iii) Display the video by resizing the window.

iv) Rotate and display the video.

## Software Used:

Anaconda - Python 3.7

## Algorithm:

### Step 1:

Import cv2 and capture the video using cv2.VideoCapture(0).

### Step 2:

Write the captured image using cv2.imwrite("NewPicture.jpg",frame).

### Step 3:

Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5).

### Step 4:

Display the image until the loop gets over.

### Step 5:

Rotate the image using cv2.rotate(smaller_frame,cv2.ROTATE_180).

## Program:

``` Python
### Developed By: Anto Richard. S
### Register No: 212221240005
```

```python
## i) Write the frame as JPG file:

import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("NewPicture.jpg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()

```

```python
## ii) Display the video:

import numpy as np
import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    cv2.imshow('frame', frame)
    if cv2.waitKey(1) == ord('s'):
        break
cap.release()
cv2.destroyAllWindows()

```


```python
## iii) Display the video by resizing the window:

import numpy as np
import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(4))
    height = int(cap.get(5))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = smaller_frame

    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('s'):
        break
cap.release()
cv2.destroyAllWindows()

```

```python
## iv) Rotate and display the video:

import numpy as np
import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:,: width//2] = smaller_frame
    image[:height//2, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:] = smaller_frame


    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('s'):
        break
cap.release()
cv2.destroyAllWindows()

```


## Output:

### i) Write the frame as JPG image:

![o1](https://user-images.githubusercontent.com/93427534/226181521-435d7dad-9890-4f38-b87d-68bce2c53568.png)

### ii) Display the video:

![o2](https://user-images.githubusercontent.com/93427534/226181556-a4bd1313-cd2a-4413-8a0f-dd5b1b85aa64.png)

### iii) Display the video by resizing the window:

![o3](https://user-images.githubusercontent.com/93427534/226181581-ba6a3698-3c7f-40db-b32a-e015c3eda8c3.png)

### iv) Rotate and display the video:

![o4](https://user-images.githubusercontent.com/93427534/226181595-6d5b3b52-df7a-4a90-b013-0a4794d95d39.png)

## Result:

Thus the image is accessed from webcamera and displayed using openCV.



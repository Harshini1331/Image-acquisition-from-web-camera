# EX.NO : 02
# DATE :

# <p align="center">Image Acquisition from Web Camera</p>

## Aim
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import cv2 and capture the video using cv2.VideoCapture(0)
### Step 2:
Write the captured image using cv2.imwrite("image.jpg",frame)
### Step 3:
Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
### Step 4:
display the image until the loop gets over
### Step 5:

Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
## Program:

### Developed By: HARSHINI M
### Register No: 212220230022

## i) Write the frame as JPG file
```python3
import cv2

videoCaptureObject = cv2.VideoCapture(0)
ret,frame = videoCaptureObject.read()
cv2.imwrite("image.jpg",frame)
```

## ii) Display the video
```python3
import cv2
import numpy as np

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()

    cv2.imshow("image",frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```

## iii) Display the video by resizing the window
```python3
import cv2
import numpy as np

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = smaller_frame

    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    cv2.imshow("image.jpg",image)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```

## iv) Rotate and display the video
```python3
import cv2
import numpy as np
cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = smaller_frame

    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)

    cv2.imshow("image.jpg",image)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```

## Output

### i) Write the frame as JPG image
</br>
<img width="724" alt="image" src="https://user-images.githubusercontent.com/75235554/162355541-13ca2ab3-a732-41f9-94b4-dd8ae68dc1e2.png">


</br>


### ii) Display the video
</br>
<img width="827" alt="image" src="https://user-images.githubusercontent.com/75235554/162356100-34ad008a-81fa-4427-b7cf-140454b2de7a.png">


</br>


### iii) Display the video by resizing the window
</br>
<img width="826" alt="image" src="https://user-images.githubusercontent.com/75235554/162356459-d4560f4b-f305-436f-9e8b-becce80a1884.png">



</br>


### iv) Rotate and display the video
</br>
<img width="818" alt="image" src="https://user-images.githubusercontent.com/75235554/162356664-8846cb04-f809-4f26-b2d0-e7e25c292542.png">



</br>



## Result:
Thus the image is accessed from webcamera and displayed using openCV.

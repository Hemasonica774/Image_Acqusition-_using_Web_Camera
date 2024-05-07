# EX NO-2
# Image_Acqusition-_using_Web_Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera

### Step 2:
Use cv2.imread to read the video or image

### Step 3:
Use cv2.imwrite to save the image

### Step 4:
Use cv2.imshow to show the video

### Step 5:
End the program and close the output video window by pressing 'q'.

## Program:
```
### Developed By:P.Hemasonica
### Register No:212222230048
```
## i) Write the frame as JPG file
```
import cv2
obj = cv2.VideoCapture(0)
while(True):
    cap,frame = obj.read()
    cv2.imshow('Video.jpg',frame)
    cv2.imwrite("Phone.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()
```

## ii) Display the video
```
import cv2
img = cv2.VideoCapture(0)
while(True):
    imagee,frame = img.read()
    cv2.imshow('Video',frame)
    cv2.imwrite("MY_Phone.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
img.release()
cv2.destroyAllWindows()

```



## iii) Display the video by resizing the window
```

import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('OSCAR ',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```




## iv) Rotate and display the video
```

import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = smaller_frame 
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    cv2.imshow('Video', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```

## Output

### i) Write the frame as JPG image

![image](https://github.com/Hemasonica774/Image_Acqusition-_using_Web_Camera/assets/118361409/a5db800a-42d9-45c2-92ee-017cc0d5af9f)



### ii) Display the video

![image](https://github.com/Hemasonica774/Image_Acqusition-_using_Web_Camera/assets/118361409/67d694e8-ad38-4cbb-903c-c448e50f47af)



### iii) Display the video by resizing the window


![image](https://github.com/Hemasonica774/Image_Acqusition-_using_Web_Camera/assets/118361409/137c9ba9-2cdc-46ff-b491-97d1c69deb7c)


### iv) Rotate and display the video


![image](https://github.com/Hemasonica774/Image_Acqusition-_using_Web_Camera/assets/118361409/4e02e86e-ed13-4f0e-a877-56825267eddc)



## Result:
Thus the image is accessed from webcamera and displayed using openCV.

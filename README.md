# Image Acquisition using web camera
## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera.

### Step 2:
Use cv2.imread to read the video or image.

### Step 3:
Use cv2.imwrite to save the image.

### Step 4:
Use cv2.imshow to show the video.

### Step 5:
End the program and close the output video window by pressing 'q'.

## Program:
``` Python
## Exp 2 - Image_Acqusition-_using_Web_Camera ##
## Name: PRAVESH N ##
## Register Number: 212223230154 ##


## i) Write the frame as JPG file
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
ret,frame=viedoCaptureObject.read()
cv2.imwrite("212223233001_Aankarsh.jpg",frame)
viedoCaptureObject.release()
cv2.destroyAllWindows()

## ii) Display the video
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
cv2.imshow('video_Pravesh',frame)
cv2.imwrite('video_Pravesh.jpg',frame)
cv2.waitKey(10000)
cap.release()
cv2.destroyAllWindows()

## iii) Display the video by resizing the window
import cv2
import numpy as np
cap  = cv2.VideoCapture(0)
ret,frame = cap.read()
width = int(cap.get(3))
height = int(cap.get(4))
image = np.zeros(frame.shape, np.uint8)
small_frame = cv2.resize(frame,(0,0),fx =0.5, fy = 0.5)
image[:height//2, :width//2]=small_frame
image[height//2:, :width//2]=small_frame
image[:height//2, width//2:]=small_frame
image[height//2:, width//2:]=small_frame
cv2.imshow('',image)
cv2.waitKey(5000)
image_dict={'captured_Pravesh1':image}
cv2.imwrite('captured_Pravesh1.jpg',image)
cap.release()
cv2.destroyAllWindows()



## iv) Rotate and display the video

import cv2
import numpy as np
cap  = cv2.VideoCapture(0)
while True:
    ret,frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8)
    small_frame = cv2.resize(frame,(0,0),fx =0.5, fy = 0.5)
    image[:height//2, :width//2]=cv2.rotate(small_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=small_frame
    image[:height//2, width//2:]=small_frame
    image[height//2:, width//2:]=cv2.rotate(small_frame,cv2.ROTATE_180)
    cv2.imshow('Pravesh_split',image)
    cv2.imwrite('Pravesh_split.jpg',image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()







```
## Output

### i) Write the frame as JPG image
![212223233001_Aankarsh - 0](https://github.com/user-attachments/assets/996bfb6a-97df-4a99-a0fb-a60e9f488c4d)



### ii) Display the video
![video_Aankarsh](https://github.com/user-attachments/assets/918f931f-52ea-48b9-9b18-5c608a95c12f)



### iii) Display the video by resizing the window
![captured_Aankarsh1](https://github.com/user-attachments/assets/a16dc137-1c23-4e6d-a6db-1019f75c60c3)



### iv) Rotate and display the video
![Aankarsh_split](https://github.com/user-attachments/assets/18c09f7b-3bcc-4a20-b594-aca8b04af875)






## Result:
Thus the image is accessed from webcamera and displayed using openCV.

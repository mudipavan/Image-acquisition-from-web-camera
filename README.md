# Image-Acquisition-from-Web-Camera
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
Import Opencv Package.

### Step 2:
Capture the Video from the WebCamera.

### Step 3:

Write the image to a file.
### Step 4:

Show the image or the live camera.
### Step 5:
End the program.

## Program:
``` Python
### Developed By:PAVAN.MUDI
### Register No:212221230067

## i) Write the frame as JPG file
import cv2
VidCap2 = cv2.VideoCapture(0)
while(True):
    ret,frame = VidCap2.read()
    cv2.imshow('video_image',frame)
    cv2.imwrite("212221230048.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
    result = False
VidCap2.release()
cv2.destroyAllWindows()



## ii) Display the video
import cv2
VidCap=cv2.VideoCapture(0)
while(True):
    ret,frame=VidCap.read()
    cv2.imshow('video_image',frame)
    if cv2.waitKey(1) == ord('q'):
        break
VidCap.release()
cv2.destroyAllWindows()



## iii) Display the video by resizing the window
import numpy as np
import cv2
im = cv2.VideoCapture(0)
while True:
    ret,frame = im.read()
    width = int(im.get(3))
    height = int(im.get(4))
    image = np.zeros(frame.shape,np.uint8)
    smallerFrame = cv2.resize(frame,(0,0),fx = 0.5,fy=0.5)
    image[:height//2,:width//2] = smallerFrame
    image[height//2:, :width // 2] = smallerFrame
    image[:height//2, width//2:] = smallerFrame
    image[height//2:, width//2:] = smallerFrame
    cv2.imshow('frame',image)
    if cv2.waitKey(1) == ord('b'):
        break
im.release()
cv2.destroyAllWindows()



## iv) Rotate and display the video
import numpy as np
import cv2
im = cv2.VideoCapture(0)
while True:
    ret,frame = im.read()
    width = int(im.get(3))
    height = int(im.get(4))
    image = np.zeros(frame.shape,np.uint8)
    smallerFrame = cv2.resize(frame,(0,0),fx = 0.5,fy=0.5)
    image[:height//2,:width//2] = cv2.rotate(smallerFrame,cv2.ROTATE_180)
    image[height//2:, :width // 2] = smallerFrame
    image[:height//2, width//2:] = smallerFrame
    image[height//2:, width//2:] = cv2.rotate(smallerFrame,cv2.ROTATE_180)
    cv2.imshow('frame',image)
    if cv2.waitKey(1) == ord('b'):
        break
im.release()
cv2.destroyAllWindows()








```
## Output

### i) Write the frame as JPG image

![Untitled20 - Jupyter Notebook - Opera 20-03-2023 22_19_51](https://user-images.githubusercontent.com/94828517/226419549-531565bd-f9f5-454e-90d3-0950da3e3689.png)


### ii) Display the video

![Untitled20 - Jupyter Notebook - Opera 20-03-2023 22_20_14](https://user-images.githubusercontent.com/94828517/226420500-937baf06-ef6c-4303-a9a0-560325abc058.png)


### iii) Display the video by resizing the window


![video_image 20-03-2023 22_20_39](https://user-images.githubusercontent.com/94828517/226420600-ac30046b-b48c-453b-8b01-8e29d8479e36.png)


### iv) Rotate and display the video

![frame 20-03-2023 22_21_02](https://user-images.githubusercontent.com/94828517/226420705-f43de5eb-4f90-425b-bcbe-b4509803903c.png)




## Result:
Thus the image is accessed from webcamera and displayed using openCV.

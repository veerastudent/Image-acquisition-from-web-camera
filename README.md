## Ex no: 2
## Date: 07/04/2022
# <p align="center">Image Acquisition from Web Camera</p>
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
<br>Use VideoCapture(0) to access web camera


### Step 2:
<br>Use imread to read the video or image


### Step 3:
<br>Use imwrite to save the image


### Step 4:
<br>Use imshow to show the video

### Step 5:
<br>End the program and close the output video windows by pressing 'q'.


## Program:
``` 
### Developed By:VEERAMALAI.S
### Register No:212220230056
## i) Write the frame as JPG file


import cv2
import numpy as np
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
cv2.imwrite("pic_1.jpg",frame)
cap.release()
cv2.destroyAllWindows()


## ii) Display the video


import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('frame',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()


## iii) Display the video by resizing the window


import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2]=smaller_frame
    image[height//2: , :width//2]=smaller_frame
    image[:height//2,width//2:]= smaller_frame
    image[height//2:,width//2:]=smaller_frame
    cv2.imshow('frame',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()


## iv) Rotate and display the video

import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2]=image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[height//2: , :width//2]=smaller_frame
    image[:height//2,width//2:]= image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[height//2:,width//2:]=smaller_frame
    cv2.imshow('frame',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image
</br>![cxvbnm,nbv](https://user-images.githubusercontent.com/75234790/162403970-17d0f8bd-5e85-4439-b243-a2512fca1c70.png)

</br>


### ii) Display the video
</br>![frgthjyukyjthrgf](https://user-images.githubusercontent.com/75234790/162404010-8328661e-9ca4-4323-b077-f0efd3b4c297.png)

</br>


### iii) Display the video by resizing the window
</br>![dfghjhgfds](https://user-images.githubusercontent.com/75234790/162404037-8e4d2202-7835-40fc-b6b4-4d3f532c7a1d.png)

</br>



### iv) Rotate and display the video
</br>
</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.

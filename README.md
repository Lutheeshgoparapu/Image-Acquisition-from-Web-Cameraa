# Image-Acquisition-from-Web-Cameraa
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
Step 1: Use VideoCapture(0) to access web camera

Step 2: Use imread to read the video or image

Step 3: Use imwrite to save the image

Step 4: Use imshow to show the video

Step 5: End the program and close the output video windows by pressing 'q'.

## Program:
```
Developed By: G.Lutheesh
Register No:21221230029
```

## i) Write the frame as JPG file
```
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
ret,frame = videoCaptureObject.read()
cv2.imwrite("1.jpg",frame)
result = False
videoCaptureObject.release()
cv2.destroyAllWindows()
```



## ii) Display the video
```
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
ret,frame = videoCaptureObject.read()
cv2.imshow('myimage',frame)
if cv2.waitKey(1) == ord('q'):
 break
videoCaptureObject.release()
cv2.destroyAllWindows()
```



## iii) Display the video by resizing the window
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
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
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
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image

![WhatsApp Image 2023-09-05 at 10 08 00](https://github.com/Lutheeshgoparapu/Image-Acquisition-from-Web-Cameraa/assets/94154531/fcba3f72-69f2-49b6-96bc-495b01fd59ad)


### ii) Display the video

![WhatsApp Image 2023-09-05 at 10 08 17](https://github.com/Lutheeshgoparapu/Image-Acquisition-from-Web-Cameraa/assets/94154531/b6aff033-9b0c-46d2-8118-6d4e86f8d2a9)


### iii) Display the video by resizing the window

![WhatsApp Image 2023-09-05 at 10 07 19](https://github.com/Lutheeshgoparapu/Image-Acquisition-from-Web-Cameraa/assets/94154531/1aa5edc7-ee8f-40d9-aac9-7f002f20e5bb)





### iv) Rotate and display the video

![WhatsApp Image 2023-09-05 at 10 09 02](https://github.com/Lutheeshgoparapu/Image-Acquisition-from-Web-Cameraa/assets/94154531/a5f1c5fa-9bfd-47aa-8d50-57975ea20d64)







## Result:
Thus the image is accessed from webcamera and displayed using openCV.

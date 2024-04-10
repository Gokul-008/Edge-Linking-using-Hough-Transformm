# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.
## Program :
### NAME : GOKUL.M
### REG NO : 212222230037
```.py
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("img.jpeg",0)
img_c=cv2.imread("pic.jpeg",1)

img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()

canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()

lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(0,0,255),3)
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()

```


## Output

### Input image and grayscale image :

![Screenshot 2024-04-10 103204](https://github.com/Gokul-008/Edge-Linking-using-Hough-Transformm/assets/121165996/a5070c1c-1451-4cf3-ac3b-82fe08276f3e)



### Canny Edge detector output : 

![Screenshot 2024-04-10 103219](https://github.com/Gokul-008/Edge-Linking-using-Hough-Transformm/assets/121165996/95b3281f-8664-437f-b33a-bea9089b8eee)

### Display the result of Hough transform :
![Screenshot 2024-04-10 103229](https://github.com/Gokul-008/Edge-Linking-using-Hough-Transformm/assets/121165996/cc29822f-da61-4f92-be45-c5f9c3b22938)


## Result :
Thus the program is written with Python and OpenCV to detect lines using Hough transform.


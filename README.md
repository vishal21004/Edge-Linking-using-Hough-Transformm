# EX 07: Edge-Linking-using-Hough-Transformm
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

## Program:

## Developed by: VISHAL M.A
## Reg no: 212222230177

## Image Processing:
```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("dog.jpeg",0)
img_c=cv2.imread("dog.jpeg",1)
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
```
## Canny Edge Detection:
```python
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
## Hough Transform:
```python
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=60,minLineLength=40,maxLineGap=200)
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```

## Output

### Input image and grayscale image
![INPUT IMG](https://github.com/vishal21004/Edge-Linking-using-Hough-Transformm/assets/119560110/57542345-0681-46a0-a867-167be6f5496d)




### Canny Edge detector output
![CANNY EDGE IMG](https://github.com/vishal21004/Edge-Linking-using-Hough-Transformm/assets/119560110/477ca23a-f765-457a-be32-8f409389fd50)




### Display the result of Hough transform
![RESULT IMG](https://github.com/vishal21004/Edge-Linking-using-Hough-Transformm/assets/119560110/7bc809ce-c4b7-4dcf-9e3a-80b6ec5089f0)



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.

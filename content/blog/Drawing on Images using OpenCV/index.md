---
title: Drawing on Images using OpenCV
date: "2021-05-29T23:46:37.121Z"
---
Lets use OpenCV library to draw some shapes on image files.

Spin up a new instance of Jupyter notebook.
Copy the cv2, numpy and matplotlib libraries into our instance.

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
```

Now create an image or blank canvas to start drawing the shapes on.

```python
blank_img = np.zeros(shape=(512,512,3), dtype=int16)
```
use imshow function of matplotlib to show the blank canvas.

![Empty canvas](./blankImg.png)

 Draw a rectangle on the blank canvas.

```python
cv2.rectangle(blank_img,pt1=(384,10),pt2=(500,150),color=(0,255,0),thickness=10)
plt.imshow(blank_img)
```
![Rectangle on Canvas](./rect1.png)

cv2 has a rectangle function that takes in parameters like image name,left corner coordinates, right corner coordinates, color of shape and thickness of the line.

Draw another rectangle at the center of canvas in a similar way and color it Blue(0,0,255)

```python
cv2.rectangle(blank_img,pt1=(200,200),pt2=(300,300),color=(0,0,255),thickness=10)
plt.imshow(blank_img)
```
![Blue Rectangle](./rect2.png)

Draw a circle of radius 50px, centered at (100,100).

```python
cv2.circle(img=blank_img,center=(100,100),radius=50,color=(255,0,0),thickness=8)
plt.imshow(blank_img)
```
![Red Circle](./circle.png)

Draw another circle of radius 50px and fill it. You can fill the shape by initializing the thickness parameter to '-1'.

```python
cv2.circle(img=blank_img,center=(400,400),radius=50,color=(255,0,0),thickness=-1)
plt.imshow(blank_img)
```
![red Circle](./circlefill.png)

Draw a line diagonally across the canvas.

```python
cv2.line(blank_img,pt1=(0,0),pt2=(512,512),color=(102,255,255),thickness=5)
plt.imshow(blank_img)
```
![Line](./line.png)

We can write on the canvas. cv2 library comes loaded with some fonts to access. I will write a simple 'Hello' in 'FONT_HERSHEY_SIMPLEX'.

```python
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(blank_img,text='Hello',org=(10,500),fontFace=font,fontScale=4,color=(255,255,255),thickness=3,lineType=cv2.LINE_AA)
plt.imshow(blank_img)
```
![Hello](./hello.png)

In this blog post, i tried to learn about some basic tools of openCV library by creating a blank canvas.
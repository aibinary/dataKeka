---
title: Image Basics with OpenCV
date: "2021-05-29T22:40:32.169Z"
description: OpenCV is a framework built on C++. Its widely used to solve computer vision problems.
---

Images are represented by pixels on the screen. Each pixel can have a value varying from(0-255) across 3 channels(RGB).

Without further ado, lets use OpenCV with python and learn to do interesting things with images.

Prerequisites: 
Anaconda distribution
OpenCV library 

I am using Jupyter Notebook IDE for this tutorial.

First we need to import the required libraries.

'numpy' library is used to build arrays and do operations on arrays in python. Pixels are represented as arrays in the computer memory.

'matplotlib' library is used to plot images in the editor.

```python
import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
import cv2

img = cv2.imread('puppy.jpg')
plt.imshow(img)
```
We read the image that is in same directory as the program using a built-in function imread of OpenCV.

imshow function of matplotlib is used to display the image in our IDE.

![dog image](./dog1.png)

Color channels are flipped when we read the image using OpenCV. Image is read in BGR order. 
OpenCV has a function to rearrange the channels in RGB order.

```python
fix_image = cv2.cvtColor(img,cv2,COLOR_BGR2RBG)
plt.imshow(fix_image)
```
![fixed image](./dog2.png)

Change the image using grayscale parameter.

```python
img_gray = cv2.imread('puppy.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img_gray,cmap='gray')
```
![Gray scale image of dog](./dog_gray.png)

Okay, that looks good. How about we check the size of this image?

```python
img_gray.shape
```
(4032,3024)

I want to change the size of this picture.

```python
new_img = cv2.resize(fix_image,(1000,400))
plt.imshow(new_img)
```
![Resized image](./dog_resize.png)

Boom, just like that the dimensions are changed using resize function of cv2 library.

I can already see why there is a lot of noise around openCV library in the industry.
Its easy to pick up, can come in handy to work on image data with built-in libraries and best of all, its free to use!


**Code & topics are from Jose, Portilla Udemy course on CV.

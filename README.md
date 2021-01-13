# imageproccesing
Program1:Program to display grayscale image using read and write operation
    description:
Binary images: are images whose pixels have only two possible intensity values. ... Binary images are often produced by thresholding a grayscale or color image, in order to separate an object in the image from the background. The color of the object (usually white) is referred to as the foreground color.
grayscale image:A grayscale (or graylevel) image is simply one in which the only colors are shades of gray. ... Often, the grayscale intensity is stored as an 8-bit integer giving 256 possible different shades of gray from black to white.
to read an image we use the function cv2.imread().
to save a image we use cv2.imwrite().
to destory all the windows().

import numpy as np
import cv2
image=cv2.imread('flower1.jpg',1)
cv2.imshow('Original', image) 
cv2.waitKey(0)
cv2.destroyAllWindows() 
cv2.imwrite("grayscale.png",image) 

output:
![image](https://user-images.githubusercontent.com/72436785/104417169-d0cc4480-5529-11eb-8b18-92c391cbe2d4.png)
![image](https://user-images.githubusercontent.com/72436785/104417993-1ccbb900-552b-11eb-919a-338e861b7ff1.png)
**********************************************************************************************************************
program2:Program to performe linear transformation #scaling(A)
description:Scaling is the procedure of measuring and assigning the objects to the numbers according to the specified rules. In other words, the process of locating the measured objects on the continuum, a continuous sequence of numbers to which the objects are assigned is called as scaling.
cv2.resize() is uesd to resizes the given iamges.

import cv2
image= cv2.imread('flower1.jpg')
scale_percent = 500
width = int(image.shape[1] * scale_percent / 100)
height = int(image.shape[0] * scale_percent / 100)
dsize = (width, height)
output = cv2.resize(image, dsize)
cv2.imshow('Original',output) 
cv2.waitKey(0)
output:

![image](https://user-images.githubusercontent.com/72436785/104422255-5bfd0880-5531-11eb-8112-47b67380feea.png)
![image](https://user-images.githubusercontent.com/72436785/104423301-c3678800-5532-11eb-8663-8c8c586dfda6.png)

program2(b)rotation

import cv2
image=cv2.imread('flower1.jpg')
cv2.imshow('original',image)
src=cv2.rotate(image,cv2.ROTATE_90_CLOCKWISE)
cv2.imshow('output',src)
cv2.waitKey(0)
output:
![image](https://user-images.githubusercontent.com/72436785/104426441-cc5a5880-5536-11eb-90e3-39f48082480d.png)








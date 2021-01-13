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
![image](https://user-images.githubusercontent.com/72436785/104434477-1e53ac00-5540-11eb-85cb-4986f27151d5.png)

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


![image](https://user-images.githubusercontent.com/72436785/104434804-85716080-5540-11eb-9479-8585de42e47d.png)


program2(b)rotation
cv2.ROTATE_90_CLOCKWISE is used to rorate image in cl;ockwise direction

import cv2
image=cv2.imread('flower1.jpg')
cv2.imshow('original',image)
src=cv2.rotate(image,cv2.ROTATE_90_CLOCKWISE)
cv2.imshow('output',src)
cv2.waitKey(0)


output:


![image](https://user-images.githubusercontent.com/72436785/104434945-b2257800-5540-11eb-942e-13a875e4c41a.png)
*************************************************************************************************************************
program3: Develop a program to find sum and mean of a set of images.
Create n number of images and read the directory and perform operation.
description:
   img.append is uesd to append all the images together
   Adding Images To add two images or add a constant value to an image. • [imadd] function adds the value of each pixel in one of the input images with the corresponding pixel in the other input image and returns the sum in the corresponding pixel of the output image.
   
   
import cv2
import os
path = 'C:\Pictures'
imgs = []

files = os.listdir(path)
for file in files:
    filepath=path+"\\"+file
    imgs.append(cv2.imread(filepath))
i=0
im = []
for im in imgs:
    #cv2.imshow(files[i],imgs[i])
    im+=imgs[i]
    i=i+1
cv2.imshow("sum of three pictures",im)
meanImg = im/len(files)
cv2.imshow("mean of  three pictures",meanImg)
cv2.waitKey(0)


output:

![image](https://user-images.githubusercontent.com/72436785/104435138-e39e4380-5540-11eb-9e85-37ba04617a45.png)

*********************************************************************************************************************
program4:convert the the given image to gray scale and binary image
  description:
Binary images: are images whose pixels have only two possible intensity values. ... Binary images are often produced by thresholding a grayscale or color image, in order to separate an object in the image from the background. The color of the object (usually white) is referred to as the foreground color.
grayscale image:A grayscale (or graylevel) image is simply one in which the only colors are shades of gray. ... Often, the grayscale intensity is stored as an 8-bit integer giving 256 possible different shades of gray from black to white.
threshold:Thresholding produces a binary image, where all pixels with intensities above (or below) a threshold value are turned on, while all other pixels are turned off.

import numpy as np
import cv2
img = cv2.imread('flower1.jpg')
cv2.imwrite('graynature.jpg',img)
cv2.imshow('Original',img,)
img = cv2.imread('flower1.jpg',0)
cv2.imwrite('gray.jpg',img)
cv2.imshow('Origi',img,)
img = cv2.imread('flower1.jpg', 2) 
ret, bw_img = cv2.threshold(img, 127, 255, cv2.THRESH_BINARY) 
cv2.imshow("Binary", bw_img) 
cv2.waitKey(0)
cv2.destroyAllWindows()

output:


![image](https://user-images.githubusercontent.com/72436785/104432074-7c32c480-553d-11eb-9dca-2d54c8ac1e6b.png)
****************************************************************************************************************************
program5:Program to covert the given image to different color space
description:
A color space is a specific organization of colors. ... Adding a specific mapping function between a color model and a reference color space establishes within the reference color space a definite "footprint", known as a gamut , and for a given color model this defines a color space.
COLOR_BGR2RGB is used to convert bgr image to RGB image
COLOR_BGR2HSV is used to convert BGR image to HSV image
COLOR_BGR2YCrCb is uesd to convert BGR image to YCrCb image

import cv2 
img = cv2.imread('flower1.jpg') 
img1 = cv2.cvtColor(img, cv2.COLOR_BGR2RGB) 
img2= cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img3=cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)   
cv2.imshow('image', img1)
cv2.waitKey(0)
cv2.imshow('image', img2) 
cv2.waitKey(0)
cv2.imshow('image', img3)
cv2.waitKey(0)
cv2.destroyAllWindows()


output:


   ![image](https://user-images.githubusercontent.com/72436785/104432418-ddf32e80-553d-11eb-937f-ceafc3e12fef.png)
*********************************************************************************************************************************
program6:Create an image from 2d array
description:
An image is an array, or a matrix, of square pixels (picture elements) arranged in columns and rows.
An image — an array or a matrix of pixels arranged in columns and rows. In a (8-bit) greyscale image each picture element has an assigned intensity that ranges from 0 to 255.
A 2D array has a type such as int[][] or String[][], with two pairs of square brackets. ... The elements of a 2D array are arranged in rows and columns, and the new operator for 2D arrays specifies both the number of rows and the number of columns.
PIL: Python Imaging Library (abbreviated as PIL) (in newer versions known as Pillow) is a free and open-source additional library for the Python programming language that adds support for opening, manipulating, and saving many different image file formats. It is available for Windows, Mac OS X and Linux.

import numpy as np
from PIL import Image
import cv2
array = np.zeros([100, 200, 3], dtype=np.uint8)
array[:,:100] = [200, 200, 200] 
array[:,100:] = [200, 100, 200]   

img = Image.fromarray(array)
img.save('testrgb.png')
img.show()
cv2.waitKey(0)


output:



   ![image](https://user-images.githubusercontent.com/72436785/104433811-5c040500-553f-11eb-9c89-765ed1bdbfab.png)
************************************************************************************************************************************


program7:Find the sum of the neighborhood values of the matrix.

import numpy as np

M = [[1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]] 

M = np.asarray(M)
N = np.zeros(M.shape)

def sumNeighbors(M,x,y):
    l = []
    for i in range(max(0,x-1),x+2): 
        for j in range(max(0,y-1),y+2):
            try:
                t = M[i][j]
                l.append(t)
            except IndexError: 
                pass
    return sum(l)-M[x][y] 

for i in range(M.shape[0]):
    for j in range(M.shape[1]):
        N[i][j] = sumNeighbors(M, i, j)

print ("Original matrix:\n", M)
print ("Summed neighbors matrix:\n", N)


output:
Original matrix:
 [[1 2 3]
 [4 5 6]
 [7 8 9]]
Summed neighbors matrix:
 [[11. 19. 13.]
 [23. 40. 27.]
 [17. 31. 19.]]
 ******************************************************************************************************************













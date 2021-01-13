# imageproccesing
Program1:Program to display grayscale image
    description:
Binary images: are images whose pixels have only two possible intensity values. ... Binary images are often produced by thresholding a grayscale or color image, in order to separate an object in the image from the background. The color of the object (usually white) is referred to as the foreground color.
grayscale image:A grayscale (or graylevel) image is simply one in which the only colors are shades of gray. ... Often, the grayscale intensity is stored as an 8-bit integer giving 256 possible different shades of gray from black to white.
to read an image we use the function cv2.imread().
to save a image we use cv2.imwrite

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



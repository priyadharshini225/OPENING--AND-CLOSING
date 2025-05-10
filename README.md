# OPENING--AND-CLOSING
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:

Load the input color image from a specified path.

### Step2:

Transform the color image into a grayscale format for easier processing.

### Step3:

Apply an edge detection technique to identify the prominent edges in the grayscale image.

### Step4:

Define a kernel (structuring element) for use in morphological operations, typically a matrix of ones.

### Step5:

Perform morphological operations: Opening: Remove small objects from the edges to clean up the image. Closing: Fill small holes in the detected edges to enhance the structure.

### Step6:

Show the original grayscale image, along with the results of the opening and closing operations for visual comparison.
 
## Program:

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
#i) Create the Text using cv2.putText
img1=np.zeros((300,600),dtype='uint8')
font=cv2.FONT_ITALIC
img2=cv2.putText(img1,"PRIYA S",(5,100),font,3,(255,0,0),5,cv2.LINE_AA)
cv2.imshow("Original",img2)
cv2.waitKey(0)
cv2.destroyAllWindows()
#ii) Create the structuring element
#kernel1=cv2.getStructuringElement(cv2.MORPH_RECT,(21,21))
#kernel2=cv2.getStructuringElement(cv2.MORPH_RECT,(9,9))
kernel1=cv2.getStructuringElement(cv2.MORPH_RECT,(11,11))
kernel2=cv2.getStructuringElement(cv2.MORPH_RECT,(5,5))
#iii) Use Opening operation
img4=cv2.morphologyEx(img1,cv2.MORPH_OPEN,kernel2)
cv2.imshow("Opening",img4)
cv2.waitKey(0)
cv2.destroyAllWindows()
#iv) Use Closing Operation
img3=cv2.morphologyEx(img1,cv2.MORPH_CLOSE,kernel1)
cv2.imshow("Closing",img3)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
## Output:

### Display the input Image
![Screenshot 2025-05-10 220550](https://github.com/user-attachments/assets/ed6ed70e-850d-4703-b81e-92f974951911)



### Display the result of Opening
![Screenshot 2025-05-10 220601](https://github.com/user-attachments/assets/12fe7974-a918-41ee-9044-a0ae4a9fd662)



### Display the result of Closing
![Screenshot 2025-05-10 220615](https://github.com/user-attachments/assets/ddfd08e0-35c0-4b74-b1d2-6d866c203a14)


## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.

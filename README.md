# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
## Step1:
Import the required modules.

## Step2:
Import the image to operate on.

## Step3:
Convert the imported image from BGR to GRAYSCALE.

## Step4:
Find the edges using canny edge detector and display the image.

## Step5:
Detect the points that form a line using hough transform.

## Step6:
Draw the lines on the image

## Step7:
Display the output

## Step8:
End the program.

## Program:
```Python

# Read image and convert it to grayscale image

import cv2
import matplotlib.pyplot as plt
import numpy as np
image = cv2.imread("road.jpeg")
smoothImage = cv2.GaussianBlur(image,(3,3),0)
plt.imshow(smoothImage)
grayImage = cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
cv2.imshow("Original Image",image)
cv2.imshow("Gray Image",grayImage)




# Find the edges in the image using canny detector and display

cannyEdges = cv2.Canny(smoothImage,120,200)
plt.imshow(cannyEdges,cmap='gray')
plt.title('Edge Image')
plt.xticks([])
plt.yticks([])
plt.show()


# Detect points that form a line using HoughLinesP

lines = cv2.HoughLinesP(cannyEdges,1,np.pi/180,threshold=80,minLineLength = 50,maxLineGap = 250)



# Draw lines on the image

for line in lines:
    x1, y1, x2, y2 = line [0]
    cv2.line(smoothImage,(x1, y1),(x2, y2),(255, 0, 0),3)



# Display the result
plt.title("Hough Transform")
plt.imshow(cannyEdges)
plt.show()

```
## Output

### Input image and grayscale image
<img width="586" alt="originalImage" src="https://user-images.githubusercontent.com/93427224/169448519-d63d4573-22c7-4a1a-a7d3-08d299adf1b6.png">

<img width="586" alt="GrayImage" src="https://user-images.githubusercontent.com/93427224/169448538-4ed524fe-e8b2-40b6-9f0a-492894018451.png">

### Canny Edge detector output

<img width="752" alt="EdgeImage" src="https://user-images.githubusercontent.com/93427224/169448581-78553a70-d189-4b8f-899b-966f788c30fb.png">


### Display the result of Hough transform
<img width="752" alt="houghTransform" src="https://user-images.githubusercontent.com/93427224/169448595-7e982afc-f72e-4b12-9390-2e60e99f9eb4.png">


## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 

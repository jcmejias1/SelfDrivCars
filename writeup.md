# **Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline function in python that finds lane lines on the road.
* Show the understanding of the key concepts of road recognition.

[//]: # (Image References)

---

### Pipeline

###1. I started the project with the sequences of transformation every frame of the video should have in order to extract the lane positions from each frame. I researched about all the functions involved and adjusted the parameters to the optimum values for a clearer detection. After that created a function for each of the transformations, below and example of them:

### Convert image to a np array 
#### Python function used mpimg.imread

### Convert the image to grayscale
#### Python function used cv2.cvtColor

<img src="./examples/gray_image.jpg" width="400px" height="240px" />

### Smooth image to reduce noise
#### Python function used cv2.GaussianBlur

<img src="./examples/blur_image.jpg" width="400px" height="240px" />

### Get edges of the images using Canny's method
#### Python function used cv2.Canny

<img src="./examples/canny_image.jpg" width="400px" height="240px" />

### Proposed mask and to retain area of interest
#### Python function used cv2.fillPoly

<img src="./examples/mask_image.jpg" width="400px" height="240px" />

### Retain only area of interest
#### Python function used cv2.bitwise_and

### Extract the points that form the lines
#### Python function used cv2.HoughLines

<img src="./examples/filtered_image.jpg" width="400px" height="240px" />

### Draw the lines
#### Python function used cv2.line

### Merge original image and lines
#### Python function used cv2.addWeighted

<img src="./examples/red.jpg" width="400px" height="240px" />

## Video processing

Then created a function that receives a video as an input and returns the video after applying the pipeline described before in order to create a video with the lane marks.


###2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when there is a change in the road such different concrete path or horizontal lines that can be similar in color or shape to lane lines.


###3. Suggest possible improvements to your pipeline

A possible improvement would be to include a function to filter base on line a range of slopes that would only contain the 2 lanes.

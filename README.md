# **Finding Lane Lines on the Road** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

<img src="examples/laneLines_thirdPass.jpg" width="480" alt="Combined Image" />

Overview
---

When we drive, we use our eyes to decide where to go.  The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle.  Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

The goal of this project is the following:

1. Write code that include a pipeline to identify and draw the lane lines on a few test images using Python and OpenCV.
2. Once you can successfully identify the lines in an image, then cut and paste to put together the code into the block provided to run on a video stream. 
3. (optional) Run the code on a challenge video and see if it can properly draw the lane lanes.

Pipeline Description
---
The pipeline consists of the following steps:

1. Convert image into grayscale.

<img src="test_images/solidWhiteRight.jpb" width="480" alt="original Image" />

<img src="test_images_output/step1.png" width="480" alt="step 1 Image" />

2. Apply gaussian smoothing to prepare for Canny transform.

<img src="test_images_output/step2.png" width="480" alt="step 2 Image" />

3. Set parameters and use OpenCV Canny function for edge detection to detect lane lines.

<img src="test_images_output/step3.png" width="480" alt="step 3 Image" />

4. Define a four-sided polygon to mask the image and show only a region of interest that include the lane lines.

<img src="test_images_output/step4.png" width="480" alt="step 4 Image" />

5. Set Hough transform parameters and run `Hough_lines` function on edge-detected masked image.

<img src="test_images_output/step5.png" width="480" alt="step 5 Image" />

6. Superimpose Hough lines on original image.

<img src="test_images_output/step6.png" width="480" alt="step 6 Image" />


Shortcomings
---
- The Hough lines shown on the video are jittery.

Possible Improvements
---
- Take averages of Hough lines coordinates over multiple frames of the video stream to smooth out the hough lines superimposed on the video image.







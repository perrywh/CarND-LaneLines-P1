# **Finding Lane Lines on the Road** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

<img src="examples/laneLines_thirdPass.jpg" width="480" alt="Combined Image" />

Overview
---

When we drive, we use our eyes to decide where to go.  The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle.  Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

The goal of this project is to:

- Write code that include a pipeline to identify and draw the lane lines on a few test images using Python and OpenCV
- Once you can successfully identify the lines in an image, then cut and paste to put together the code into the block provided to run on a video stream. 

Pipeline Description
---
The pipeline consists of the following steps:

1. Convert images into grayscale
2. Apply gaussian smoothing to prepare for Canny transform
3. Set parameters and use OpenCV Canny function for edge detection to detect lane lines.
4. Define a four sided polygon to mask the image and show only a region of interest that include the lane lines
5. Set Hough transform parameter and run Hough on edge-detected masked image
6. Superimpose Hough lines on original image

Shortcomings
---
- The Hough lines are jittery

Possible Improvements
---
- Take averages of Hough Lines coordinate over multiple frames of the vide stream to smooth out the hough lines superimposed on the video image







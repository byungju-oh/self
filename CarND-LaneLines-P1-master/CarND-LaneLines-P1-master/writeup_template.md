# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I used gaussianblur  to reduce noise. I passed the image to canny edge detection . The area of interest was set to reduce the amount of calculation and make more accurate judgments. I used to hough conversion to find the lane.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function. 
First, calculate the slope of each hough line element determine the left and right sides of the lane by slope. Calculate the average slope of the left and right lanes. To reduce errors throw away below slope of |0.5|. To reduce errors remove the non-matched slope and coordinate
Draw a lane with a slope of average by selecting random coordinates on the lane.





### 2. Identify potential shortcomings with your current pipeline


Lack the ability to distinuish shadows.
Vulnerable to curved roads.
Affected by vehicles running around.



### 3. Suggest possible improvements to your pipeline

Chek the route using the lost point of lane. To reduce noise save the privious frame and compare it to the present value.

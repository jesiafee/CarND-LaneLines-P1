# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.
First of all, the codes are in the jupyter notebook.

My pipeline consisted of 5 steps. 

First, in order not to change the source image, I made a copy of the image;

Second, I converted the copied image to grayscale, and blurred the grayscaled image by gaussian_blur;

Third, I detected the edges of the image processed above by canny function;

Fourth, I defined the ROI by the function region_of_interest();

Fifth, I adopted the hough_lines function to obtain the lines, which will be used for calculating average slope;

Optionally, the hough_lines function would return the image with marked red lines(to show the effect, all codes in this notebook below should be commented)["Your output should look something like this (above) after detecting line segments using the helper functions below"].

Sixth, I added a separate function called HoughLinesP() to get the lines information, then I built a filter to collect all possible reasonable line slopes, and calculated the average value as the slope of the pipelines;

Finally, I connected the points at the bottom and the points almost within the ROI, and draw pipelines by the function draw_lines.["Your goal is to connect/average/extrapolate line segments to get output like this"]


### 2. Identify potential shortcomings with your current pipeline

Once the ROI is not selected appropriately, the numbers of the slopes of the lines obtained by the HoughLinesP() may be ZERO, which may cause a error "devided by zero".

Another one is that the codes in the jupyter may only suit simple straight lane lines listed in the category.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to apart the left and right lane lines, analysis them dependently, and combine them into one image.

Another potential improvement could be to try other functions like cvErode() and cvDilate().

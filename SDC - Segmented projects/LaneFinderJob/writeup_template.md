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

My pipeline consisted of 5 steps. Put simply all of the technologies taught in the lesson are combined like pieces of lego.
First we turn the image to gray in order to remove noise from colors, then we filter it with Gauss and apply the Canny edge detector.
Next we set the polynomial boundaries(vertices) and create a mask for the area of interest. After Hough transformation is applied
and last but not least the images are stacked one onto another in order to apply the red markings on the original image.

In order to draw a single line on the left and right lanes, I haven't modified the draw_lines() function significantly, most of the
valuable configurations are in the hough_lines method.


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when there are shadows in the middle of the road creating a new edge for the Canny filter. 

Another shortcoming could be different POV for the camera, for example during steering and road curves - the region of interest would go out of the road boundaries.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to set a different threshold for the Canny or to improve the region of interest logic, by marking only several pixels away 
from the region edges.

Another potential improvement could be to make the region dynamically adjustable as to not go out of bounds during curves. Ex.: When a lane marking is conducting a curve the 
region edges might shrink in the opposite direction of movement and expand following the curve path.

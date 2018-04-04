**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

I convert the image to grayscale and apply Gaussian smoothing. Then I take the modified image and do canny edge detection on it. Following this I do a Hough transformation on a certain region of the image where the lane lines are located. I took the following steps to modify my draw_lines method:

I find all the coordinates and slopes of the Hough transformation and divide them into 2 groups based if they are for the left or right lane marker. Using the slope of the lines, I calculate the top and bottom coordinates of the lane line in the image. Then I draw this line on the original image. With this approach I can draw lines on my image even when the lane line is segmented.

Finally I draw these lines on the original image of the road.


###2. Identify potential shortcomings with your current pipeline

I have many hard-coded values in my pipeline. I think this is what causes challenge portion of this project to not work properly.


###3. Suggest possible improvements to your pipeline

Get parameters from a heuristics based approach. 
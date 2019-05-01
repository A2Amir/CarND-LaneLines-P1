# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report



### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 6 steps. 

1-First, I converted the images to grayscale.
2-then I applaied on the grayscale image a Gussian filter with the kernel of size 5
3-After the determination of the min(50) and max(150) thresholds for the  Canny transform I found edegs.
4-After the regulation of the vertices (qualrilateral) i draw on the canny image the region of the interset.
5-At this level the parameters of the hough_lines were defined and the lines were drawn on the defined region of interest from the last step.  
6-At the end, the weights of the image and the drawn lines were added by the weighted_img function 



In order to draw a single line on the left and right lanes, I modified the hough_lines() function by seperating all intercepts an slopes belonging to the left or right lanes (using np.polyfit) then to calculate the coordinates of the first and end points of the left and right lane lines I averaged them to the axis zero and got the coordinates with the make_coordinate() function.





### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the lane lines will be tilted. 

Another shortcoming could be the vertices of the region of interset or the regulation of the parameters.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be in curves 

Another potential improvement could be  automatic detection or improvment of the parameters like vertices 

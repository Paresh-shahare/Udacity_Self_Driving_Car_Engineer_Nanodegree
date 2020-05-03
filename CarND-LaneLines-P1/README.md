# Finding Lane Lines on the Road

> The goals of this project:
> * Make a pipeline that finds lane lines on the road using OpenCV (an open-source computer vision library)
> * Apply this pipeline on images as well as videos to find lane lines

![Image 1](https://github.com/Paresh-shahare/Udacity_Self_Driving_Car_Engineer_Nanodegree/blob/master/CarND-LaneLines-P1/examples/line-segments-example.jpg?raw=true)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### 1. Pipeline for finding lane lines using OpenCV
#### Tools and funcitons used:
> **Tools** - OpenCV, Numpy, Matplotlib, OS, VideoFileClip, HTML (Python)
> **Functions** - Grayscale, Color selection, Guassian Blur, Canny Edge Detection, Region of Interest selection, draw lines, Hough Transform Lines detection,Weighted image, extrapolate line segments
1. Importing useful packages
2. Reading an image using matplotlib.Image
![Image 2](https://github.com/Paresh-shahare/Udacity_Self_Driving_Car_Engineer_Nanodegree/blob/master/CarND-LaneLines-P1/test_images/solidWhiteCurve.jpg)
3. Converting RGB image to Grayscale image and applying GuassianBlur for smoothening.
![Image 3](https://github.com/Paresh-shahare/Udacity_Self_Driving_Car_Engineer_Nanodegree/blob/master/CarND-LaneLines-P1/intermediate_results/grayscale.jpg)
4. Applying Canny edge detection to detect edges
![Image 4](https://github.com/Paresh-shahare/Udacity_Self_Driving_Car_Engineer_Nanodegree/blob/master/CarND-LaneLines-P1/intermediate_results/canny_edge.jpg)
5. Selection of Region of Interest for lane lines and masking out the region
![Image 5](https://github.com/Paresh-shahare/Udacity_Self_Driving_Car_Engineer_Nanodegree/blob/master/CarND-LaneLines-P1/intermediate_results/ROI_mask.jpg)
6. Using HoughLinesP to return an image with hough lines drawn on the output of Canny transform
![Image 6](https://github.com/Paresh-shahare/Udacity_Self_Driving_Car_Engineer_Nanodegree/blob/master/CarND-LaneLines-P1/intermediate_results/Hough_line_drawn.png)
7. Formation of output image by stacking lines drawn on original image.
![Image 7](https://github.com/Paresh-shahare/Udacity_Self_Driving_Car_Engineer_Nanodegree/blob/master/CarND-LaneLines-P1/intermediate_results/line_edges_output.png)
##### Using the same draw_lines() function to draw lane lines over videos.
![click here](https://github.com/Paresh-shahare/Udacity_Self_Driving_Car_Engineer_Nanodegree/blob/master/CarND-LaneLines-P1/test_videos_output/solidYellowLeft.mp4)


### 2. Potential shortcomings with current pipeline
> 1. Changes in lightning conditions changes results 
> 2. Camera position cannot be changed (since it will disturb ROI values)
> 3. Difficulty in detecting lane lines at low lightning conditions
> 4. The current pipeline cannot be generalized and used in every conditions (major drawback)

### 3. Possible improvements to current pipeline
> 1. Using Convolutional Neural Networks for detecting lane lines will be better appraoch. This can be a generalized approach that can be used in every lightning coditions. Also, the compulsion of camera positioning can be eased.

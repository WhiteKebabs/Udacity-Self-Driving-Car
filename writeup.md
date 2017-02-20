#**Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Using the algorithms and concepts taught in Lesson 2, create a pipeline that will detect lane lines.
* Write a written report on the approaches I took, difficulties I encountered, and possible improvements.

---

### Reflection

###1. Approach

The overall approach I took in order to detect lane lines is as follows:
* Convert RGB image to greyscale
* Apply Gaussian Blur to the greyscale image
* Create two separate traingle masks for the left and right lanes and apply them on the greyscale image
* Apply the Uncanny algorithm to detect edges on the lanes
* Apply the Hough Lines algorithm supplied to us as a helper function to extract potential lines from the images
* Combine the left and right Hough Line extractions
* Add the combined Hough lines extraction to the original image

[image1]: ./output_images/left_canny.jpg "Left Uncanny Mask"
[image2]: ./output_images/right_canny.jpg "Right Uncanny Mask"

[image3]: ./output_images/left_hough.jpg "Left Hough Lines"
[image4]: ./output_images/right_hough.jpg "Right Hough Lines"

###2. Difficulties

The above approach worked relatively well with lanes that have a low curvature but fails to detect lanes with high curvature. This is due to the fact that the algorithm splits the mask into two which makes it difficult to find lanes that cross the centre of the image.

Another difficulty I encountered was small jittering in the annotation. To minimise the jitter, a compromise had to be made between the Uncanny algorithm thresholds and the Gaussian Blur. Too much of both removed too much of the lane lines, leaving nothing for the Hough Lines algorithm to return. 

###3. Possible Improvements

The algorithm could further be improved by tweaking the Hough Lines algorithm to adapt to lanes that have high curvature and fit a higher degree polynomial to the lines. 

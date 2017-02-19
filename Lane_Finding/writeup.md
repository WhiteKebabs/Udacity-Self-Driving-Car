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
* Create two separate traingle masks for the left and right lanes and apply them on the greyscale image
* Apply the Uncanny algorithm to detect edges on the lanes
* Apply the Hough Lines algorithm supplied to us as a helper function to extract potential lines from the images
* Combine the left and right Hough Line extractions
* Add the combined Hough lines extraction to the original image



###2. Difficulties



###3. Possible Improvements

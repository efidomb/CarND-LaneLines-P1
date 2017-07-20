
# **Finding Lane Lines on the Road** 

## Writeup

---

### Finding Lane Lines on the Road

The goal of this project is to make a pipeline that finds lane lines on the road.

[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflections

### 1. Description of my pipeline

My pipeline consisted of 5 steps.

1. I converted the images to grayscale.
2. I run the gaussian_blur function to 'smooth out' the image. I set the kernel_size to 3.
3. I applied the canny transformation with thresholds of 10 and 200.
4. I set region of interst around the lane lines, so other lines from other areas in the image won't be considered.
5. I transformed the image into hough lines (with 50, 10, 10 for the threshold, min_line_len and max_line_gap, respectively) and paste them on the original image.


### 2. Potential shortcomings with current pipeline

there is a two kinds of shortcomings with the current pipeline:
most of them related to the manual nature of the parameter tuning.
1. the manual nature of the parameter tuning in this method is very fragile. for example, if the lane is suddenly too wide, like when two lanes merge to one lane, the lane lines would be way out of the region of interes. same is true for the other parameters.
2. this method is not very helpfull where the lanes are very curved, sinse it can only describe linear representation of the lane lines.


### 3. Possible improvement to the pipeline

my idea for improvment of the pipeline is to use machine learning techniques for those 'manully-picked' parameters so they will be more flexable.

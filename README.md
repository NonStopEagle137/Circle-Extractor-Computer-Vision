# Circle-Extractor-Computer-Vision
This is a circle extractor algorithm that I used in one of my Computer Vision Projects. The code is quite robust and generally performs better than Hough Circles and Hough Ellipse.

# How does the code work?
1. First step is segmentation, this is currently being by K-means segmentation and then adaptive thresholding.
2. Once the Image is segmented correctly, we procees to find the contours in the Image.
3. We then fit ellipses over each contour and set some accepting criterion.
4. In this case the accepting criterion could be to select ellipses with '(MA/ma)' < 1.7 (Meaning, the ratio of the Major axis to the minor axis is les than 1.7). This eliminates very skewed ellipses.
5. Next, Regarding the size of the ellipses. Here you could set the accepting criterion based on the image on which you are testing out this algorithm. But, the rule of thumb is to have the 'radius < max(image_shape)'.

## Summarizing the above, there are the following Hyper-parameters
1. Number of clusters for K-means segmentation.
2. (MA/ma), the ratio of the major axis to minor axis.
3. Maximum allowed major axis of the ellipses

I have Used K-means segmentation and adptive thresholding as my application required them both, but you are free to make changes that suit your specific application.
### Some Examples :
1. Select ROI \
![alt text](https://github.com/NonStopEagle137/Circle-Extractor-Computer-Vision/blob/main/Images/github_roi.JPG)
\
2. K - Means Segmentation \
![alt text](https://github.com/NonStopEagle137/Circle-Extractor-Computer-Vision/blob/main/Images/K_means.JPG)
\
3. Final Results (Detected Circles/ Ellipses) \
![alt text](https://github.com/NonStopEagle137/Circle-Extractor-Computer-Vision/blob/main/Images/results.JPG)
\
### Checking on a slightly better quality Image

1. Select ROI \
![alt text](https://github.com/NonStopEagle137/Circle-Extractor-Computer-Vision/blob/main/Images/roi_selection.JPG)
\
2. K - Means Segmentation \
![alt text](https://github.com/NonStopEagle137/Circle-Extractor-Computer-Vision/blob/main/Images/k_means2.JPG)
\
3. Results (Detected circles/ Ellipses) \
![alt text](https://github.com/NonStopEagle137/Circle-Extractor-Computer-Vision/blob/main/Images/result2.JPG)
\

### The Noise that You see in some of the Results are smaller ellipses detected, you can easily get rid of them by setting a suitable 'min_major_axis' threshold.
## If you use the code here for anything, please make sure to cite this repository.
### The adaptive threshold code comes from a publication, but I can't seem to find it. If you do find it, let me know so that I can acknowledge it here.
### This code or derivatives of this implementation can only be used for academic purposes, if you wish to use this code for commercial purposes please contact me athrva98@gmail.com

# Circle-Extractor-Computer-Vision
This is a circle extractor algorithm that I used in one of my Computer Vision Projects. The code is quite robust and generally performs better than Hough Circles and Hough Ellipse.

# How does the code work?
1. First step is segmentation, this is currently being by K-means segmentation and then adaptive thresholding.
2. Once the Image is segmented correctly, we procees to find the contours in the Image.
3. We then fit ellipses over each contour and set some accepting criterion.
4. In this case the accepting criterion could be to select ellipses with '(MA/ma)' < 1.7 (Meaning, the ratio of the Major axis to the minor axis is les than 1.7). This eliminates very skewed ellipses.
5. Next, Regarding the size of the ellipses. Here you could set the accepting criterion based on the image on which you are testing out this algprithm. But, the rule of thumb is to have the 'radius < max(image_shape)'.

## Summarizing the above, there are the following Hyper-parameters
1. Number of clusters for K-means segmentation.
2. (MA/ma), the ratio of the major axis to minor axis.
3. Maximum allowed major axis of the ellipses

I have Used K-means segmentation and adptive thresholding as my application required them both, but you are free to amke changes that suit your specific application.
### Some Examples :
1. Select ROI
![alt text](https://github.com/NonStopEagle137/Circle-Extractor-Computer-Vision/blob/main/github_roi.jpg?raw=true)



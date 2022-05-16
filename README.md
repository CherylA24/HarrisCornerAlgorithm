# HarrisCornerAlgorithm
This code will demonstrate Harris corner algorithm without using OpenCV Library

Harris Corner Algorithm Step :
1) Compute Gaussian Derivatives at Each Pixel
I use gaussian filter and sobel filter to find derivatives for each pixel. The 
picture will be converted into gray scale before applied to gaussian filter. Then 
the result of the gaussian filter will be compute derivatives by sobel filter. 
Before executing convolution, open-source versions of the sobel derivative 
transform the picture to float.
2) Compute second moment Matix M in a Gaussian window around each pixel
To compute second moment matrix M, by sliding a window through all the 
pixels in our image, I first compute the sum of squares of our gradient at each 
pixel. The window is adjusted in accordance with the offset that chosen
depending on the image. We find the corner response R at each pixel using the 
sum of squares of each window.
3) Compute corner response function R
The response function formula : R=det(matrixH)-k(Trace(matrixH))^2 )
4) Threshold R
To apply the threshold R, I normalize the matrix first. If value R is bigger than 
the threshold then it is the corner of the images.
5) Find local maxima of response function (non-maximum suppression)
I use corner_peaks library that provided in the skimage to find the local maxima 
of response function. The purpose of finding the local maxima is to find the 
peaks of the corner

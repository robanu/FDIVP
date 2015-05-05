#Information
Hard Deadline: 	Mon 11 May 2015 7:00 AM PDT  
Duration: Untimed  
Attempts: 100  

#Question 1
The main difference between image enhancement and image restoration is the fact that the degradation model must be known in latter.

[X] True  
[ ] False


#Question 2
If you wanted to make an image look brighter than what it currently does, which one of the following intensity transformations would you use?

[ ] ![](W04Q02IMG01.png)  
[ ] ![](W04Q02IMG02.png)  
[X] ![](W04Q02IMG03.png)  
[ ] ![](W04Q02IMG04.png)  


#Question 3
The mean and standard deviation of pixel intensity values in an 8-bit gray-scale image are 120 and 10, respectively. What are the mean and standard deviation of pixel intensity values in the negative of this image?

[X] 135, 10  
[ ] 120, 10  
[ ] 110, 20  
[ ] They can't be determined without knowing the size of the image.  


#Question 4
Check all statements that apply to the following intensity transformation:

[X] The output image is binary since its pixels take on only two intensity levels.  
[ ] It is possible to recover the input image after it undergoes this transformation.  
[X] The mean intensity value of the pixels in the transformed image is always between a and b (including the end points a and b).  
[ ] In the transformed image, the number of pixels with intensity level b is less than the number of pixels with intensity level a.  


#Question 5
Check all statements that are true regarding image histogram equalization:

[X] After histogram equalization, the intensity values are more effectively distributed over the histogram range.  
[ ] The mean intensity value of the pixels in an image increases after histogram equalization.  
[ ] After histogram equalization images will always look brighter.  
[X] If pixel p is the brightest pixel in image x, it will remain the brightest pixel after histogram equalization.  


#Question 6
Check all that apply:

[ ] Median filters are linear.  
[ ] Median filters are well-suited to deal with additive Gaussian noise.  
[ ] The performance of median filters is independent of the number of noisy pixels.  
[X] If you apply a median filter on a noisy image for a large number of times, the image will stop changing after some point.  


#Question 7
In this problem you will perform median filtering to enhance the quality of a noise corrupted image. Recall from the video lecture that median filtering is effective for removing "salt-and-pepper" noise from images. Follow the instructions below to complete this problem.

1. Download the noisy image from [here](W05Q07IMG01.jpg). Load the noisy image into a MATLAB array and convert the type of the array from 8-bit integer 'uint8' to real number 'double'. Refer to MATLAB problems in previous homework if you need help with loading and converting images. Visualize the noisy image using the built-in MATLAB function "imshow". The function "imshow" takes as its argument either [0-255] for an 8-bit integer array (i.e., of type 'uint8'), or [0-1] for a normalized real-valued array (i.e., of type 'double'). To provide "imshow" with the correct argument, you would need either to "cast" your real-valued array into 'uint8', or normalize it by 255.

2. Perform 3x3 median filtering using the built-in MATLAB function "medfilt2". For this problem, the only argument you need to provide "medfilt2" with is the array you have created in step (1). Visualize the filtered image using "imshow". Remember to either cast the result to 'uint8' or normalize it before feeding it to "imshow".

3. Perform a second-pass median filtering on the filtered image that you have obtained from step (2). Visualize the two-pass filtered image. Compare it with the noisy input image and the 1-pass filtered image.

4. Download the noise-free image from [here](W05Q07IMG02.jpg). Compute the PSNR values between (a) the noise-free image and the noisy input image, (b) the noise-free image and the 1-pass filtering output, and (c) the noise-free image and the 2-pass filtering output. Enter the three PSNR values in the box below. Enter the numbers to two decimal points.

##Personal notes

```matlab
% GNU Octave
img = im2double(imread('W05Q07IMG01.jpg'))
%imshow(img)

imgfil1 = medfilt2(img)
%imgshow(imgfil1)

imgfil2 = medfilt2(imgfil1)
%imgshow(imgfil2)

original = im2double(imread('W05Q07IMG02.jpg'))
%imshow(original)

[h,w] = size(original)
mse = sum(sum(power(imgfil2-original,2)))/(h*w)
psnr = 10*log10(1/mse)

%psnr = 5.5845
%psnr = 29.65
```

```matlab
% GNU Octave
img = double(imread('W05Q07IMG01.jpg'))
imshow(img/256)

imgfil1 = medfilt2(img)
imshow(imgfil1/256)

imgfil2 = medfilt2(imgfil1)
imshow(imgfil2/256)

original = double(imread('W05Q07IMG02.jpg'))
imshow(original/256)

[h,w] = size(original)
mse = sum(sum(power(imgfil2-original,2)))/(h*w)
psnr = 10*log10(256/mse)

%psnr = 5.5845
%psnr = 29.65
%psnr = 5.60
%WTF?
```
#Information
Mon 4 May 2015 7:00 AM PDT
Duration:	Untimed
Attempts:	0/100


#Question 1
Check all the applications where motion estimation can be employed to improve the results:

[ ] Object tracking  
[ ] Human-computer interaction  
[ ] Still image inpainting  
[ ] Video compression  
[ ] Segmentation of a single image  


#Question 2
We want to increase the frame rate of a video sequence by inserting a new frame between every two existing consecutive frames. Denote by y the new frame formed via linear interpolation of motion vectors between frames xt−1 and xt in the original video. Assuming that a circular object is centered at pixel (i,j) in xt−1 and at pixel (p,q) in xt, where will it be centered in y?

[ ] (p+i,q+j)  
[ ] ((p+i)/2,(q+j)/2)  
[ ] (p−i,q−j)  
[ ] ((p−i)/2,(q−j)/2)  


#Question 3
Calculate the Mean Square Error (MSE) between the two given image blocks (enter your answer to at least one decimal point): ![](W04Q03IMG00.png)

[ ] 


#Question 4
Assume that we want to perform block matching for the image block x given below. Which of the following image blocks is a better match in the Mean Absolute Error (MAE) sense? ![](W04Q04IMG00.png)

[ ] ![](W04Q04IMG01.png)  
[ ] ![](W04Q04IMG02.png)  
[ ] ![](W04Q04IMG03.png)  
[ ] ![](W04Q04IMG04.png)  


#Question 5
(True or False) Sub-pixel motion estimation is used in applications where a faster and hence less accurate estimation of motion is needed.

[ ] True  
[ ] False


#Question 6
Refer to the RGB cube shown in the video lecture for this problem. Color magenta can be obtained by 1:1 mixing red and blue; yellow can be obtained by 1:1 mixing red and green; cyan can be obtained by 1:1 mixing blue and green. If magenta, yellow, and cyan are mixed at 1:1:1 proportion, what is the resulting color?

[ ] red  
[ ] green  
[ ] blue  
[ ] white  
[ ] black  


#Question 7
(True or False) Intensity in HSI color space is exactly the same as the Y-channel in YCbCr color space, as both represent the "brightness" of an image.

[ ] True  
[ ] False  


#Question 8
In this problem you will perform block matching motion estimation between two consecutive video frames. Follow the instructions below to complete this problem. 

1. Download the two video frames from frame_1 and frame_2. The frames/images are of height 288 and width 352.
2. Load the frame with file name "frame_1.jpg" into a 288×352 MATLAB array using function "imread", and then convert the array type from 8-bit integer to real number using function "double" or "cast" (note that the range of intensity values after conversion is between 0 and 255). Denote by I<sub>1</sub> the converted MATLAB array. Repeat this step for the frame with file name "frame_2.jpg" and denote the resulting MATLAB array by I<sub>2</sub>. In this problem, I<sub>2</sub> corresponds to the current frame, and I<sub>1</sub> corresponds to the previous frame (i.e., the reference frame).
3. Consider the 32×32 target block in I<sub>2</sub> that has its upper-left corner at (65,81) and lower-right corner at (96,112). Note this is MATLAB coordinate convention, i.e., the first number between the parenthesis is the row index extending from 1 to 288 and the second number is the column index extending from 1 to 352. This target block is therefore a 32×32 sub-array of I<sub>2</sub>.
4. Denote the target block by B<sub>target</sub>. Motion estimation via block matching searches for the 32×32 sub-array of I<sub>1</sub> that is "most similar" to Btarget. Recall in the video lectures we have introduced various forms of matching criteria, e.g., correlation coefficient, mean-squared-error (MSE), mean-absolute-error (MAE), etc. In this problem, we use MAE as the matching criterion. Given two blocks B<sub>1</sub> and B<sub>2</sub> both of size M×N, the MAE is defined as ![](W04Q08IMG00.png). To find the block in I<sub>1</sub> that is most similar to B<sub>target</sub> in the MAE sense, you will need to scan through all the 32×32 blocks in I<sub>1</sub>, compute the MAE between each of these blocks and B<sub>target</sub>, and find the one that yields the smallest value of MAE. Note in practice motion search is only performed over a certain region of the reference frame, but for the sake of simplicity, we perform motion search over the entire reference frame I<sub>1</sub> in this problem. When you find the matched block in I<sub>1</sub>, enter the following information:

1. the coordinate of the upper-left corner of the matched block in MATLAB convention. This requires two integer numbers;
2. the corresponding MAE value, which is a floating-point number. Enter the last number to two decimal points. As an example for format of answer, suppose the matched block has upper-left corner located at (1,1), and the corresponding MAE is 10.12, then you should enter 1 1 10.12 (the three numbers are separated by spaces).


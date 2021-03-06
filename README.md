# Image-Stitching-AE
Using Auto Encoders to Stitch Images

This project focuses on stitching multiple videos together! In short, you can get a wider FOV (Field of View) as compared to a normal camera thus improving the capabilities of autonomous cars as well as humans driving one. But instead of the traditional approaches like Linear Pushbroom, the Stitcher class of CV2, we have tried implementing something new.

We have used Autoencoders for the stitching process along with basic CV2 libraries for the pre-processing of the images. For generating this, we've used the CARLA Simulator to generate the videos/images at 3 different angles.

CARLA - https://carla.org/

![Dataset Images](Images/Carla.jpg?raw=true) 

This is just a glimpse of the total dataset that includes **15k-16k images per camera** from a video recorded at native **1080p at 30 frames per second.**

We then **cylindrically warped** the images to pass into the AutoEncoder as the Input images with the Output/Target Images being the images generated by the Stitcher class. 

![Cylindrical Warp](Images/Cylindrical.jpg?raw=true) 

We created a simple AE with the following architecture - 

![AE Architecture](Images/AE.jpg?raw=true) 

We got a decent result as visible in the picture below -

![Output](Images/result_epoch_500_BS_16_954samples_2xFilters.jpg?raw=true) 

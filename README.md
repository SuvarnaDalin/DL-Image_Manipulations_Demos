# DL Based Image Manipulations for Visulon DAM

Contains Images of the DL based Image manipulation Projects. Unfortunately the codes to these project repos cannot be made public.

## Image Crop Detection - Image_Autocorrect - Image Repair
Auto-corrects cropped Image Parts and aligns centrally

This web app identifies whether the object in the image is cropped, uses DCGAN to auto complete cropped images and then places the object in the image centrally.
The web app was built in Python using the following libraries:
* streamlit
* pytorch
* numpy
* matplotlib
* pillow
* opencv
* imutils

### CROP DETECTION

### CROP CORRECTION/REPAIR
DCGAN, a deep learning generative model was made use to perform image reconstruction. 4, 8 and 64 batch images were trained for 32x32 pixel images.
The results for 4 and 8 batch training set are shown below:
![alt text](https://github.com/SuvarnaDalin/DL-Image_Manipulations_Demos/blob/main/AutoImage_Correction/batch4.png)

The training set was autocropped and resized for the above gan model. The results generated were small. 

The same model is being remodeled to train single batch images with 512x512 pixels. The results shown below are not good enough. 

The GAN model was trained for 500 epochs and better results were obtained.


The model is trained on 500 shoe images with below features. 
Images with dimensions less than 550x550.
Images with shoes facing right.
Cropped on the right side (front part) of the image.

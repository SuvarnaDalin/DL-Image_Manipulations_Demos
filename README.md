# DL Based Image Manipulations for DAM

Contains Images of the DL based Image manipulation Projects. Unfortunately the codes to these project repos cannot be made public.

## Image Crop Detection - Image_Autocorrect - Image Repair
Auto-corrects cropped Image Parts and aligns centrally

This web app identifies whether the object in the image is cropped, uses DCGAN to auto complete cropped images and then places the object in the image centrally.
The web app was built in Python using the following libraries:
* streamlit, tensorflow, torch, pillow, opencv, numpy, matplotlib, imutils

### CROP DETECTION
Detects if the object in an image is cropped or not.
![alt text](https://github.com/SuvarnaDalin/DL-Image_Manipulations_Demos/blob/main/AutoImage_Correction/cropOrnot.png)

### CROP CORRECTION/REPAIR
DCGAN, a deep learning generative model was made use to perform image reconstruction. 4, 8 and 64 batch images were trained for 32x32 pixel images.
The results for 4 and 8 batch training set are shown below:

#### Batch 4
![alt text](https://github.com/SuvarnaDalin/DL-Image_Manipulations_Demos/blob/main/AutoImage_Correction/batch4.png)

#### Batch 8
![alt text](https://github.com/SuvarnaDalin/DL-Image_Manipulations_Demos/blob/main/AutoImage_Correction/batch8.png)

The training set was autocropped and resized for the above gan model. The results generated were small. 

The same model was remodeled to train single batch images with 512x512 pixels. The results shown below for 100 epochs are not good enough.

![alt text](https://github.com/SuvarnaDalin/DL-Image_Manipulations_Demos/blob/main/AutoImage_Correction/512check1.png)

The GAN model was trained for 500 epochs and better results were obtained.

![alt text](https://github.com/SuvarnaDalin/DL-Image_Manipulations_Demos/blob/main/AutoImage_Correction/croprep1.png)

![alt text](https://github.com/SuvarnaDalin/DL-Image_Manipulations_Demos/blob/main/AutoImage_Correction/croprep2.png)

![alt text](https://github.com/SuvarnaDalin/DL-Image_Manipulations_Demos/blob/main/AutoImage_Correction/croprep3.png)

The model was trained on 500 shoe images with below features. 
* Images with dimensions less than 550x550.
* Images with shoes facing right.
* Cropped on the right side (front part) of the image.

#################################################################################################

## Watermark Detection - Watermark Removal
Watermark Detaection and Removal was performed using Keras libraries and GAN generative models.
The web app detects watermarks, removes text based watermark from an Image, and then converts the background to white.
The web app was built in Python using the following libraries:
* streamlit, keras-ocr, tensorflow, torch, rembg, pandas, numpy, matplotlib, pillow, opencv, imutils, scikit-image

### Watermark Detection
Object Classification was performed using CNN (Tensorflow Keras), DL model with custom trained dataset. The results are shown below:

![alt text](https://github.com/SuvarnaDalin/DL-Image_Manipulations_Demos/blob/main/Watermark/WithWat.png)

![alt text](https://github.com/SuvarnaDalin/DL-Image_Manipulations_Demos/blob/main/Watermark/WithoutWat.png)

### Watermark Removal
Compared to the GAN generative model, better results were generated using Keras OCR. The watermarks outside the image was removed perfectly using Keras, however after removing watermarks across images the results were not perfect. The results are shown below:

#### Using GAN

![alt text](https://github.com/SuvarnaDalin/DL-Image_Manipulations_Demos/blob/main/Watermark/GanFuzzyApproach.png)

#### Using Keras OCR

![alt text](https://github.com/SuvarnaDalin/DL-Image_Manipulations_Demos/blob/main/Watermark/kerasWat1.png)

![alt text](https://github.com/SuvarnaDalin/DL-Image_Manipulations_Demos/blob/main/Watermark/kerasWat2.png)

#################################################################################################

## Background Detector & Converter
The web app detects whether the object in the image contains a busy or bordered background. These background based images are then converted to white background images.
The web app was built in Python using the following libraries:
* streamlit, rembg, pandas, numpy, matplotlib, pillow, opencv, imutils, scikit-image

### Busy Background Detection & Conversion

![alt text](https://github.com/SuvarnaDalin/DL-Image_Manipulations_Demos/blob/main/Background/busy.png)

### Bordered Background Detection & Conversion

![alt text](https://github.com/SuvarnaDalin/DL-Image_Manipulations_Demos/blob/main/Background/bordered.png)

#################################################################################################

## Single Or Multiple Object Detector
This web app detects whether an image has a single object or multiple objects.
The web app was built in Python using the following libraries:
* streamlit, torch, rembg, pandas, numpy, matplotlib, pillow, opencv

Object detection was tried using OpenCV and Keras CNN model. The OpenCV method failed in identifying certain images with overlapping objects.
Using Keras (Tensorfow) CNN model, objects in the images were classified correctly. The model was trained using custom dataset containing multiple and single object images. 

### Single Object Detector

![alt text](https://github.com/SuvarnaDalin/DL-Image_Manipulations_Demos/blob/main/ManyVSOne/Single.png)

### Multiple Object Detector

![alt text](https://github.com/SuvarnaDalin/DL-Image_Manipulations_Demos/blob/main/ManyVSOne/Multiple.png)

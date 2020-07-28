# Image_blending_using_opencv
Basic code for smooth blending of 2 images using python and opencv and numpy(obvio) library

We will be making use of python and openCV library for blending 2 images. For this we will need knowledge of openCV, python. Also we will need 2 images. They need not be of the same size(as they will be resized by the code) but its preferable.

# How are we blending the two images?
The most simple way of blending the images is by taking one half of the pixels from one image and other half of pixels from the second image and reconstructing a ew image. This is a simple procedure but it does not give us a smooth merged/blended image. Therfore to have a smooth blended image we make use of gaussian and laplacian pyramids.

# Gaussian pyramid
In a Gaussian pyramid, subsequent images are weighted down using a Gaussian average (Gaussian blur) and scaled down. Each pixel containing a local average corresponds to a neighborhood pixel on a lower level of the pyramid. This technique is used especially in texture synthesis.(Wiki)

# Laplacian pyramid
A Laplacian pyramid is very similar to a Gaussian pyramid but saves the difference image of the blurred versions between each levels. Only the smallest level is not a difference image to enable reconstruction of the high resolution image using the difference images on higher levels. This technique can be used in image compression.(wiki)

# So whats happening?
At first we will compress both the images(i.e apple.jpg and orange.jpg). After that we take one half of the compressed apple.jpg and ohter half of orange.jpg and join the 2 images and construct a new image (apple_orange_blend). After this step we scale up the apple_orange_blend image. In this process there is a loss of pixels. In simple words the image is blured than what you would actually expcect. This blur helps smoothen the middle part of the image and creates the feel og the images being blended together. But this blur is also present on the edges of the fruits. We want the edges of the fruits to be as sharp as possible. Thus we make use of the laplacian pyramids that we constructed. By adding the values of laplacian pyramid to the apple_orange_blend we end up sharpening the edges of the fruits with a blur effect in the middle of the image which gives us the feel of a blended image 

The image in window apple-orange is the image formed by taking one half of the pixels from one image and other half of pixels from the second image.
The image in windoe apple-orange-blend is the image which is blended.

# How to run.
Well its simple. Just download the zip folder and extract into your pc/laptop. Open any editor and run image_blending.py. You are good to go :D

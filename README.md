# LGMVIP-Data-science
# Task 1 Image to pencil sketch

OpenCV-Python is a library of Python bindings designed to solve computer vision problems. cv2.imshow () method is used to display an image in a window. The window automatically fits to the image size.
In this task

first we need to import the cv2 library then find the image which you want to convert into a pencil sketch using python.

We need to read the image in RBG format and then convert it to a grayscale image.
we will read that image by image=cv2.imread In RGB format
then convert into gray scale image 
grey_image=cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
This will turn an image into a classic black and white photo.
Then the next thing to do is invert the grayscale image also called negative image, this will be our inverted grayscale image.Inversion can be used to enhance details.
invert_grey_image=255-grey_image

then convert into a blurred image by using GaussianBlur function
blurred_image=cv2.GaussianBlur(invert_grey_image,(21,21),0)

then convert into a inverted blurred image
inverted_blurred_image=255-blurred_image

Then we can finally create the pencil sketch by mixing the grayscale image with the inverted blurry image.
This can be done by dividing the grayscale image by the inverted blurry image.
pencil_sketch_image=cv2.divide(grey_image,invert_blurred_image,scale=256.0)
Since images are just arrays, we can easily do this programmatically using the divide function from the cv2 library in Python.

## Is this gray or full of color?
Whats the main difference between the images shown below?

![Image of coffee next to coins image](imgs/image01.png)

These images have been preloaded as `coffee_image` and `coins_image` from the scikit-image `data` module using:

``` python
coffee_image = data.coffee()
coins_image = data.coins()
```

Choose the right answer that best describes the main difference related to color and dimensional structure.

In the console, use the function `shape()` from NumPy, to obtain the image shape (Height, Width, Dimensions) and find out. NumPy is already imported as `np`.

**Instructions**

- [ ] Both have 3 channels for RGB-3 color representation.
- [ ] `coffee_image` has a shape of (303, 384), grayscale. And `coins_image` (400, 600, 3), RGB-3.
- [x] `coins_image` has a shape of (303, 384), grayscale. And `coffee_image` (400, 600, 3), RGB-3.
- [ ] Both are grayscale, with single color dimension.

``` python
coffee_image = data.coffee()
coins_image = data.coins()

np.shape(coffee_image)  # coffe_image.shape
np.shape(coins_image)  # coins_image.shape
```

> Yes! The coffee image is RGB-3 colored, that's why it has a 3 at the end, when displaying the shape (H, W, D) of it. While the coins image is grayscale and has a single color channel.

<br>

## RGB to grayscale
In this exercise you will load an image from scikit-image module `data` and make it grayscale, then compare both of them in the output.

We have preloaded a function `show_image(image, title='Image')` that displays the image using Matplotlib. You can check more about its parameters using `?show_image()` or `help(show_image)` in the console.

![Rocket](imgs/image02.png)

**Instructions**

- Import the `data` and `color` modules from Scikit image. The first module provides example images, and the second, color transformation functions.
- Load the `rocket` image.
- Convert the RGB-3 rocket image to grayscale.

``` python
# Import the modules from skimage
from skimage import data, color

# Load the rocket image
rocket = data.rocket()

# Convert the image to grayscale
gray_scaled_rocket = color.rgb2gray(rocket)

# Show the original image
show_image(rocket, 'Original RGB image')

# Show the grayscale image
show_image(gray_scaled_rocket, 'Grayscale image')
```

![alt text](imgs/image03.png)

> Great! You converted an image to grayscale. For many applications of image processing, color information doesn't help us identify important edges or other features. Something that we will cover later in the course.

<br>

## Flipping out
As a prank, someone has turned an image from a photo album of a trip to Seville upside-down and back-to-front! Now, we need to straighten the image, by flipping it.

![City of Seville upside-down!](imgs/image04.png)

_Image loaded as `flipped_seville`._

Using the NumPy methods learned in the course, flip the image horizontally and vertically. Then display the corrected image using the `show_image()` function.
NumPy is already imported as `np`.

**Instructions**

1. Flip the image vertically.
2. Now, flip the vertically-flipped image horizontally.
3. Show the, now fixed, image.

``` python
# Flip the image vertically
seville_vertical_flip = np.flipud(flipped_seville)

# Flip the previous image horizontally
seville_horizontal_flip = np.fliplr(seville_vertical_flip)

# Show the resulting image
show_image(seville_horizontal_flip, 'Seville')
```

![alt text](imgs/image05.png)

> Great work!

<br>

## Histograms
In this exercise, you will analyze the amount of red in the image. To do this, the histogram of the red channel will be computed for the image shown below:

![Woman smiling](imgs/image06.png)

_Image loaded as `image`._

Extracting information from images is a fundamental part of image enhancement. This way you can balance the red and blue to make the image look colder or warmer.

You will use `hist()` to display the 256 different intensities of the red color. And `ravel()` to make these color values an array of one flat dimension.

Matplotlib is preloaded as `plt` and Numpy as `np`.

Remember that if we want to obtain the green color of an image we would do the following:

``` python
green = image[:, :, 1]
```

**Instructions**

Obtain the red channel using slicing.
Plot the histogram and bins in a range of 256. Don't forget `.ravel()` for the color channel.

``` python
# Obtain the red channel
red_channel = image[:, :, 0]

# Plot the red histogram with bins in a range of 256
plt.hist(red_channel.ravel(), bins=256, color='red')

# Set title and show
plt.title('Red Histogram')
plt.show()
```

![alt text](imgs/image07.png)

> Good! With this histogram we see that the image is quite reddish, meaning it has a sensation of warmness. This is because it has a wide and large distribution of bright red pixels, from 0 to around 150.

<br>

## Apply global thresholding
In this exercise, you'll transform a photograph to binary so you can separate the foreground from the background.

To do so, you need to import the required modules, load the image, obtain the optimal thresh value using `threshold_otsu()` and apply it to the image.

You'll see the resulting binarized image when using the `show_image()` function, previously explained.

![Chess pieces](imgs/image08.png)

**_Image loaded as `chess_pieces_image`._**

Remember we have to turn colored images to grayscale. For that we will use the `rgb2gray()` function learned in previous video. Which has already been imported for you.

**Instructions**

- Import the otsu threshold function.
- Turn the image to grayscale.
- Obtain the optimal threshold value of the image.
- Apply thresholding to the image.

``` python
# Import the otsu threshold function
from skimage.filters import threshold_otsu

# Make the image grayscale using rgb2gray
chess_pieces_image_gray = rgb2gray(chess_pieces_image)

# Obtain the optimal threshold value with otsu
thresh = threshold_otsu(chess_pieces_image_gray)

# Apply thresholding to the image
binary = chess_pieces_image_gray > thresh

# Show the image
show_image(binary, 'Binary image')
```

![alt text](imgs/image09.png)

> Awesome! You just converted the image to binary and we can separate the foreground from the background.

<br>

## When the background isn't that obvious
Sometimes, it isn't that obvious to identify the background. If the image background is relatively uniform, then you can use a global threshold value as we practiced before, using `threshold_otsu()`. However, if there's uneven background illumination, adaptive thresholding `threshold_local()` (a.k.a. local thresholding) may produce better results.

In this exercise, you will compare both types of thresholding methods (global and local), to find the optimal way to obtain the binary image we need.

![Page with text](imgs/image10.png)

**_Image loaded as `page_image`._**

**Instructions**

1. Import the otsu threshold function, obtain the optimal global thresh value of the image, and apply global thresholding.

``` python
# Import the otsu threshold function
from skimage.filters import threshold_otsu

# Obtain the optimal otsu global thresh value
global_thresh = threshold_otsu(page_image)

# Obtain the binary image by applying global thresholding
binary_global = page_image > global_thresh

# Show the binary image obtained
show_image(binary_global, 'Global thresholding')
```

![alt text](imgs/image11.png)

2. Import the local threshold function, set block size to 35, obtain the local thresh value, and apply local thresholding.

``` python
# Import the otsu threshold function
from skimage.filters import threshold_local

# Obtain the optimal otsu global thresh value
local_thresh = threshold_local(page_image, 35, offset=10)

# Obtain the binary image by applying global thresholding
binary_local = page_image > local_thresh

# Show the binary image obtained
show_image(binary_local, 'Local thresholding')
```

![alt text](imgs/image12.png)

> Great job! Now you know that you should use local thresholding instead of global if the image has a wide variation of background intensity.

<br>

## Trying other methods
As we saw in the video, not being sure about what thresholding method to use isn't a problem. In fact, scikit-image provides us with a function to check multiple methods and see for ourselves what the best option is. It returns a figure comparing the outputs of different **global** thresholding methods.

![Forest fruits](imgs/image13.png)

**_Image loaded as `fruits_image`._**

You will apply this function to this image, `matplotlib.pyplot` has been loaded as `plt`. Remember that you can use `try_all_threshold()` to try multiple global algorithms.

**Instructions**

- Import the try all function.
- Import the rgb to gray convertor function.
- Turn the fruits image to grayscale.
- Use the try all method on the resulting grayscale image.

``` python
# Import the try all function
from skimage.filters import try_all_threshold

# Import the rgb to gray convertor function 
from skimage.color import rgb2gray

# Turn the fruits_image to grayscale
grayscale = rgb2gray(fruits_image)

# Use the try all method on the resulting grayscale image
fig, ax = try_all_threshold(grayscale, verbose=False)

# Show the resulting plots
plt.show()
```

![alt text](imgs/image14.png)

> Nice! As you see, this image works good with some global thresholding methods (like the "Yen" and "Mean") and not so well in others, (like the "Minimum").

<br>

## Apply thresholding
In this exercise, you will decide what type of thresholding is best used to binarize an image of knitting and craft tools. In doing so, you will be able to see the shapes of the objects, from paper hearts to scissors more clearly.

![Several tools for handcraft art](imgs/image15.png)

**_Image loaded as `tools_image`._**

What type of thresholding would you use judging by the characteristics of the image? Is the background illumination and intensity even or uneven?

**Instructions**

- Import the appropriate thresholding and `rgb2gray()` functions.
- Turn the image to grayscale.
- Obtain the optimal thresh.
- Obtain the binary image by applying thresholding.

``` python 
# Import threshold and gray convertor functions
from skimage.filters import threshold_otsu
from skimage.color import rgb2gray

# Turn the image grayscale
gray_tools_image = rgb2gray(tools_image)

# Obtain the optimal thresh
thresh = threshold_otsu(gray_tools_image)

# Obtain the binary image by applying thresholding
binary_image = gray_tools_image > thresh

# Show the resulting binary image
show_image(binary_image, 'Binarized image')
```

![alt text](imgs/image16.png)

> Awesome! By using a global thresholding method, you obtained the precise binarized image. If you would have used local instead nothing would have been segmented.

> Try it yourself and see it! In the next chapters, we'll get into image restoration, face detection, and much more. Stay tuned!
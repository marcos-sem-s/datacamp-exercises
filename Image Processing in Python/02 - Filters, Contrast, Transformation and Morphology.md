## Edge detection
In this exercise, you'll detect edges in an image by applying the Sobel filter.

![Soap pills of heart and rectangle shapes in blue background](image.png)

Image preloaded as `soaps_image`.

The `show_image()` function has been already loaded for you.

Let's see if it spots all the figures in the image.

**Instructions**

- Import the `color` module so you can convert the image to grayscale.
- Import the `sobel()` function from `filters` module.
- Make `soaps_image` grayscale using the appropriate method from the `color` module.
- Apply the sobel edge detection filter on the obtained grayscale image `soaps_image_gray`.

``` python
# Import the color module
from skimage import color

# Import the filters module and sobel function
from skimage.filters import sobel

# Make the image grayscale
soaps_image_gray = color.rgb2gray(soaps_image)

# Apply edge detection filter
edge_sobel = sobel(soaps_image_gray)

# Show original and resulting image to compare
show_image(soaps_image, "Original")
show_image(edge_sobel, "Edges with Sobel")
```

<br>

## Blurring to reduce noise
In this exercise you will reduce the sharpness of an image of a building taken during a London trip, through filtering.

![Building in Lodon](image-1.png)
Image loaded as `building_image`.

**Instructions**

- Import the Gaussian filter.
- Apply the filter to the `building_image`, set the multichannel parameter to the correct value.
- Show the original `building_image` and resulting `gaussian_image`.

``` python
# Import Gaussian filter 
from skimage.filters import gaussian

# Apply filter
gaussian_image = gaussian(building_image, multichannel=True)

# Show original and resulting image to compare
show_image(building_image, "Original")
show_image(gaussian_image, "Reduced sharpness Gaussian")
```

<br>

## What's the contrast of this image?

![Black and white clock hanging and moving](image-2.png)
![Histogram of the clock's image](image-3.png)

The histogram tell us.

Just as we saw previously, you can calculate the contrast by calculating the **range** of the pixel intensities i.e. by subtracting the minimum pixel intensity value from the **histogram** to the maximum one.

You can obtain the maximum pixel intensity of the image by using the `np.max()` method from NumPy and the minimum with `np.min()` **in the console**.

The image has already been loaded as `clock_image`, NumPy as `np` and the `show_image()` function.

**Instructions**

- [ ] The contrast is 255 (high contrast).

- [ ] The contrast is 148.

- [ ] The contrast is 189.

- [ ] The contrast is 49 (low contrast).

<br>

## 
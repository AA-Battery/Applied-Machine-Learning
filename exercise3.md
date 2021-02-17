### Apply three filters to image:

##### Here is the original image:
![Original Image](orignal.png)

##### Here is the image convolved with filter one:
![Convolution One](conv_1.png)

This filter highlighted (detected) the background diagonal lines in the image.

##### Here is the image convolved with filter two:
![Convolution Two](conv_2.png)

This filter highlighted (detected) the vertical lines in the image. 

##### Here is the image convolved with filter three:
![Convolution Three](conv_3.png)

This filter highlighted (detected) the horizontal lines in the image. 

### What are you functionally accomplishing by applying these filters to your original array? Why is this useful?

Each filter has three sets of arrays with three integers in each. Each integer in each array is applied to a corresponding integer pixel value in the original image. This distorts the image, i.e. highlighting certain aspects of the image based on the interger values in the filter. This is useful because it allows the network to more accurately associate distinct features in an image with the output.

### Apply 2x2 pooling filter to image:

##### Here is the image convoled with filter three and pooled with a filter of dimension 2x2:
![Pooled Image](conv_3_pooled.png)

### What have you accomplished with pooling? Which type of filter pooling is applied? Did the result increase or decrease in size?

This pooling has made the image a quarter as big. The pooling used is max pooling. A filter of size 2x2 was iteratively slid across the original pixel values of the image, and the largest of those four pixels was extracted as the value for the new pooled image. The pooled image is smaller in size.


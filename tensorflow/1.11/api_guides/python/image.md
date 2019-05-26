# Images

Note: Functions taking `Tensor` arguments can also take anything accepted by
<a href="../../api_docs/python/tf/convert_to_tensor.md"><code>tf.convert_to_tensor</code></a>.

[TOC]

<h2 id="Encoding_and_Decoding">Encoding and Decoding</h2>

TensorFlow provides Ops to decode and encode JPEG and PNG formats.  Encoded
images are represented by scalar string Tensors, decoded images by 3-D uint8
tensors of shape `[height, width, channels]`. (PNG also supports uint16.)

The encode and decode Ops apply to one image at a time.  Their input and output
are all of variable size.  If you need fixed size images, pass the output of
the decode Ops to one of the cropping and resizing Ops.

Note: The PNG encode and decode Ops support RGBA, but the conversions Ops
presently only support RGB, HSV, and GrayScale. Presently, the alpha channel has
to be stripped from the image and re-attached using slicing ops.

*   <a href="../../api_docs/python/tf/image/decode_bmp.md"><code>tf.image.decode_bmp</code></a>
*   <a href="../../api_docs/python/tf/image/decode_gif.md"><code>tf.image.decode_gif</code></a>
*   <a href="../../api_docs/python/tf/image/decode_jpeg.md"><code>tf.image.decode_jpeg</code></a>
*   <a href="../../api_docs/python/tf/image/encode_jpeg.md"><code>tf.image.encode_jpeg</code></a>
*   <a href="../../api_docs/python/tf/image/decode_png.md"><code>tf.image.decode_png</code></a>
*   <a href="../../api_docs/python/tf/image/encode_png.md"><code>tf.image.encode_png</code></a>
*   <a href="../../api_docs/python/tf/image/decode_image.md"><code>tf.image.decode_image</code></a>

<h2 id="Resizing">Resizing</h2>

The resizing Ops accept input images as tensors of several types.  They always
output resized images as float32 tensors.

The convenience function <a href="../../api_docs/python/tf/image/resize_images.md"><code>tf.image.resize_images</code></a> supports both 4-D
and 3-D tensors as input and output.  4-D tensors are for batches of images,
3-D tensors for individual images.

Other resizing Ops only support 4-D batches of images as input:
<a href="../../api_docs/python/tf/image/resize_area.md"><code>tf.image.resize_area</code></a>, <a href="../../api_docs/python/tf/image/resize_bicubic.md"><code>tf.image.resize_bicubic</code></a>,
<a href="../../api_docs/python/tf/image/resize_bilinear.md"><code>tf.image.resize_bilinear</code></a>,
<a href="../../api_docs/python/tf/image/resize_nearest_neighbor.md"><code>tf.image.resize_nearest_neighbor</code></a>.

Example:

```python
# Decode a JPG image and resize it to 299 by 299 using default method.
image = tf.image.decode_jpeg(...)
resized_image = tf.image.resize_images(image, [299, 299])
```

*   <a href="../../api_docs/python/tf/image/resize_images.md"><code>tf.image.resize_images</code></a>
*   <a href="../../api_docs/python/tf/image/resize_area.md"><code>tf.image.resize_area</code></a>
*   <a href="../../api_docs/python/tf/image/resize_bicubic.md"><code>tf.image.resize_bicubic</code></a>
*   <a href="../../api_docs/python/tf/image/resize_bilinear.md"><code>tf.image.resize_bilinear</code></a>
*   <a href="../../api_docs/python/tf/image/resize_nearest_neighbor.md"><code>tf.image.resize_nearest_neighbor</code></a>

<h2 id="Cropping">Cropping</h2>

*   <a href="../../api_docs/python/tf/image/resize_image_with_crop_or_pad.md"><code>tf.image.resize_image_with_crop_or_pad</code></a>
*   <a href="../../api_docs/python/tf/image/central_crop.md"><code>tf.image.central_crop</code></a>
*   <a href="../../api_docs/python/tf/image/pad_to_bounding_box.md"><code>tf.image.pad_to_bounding_box</code></a>
*   <a href="../../api_docs/python/tf/image/crop_to_bounding_box.md"><code>tf.image.crop_to_bounding_box</code></a>
*   <a href="../../api_docs/python/tf/image/extract_glimpse.md"><code>tf.image.extract_glimpse</code></a>
*   <a href="../../api_docs/python/tf/image/crop_and_resize.md"><code>tf.image.crop_and_resize</code></a>

<h2 id="Flipping_Rotating_and_Transposing">Flipping, Rotating and Transposing</h2>

*   <a href="../../api_docs/python/tf/image/flip_up_down.md"><code>tf.image.flip_up_down</code></a>
*   <a href="../../api_docs/python/tf/image/random_flip_up_down.md"><code>tf.image.random_flip_up_down</code></a>
*   <a href="../../api_docs/python/tf/image/flip_left_right.md"><code>tf.image.flip_left_right</code></a>
*   <a href="../../api_docs/python/tf/image/random_flip_left_right.md"><code>tf.image.random_flip_left_right</code></a>
*   <a href="../../api_docs/python/tf/image/transpose_image.md"><code>tf.image.transpose_image</code></a>
*   <a href="../../api_docs/python/tf/image/rot90.md"><code>tf.image.rot90</code></a>

<h2 id="Converting_Between_Colorspaces">Converting Between Colorspaces</h2>

Image ops work either on individual images or on batches of images, depending on
the shape of their input Tensor.

If 3-D, the shape is `[height, width, channels]`, and the Tensor represents one
image. If 4-D, the shape is `[batch_size, height, width, channels]`, and the
Tensor represents `batch_size` images.

Currently, `channels` can usefully be 1, 2, 3, or 4. Single-channel images are
grayscale, images with 3 channels are encoded as either RGB or HSV. Images
with 2 or 4 channels include an alpha channel, which has to be stripped from the
image before passing the image to most image processing functions (and can be
re-attached later).

Internally, images are either stored in as one `float32` per channel per pixel
(implicitly, values are assumed to lie in `[0,1)`) or one `uint8` per channel
per pixel (values are assumed to lie in `[0,255]`).

TensorFlow can convert between images in RGB or HSV. The conversion functions
work only on float images, so you need to convert images in other formats using
<a href="../../api_docs/python/tf/image/convert_image_dtype.md"><code>tf.image.convert_image_dtype</code></a>.

Example:

```python
# Decode an image and convert it to HSV.
rgb_image = tf.image.decode_png(...,  channels=3)
rgb_image_float = tf.image.convert_image_dtype(rgb_image, tf.float32)
hsv_image = tf.image.rgb_to_hsv(rgb_image)
```

*   <a href="../../api_docs/python/tf/image/rgb_to_grayscale.md"><code>tf.image.rgb_to_grayscale</code></a>
*   <a href="../../api_docs/python/tf/image/grayscale_to_rgb.md"><code>tf.image.grayscale_to_rgb</code></a>
*   <a href="../../api_docs/python/tf/image/hsv_to_rgb.md"><code>tf.image.hsv_to_rgb</code></a>
*   <a href="../../api_docs/python/tf/image/rgb_to_hsv.md"><code>tf.image.rgb_to_hsv</code></a>
*   <a href="../../api_docs/python/tf/image/convert_image_dtype.md"><code>tf.image.convert_image_dtype</code></a>

<h2 id="Image_Adjustments">Image Adjustments</h2>

TensorFlow provides functions to adjust images in various ways: brightness,
contrast, hue, and saturation.  Each adjustment can be done with predefined
parameters or with random parameters picked from predefined intervals. Random
adjustments are often useful to expand a training set and reduce overfitting.

If several adjustments are chained it is advisable to minimize the number of
redundant conversions by first converting the images to the most natural data
type and representation (RGB or HSV).

*   <a href="../../api_docs/python/tf/image/adjust_brightness.md"><code>tf.image.adjust_brightness</code></a>
*   <a href="../../api_docs/python/tf/image/random_brightness.md"><code>tf.image.random_brightness</code></a>
*   <a href="../../api_docs/python/tf/image/adjust_contrast.md"><code>tf.image.adjust_contrast</code></a>
*   <a href="../../api_docs/python/tf/image/random_contrast.md"><code>tf.image.random_contrast</code></a>
*   <a href="../../api_docs/python/tf/image/adjust_hue.md"><code>tf.image.adjust_hue</code></a>
*   <a href="../../api_docs/python/tf/image/random_hue.md"><code>tf.image.random_hue</code></a>
*   <a href="../../api_docs/python/tf/image/adjust_gamma.md"><code>tf.image.adjust_gamma</code></a>
*   <a href="../../api_docs/python/tf/image/adjust_saturation.md"><code>tf.image.adjust_saturation</code></a>
*   <a href="../../api_docs/python/tf/image/random_saturation.md"><code>tf.image.random_saturation</code></a>
*   <a href="../../api_docs/python/tf/image/per_image_standardization.md"><code>tf.image.per_image_standardization</code></a>

<h2 id="Working_with_Bounding_Boxes">Working with Bounding Boxes</h2>

*   <a href="../../api_docs/python/tf/image/draw_bounding_boxes.md"><code>tf.image.draw_bounding_boxes</code></a>
*   <a href="../../api_docs/python/tf/image/non_max_suppression.md"><code>tf.image.non_max_suppression</code></a>
*   <a href="../../api_docs/python/tf/image/sample_distorted_bounding_box.md"><code>tf.image.sample_distorted_bounding_box</code></a>

<h2 id="Denoising">Denoising</h2>

*   <a href="../../api_docs/python/tf/image/total_variation.md"><code>tf.image.total_variation</code></a>

<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.resize_images" />
</div>

# tf.image.resize_images

``` python
tf.image.resize_images(
    images,
    size,
    method=ResizeMethod.BILINEAR,
    align_corners=False,
    preserve_aspect_ratio=False
)
```



Defined in [`tensorflow/python/ops/image_ops_impl.py`](https://www.tensorflow.org/code/tensorflow/python/ops/image_ops_impl.py).

See the guide: [Images > Resizing](../../../../api_guides/python/image.md#Resizing)

Resize `images` to `size` using the specified `method`.

Resized images will be distorted if their original aspect ratio is not
the same as `size`.  To avoid distortions see
<a href="../../tf/image/resize_image_with_pad.md"><code>tf.image.resize_image_with_pad</code></a>.

`method` can be one of:

*   <b>`ResizeMethod.BILINEAR`</b>: [Bilinear interpolation.](
  https://en.wikipedia.org/wiki/Bilinear_interpolation)
*   <b>`ResizeMethod.NEAREST_NEIGHBOR`</b>: [Nearest neighbor interpolation.](
  https://en.wikipedia.org/wiki/Nearest-neighbor_interpolation)
*   <b>`ResizeMethod.BICUBIC`</b>: [Bicubic interpolation.](
  https://en.wikipedia.org/wiki/Bicubic_interpolation)
*   <b>`ResizeMethod.AREA`</b>: Area interpolation.

The return value has the same type as `images` if `method` is
`ResizeMethod.NEAREST_NEIGHBOR`. It will also have the same type as `images`
if the size of `images` can be statically determined to be the same as `size`,
because `images` is returned in this case. Otherwise, the return value has
type `float32`.

#### Args:

* <b>`images`</b>: 4-D Tensor of shape `[batch, height, width, channels]` or
          3-D Tensor of shape `[height, width, channels]`.
* <b>`size`</b>: A 1-D int32 Tensor of 2 elements: `new_height, new_width`.  The
        new size for the images.
* <b>`method`</b>: ResizeMethod.  Defaults to `ResizeMethod.BILINEAR`.
* <b>`align_corners`</b>: bool.  If True, the centers of the 4 corner pixels of the
      input and output tensors are aligned, preserving the values at the
      corner pixels. Defaults to `False`.
* <b>`preserve_aspect_ratio`</b>: Whether to preserve the aspect ratio. If this is set,
    then `images` will be resized to a size that fits in `size` while
    preserving the aspect ratio of the original image. Scales up the image if
    `size` is bigger than the current size of the `image`. Defaults to False.


#### Raises:

* <b>`ValueError`</b>: if the shape of `images` is incompatible with the
    shape arguments to this function
* <b>`ValueError`</b>: if `size` has invalid shape or type.
* <b>`ValueError`</b>: if an unsupported resize method is specified.


#### Returns:

If `images` was 4-D, a 4-D float Tensor of shape
`[batch, new_height, new_width, channels]`.
If `images` was 3-D, a 3-D float Tensor of shape
`[new_height, new_width, channels]`.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.rot90" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.rot90

``` python
tf.image.rot90(
    image,
    k=1,
    name=None
)
```



Defined in [`tensorflow/python/ops/image_ops_impl.py`](https://www.tensorflow.org/code/tensorflow/python/ops/image_ops_impl.py).

See the guide: [Images > Flipping, Rotating and Transposing](../../../../api_guides/python/image.md#Flipping_Rotating_and_Transposing)

Rotate image(s) counter-clockwise by 90 degrees.

#### Args:

* <b>`image`</b>: 4-D Tensor of shape `[batch, height, width, channels]` or
         3-D Tensor of shape `[height, width, channels]`.
* <b>`k`</b>: A scalar integer. The number of times the image is rotated by 90 degrees.
* <b>`name`</b>: A name for this operation (optional).


#### Returns:

A rotated tensor of the same type and shape as `image`.


#### Raises:

* <b>`ValueError`</b>: if the shape of `image` not supported.
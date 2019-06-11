<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.flip_left_right" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.flip_left_right

Flip an image horizontally (left to right).

### Aliases:

* `tf.compat.v1.image.flip_left_right`
* `tf.compat.v2.image.flip_left_right`
* `tf.image.flip_left_right`

``` python
tf.image.flip_left_right(image)
```



Defined in [`python/ops/image_ops_impl.py`](/code/stable/tensorflow/python/ops/image_ops_impl.py).

<!-- Placeholder for "Used in" -->

Outputs the contents of `image` flipped along the width dimension.

See also `reverse()`.

#### Args:


* <b>`image`</b>: 4-D Tensor of shape `[batch, height, width, channels]` or 3-D Tensor
  of shape `[height, width, channels]`.


#### Returns:

A tensor of the same type and shape as `image`.



#### Raises:


* <b>`ValueError`</b>: if the shape of `image` not supported.
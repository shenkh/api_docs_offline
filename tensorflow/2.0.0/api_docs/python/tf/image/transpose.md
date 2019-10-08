<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.transpose" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.transpose

``` python
tf.image.transpose(
    image,
    name=None
)
```



Defined in [`tensorflow/python/ops/image_ops_impl.py`](/code/stable/tensorflow/python/ops/image_ops_impl.py).

Transpose image(s) by swapping the height and width dimension.

#### Args:

* <b>`image`</b>: 4-D Tensor of shape `[batch, height, width, channels]` or 3-D Tensor
    of shape `[height, width, channels]`.
* <b>`name`</b>: A name for this operation (optional).


#### Returns:

 If `image` was 4-D, a 4-D float Tensor of shape
`[batch, width, height, channels]`
 If `image` was 3-D, a 3-D float Tensor of shape
`[width, height, channels]`


#### Raises:

* <b>`ValueError`</b>: if the shape of `image` not supported.
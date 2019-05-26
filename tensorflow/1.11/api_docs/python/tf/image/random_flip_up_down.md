<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.random_flip_up_down" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.random_flip_up_down

``` python
tf.image.random_flip_up_down(
    image,
    seed=None
)
```



Defined in [`tensorflow/python/ops/image_ops_impl.py`](https://www.tensorflow.org/code/tensorflow/python/ops/image_ops_impl.py).

See the guide: [Images > Flipping, Rotating and Transposing](../../../../api_guides/python/image.md#Flipping_Rotating_and_Transposing)

Randomly flips an image vertically (upside down).

With a 1 in 2 chance, outputs the contents of `image` flipped along the first
dimension, which is `height`.  Otherwise output the image as-is.

#### Args:

* <b>`image`</b>: 4-D Tensor of shape `[batch, height, width, channels]` or
         3-D Tensor of shape `[height, width, channels]`.
* <b>`seed`</b>: A Python integer. Used to create a random seed. See
    <a href="../../tf/set_random_seed.md"><code>tf.set_random_seed</code></a>
    for behavior.


#### Returns:

A tensor of the same type and shape as `image`.

#### Raises:

* <b>`ValueError`</b>: if the shape of `image` not supported.
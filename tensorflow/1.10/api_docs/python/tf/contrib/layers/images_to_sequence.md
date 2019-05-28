<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.layers.images_to_sequence" />
</div>

# tf.contrib.layers.images_to_sequence

``` python
tf.contrib.layers.images_to_sequence(
    inputs,
    data_format=DATA_FORMAT_NHWC,
    outputs_collections=None,
    scope=None
)
```



Defined in [`tensorflow/contrib/layers/python/layers/layers.py`](https://www.tensorflow.org/code/tensorflow/contrib/layers/python/layers/layers.py).

Convert a batch of images into a batch of sequences.

#### Args:

* <b>`inputs`</b>: a (num_images, height, width, depth) tensor
* <b>`data_format`</b>: A string. `NHWC` (default) and `NCHW` are supported.
* <b>`outputs_collections`</b>: The collections to which the outputs are added.
* <b>`scope`</b>: Optional scope for name_scope.


#### Raises:

* <b>`ValueError`</b>: If `data_format` is not either NCHW or NHWC.


#### Returns:

(width, num_images*height, depth) sequence tensor
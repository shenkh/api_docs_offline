<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.rgb_to_yiq" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.rgb_to_yiq

``` python
tf.image.rgb_to_yiq(images)
```



Defined in [`tensorflow/python/ops/image_ops_impl.py`](/code/stable/tensorflow/python/ops/image_ops_impl.py).

Converts one or more images from RGB to YIQ.

Outputs a tensor of the same shape as the `images` tensor, containing the YIQ
value of the pixels.
The output is only well defined if the value in images are in [0,1].

#### Args:

* <b>`images`</b>: 2-D or higher rank. Image data to convert. Last dimension must be
    size 3.


#### Returns:

* <b>`images`</b>: tensor with the same shape as `images`.
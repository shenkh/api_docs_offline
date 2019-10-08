<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.yiq_to_rgb" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.yiq_to_rgb

``` python
tf.image.yiq_to_rgb(images)
```



Defined in [`tensorflow/python/ops/image_ops_impl.py`](/code/stable/tensorflow/python/ops/image_ops_impl.py).

Converts one or more images from YIQ to RGB.

Outputs a tensor of the same shape as the `images` tensor, containing the RGB
value of the pixels.
The output is only well defined if the Y value in images are in [0,1],
I value are in [-0.5957,0.5957] and Q value are in [-0.5226,0.5226].

#### Args:

* <b>`images`</b>: 2-D or higher rank. Image data to convert. Last dimension must be
    size 3.


#### Returns:

* <b>`images`</b>: tensor with the same shape as `images`.
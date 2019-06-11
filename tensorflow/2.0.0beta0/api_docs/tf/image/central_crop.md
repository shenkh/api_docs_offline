<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.central_crop" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.central_crop

Crop the central region of the image(s).

### Aliases:

* `tf.compat.v1.image.central_crop`
* `tf.compat.v2.image.central_crop`
* `tf.image.central_crop`

``` python
tf.image.central_crop(
    image,
    central_fraction
)
```



Defined in [`python/ops/image_ops_impl.py`](/code/stable/tensorflow/python/ops/image_ops_impl.py).

<!-- Placeholder for "Used in" -->

Remove the outer parts of an image but retain the central region of the image
along each dimension. If we specify central_fraction = 0.5, this function
returns the region marked with "X" in the below diagram.

     --------
    |        |
    |  XXXX  |
    |  XXXX  |
    |        |   where "X" is the central 50% of the image.
     --------

This function works on either a single image (`image` is a 3-D Tensor), or a
batch of images (`image` is a 4-D Tensor).

#### Args:


* <b>`image`</b>: Either a 3-D float Tensor of shape [height, width, depth], or a 4-D
  Tensor of shape [batch_size, height, width, depth].
* <b>`central_fraction`</b>: float (0, 1], fraction of size to crop


#### Raises:


* <b>`ValueError`</b>: if central_crop_fraction is not within (0, 1].


#### Returns:

3-D / 4-D float Tensor, as per the input.

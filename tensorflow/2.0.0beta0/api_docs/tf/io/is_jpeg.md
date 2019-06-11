<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io.is_jpeg" />
<meta itemprop="path" content="Stable" />
</div>

# tf.io.is_jpeg

Convenience function to check if the 'contents' encodes a JPEG image.

### Aliases:

* `tf.compat.v1.image.is_jpeg`
* `tf.compat.v1.io.is_jpeg`
* `tf.compat.v2.image.is_jpeg`
* `tf.compat.v2.io.is_jpeg`
* `tf.image.is_jpeg`
* `tf.io.is_jpeg`

``` python
tf.io.is_jpeg(
    contents,
    name=None
)
```



Defined in [`python/ops/image_ops_impl.py`](/code/stable/tensorflow/python/ops/image_ops_impl.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`contents`</b>: 0-D `string`. The encoded image bytes.
* <b>`name`</b>: A name for the operation (optional)


#### Returns:

A scalar boolean tensor indicating if 'contents' may be a JPEG image.
is_jpeg is susceptible to false positives.

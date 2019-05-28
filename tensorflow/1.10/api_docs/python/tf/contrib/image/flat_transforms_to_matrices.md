<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.image.flat_transforms_to_matrices" />
</div>

# tf.contrib.image.flat_transforms_to_matrices

``` python
tf.contrib.image.flat_transforms_to_matrices(transforms)
```



Defined in [`tensorflow/contrib/image/python/ops/image_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/image/python/ops/image_ops.py).

Converts <a href="../../../tf/contrib/image.md"><code>tf.contrib.image</code></a> projective transforms to affine matrices.

Note that the output matrices map output coordinates to input coordinates. For
the forward transformation matrix, call <a href="../../../tf/matrix_inverse.md"><code>tf.linalg.inv</code></a> on the result.

#### Args:

* <b>`transforms`</b>: Vector of length 8, or batches of transforms with shape
    `(N, 8)`.


#### Returns:

3D tensor of matrices with shape `(N, 3, 3)`. The output matrices map the
  *output coordinates* (in homogeneous coordinates) of each transform to the
  corresponding *input coordinates*.


#### Raises:

* <b>`ValueError`</b>: If `transforms` have an invalid shape.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.kfac.utils.mat2d_to_layer_params" />
</div>

# tf.contrib.kfac.utils.mat2d_to_layer_params

``` python
tf.contrib.kfac.utils.mat2d_to_layer_params(
    vector_template,
    mat2d
)
```



Defined in [`tensorflow/contrib/kfac/python/ops/utils.py`](https://www.tensorflow.org/code/tensorflow/contrib/kfac/python/ops/utils.py).

Converts a canonical 2D matrix representation back to a vector.

#### Args:

* <b>`vector_template`</b>: A Tensor or pair of Tensors shaped like layer parameters.
* <b>`mat2d`</b>: A 2D Tensor with the same shape as the value of
      layer_params_to_mat2d(vector_template).


#### Returns:

A Tensor or pair of Tensors with the same coefficients as mat2d and the same
    shape as vector_template.
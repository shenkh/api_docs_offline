<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.reduce_max" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.reduce_max

Computes the maximum of elements across dimensions of a tensor.

### Aliases:

* `tf.compat.v2.math.reduce_max`
* `tf.compat.v2.reduce_max`
* `tf.math.reduce_max`
* `tf.reduce_max`

``` python
tf.math.reduce_max(
    input_tensor,
    axis=None,
    keepdims=False,
    name=None
)
```



Defined in [`python/ops/math_ops.py`](/code/stable/tensorflow/python/ops/math_ops.py).

<!-- Placeholder for "Used in" -->

Reduces `input_tensor` along the dimensions given in `axis`.
Unless `keepdims` is true, the rank of the tensor is reduced by 1 for each
entry in `axis`. If `keepdims` is true, the reduced dimensions
are retained with length 1.

If `axis` is None, all dimensions are reduced, and a
tensor with a single element is returned.

#### Args:


* <b>`input_tensor`</b>: The tensor to reduce. Should have real numeric type.
* <b>`axis`</b>: The dimensions to reduce. If `None` (the default), reduces all
  dimensions. Must be in the range `[-rank(input_tensor),
  rank(input_tensor))`.
* <b>`keepdims`</b>: If true, retains reduced dimensions with length 1.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

The reduced tensor.




#### Numpy Compatibility
Equivalent to np.max


<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.reduce_min" />
<meta itemprop="path" content="Stable" />
</div>

# tf.reduce_min

``` python
tf.reduce_min(
    input_tensor,
    axis=None,
    keepdims=None,
    name=None,
    reduction_indices=None,
    keep_dims=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](https://www.tensorflow.org/code/tensorflow/python/ops/math_ops.py).

See the guides: [Math > Reduction](../../../api_guides/python/math_ops.md#Reduction), [Upgrade to TensorFlow 1.0 > Upgrading your code manually](../../../api_guides/python/upgrade.md#Upgrading_your_code_manually)

Computes the minimum of elements across dimensions of a tensor. (deprecated arguments)

SOME ARGUMENTS ARE DEPRECATED. They will be removed in a future version.
Instructions for updating:
keep_dims is deprecated, use keepdims instead

Reduces `input_tensor` along the dimensions given in `axis`.
Unless `keepdims` is true, the rank of the tensor is reduced by 1 for each
entry in `axis`. If `keepdims` is true, the reduced dimensions
are retained with length 1.

If `axis` is None, all dimensions are reduced, and a
tensor with a single element is returned.

#### Args:

* <b>`input_tensor`</b>: The tensor to reduce. Should have real numeric type.
* <b>`axis`</b>: The dimensions to reduce. If `None` (the default),
    reduces all dimensions. Must be in the range
    `[-rank(input_tensor), rank(input_tensor))`.
* <b>`keepdims`</b>: If true, retains reduced dimensions with length 1.
* <b>`name`</b>: A name for the operation (optional).
* <b>`reduction_indices`</b>: The old (deprecated) name for axis.
* <b>`keep_dims`</b>: Deprecated alias for `keepdims`.


#### Returns:

The reduced tensor.



#### Numpy Compatibility
Equivalent to np.min


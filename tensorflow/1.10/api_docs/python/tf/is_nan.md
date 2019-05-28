<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.is_nan" />
</div>

# tf.is_nan

### Aliases:

* `tf.debugging.is_nan`
* `tf.is_nan`

``` python
tf.is_nan(
    x,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

See the guide: [Control Flow > Debugging Operations](../../../api_guides/python/control_flow_ops.md#Debugging_Operations)

Returns which elements of x are NaN.



#### Args:

* <b>`x`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type `bool`.

#### Numpy Compatibility
Equivalent to np.isnan


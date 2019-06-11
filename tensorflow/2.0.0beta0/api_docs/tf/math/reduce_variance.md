<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.reduce_variance" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.reduce_variance

Computes the variance of elements across dimensions of a tensor.

### Aliases:

* `tf.compat.v1.math.reduce_variance`
* `tf.compat.v2.math.reduce_variance`
* `tf.math.reduce_variance`

``` python
tf.math.reduce_variance(
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

#### For example:



```python
x = tf.constant([[1., 2.], [3., 4.]])
tf.reduce_variance(x)  # 1.25
tf.reduce_variance(x, 0)  # [1., 1.]
tf.reduce_variance(x, 1)  # [0.25,  0.25]
```

#### Args:


* <b>`input_tensor`</b>: The tensor to reduce. Should have numeric type.
* <b>`axis`</b>: The dimensions to reduce. If `None` (the default), reduces all
  dimensions. Must be in the range `[-rank(input_tensor),
  rank(input_tensor))`.
* <b>`keepdims`</b>: If true, retains reduced dimensions with length 1.
* <b>`name`</b>: A name scope for the associated operations (optional).


#### Returns:

The reduced tensor, of the same dtype as the input_tensor.




#### Numpy Compatibility
Equivalent to np.var

Please note that `np.var` has a `dtype` parameter that could be used to
specify the output type. By default this is `dtype=float64`. On the other
hand, `tf.reduce_variance` has an aggressive type inference from
`input_tensor`,


<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.not_equal" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.not_equal

### Aliases:

* `tf.math.not_equal`
* `tf.not_equal`

``` python
tf.math.not_equal(
    x,
    y,
    name=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](/code/stable/tensorflow/python/ops/math_ops.py).

Returns the truth value of (x != y) element-wise.

**NOTE**: `NotEqual` supports broadcasting. More about broadcasting [here](
https://docs.scipy.org/doc/numpy-1.13.0/user/basics.broadcasting.html)

#### Args:

* <b>`x`</b>: A `Tensor` or `SparseTensor` or `IndexedSlices`.
* <b>`y`</b>: A `Tensor` or `SparseTensor` or `IndexedSlices`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of type bool with the same size as that of x or y.
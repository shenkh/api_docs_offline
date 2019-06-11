<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.zeros" />
<meta itemprop="path" content="Stable" />
</div>

# tf.zeros

Creates a tensor with all elements set to zero.

### Aliases:

* `tf.compat.v1.zeros`
* `tf.compat.v2.zeros`
* `tf.zeros`

``` python
tf.zeros(
    shape,
    dtype=tf.dtypes.float32,
    name=None
)
```



Defined in [`python/ops/array_ops.py`](/code/stable/tensorflow/python/ops/array_ops.py).

<!-- Placeholder for "Used in" -->

This operation returns a tensor of type `dtype` with shape `shape` and
all elements set to zero.

#### For example:



```python
tf.zeros([3, 4], tf.int32)  # [[0, 0, 0, 0], [0, 0, 0, 0], [0, 0, 0, 0]]
```

#### Args:


* <b>`shape`</b>: A list of integers, a tuple of integers, or a 1-D `Tensor` of type
  `int32`.
* <b>`dtype`</b>: The type of an element in the resulting `Tensor`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` with all elements set to zero.

<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.ones" />
<meta itemprop="path" content="Stable" />
</div>

# tf.ones

Creates a tensor with all elements set to 1.

### Aliases:

* `tf.compat.v1.ones`
* `tf.compat.v2.ones`
* `tf.ones`

``` python
tf.ones(
    shape,
    dtype=tf.dtypes.float32,
    name=None
)
```



Defined in [`python/ops/array_ops.py`](/code/stable/tensorflow/python/ops/array_ops.py).

<!-- Placeholder for "Used in" -->

This operation returns a tensor of type `dtype` with shape `shape` and all
elements set to 1.

#### For example:



```python
tf.ones([2, 3], tf.int32)  # [[1, 1, 1], [1, 1, 1]]
```

#### Args:


* <b>`shape`</b>: A list of integers, a tuple of integers, or a 1-D `Tensor` of type
  `int32`.
* <b>`dtype`</b>: The type of an element in the resulting `Tensor`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` with all elements set to 1.

<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.add_n" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.add_n

### Aliases:

* `tf.add_n`
* `tf.math.add_n`

``` python
tf.math.add_n(
    inputs,
    name=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](/code/stable/tensorflow/python/ops/math_ops.py).

Adds all input tensors element-wise.

#### Args:

* <b>`inputs`</b>: A list of `Tensor` or `IndexedSlices` objects, each with same shape
    and type.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor` of same shape and type as the elements of `inputs`.


#### Raises:

* <b>`ValueError`</b>: If `inputs` don't all have same shape and dtype or the shape
  cannot be inferred.
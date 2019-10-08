<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.squeeze" />
<meta itemprop="path" content="Stable" />
</div>

# tf.squeeze

``` python
tf.squeeze(
    input,
    axis=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/array_ops.py`](/code/stable/tensorflow/python/ops/array_ops.py).

Removes dimensions of size 1 from the shape of a tensor.

Given a tensor `input`, this operation returns a tensor of the same type with
all dimensions of size 1 removed. If you don't want to remove all size 1
dimensions, you can remove specific size 1 dimensions by specifying
`axis`.

For example:

```python
# 't' is a tensor of shape [1, 2, 1, 3, 1, 1]
tf.shape(tf.squeeze(t))  # [2, 3]
```

Or, to remove specific size 1 dimensions:

```python
# 't' is a tensor of shape [1, 2, 1, 3, 1, 1]
tf.shape(tf.squeeze(t, [2, 4]))  # [1, 2, 3, 1]
```

Unlike the older op `tf.compat.v1.squeeze`, this op does not accept a
deprecated `squeeze_dims` argument.

Note: if `input` is a <a href="../tf/RaggedTensor.md"><code>tf.RaggedTensor</code></a>, then this operation takes `O(N)`
time, where `N` is the number of elements in the squeezed dimensions.

#### Args:

* <b>`input`</b>: A `Tensor`. The `input` to squeeze.
* <b>`axis`</b>: An optional list of `ints`. Defaults to `[]`. If specified, only
    squeezes the dimensions listed. The dimension index starts at 0. It is an
    error to squeeze a dimension that is not 1. Must be in the range
    `[-rank(input), rank(input))`. Must be specified if `input` is a
    `RaggedTensor`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `input`.
Contains the same data as `input`, but has one or more dimensions of
size 1 removed.


#### Raises:

* <b>`ValueError`</b>: The input cannot be converted to a tensor, or the specified
    axis cannot be squeezed.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.range" />
<meta itemprop="path" content="Stable" />
</div>

# tf.range

``` python
tf.range(limit, delta=1, dtype=None, name='range')
tf.range(start, limit, delta=1, dtype=None, name='range')
```



Defined in [`tensorflow/python/ops/math_ops.py`](/code/stable/tensorflow/python/ops/math_ops.py).

Creates a sequence of numbers.

Creates a sequence of numbers that begins at `start` and extends by
increments of `delta` up to but not including `limit`.

The dtype of the resulting tensor is inferred from the inputs unless
it is provided explicitly.

Like the Python builtin `range`, `start` defaults to 0, so that
`range(n) = range(0, n)`.

For example:

```python
start = 3
limit = 18
delta = 3
tf.range(start, limit, delta)  # [3, 6, 9, 12, 15]

start = 3
limit = 1
delta = -0.5
tf.range(start, limit, delta)  # [3, 2.5, 2, 1.5]

limit = 5
tf.range(limit)  # [0, 1, 2, 3, 4]
```

#### Args:

* <b>`start`</b>: A 0-D `Tensor` (scalar). Acts as first entry in the range if `limit`
    is not None; otherwise, acts as range limit and first entry defaults to 0.
* <b>`limit`</b>: A 0-D `Tensor` (scalar). Upper limit of sequence, exclusive. If None,
    defaults to the value of `start` while the first entry of the range
    defaults to 0.
* <b>`delta`</b>: A 0-D `Tensor` (scalar). Number that increments `start`. Defaults to
    1.
* <b>`dtype`</b>: The type of the elements of the resulting tensor.
* <b>`name`</b>: A name for the operation. Defaults to "range".


#### Returns:

An 1-D `Tensor` of type `dtype`.



#### Numpy Compatibility
Equivalent to np.arange


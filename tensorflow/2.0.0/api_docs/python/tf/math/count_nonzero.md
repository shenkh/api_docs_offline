<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.count_nonzero" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.count_nonzero

``` python
tf.math.count_nonzero(
    input,
    axis=None,
    keepdims=None,
    dtype=tf.dtypes.int64,
    name=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](/code/stable/tensorflow/python/ops/math_ops.py).

Computes number of nonzero elements across dimensions of a tensor.

Reduces `input` along the dimensions given in `axis`.
Unless `keepdims` is true, the rank of the tensor is reduced by 1 for each
entry in `axis`. If `keepdims` is true, the reduced dimensions
are retained with length 1.

If `axis` has no entries, all dimensions are reduced, and a
tensor with a single element is returned.

**NOTE** Floating point comparison to zero is done by exact floating point
equality check.  Small values are **not** rounded to zero for purposes of
the nonzero check.

For example:

```python
x = tf.constant([[0, 1, 0], [1, 1, 0]])
tf.math.count_nonzero(x)  # 3
tf.math.count_nonzero(x, 0)  # [1, 2, 0]
tf.math.count_nonzero(x, 1)  # [1, 2]
tf.math.count_nonzero(x, 1, keepdims=True)  # [[1], [2]]
tf.math.count_nonzero(x, [0, 1])  # 3
```

**NOTE** Strings are compared against zero-length empty string `""`. Any
string with a size greater than zero is already considered as nonzero.

For example:
```python
x = tf.constant(["", "a", "  ", "b", ""])
tf.math.count_nonzero(x) # 3, with "a", "  ", and "b" as nonzero strings.
```

#### Args:

* <b>`input`</b>: The tensor to reduce. Should be of numeric type, `bool`, or `string`.
* <b>`axis`</b>: The dimensions to reduce. If `None` (the default), reduces all
    dimensions. Must be in the range `[-rank(input), rank(input))`.
* <b>`keepdims`</b>: If true, retains reduced dimensions with length 1.
* <b>`dtype`</b>: The output dtype; defaults to <a href="../../tf/dtypes.md#int64"><code>tf.int64</code></a>.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

The reduced tensor (number of nonzero values).
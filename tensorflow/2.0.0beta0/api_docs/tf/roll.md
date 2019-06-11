<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.roll" />
<meta itemprop="path" content="Stable" />
</div>

# tf.roll

Rolls the elements of a tensor along an axis.

### Aliases:

* `tf.compat.v1.manip.roll`
* `tf.compat.v1.roll`
* `tf.compat.v2.roll`
* `tf.roll`

``` python
tf.roll(
    input,
    shift,
    axis,
    name=None
)
```



Defined in [`python/ops/manip_ops.py`](/code/stable/tensorflow/python/ops/manip_ops.py).

<!-- Placeholder for "Used in" -->

The elements are shifted positively (towards larger indices) by the offset of
`shift` along the dimension of `axis`. Negative `shift` values will shift
elements in the opposite direction. Elements that roll passed the last position
will wrap around to the first and vice versa. Multiple shifts along multiple
axes may be specified.

#### For example:



```
# 't' is [0, 1, 2, 3, 4]
roll(t, shift=2, axis=0) ==> [3, 4, 0, 1, 2]

# shifting along multiple dimensions
# 't' is [[0, 1, 2, 3, 4], [5, 6, 7, 8, 9]]
roll(t, shift=[1, -2], axis=[0, 1]) ==> [[7, 8, 9, 5, 6], [2, 3, 4, 0, 1]]

# shifting along the same axis multiple times
# 't' is [[0, 1, 2, 3, 4], [5, 6, 7, 8, 9]]
roll(t, shift=[2, -3], axis=[1, 1]) ==> [[1, 2, 3, 4, 0], [6, 7, 8, 9, 5]]
```

#### Args:


* <b>`input`</b>: A `Tensor`.
* <b>`shift`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`.
  Dimension must be 0-D or 1-D. `shift[i]` specifies the number of places by which
  elements are shifted positively (towards larger indices) along the dimension
  specified by `axis[i]`. Negative shifts will roll the elements in the opposite
  direction.
* <b>`axis`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`.
  Dimension must be 0-D or 1-D. `axis[i]` specifies the dimension that the shift
  `shift[i]` should occur. If the same axis is referenced more than once, the
  total shift for that axis will be the sum of all the shifts that belong to that
  axis.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `input`.

<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.reduce_euclidean_norm" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.reduce_euclidean_norm

Computes the Euclidean norm of elements across dimensions of a tensor.

### Aliases:

* `tf.compat.v1.math.reduce_euclidean_norm`
* `tf.compat.v2.math.reduce_euclidean_norm`
* `tf.math.reduce_euclidean_norm`

``` python
tf.math.reduce_euclidean_norm(
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
x = tf.constant([[1, 2, 3], [1, 1, 1]])
tf.reduce_euclidean_norm(x)  # sqrt(17)
tf.reduce_euclidean_norm(x, 0)  # [sqrt(2), sqrt(5), sqrt(10)]
tf.reduce_euclidean_norm(x, 1)  # [sqrt(14), sqrt(3)]
tf.reduce_euclidean_norm(x, 1, keepdims=True)  # [[sqrt(14)], [sqrt(3)]]
tf.reduce_euclidean_norm(x, [0, 1])  # sqrt(17)
```

#### Args:


* <b>`input_tensor`</b>: The tensor to reduce. Should have numeric type.
* <b>`axis`</b>: The dimensions to reduce. If `None` (the default), reduces all
  dimensions. Must be in the range `[-rank(input_tensor),
  rank(input_tensor))`.
* <b>`keepdims`</b>: If true, retains reduced dimensions with length 1.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

The reduced tensor, of the same dtype as the input_tensor.

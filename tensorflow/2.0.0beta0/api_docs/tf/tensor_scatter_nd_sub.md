<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.tensor_scatter_nd_sub" />
<meta itemprop="path" content="Stable" />
</div>

# tf.tensor_scatter_nd_sub

Subtracts sparse `updates` from an existing tensor according to `indices`.

### Aliases:

* `tf.compat.v1.tensor_scatter_nd_sub`
* `tf.compat.v1.tensor_scatter_sub`
* `tf.compat.v2.tensor_scatter_nd_sub`
* `tf.tensor_scatter_nd_sub`

``` python
tf.tensor_scatter_nd_sub(
    tensor,
    indices,
    updates,
    name=None
)
```



Defined in generated file: `python/ops/gen_array_ops.py`.

<!-- Placeholder for "Used in" -->

This operation creates a new tensor by subtracting sparse `updates` from the
passed in `tensor`.
This operation is very similar to `tf.scatter_nd_sub`, except that the updates
are subtracted from an existing tensor (as opposed to a variable). If the memory
for the existing tensor cannot be re-used, a copy is made and updated.

`indices` is an integer tensor containing indices into a new tensor of shape
`shape`.  The last dimension of `indices` can be at most the rank of `shape`:

    indices.shape[-1] <= shape.rank

The last dimension of `indices` corresponds to indices into elements
(if `indices.shape[-1] = shape.rank`) or slices
(if `indices.shape[-1] < shape.rank`) along dimension `indices.shape[-1]` of
`shape`.  `updates` is a tensor with shape

    indices.shape[:-1] + shape[indices.shape[-1]:]

The simplest form of tensor_scatter_sub is to subtract individual elements
from a tensor by index. For example, say we want to insert 4 scattered elements
in a rank-1 tensor with 8 elements.

In Python, this scatter subtract operation would look like this:

```python
    indices = tf.constant([[4], [3], [1], [7]])
    updates = tf.constant([9, 10, 11, 12])
    tensor = tf.ones([8], dtype=tf.int32)
    updated = tf.tensor_scatter_sub(tensor, indices, updates)
    with tf.Session() as sess:
      print(sess.run(scatter))
```

The resulting tensor would look like this:

    [1, -10, 1, -9, -8, 1, 1, -11]

We can also, insert entire slices of a higher rank tensor all at once. For
example, if we wanted to insert two slices in the first dimension of a
rank-3 tensor with two matrices of new values.

In Python, this scatter add operation would look like this:

```python
    indices = tf.constant([[0], [2]])
    updates = tf.constant([[[5, 5, 5, 5], [6, 6, 6, 6],
                            [7, 7, 7, 7], [8, 8, 8, 8]],
                           [[5, 5, 5, 5], [6, 6, 6, 6],
                            [7, 7, 7, 7], [8, 8, 8, 8]]])
    tensor = tf.ones([4, 4, 4])
    updated = tf.tensor_scatter_sub(tensor, indices, updates)
    with tf.Session() as sess:
      print(sess.run(scatter))
```

The resulting tensor would look like this:

    [[[-4, -4, -4, -4], [-5, -5, -5, -5], [-6, -6, -6, -6], [-7, -7, -7, -7]],
     [[1, 1, 1, 1], [1, 1, 1, 1], [1, 1, 1, 1], [1, 1, 1, 1]],
     [[-4, -4, -4, -4], [-5, -5, -5, -5], [-6, -6, -6, -6], [-7, -7, -7, -7]],
     [[1, 1, 1, 1], [1, 1, 1, 1], [1, 1, 1, 1], [1, 1, 1, 1]]]

Note that on CPU, if an out of bound index is found, an error is returned.
On GPU, if an out of bound index is found, the index is ignored.

#### Args:


* <b>`tensor`</b>: A `Tensor`. Tensor to copy/update.
* <b>`indices`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`.
  Index tensor.
* <b>`updates`</b>: A `Tensor`. Must have the same type as `tensor`.
  Updates to scatter into output.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `tensor`.

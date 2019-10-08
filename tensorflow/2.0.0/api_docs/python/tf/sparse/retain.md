<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.sparse.retain" />
<meta itemprop="path" content="Stable" />
</div>

# tf.sparse.retain

``` python
tf.sparse.retain(
    sp_input,
    to_retain
)
```



Defined in [`tensorflow/python/ops/sparse_ops.py`](/code/stable/tensorflow/python/ops/sparse_ops.py).

Retains specified non-empty values within a `SparseTensor`.

For example, if `sp_input` has shape `[4, 5]` and 4 non-empty string values:

    [0, 1]: a
    [0, 3]: b
    [2, 0]: c
    [3, 1]: d

and `to_retain = [True, False, False, True]`, then the output will
be a `SparseTensor` of shape `[4, 5]` with 2 non-empty values:

    [0, 1]: a
    [3, 1]: d

#### Args:

* <b>`sp_input`</b>: The input `SparseTensor` with `N` non-empty elements.
* <b>`to_retain`</b>: A bool vector of length `N` with `M` true values.


#### Returns:

A `SparseTensor` with the same shape as the input and `M` non-empty
elements corresponding to the true positions in `to_retain`.


#### Raises:

* <b>`TypeError`</b>: If `sp_input` is not a `SparseTensor`.
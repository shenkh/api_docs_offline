<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.sparse.split" />
<meta itemprop="path" content="Stable" />
</div>

# tf.sparse.split

``` python
tf.sparse.split(
    sp_input=None,
    num_split=None,
    axis=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/sparse_ops.py`](/code/stable/tensorflow/python/ops/sparse_ops.py).

Split a `SparseTensor` into `num_split` tensors along `axis`.

If the `sp_input.dense_shape[axis]` is not an integer multiple of `num_split`
each slice starting from 0:`shape[axis] % num_split` gets extra one
dimension. For example, if `axis = 1` and `num_split = 2` and the
input is:

    input_tensor = shape = [2, 7]
    [    a   d e  ]
    [b c          ]

Graphically the output tensors are:

    output_tensor[0] =
    [    a ]
    [b c   ]

    output_tensor[1] =
    [ d e  ]
    [      ]

#### Args:

* <b>`sp_input`</b>: The `SparseTensor` to split.
* <b>`num_split`</b>: A Python integer. The number of ways to split.
* <b>`axis`</b>: A 0-D `int32` `Tensor`. The dimension along which to split.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

`num_split` `SparseTensor` objects resulting from splitting `value`.


#### Raises:

* <b>`TypeError`</b>: If `sp_input` is not a `SparseTensor`.
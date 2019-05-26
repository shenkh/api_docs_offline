<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.linalg.tensor_diag" />
<meta itemprop="path" content="Stable" />
</div>

# tf.linalg.tensor_diag

### Aliases:

* `tf.diag`
* `tf.linalg.tensor_diag`

``` python
tf.linalg.tensor_diag(
    diagonal,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_array_ops.py`.

Returns a diagonal tensor with a given diagonal values.

Given a `diagonal`, this operation returns a tensor with the `diagonal` and
everything else padded with zeros. The diagonal is computed as follows:

Assume `diagonal` has dimensions [D1,..., Dk], then the output is a tensor of
rank 2k with dimensions [D1,..., Dk, D1,..., Dk] where:

`output[i1,..., ik, i1,..., ik] = diagonal[i1, ..., ik]` and 0 everywhere else.

For example:

```
# 'diagonal' is [1, 2, 3, 4]
tf.diag(diagonal) ==> [[1, 0, 0, 0]
                       [0, 2, 0, 0]
                       [0, 0, 3, 0]
                       [0, 0, 0, 4]]
```

#### Args:

* <b>`diagonal`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `half`, `float32`, `float64`, `int32`, `int64`, `complex64`, `complex128`.
    Rank k tensor where k is at most 1.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `diagonal`.
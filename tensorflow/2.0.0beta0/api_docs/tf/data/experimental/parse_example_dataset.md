<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.parse_example_dataset" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.parse_example_dataset

A transformation that parses `Example` protos into a `dict` of tensors.

### Aliases:

* `tf.compat.v1.data.experimental.parse_example_dataset`
* `tf.compat.v2.data.experimental.parse_example_dataset`
* `tf.data.experimental.parse_example_dataset`

``` python
tf.data.experimental.parse_example_dataset(
    features,
    num_parallel_calls=1
)
```



Defined in [`python/data/experimental/ops/parsing_ops.py`](/code/stable/tensorflow/python/data/experimental/ops/parsing_ops.py).

<!-- Placeholder for "Used in" -->

Parses a number of serialized `Example` protos given in `serialized`. We refer
to `serialized` as a batch with `batch_size` many entries of individual
`Example` protos.

This op parses serialized examples into a dictionary mapping keys to `Tensor`
and `SparseTensor` objects. `features` is a dict from keys to `VarLenFeature`,
`SparseFeature`, and `FixedLenFeature` objects. Each `VarLenFeature`
and `SparseFeature` is mapped to a `SparseTensor`, and each
`FixedLenFeature` is mapped to a `Tensor`. See <a href="../../../tf/io/parse_example.md"><code>tf.io.parse_example</code></a> for more
details about feature dictionaries.

#### Args:


* <b>`features`</b>: A `dict` mapping feature keys to `FixedLenFeature`,
  `VarLenFeature`, and `SparseFeature` values.
* <b>`num_parallel_calls`</b>: (Optional.) A <a href="../../../tf.md#int32"><code>tf.int32</code></a> scalar <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>,
   representing the number of parsing processes to call in parallel.


#### Returns:

A dataset transformation function, which can be passed to
<a href="../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>.



#### Raises:


* <b>`ValueError`</b>: if features argument is None.
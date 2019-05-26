<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.data.parse_example_dataset" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.data.parse_example_dataset

``` python
tf.contrib.data.parse_example_dataset(
    features,
    num_parallel_calls=1
)
```



Defined in [`tensorflow/contrib/data/python/ops/parsing_ops.py`](https://www.tensorflow.org/code/tensorflow/contrib/data/python/ops/parsing_ops.py).

A transformation that parses `Example` protos into a `dict` of tensors.

Parses a number of serialized `Example` protos given in `serialized`. We refer
to `serialized` as a batch with `batch_size` many entries of individual
`Example` protos.

This op parses serialized examples into a dictionary mapping keys to `Tensor`
and `SparseTensor` objects. `features` is a dict from keys to `VarLenFeature`,
`SparseFeature`, and `FixedLenFeature` objects. Each `VarLenFeature`
and `SparseFeature` is mapped to a `SparseTensor`, and each
`FixedLenFeature` is mapped to a `Tensor`. See <a href="../../../tf/parse_example.md"><code>tf.parse_example</code></a> for more
details about feature dictionaries.

#### Args:

features: A `dict` mapping feature keys to `FixedLenFeature`,
  `VarLenFeature`, and `SparseFeature` values.
num_parallel_calls: (Optional.) A <a href="../../../tf/int32.md"><code>tf.int32</code></a> scalar <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>,
   representing the number of parsing processes to call in parallel.


#### Returns:

A dataset transformation function, which can be passed to
<a href="../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>.


#### Raises:

* <b>`ValueError`</b>: if features argument is None.
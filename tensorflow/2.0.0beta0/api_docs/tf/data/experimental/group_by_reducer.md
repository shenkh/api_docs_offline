<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.group_by_reducer" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.group_by_reducer

A transformation that groups elements and performs a reduction.

### Aliases:

* `tf.compat.v1.data.experimental.group_by_reducer`
* `tf.compat.v2.data.experimental.group_by_reducer`
* `tf.data.experimental.group_by_reducer`

``` python
tf.data.experimental.group_by_reducer(
    key_func,
    reducer
)
```



Defined in [`python/data/experimental/ops/grouping.py`](/code/stable/tensorflow/python/data/experimental/ops/grouping.py).

<!-- Placeholder for "Used in" -->

This transformation maps element of a dataset to a key using `key_func` and
groups the elements by key. The `reducer` is used to process each group; its
`init_func` is used to initialize state for each group when it is created, the
`reduce_func` is used to update the state every time an element is mapped to
the matching group, and the `finalize_func` is used to map the final state to
an output value.

#### Args:


* <b>`key_func`</b>: A function mapping a nested structure of tensors
  (having shapes and types defined by `self.output_shapes` and
  `self.output_types`) to a scalar <a href="../../../tf.md#int64"><code>tf.int64</code></a> tensor.
* <b>`reducer`</b>: An instance of `Reducer`, which captures the reduction logic using
  the `init_func`, `reduce_func`, and `finalize_func` functions.


#### Returns:

A `Dataset` transformation function, which can be passed to
<a href="../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>.

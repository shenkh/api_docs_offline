<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.group_by_window" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.group_by_window

A transformation that groups windows of elements by key and reduces them.

### Aliases:

* `tf.compat.v1.data.experimental.group_by_window`
* `tf.compat.v2.data.experimental.group_by_window`
* `tf.data.experimental.group_by_window`

``` python
tf.data.experimental.group_by_window(
    key_func,
    reduce_func,
    window_size=None,
    window_size_func=None
)
```



Defined in [`python/data/experimental/ops/grouping.py`](/code/stable/tensorflow/python/data/experimental/ops/grouping.py).

<!-- Placeholder for "Used in" -->

This transformation maps each consecutive element in a dataset to a key
using `key_func` and groups the elements by key. It then applies
`reduce_func` to at most `window_size_func(key)` elements matching the same
key. All except the final window for each key will contain
`window_size_func(key)` elements; the final window may be smaller.

You may provide either a constant `window_size` or a window size determined by
the key through `window_size_func`.

#### Args:


* <b>`key_func`</b>: A function mapping a nested structure of tensors
  (having shapes and types defined by `self.output_shapes` and
  `self.output_types`) to a scalar <a href="../../../tf.md#int64"><code>tf.int64</code></a> tensor.
* <b>`reduce_func`</b>: A function mapping a key and a dataset of up to `window_size`
  consecutive elements matching that key to another dataset.
* <b>`window_size`</b>: A <a href="../../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the number of
  consecutive elements matching the same key to combine in a single
  batch, which will be passed to `reduce_func`. Mutually exclusive with
  `window_size_func`.
* <b>`window_size_func`</b>: A function mapping a key to a <a href="../../../tf.md#int64"><code>tf.int64</code></a> scalar
  <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the number of consecutive elements matching
  the same key to combine in a single batch, which will be passed to
  `reduce_func`. Mutually exclusive with `window_size`.


#### Returns:

A `Dataset` transformation function, which can be passed to
<a href="../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>.



#### Raises:


* <b>`ValueError`</b>: if neither or both of {`window_size`, `window_size_func`} are
  passed.
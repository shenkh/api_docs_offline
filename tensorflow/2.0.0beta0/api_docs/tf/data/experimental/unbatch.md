<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.data.experimental.unbatch" />
<meta itemprop="path" content="Stable" />
</div>

# tf.data.experimental.unbatch

Splits elements of a dataset into multiple elements on the batch dimension. (deprecated)

### Aliases:

* `tf.compat.v1.data.experimental.unbatch`
* `tf.compat.v2.data.experimental.unbatch`
* `tf.data.experimental.unbatch`

``` python
tf.data.experimental.unbatch()
```



Defined in [`python/data/experimental/ops/batching.py`](/code/stable/tensorflow/python/data/experimental/ops/batching.py).

<!-- Placeholder for "Used in" -->

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `tf.data.Dataset.unbatch()`.

For example, if elements of the dataset are shaped `[B, a0, a1, ...]`,
where `B` may vary for each input element, then for each element in the
dataset, the unbatched dataset will contain `B` consecutive elements
of shape `[a0, a1, ...]`.

```python
# NOTE: The following example uses `{ ... }` to represent the contents
# of a dataset.
a = { ['a', 'b', 'c'], ['a', 'b'], ['a', 'b', 'c', 'd'] }

a.apply(tf.data.experimental.unbatch()) == {
    'a', 'b', 'c', 'a', 'b', 'a', 'b', 'c', 'd'}
```

#### Returns:

A `Dataset` transformation function, which can be passed to
<a href="../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>.

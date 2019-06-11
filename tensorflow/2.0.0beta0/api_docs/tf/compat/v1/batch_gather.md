<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.batch_gather" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.batch_gather

Gather slices from params according to indices with leading batch dims. (deprecated)

``` python
tf.compat.v1.batch_gather(
    params,
    indices,
    name=None
)
```



Defined in [`python/ops/array_ops.py`](/code/stable/tensorflow/python/ops/array_ops.py).

<!-- Placeholder for "Used in" -->

Warning: THIS FUNCTION IS DEPRECATED. It will be removed after 2017-10-25.
Instructions for updating:
`tf.batch_gather` is deprecated, please use <a href="../../../tf/gather.md"><code>tf.gather</code></a> with `batch_dims` instead.
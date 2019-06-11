<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.summary.merge_all" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.summary.merge_all

Merges all summaries collected in the default graph.

``` python
tf.compat.v1.summary.merge_all(
    key=tf.GraphKeys.SUMMARIES,
    scope=None,
    name=None
)
```



Defined in [`python/summary/summary.py`](/code/stable/tensorflow/python/summary/summary.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`key`</b>: `GraphKey` used to collect the summaries.  Defaults to
  `GraphKeys.SUMMARIES`.
* <b>`scope`</b>: Optional scope used to filter the summary ops, using `re.match`


#### Returns:

If no summaries were collected, returns None.  Otherwise returns a scalar
`Tensor` of type `string` containing the serialized `Summary` protocol
buffer resulting from the merging.



#### Raises:


* <b>`RuntimeError`</b>: If called with eager execution enabled.



#### Eager Compatibility
Not compatible with eager execution. To write TensorBoard
summaries under eager execution, use `tf.contrib.summary` instead.


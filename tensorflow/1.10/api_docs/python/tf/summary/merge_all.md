<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.summary.merge_all" />
</div>

# tf.summary.merge_all

``` python
tf.summary.merge_all(
    key=tf.GraphKeys.SUMMARIES,
    scope=None
)
```



Defined in [`tensorflow/python/summary/summary.py`](https://www.tensorflow.org/code/tensorflow/python/summary/summary.py).

See the guide: [Summary Operations > Generation of Summaries](../../../../api_guides/python/summary.md#Generation_of_Summaries)

Merges all summaries collected in the default graph.

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

@compatibility(eager)
Not compatible with eager execution. To write TensorBoard
summaries under eager execution, use <a href="../../tf/contrib/summary.md"><code>tf.contrib.summary</code></a> instead.
@end_compatbility
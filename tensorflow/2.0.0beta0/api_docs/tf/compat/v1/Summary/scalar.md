<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.summary.scalar" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.summary.scalar

Outputs a `Summary` protocol buffer containing a single scalar value.

``` python
tf.compat.v1.summary.scalar(
    name,
    tensor,
    collections=None,
    family=None
)
```



Defined in [`python/summary/summary.py`](/code/stable/tensorflow/python/summary/summary.py).

<!-- Placeholder for "Used in" -->

The generated Summary has a Tensor.proto containing the input Tensor.

#### Args:


* <b>`name`</b>: A name for the generated node. Will also serve as the series name in
  TensorBoard.
* <b>`tensor`</b>: A real numeric Tensor containing a single value.
* <b>`collections`</b>: Optional list of graph collections keys. The new summary op is
  added to these collections. Defaults to `[GraphKeys.SUMMARIES]`.
* <b>`family`</b>: Optional; if provided, used as the prefix of the summary tag name,
  which controls the tab name used for display on Tensorboard.


#### Returns:

A scalar `Tensor` of type `string`. Which contains a `Summary` protobuf.



#### Raises:


* <b>`ValueError`</b>: If tensor has the wrong shape or type.
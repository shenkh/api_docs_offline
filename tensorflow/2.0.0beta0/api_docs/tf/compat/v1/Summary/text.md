<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.summary.text" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.summary.text

Summarizes textual data.

``` python
tf.compat.v1.summary.text(
    name,
    tensor,
    collections=None
)
```



Defined in [`python/summary/summary.py`](/code/stable/tensorflow/python/summary/summary.py).

<!-- Placeholder for "Used in" -->

Text data summarized via this plugin will be visible in the Text Dashboard
in TensorBoard. The standard TensorBoard Text Dashboard will render markdown
in the strings, and will automatically organize 1d and 2d tensors into tables.
If a tensor with more than 2 dimensions is provided, a 2d subarray will be
displayed along with a warning message. (Note that this behavior is not
intrinsic to the text summary api, but rather to the default TensorBoard text
plugin.)

#### Args:


* <b>`name`</b>: A name for the generated node. Will also serve as a series name in
  TensorBoard.
* <b>`tensor`</b>: a string-type Tensor to summarize.
* <b>`collections`</b>: Optional list of ops.GraphKeys.  The collections to add the
  summary to.  Defaults to [_ops.GraphKeys.SUMMARIES]


#### Returns:

A TensorSummary op that is configured so that TensorBoard will recognize
that it contains textual data. The TensorSummary is a scalar `Tensor` of
type `string` which contains `Summary` protobufs.



#### Raises:


* <b>`ValueError`</b>: If tensor has the wrong type.
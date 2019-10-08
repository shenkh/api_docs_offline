<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.summary.experimental.write_raw_pb" />
<meta itemprop="path" content="Stable" />
</div>

# tf.summary.experimental.write_raw_pb

``` python
tf.summary.experimental.write_raw_pb(
    tensor,
    step=None,
    name=None
)
```



Defined in [`tensorflow/python/ops/summary_ops_v2.py`](/code/stable/tensorflow/python/ops/summary_ops_v2.py).

Writes a summary using raw `tf.compat.v1.Summary` protocol buffers.

Experimental: this exists to support the usage of V1-style manual summary
writing (via the construction of a `tf.compat.v1.Summary` protocol buffer)
with the V2 summary writing API.

#### Args:

* <b>`tensor`</b>: the string Tensor holding one or more serialized `Summary` protobufs
* <b>`step`</b>: Explicit `int64`-castable monotonic step value for this summary. If
    omitted, this defaults to `tf.summary.experimental.get_step()`, which must
    not be None.
* <b>`name`</b>: Optional string name for this op.


#### Returns:

True on success, or false if no summary was written because no default
summary writer was available.


#### Raises:

* <b>`ValueError`</b>: if a default writer exists, but no step was provided and
    `tf.summary.experimental.get_step()` is None.
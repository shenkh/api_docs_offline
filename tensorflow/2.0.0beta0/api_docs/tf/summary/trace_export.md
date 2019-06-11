<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.summary.trace_export" />
<meta itemprop="path" content="Stable" />
</div>

# tf.summary.trace_export

Stops and exports the active trace as a Summary and/or profile file.

### Aliases:

* `tf.compat.v2.summary.trace_export`
* `tf.summary.trace_export`

``` python
tf.summary.trace_export(
    name,
    step=None,
    profiler_outdir=None
)
```



Defined in [`python/ops/summary_ops_v2.py`](/code/stable/tensorflow/python/ops/summary_ops_v2.py).

<!-- Placeholder for "Used in" -->

Stops the trace and exports all metadata collected during the trace to the
default SummaryWriter, if one has been set.

#### Args:


* <b>`name`</b>: A name for the summary to be written.
* <b>`step`</b>: Explicit `int64`-castable monotonic step value for this summary. If
  omitted, this defaults to `tf.summary.experimental.get_step()`, which must
  not be None.
* <b>`profiler_outdir`</b>: Output directory for profiler. It is required when profiler
  is enabled when trace was started. Otherwise, it is ignored.


#### Raises:


* <b>`ValueError`</b>: if a default writer exists, but no step was provided and
  `tf.summary.experimental.get_step()` is None.
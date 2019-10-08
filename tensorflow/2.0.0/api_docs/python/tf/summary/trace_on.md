<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.summary.trace_on" />
<meta itemprop="path" content="Stable" />
</div>

# tf.summary.trace_on

``` python
tf.summary.trace_on(
    graph=True,
    profiler=False
)
```



Defined in [`tensorflow/python/ops/summary_ops_v2.py`](/code/stable/tensorflow/python/ops/summary_ops_v2.py).

Starts a trace to record computation graphs and profiling information.

Must be invoked in eager mode.

When enabled, TensorFlow runtime will collection information that can later be
exported and consumed by TensorBoard. The trace is activated across the entire
TensorFlow runtime and affects all threads of execution.

To stop the trace and export the collected information, use
<a href="../../tf/summary/trace_export.md"><code>tf.summary.trace_export</code></a>. To stop the trace without exporting, use
<a href="../../tf/summary/trace_off.md"><code>tf.summary.trace_off</code></a>.

#### Args:

* <b>`graph`</b>: If True, enables collection of executed graphs. It includes ones from
      tf.function invocation and ones from the legacy graph mode. The default
      is True.
* <b>`profiler`</b>: If True, enables the advanced profiler. Enabling profiler
      implicitly enables the graph collection. The profiler may incur a high
      memory overhead. The default is False.
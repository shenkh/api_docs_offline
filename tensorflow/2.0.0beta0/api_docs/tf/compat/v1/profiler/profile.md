<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.profiler.profile" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.profiler.profile

Profile model.

``` python
tf.compat.v1.profiler.profile(
    graph=None,
    run_meta=None,
    op_log=None,
    cmd='scope',
    options=_DEFAULT_PROFILE_OPTIONS
)
```



Defined in [`python/profiler/model_analyzer.py`](/code/stable/tensorflow/python/profiler/model_analyzer.py).

<!-- Placeholder for "Used in" -->

  Tutorials and examples can be found in:
  https://github.com/tensorflow/tensorflow/tree/master/tensorflow/core/profiler/README.md

#### Args:


* <b>`graph`</b>: tf.Graph. If None and eager execution is not enabled, use
    default graph.
* <b>`run_meta`</b>: optional tensorflow.RunMetadata proto. It is necessary to
    to support run time information profiling, such as time and memory.
* <b>`op_log`</b>: tensorflow.tfprof.OpLogProto proto. User can assign "types" to
    graph nodes with op_log. "types" allow user to flexibly group and
    account profiles using options['accounted_type_regexes'].
* <b>`cmd`</b>: string. Either 'op', 'scope', 'graph' or 'code'.
    'op' view organizes profile using operation type. (e.g. MatMul)
    'scope' view organizes profile using graph node name scope.
    'graph' view organizes profile using graph node inputs/outputs.
    'code' view organizes profile using Python call stack.
* <b>`options`</b>: A dict of options. See core/profiler/g3doc/options.md.

#### Returns:

If cmd is 'scope' or 'graph', returns GraphNodeProto proto.
If cmd is 'op' or 'code', returns MultiGraphNodeProto proto.
Side effect: stdout/file/timeline.json depending on options['output']

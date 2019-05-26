<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.profiler.advise" />
<meta itemprop="path" content="Stable" />
</div>

# tf.profiler.advise

``` python
tf.profiler.advise(
    graph=None,
    run_meta=None,
    options=_DEFAULT_ADVISE_OPTIONS
)
```



Defined in [`tensorflow/python/profiler/model_analyzer.py`](/code/stable/tensorflow/python/profiler/model_analyzer.py).

Auto profile and advise.

  Builds profiles and automatically check anomalies of various
  aspects. For more details:
  https://github.com/tensorflow/tensorflow/tree/master/tensorflow/core/profiler/README.md

#### Args:

* <b>`graph`</b>: tf.Graph. If None and eager execution is not enabled, use
      default graph.
* <b>`run_meta`</b>: optional tensorflow.RunMetadata proto. It is necessary to
      to support run time information profiling, such as time and memory.
* <b>`options`</b>: see ALL_ADVICE example above. Default checks everything.

#### Returns:

Returns AdviceProto proto
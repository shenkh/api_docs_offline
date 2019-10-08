<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.experimental.disable_mixed_precision_graph_rewrite" />
<meta itemprop="path" content="Stable" />
</div>

# tf.train.experimental.disable_mixed_precision_graph_rewrite

``` python
tf.train.experimental.disable_mixed_precision_graph_rewrite()
```



Defined in [`tensorflow/python/training/experimental/mixed_precision.py`](/code/stable/tensorflow/python/training/experimental/mixed_precision.py).

Disables the mixed precision graph rewrite.

After this is called, the mixed precision graph rewrite will no longer run for
tf.functions, and so float32 operations will no longer be converted to
float16.

This does not undo the effects of loss scaling. Any optimizers wrapped with a
LossScaleOptimizer will continue to do loss scaling, although this loss
scaling will no longer be useful, as the graph rewrite no longer converts
tf.functions to use float16.

This function is useful for unit testing. A unit test can test using the mixed
precision graph rewrite, then disable it so future unit tests continue using
float32.
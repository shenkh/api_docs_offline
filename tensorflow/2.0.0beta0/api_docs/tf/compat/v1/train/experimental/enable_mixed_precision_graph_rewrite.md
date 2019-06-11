<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.train.experimental.enable_mixed_precision_graph_rewrite" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.train.experimental.enable_mixed_precision_graph_rewrite

Enable mixed precision via a graph rewrite.

``` python
tf.compat.v1.train.experimental.enable_mixed_precision_graph_rewrite(
    opt,
    loss_scale='dynamic'
)
```



Defined in [`python/training/experimental/mixed_precision.py`](/code/stable/tensorflow/python/training/experimental/mixed_precision.py).

<!-- Placeholder for "Used in" -->

Mixed precision is the use of both float16 and float32 when training a model,
and is used to make the model run faster. This function will use mixed
precision to speed up the execution time of your model when run on a GPU. It
does this by changing the dtype of certain operations in the graph from
float32 to float16.

This function additionally wraps an Optimizer with a LossScaleOptimizer, which
is required to prevent underflow in the float16 tensors during the backwards
pass. An optimizer must be passed to this function, which will then be wrapped
to use loss scaling.

When this function is used, gradients should only be computed and applied with
the returned optimizer, either by calling `opt.minimize()` or
`opt.compute_gradients()` followed by `opt.apply_gradients()`. Gradients
should not be computed with <a href="../../../../../tf/gradients.md"><code>tf.gradients</code></a> or <a href="../../../../../tf/GradientTape.md"><code>tf.GradientTape</code></a>. This is
because the returned optimizer will apply loss scaling, and
<a href="../../../../../tf/gradients.md"><code>tf.gradients</code></a>/<a href="../../../../../tf/GradientTape.md"><code>tf.GradientTape</code></a> will not. If you do directly use
<a href="../../../../../tf/gradients.md"><code>tf.gradients</code></a> or <a href="../../../../../tf/GradientTape.md"><code>tf.GradientTape</code></a>, your model may train to a worse quality.

When eager execution is enabled, the mixed precision graph rewrite is only
enabled within <a href="../../../../../tf/function.md"><code>tf.function</code></a>s, as outside <a href="../../../../../tf/function.md"><code>tf.function</code></a>s, there is no graph.

When enabled, mixed precision is only used on Volta GPUs and above. The parts
of the graph on CPUs and TPUs are untouched by the graph rewrite.

#### Args:


* <b>`opt`</b>: An instance of a <a href="../../../../../tf/keras/optimizers/Optimizer.md"><code>tf.keras.optimizers.Optimizer</code></a> or a
  `tf.train.Optimizer`.
* <b>`loss_scale`</b>: Either an int/float, the string "dynamic", or an instance of a
  <a href="../../../../../tf/train/experimental/LossScale.md"><code>tf.train.experimental.LossScale</code></a>. The loss scale to use. It is
  recommended to keep this as its default value of "dynamic".


#### Returns:

A version of `opt` that will use loss scaling to prevent underflow.

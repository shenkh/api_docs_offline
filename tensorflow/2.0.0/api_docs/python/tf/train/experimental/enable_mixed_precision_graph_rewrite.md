<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.experimental.enable_mixed_precision_graph_rewrite" />
<meta itemprop="path" content="Stable" />
</div>

# tf.train.experimental.enable_mixed_precision_graph_rewrite

``` python
tf.train.experimental.enable_mixed_precision_graph_rewrite(
    opt,
    loss_scale='dynamic'
)
```



Defined in [`tensorflow/python/training/experimental/mixed_precision.py`](/code/stable/tensorflow/python/training/experimental/mixed_precision.py).

Enable mixed precision in <a href="../../../tf/function.md"><code>tf.function</code></a>s via a graph rewrite.

Mixed precision is the use of both float16 and float32 when training a model,
and is used to make the model run faster. This function will use mixed
precision to speed up the execution time of <a href="../../../tf/function.md"><code>tf.function</code></a>s when run on a GPU.
It does this by changing the dtype of certain operations in the function's
graph from float32 to float16.

This function additionally wraps an Optimizer with a LossScaleOptimizer, which
is required to prevent underflow in the float16 tensors during the backwards
pass. An optimizer must be passed to this function, which will then be wrapped
to use loss scaling.

When this function is used, gradients should only be computed and applied with
the returned optimizer through `opt.minimize()`, and not with a
<a href="../../../tf/GradientTape.md"><code>tf.GradientTape</code></a>. This is because the returned optimizer will apply loss
scaling, and <a href="../../../tf/GradientTape.md"><code>tf.GradientTape</code></a> will not. If you do use a <a href="../../../tf/GradientTape.md"><code>tf.GradientTape</code></a>,
your model may train to a worse quality.

Currently, mixed precision is only enabled on Volta GPUs and above. TPU
support is coming soon. CPUs are not supported, as CPUs do not run float16
operations faster than float32 operations.

WARNING: This rewrite silently affects the entire model and can have
unintended consequences. One example: If a NaN occurs during dynamic loss
scaling, the data for the batch is silently dropped while the
LossScaleOptimizer attempts to find the appropriate scaling value on the next
batch.

#### Args:

* <b>`opt`</b>: An instance of a <a href="../../../tf/optimizers/Optimizer.md"><code>tf.keras.optimizers.Optimizer</code></a>.
* <b>`loss_scale`</b>: Either an int/float, the string "dynamic", or an instance of a
    <a href="../../../tf/train/experimental/LossScale.md"><code>tf.train.experimental.LossScale</code></a>. The loss scale to use. It is
    recommended to keep this as its default value of "dynamic".


#### Returns:

A version of `opt` that will use loss scaling to prevent underflow.
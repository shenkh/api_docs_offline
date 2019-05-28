<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.tpu.TPUEstimatorSpec" />
<meta itemprop="property" content="eval_metrics"/>
<meta itemprop="property" content="export_outputs"/>
<meta itemprop="property" content="host_call"/>
<meta itemprop="property" content="loss"/>
<meta itemprop="property" content="mode"/>
<meta itemprop="property" content="predictions"/>
<meta itemprop="property" content="scaffold_fn"/>
<meta itemprop="property" content="train_op"/>
<meta itemprop="property" content="__new__"/>
<meta itemprop="property" content="as_estimator_spec"/>
</div>

# tf.contrib.tpu.TPUEstimatorSpec

## Class `TPUEstimatorSpec`





Defined in [`tensorflow/contrib/tpu/python/tpu/tpu_estimator.py`](https://www.tensorflow.org/code/tensorflow/contrib/tpu/python/tpu/tpu_estimator.py).

Ops and objects returned from a `model_fn` and passed to `TPUEstimator`.

See `EstimatorSpec` for `mode`, `predictions`, `loss`, `train_op`, and
`export_outputs`.

For evaluation, `eval_metrics `is a tuple of `metric_fn` and `tensors`, where
`metric_fn` runs on CPU to generate metrics and `tensors` represents the
`Tensor`s transferred from TPU system to CPU host and passed to `metric_fn`.
To be precise, TPU evaluation expects a slightly different signature from the
<a href="../../../tf/estimator/Estimator.md"><code>tf.estimator.Estimator</code></a>. While `EstimatorSpec.eval_metric_ops` expects a
dict, `TPUEstimatorSpec.eval_metrics` is a tuple of `metric_fn` and `tensors`.
The `tensors` could be a list of `Tensor`s or dict of names to `Tensor`s. The
`tensors` usually specify the model logits, which are transferred back from
TPU system to CPU host. All tensors must have be batch-major, i.e., the batch
size is the first dimension. Once all tensors are available at CPU host from
all shards, they are concatenated (on CPU) and passed as positional arguments
to the `metric_fn` if `tensors` is list or keyword arguments if `tensors` is
a dict. `metric_fn` takes the `tensors` and returns a dict from metric string
name to the result of calling a metric function, namely a `(metric_tensor,
update_op)` tuple. See `TPUEstimator` for MNIST example how to specify the
`eval_metrics`.

`scaffold_fn` is a function running on CPU to generate the `Scaffold`. This
function should not capture any Tensors in `model_fn`.

`host_call` is a tuple of a `function` and a list or dictionary of `tensors`
to pass to that function and returns a list of Tensors. `host_call` currently
works for train() and evaluate(). The Tensors returned by the function is
executed on the CPU on every step, so there is communication overhead when
sending tensors from TPU to CPU. To reduce the overhead, try reducing the
size of the tensors. The `tensors` are concatenated along their major (batch)
dimension, and so must be >= rank 1. The `host_call` is useful for writing
summaries with <a href="../../../tf/contrib/summary/create_file_writer.md"><code>tf.contrib.summary.create_file_writer</code></a>.

## Properties

<h3 id="eval_metrics"><code>eval_metrics</code></h3>

Alias for field number 4

<h3 id="export_outputs"><code>export_outputs</code></h3>

Alias for field number 5

<h3 id="host_call"><code>host_call</code></h3>

Alias for field number 7

<h3 id="loss"><code>loss</code></h3>

Alias for field number 2

<h3 id="mode"><code>mode</code></h3>

Alias for field number 0

<h3 id="predictions"><code>predictions</code></h3>

Alias for field number 1

<h3 id="scaffold_fn"><code>scaffold_fn</code></h3>

Alias for field number 6

<h3 id="train_op"><code>train_op</code></h3>

Alias for field number 3



## Methods

<h3 id="__new__"><code>__new__</code></h3>

``` python
@staticmethod
__new__(
    cls,
    mode,
    predictions=None,
    loss=None,
    train_op=None,
    eval_metrics=None,
    export_outputs=None,
    scaffold_fn=None,
    host_call=None
)
```

Creates a validated `TPUEstimatorSpec` instance.

<h3 id="as_estimator_spec"><code>as_estimator_spec</code></h3>

``` python
as_estimator_spec()
```

Creates an equivalent `EstimatorSpec` used by CPU train/eval.




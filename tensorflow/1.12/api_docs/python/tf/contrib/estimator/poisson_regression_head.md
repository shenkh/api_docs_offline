<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.estimator.poisson_regression_head" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.estimator.poisson_regression_head

``` python
tf.contrib.estimator.poisson_regression_head(
    weight_column=None,
    label_dimension=1,
    loss_reduction=losses.Reduction.SUM_OVER_BATCH_SIZE,
    compute_full_loss=True,
    name=None
)
```



Defined in [`tensorflow/contrib/estimator/python/estimator/head.py`](/code/stable/tensorflow/contrib/estimator/python/estimator/head.py).

Creates a `_Head` for poisson regression using <a href="../../../tf/nn/log_poisson_loss.md"><code>tf.nn.log_poisson_loss</code></a>.

The loss is the weighted sum over all input dimensions. Namely, if the input
labels have shape `[batch_size, label_dimension]`, the loss is the weighted
sum over both `batch_size` and `label_dimension`.

The head expects `logits` with shape `[D0, D1, ... DN, label_dimension]`.
In many applications, the shape is `[batch_size, label_dimension]`.

The `labels` shape must match `logits`, namely
`[D0, D1, ... DN, label_dimension]`. If `label_dimension=1`, shape
`[D0, D1, ... DN]` is also supported.

If `weight_column` is specified, weights must be of shape
`[D0, D1, ... DN]`, `[D0, D1, ... DN, 1]` or
`[D0, D1, ... DN, label_dimension]`.

This is implemented as a generalized linear model, see
https://en.wikipedia.org/wiki/Generalized_linear_model.

The head can be used with a canned estimator. Example:

```python
my_head = tf.contrib.estimator.poisson_regression_head()
my_estimator = tf.contrib.estimator.DNNEstimator(
    head=my_head,
    hidden_units=...,
    feature_columns=...)
```

It can also be used with a custom `model_fn`. Example:

```python
def _my_model_fn(features, labels, mode):
  my_head = tf.contrib.estimator.poisson_regression_head()
  logits = tf.keras.Model(...)(features)

  return my_head.create_estimator_spec(
      features=features,
      mode=mode,
      labels=labels,
      optimizer=tf.AdagradOptimizer(learning_rate=0.1),
      logits=logits)

my_estimator = tf.estimator.Estimator(model_fn=_my_model_fn)
```

#### Args:

* <b>`weight_column`</b>: A string or a `_NumericColumn` created by
    <a href="../../../tf/feature_column/numeric_column.md"><code>tf.feature_column.numeric_column</code></a> defining feature column representing
    weights. It is used to down weight or boost examples during training. It
    will be multiplied by the loss of the example.
* <b>`label_dimension`</b>: Number of regression labels per example. This is the size
    of the last dimension of the labels `Tensor` (typically, this has shape
    `[batch_size, label_dimension]`).
* <b>`loss_reduction`</b>: One of <a href="../../../tf/losses/Reduction.md"><code>tf.losses.Reduction</code></a> except `NONE`. Describes how to
    reduce training loss over batch and label dimension. Defaults to
    `SUM_OVER_BATCH_SIZE`, namely weighted sum of losses divided by
    `batch size * label_dimension`. See <a href="../../../tf/losses/Reduction.md"><code>tf.losses.Reduction</code></a>.
* <b>`compute_full_loss`</b>: Whether to include the constant `log(z!)` term in
    computing the poisson loss. See <a href="../../../tf/nn/log_poisson_loss.md"><code>tf.nn.log_poisson_loss</code></a> for the full
    documentation.
* <b>`name`</b>: name of the head. If provided, summary and metrics keys will be
    suffixed by `"/" + name`. Also used as `name_scope` when creating ops.


#### Returns:

An instance of `_Head` for poisson regression.


#### Raises:

* <b>`ValueError`</b>: If `label_dimension` or `loss_reduction` is invalid.
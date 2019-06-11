<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.compute_average_loss" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.compute_average_loss

Scales per-example losses with sample_weights and computes their average.

### Aliases:

* `tf.compat.v1.nn.compute_average_loss`
* `tf.compat.v2.nn.compute_average_loss`
* `tf.nn.compute_average_loss`

``` python
tf.nn.compute_average_loss(
    per_example_loss,
    sample_weight=None,
    global_batch_size=None
)
```



Defined in [`python/ops/nn_impl.py`](/code/stable/tensorflow/python/ops/nn_impl.py).

<!-- Placeholder for "Used in" -->

Usage with distribution strategy and custom training loop:

```python
with strategy.scope():
  def compute_loss(labels, predictions, sample_weight=None):

    # If you are using a `Loss` class instead, set reduction to `NONE` so that
    # we can do the reduction afterwards and divide by global batch size.
    per_example_loss = tf.keras.losses.sparse_categorical_crossentropy(
        labels, predictions)

    # Compute loss that is scaled by sample_weight and by global batch size.
    return tf.compute_average_loss(
        per_example_loss,
        sample_weight=sample_weight,
        global_batch_size=GLOBAL_BATCH_SIZE)
```

#### Args:


* <b>`per_example_loss`</b>: Per-example loss.
* <b>`sample_weight`</b>: Optional weighting for each example.
* <b>`global_batch_size`</b>: Optional global batch size value. Defaults to (size of
  first dimension of `losses`) * (number of replicas).


#### Returns:

Scalar loss value.

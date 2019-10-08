<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.losses.KLD" />
<meta itemprop="path" content="Stable" />
</div>

# tf.losses.KLD

### Aliases:

* `tf.keras.losses.KLD`
* `tf.keras.losses.kld`
* `tf.keras.losses.kullback_leibler_divergence`
* `tf.keras.metrics.KLD`
* `tf.keras.metrics.kld`
* `tf.keras.metrics.kullback_leibler_divergence`
* `tf.losses.KLD`
* `tf.losses.kld`
* `tf.losses.kullback_leibler_divergence`
* `tf.metrics.KLD`
* `tf.metrics.kld`
* `tf.metrics.kullback_leibler_divergence`

``` python
tf.losses.KLD(
    y_true,
    y_pred
)
```



Defined in [`tensorflow/python/keras/losses.py`](/code/stable/tensorflow/python/keras/losses.py).

Computes Kullback-Leibler divergence loss between `y_true` and `y_pred`.

`loss = y_true * log(y_true / y_pred)`

See: https://en.wikipedia.org/wiki/Kullback%E2%80%93Leibler_divergence

Usage:

```python
loss = tf.keras.losses.KLD([.4, .9, .2], [.5, .8, .12])
print('Loss: ', loss.numpy())  # Loss: 0.11891246
```

#### Args:

* <b>`y_true`</b>: Tensor of true targets.
* <b>`y_pred`</b>: Tensor of predicted targets.


#### Returns:

A `Tensor` with loss.


#### Raises:

* <b>`TypeError`</b>: If `y_true` cannot be cast to the `y_pred.dtype`.
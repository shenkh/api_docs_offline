<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.losses.hinge" />
<meta itemprop="path" content="Stable" />
</div>

# tf.losses.hinge

### Aliases:

* `tf.keras.losses.hinge`
* `tf.keras.metrics.hinge`
* `tf.losses.hinge`
* `tf.metrics.hinge`

``` python
tf.losses.hinge(
    y_true,
    y_pred
)
```



Defined in [`tensorflow/python/keras/losses.py`](/code/stable/tensorflow/python/keras/losses.py).

Computes the hinge loss between `y_true` and `y_pred`.

#### Args:

* <b>`y_true`</b>: The ground truth values. `y_true` values are expected to be -1 or 1.
    If binary (0 or 1) labels are provided they will be converted to -1 or 1.
* <b>`y_pred`</b>: The predicted values.


#### Returns:

Tensor with one scalar loss entry per sample.
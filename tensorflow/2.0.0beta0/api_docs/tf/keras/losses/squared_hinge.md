<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.losses.squared_hinge" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.losses.squared_hinge

Computes the squared hinge loss between `y_true` and `y_pred`.

### Aliases:

* `tf.compat.v1.keras.losses.squared_hinge`
* `tf.compat.v1.keras.metrics.squared_hinge`
* `tf.compat.v2.keras.losses.squared_hinge`
* `tf.compat.v2.keras.metrics.squared_hinge`
* `tf.compat.v2.losses.squared_hinge`
* `tf.compat.v2.metrics.squared_hinge`
* `tf.keras.losses.squared_hinge`
* `tf.keras.metrics.squared_hinge`
* `tf.losses.squared_hinge`
* `tf.metrics.squared_hinge`

``` python
tf.keras.losses.squared_hinge(
    y_true,
    y_pred
)
```



Defined in [`python/keras/losses.py`](/code/stable/tensorflow/python/keras/losses.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`y_true`</b>: The ground truth values. `y_true` values are expected to be -1 or 1.
  If binary (0 or 1) labels are provided we will convert them to -1 or 1.
* <b>`y_pred`</b>: The predicted values.


#### Returns:

Tensor with one scalar loss entry per sample.

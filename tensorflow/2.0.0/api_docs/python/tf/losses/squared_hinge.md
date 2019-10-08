<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.losses.squared_hinge" />
<meta itemprop="path" content="Stable" />
</div>

# tf.losses.squared_hinge

### Aliases:

* `tf.keras.losses.squared_hinge`
* `tf.keras.metrics.squared_hinge`
* `tf.losses.squared_hinge`
* `tf.metrics.squared_hinge`

``` python
tf.losses.squared_hinge(
    y_true,
    y_pred
)
```



Defined in [`tensorflow/python/keras/losses.py`](/code/stable/tensorflow/python/keras/losses.py).

Computes the squared hinge loss between `y_true` and `y_pred`.

#### Args:

* <b>`y_true`</b>: The ground truth values. `y_true` values are expected to be -1 or 1.
    If binary (0 or 1) labels are provided we will convert them to -1 or 1.
* <b>`y_pred`</b>: The predicted values.


#### Returns:

Tensor with one scalar loss entry per sample.
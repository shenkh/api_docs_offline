<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.losses.categorical_hinge" />
<meta itemprop="path" content="Stable" />
</div>

# tf.losses.categorical_hinge

### Aliases:

* `tf.keras.losses.categorical_hinge`
* `tf.losses.categorical_hinge`

``` python
tf.losses.categorical_hinge(
    y_true,
    y_pred
)
```



Defined in [`tensorflow/python/keras/losses.py`](/code/stable/tensorflow/python/keras/losses.py).

Computes the categorical hinge loss between `y_true` and `y_pred`.

#### Args:

* <b>`y_true`</b>: The ground truth values. `y_true` values are expected to be -1 or 1.
    If binary (0 or 1) labels are provided they will be converted to -1 or 1.
* <b>`y_pred`</b>: The predicted values.


#### Returns:

A tensor.
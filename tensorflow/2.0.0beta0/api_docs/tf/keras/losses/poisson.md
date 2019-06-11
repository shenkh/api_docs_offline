<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.losses.poisson" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.losses.poisson

Computes the Poisson loss between y_true and y_pred.

### Aliases:

* `tf.compat.v1.keras.losses.poisson`
* `tf.compat.v1.keras.metrics.poisson`
* `tf.compat.v2.keras.losses.poisson`
* `tf.compat.v2.keras.metrics.poisson`
* `tf.compat.v2.losses.poisson`
* `tf.compat.v2.metrics.poisson`
* `tf.keras.losses.poisson`
* `tf.keras.metrics.poisson`
* `tf.losses.poisson`
* `tf.metrics.poisson`

``` python
tf.keras.losses.poisson(
    y_true,
    y_pred
)
```



Defined in [`python/keras/losses.py`](/code/stable/tensorflow/python/keras/losses.py).

<!-- Placeholder for "Used in" -->

The Poisson loss is the mean of the elements of the `Tensor`
`y_pred - y_true * log(y_pred)`.

#### Usage:



```python
loss = tf.keras.losses.poisson([1.4, 9.3, 2.2], [4.3, 8.2, 12.2])
print('Loss: ', loss.numpy())  # Loss: -0.8045559
```

#### Args:


* <b>`y_true`</b>: Tensor of true targets.
* <b>`y_pred`</b>: Tensor of predicted targets.


#### Returns:

A `Tensor` with the mean Poisson loss.



#### Raises:


* <b>`InvalidArgumentError`</b>: If `y_true` and `y_pred` have incompatible shapes.
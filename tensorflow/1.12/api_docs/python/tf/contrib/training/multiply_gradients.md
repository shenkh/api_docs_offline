<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.training.multiply_gradients" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.training.multiply_gradients

``` python
tf.contrib.training.multiply_gradients(
    grads_and_vars,
    gradient_multipliers
)
```



Defined in [`tensorflow/contrib/training/python/training/training.py`](/code/stable/tensorflow/contrib/training/python/training/training.py).

Multiply specified gradients.

#### Args:

* <b>`grads_and_vars`</b>: A list of gradient to variable pairs (tuples).
* <b>`gradient_multipliers`</b>: A map from either `Variables` or `Variable` op names
    to the coefficient by which the associated gradient should be scaled.


#### Returns:

The updated list of gradient to variable pairs.


#### Raises:

* <b>`ValueError`</b>: If `grads_and_vars` is not a list or if `gradient_multipliers`
  is empty or None or if `gradient_multipliers` is not a dictionary.
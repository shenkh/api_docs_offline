<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.switch" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.switch

``` python
tf.keras.backend.switch(
    condition,
    then_expression,
    else_expression
)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Switches between two operations depending on a scalar value.

Note that both `then_expression` and `else_expression`
should be symbolic tensors of the *same shape*.

#### Arguments:

* <b>`condition`</b>: tensor (`int` or `bool`).
* <b>`then_expression`</b>: either a tensor, or a callable that returns a tensor.
* <b>`else_expression`</b>: either a tensor, or a callable that returns a tensor.


#### Returns:

The selected tensor.


#### Raises:

* <b>`ValueError`</b>: If rank of `condition` is greater than rank of expressions.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.stop_gradient" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.stop_gradient

``` python
tf.keras.backend.stop_gradient(variables)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Returns `variables` but with zero gradient w.r.t. every other variable.

#### Arguments:

* <b>`variables`</b>: Tensor or list of tensors to consider constant with respect
      to any other variable.



#### Returns:

A single tensor or a list of tensors (depending on the passed argument)
that has no gradient with respect to any other variable.
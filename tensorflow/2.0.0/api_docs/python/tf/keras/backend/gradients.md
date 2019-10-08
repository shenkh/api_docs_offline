<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.gradients" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.gradients

``` python
tf.keras.backend.gradients(
    loss,
    variables
)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Returns the gradients of `loss` w.r.t. `variables`.

#### Arguments:

* <b>`loss`</b>: Scalar tensor to minimize.
* <b>`variables`</b>: List of variables.


#### Returns:

A gradients tensor.
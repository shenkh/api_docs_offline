<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.zeros_like" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.zeros_like

``` python
tf.keras.backend.zeros_like(
    x,
    dtype=None,
    name=None
)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Instantiates an all-zeros variable of the same shape as another tensor.

#### Arguments:

* <b>`x`</b>: Keras variable or Keras tensor.
* <b>`dtype`</b>: dtype of returned Keras variable.
           `None` uses the dtype of `x`.
* <b>`name`</b>: name for the variable to create.


#### Returns:

    A Keras variable with the shape of `x` filled with zeros.

Example:

```python
from tensorflow.keras import backend as K
kvar = K.variable(np.random.random((2,3)))
kvar_zeros = K.zeros_like(kvar)
K.eval(kvar_zeros)
# array([[ 0.,  0.,  0.], [ 0.,  0.,  0.]], dtype=float32)
```
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.activations.sigmoid" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.activations.sigmoid

``` python
tf.keras.activations.sigmoid(x)
```



Defined in [`tensorflow/python/keras/activations.py`](/code/stable/tensorflow/python/keras/activations.py).

Sigmoid.

Applies the sigmoid activation function. The sigmoid function is defined as
1 divided by (1 + exp(-x)). It's curve is like an "S" and is like a smoothed
version of the Heaviside (Unit Step Function) function. For small values
(<-5) the sigmoid returns a value close to zero and for larger values (>5)
the result of the function gets close to 1.
#### Arguments:

* <b>`x`</b>: A tensor or variable.


#### Returns:

    A tensor.
Sigmoid activation function.


#### Arguments:

* <b>`x`</b>: Input tensor.


#### Returns:

The sigmoid activation: `(1.0 / (1.0 + exp(-x)))`.
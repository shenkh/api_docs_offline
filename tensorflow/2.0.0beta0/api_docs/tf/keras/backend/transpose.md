<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.transpose" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.transpose

Transposes a tensor and returns it.

### Aliases:

* `tf.compat.v1.keras.backend.transpose`
* `tf.compat.v2.keras.backend.transpose`
* `tf.keras.backend.transpose`

``` python
tf.keras.backend.transpose(x)
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->


#### Arguments:


* <b>`x`</b>: Tensor or variable.


#### Returns:

A tensor.



#### Examples:


```python
    >>> var = K.variable([[1, 2, 3], [4, 5, 6]])
    >>> K.eval(var)
    array([[ 1.,  2.,  3.],
           [ 4.,  5.,  6.]], dtype=float32)
    >>> var_transposed = K.transpose(var)
    >>> K.eval(var_transposed)
    array([[ 1.,  4.],
           [ 2.,  5.],
           [ 3.,  6.]], dtype=float32)
```

```python
    >>> input = K.placeholder((2, 3))
    >>> input
    <tf.Tensor 'Placeholder_11:0' shape=(2, 3) dtype=float32>
    >>> input_transposed = K.transpose(input)
    >>> input_transposed
    <tf.Tensor 'transpose_4:0' shape=(3, 2) dtype=float32>

```
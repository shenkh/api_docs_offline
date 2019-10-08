<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.arange" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.arange

``` python
tf.keras.backend.arange(
    start,
    stop=None,
    step=1,
    dtype='int32'
)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Creates a 1D tensor containing a sequence of integers.

The function arguments use the same convention as
Theano's arange: if only one argument is provided,
it is in fact the "stop" argument and "start" is 0.

The default type of the returned tensor is `'int32'` to
match TensorFlow's default.

#### Arguments:

* <b>`start`</b>: Start value.
* <b>`stop`</b>: Stop value.
* <b>`step`</b>: Difference between two successive values.
* <b>`dtype`</b>: Integer dtype to use.


#### Returns:

    An integer tensor.

Example:
    ```python
      >>> tf.keras.backend.arange(start=0, stop=10, step=1.5)
      <tf.Tensor: id=96, shape=(7,), dtype=float32,
          numpy=array([0. , 1.5, 3. , 4.5, 6. , 7.5, 9. ], dtype=float32)>

    ```
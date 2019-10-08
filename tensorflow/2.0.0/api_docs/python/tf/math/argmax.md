<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.argmax" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.argmax

### Aliases:

* `tf.argmax`
* `tf.math.argmax`

``` python
tf.math.argmax(
    input,
    axis=None,
    output_type=tf.dtypes.int64,
    name=None
)
```



Defined in [`tensorflow/python/ops/math_ops.py`](/code/stable/tensorflow/python/ops/math_ops.py).

Returns the index with the largest value across axes of a tensor.

Note that in case of ties the identity of the return value is not guaranteed.

For example:
```python
A=tf.constant([2,20,30,3,6]) # Constant 1-D Tensor
tf.math.argmax(A) # output 2 as index 2 (A[2]) is maximum in tensor A
B=tf.constant([[2,20,30,3,6],[3,11,16,1,8],[14,45,23,5,27]])
tf.math.argmax(B,0) # [2, 2, 0, 2, 2]
tf.math.argmax(B,1) # [2, 2, 1]
```
 
#### Args:

* <b>`input`</b>: A `Tensor`. Must be one of the following types: `float32`, `float64`,
    `int32`, `uint8`, `int16`, `int8`, `complex64`, `int64`, `qint8`,
    `quint8`, `qint32`, `bfloat16`, `uint16`, `complex128`, `half`, `uint32`,
    `uint64`.
* <b>`axis`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`.
    int32 or int64, must be in the range `-rank(input), rank(input))`.
    Describes which axis of the input Tensor to reduce across. For vectors,
    use axis = 0.
* <b>`output_type`</b>: An optional <a href="../../tf/dtypes/DType.md"><code>tf.DType</code></a> from: `tf.int32, tf.int64`. Defaults to
    <a href="../../tf/dtypes.md#int64"><code>tf.int64</code></a>.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

  A `Tensor` of type `output_type`.

Usage:
```python
import tensorflow as tf
a = [1, 10, 26.9, 2.8, 166.32, 62.3]
b = tf.math.argmax(input = a)
c = tf.keras.backend.eval(b)
# c = 4
# here a[4] = 166.32 which is the largest element of a across axis 0
```
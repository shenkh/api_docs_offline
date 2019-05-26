<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.rnn.transpose_batch_time" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.rnn.transpose_batch_time

``` python
tf.contrib.rnn.transpose_batch_time(x)
```



Defined in [`tensorflow/python/ops/rnn.py`](https://www.tensorflow.org/code/tensorflow/python/ops/rnn.py).

Transposes the batch and time dimensions of a Tensor.

If the input tensor has rank < 2 it returns the original tensor. Retains as
much of the static shape information as possible.

#### Args:

* <b>`x`</b>: A Tensor.


#### Returns:

x transposed along the first two dimensions.
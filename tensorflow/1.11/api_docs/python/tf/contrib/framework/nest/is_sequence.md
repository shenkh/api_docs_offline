<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.nest.is_sequence" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.framework.nest.is_sequence

``` python
tf.contrib.framework.nest.is_sequence(o)
```



Defined in [`tensorflow/python/pywrap_tensorflow_internal.py`](https://www.tensorflow.org/code/tensorflow/python/pywrap_tensorflow_internal.py).

Returns a true if its input is a collections.Sequence (except strings).

#### Args:

* <b>`seq`</b>: an input sequence.


#### Returns:

True if the sequence is a not a string and is a collections.Sequence or a
dict.
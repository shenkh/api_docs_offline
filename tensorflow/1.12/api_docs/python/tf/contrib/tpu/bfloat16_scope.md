<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.tpu.bfloat16_scope" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.tpu.bfloat16_scope

``` python
tf.contrib.tpu.bfloat16_scope()
```



Defined in [`tensorflow/contrib/tpu/python/tpu/bfloat16.py`](/code/stable/tensorflow/contrib/tpu/python/tpu/bfloat16.py).

Scope class for bfloat16 variables so that the model uses custom getter.

This enables variables to be read as bfloat16 type when using get_variable.
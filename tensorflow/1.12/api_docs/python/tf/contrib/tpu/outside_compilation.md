<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.tpu.outside_compilation" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.tpu.outside_compilation

``` python
tf.contrib.tpu.outside_compilation(
    computation,
    *args,
    **kwargs
)
```



Defined in [`tensorflow/contrib/tpu/python/tpu/tpu.py`](/code/stable/tensorflow/contrib/tpu/python/tpu/tpu.py).

Builds part of a computation outside any current TPU replicate scope.

#### Args:

* <b>`computation`</b>: A Python function that builds the computation to
    place on the host.
* <b>`*args`</b>: the positional arguments for the computation.
* <b>`**kwargs`</b>: the keyword arguments for the computation.


#### Returns:

The Tensors returned by computation.
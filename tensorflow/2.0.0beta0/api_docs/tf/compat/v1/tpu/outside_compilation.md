<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.tpu.outside_compilation" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.tpu.outside_compilation

Builds part of a computation outside any current TPU replicate scope.

``` python
tf.compat.v1.tpu.outside_compilation(
    computation,
    *args,
    **kwargs
)
```



Defined in [`python/tpu/tpu.py`](/code/stable/tensorflow/python/tpu/tpu.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`computation`</b>: A Python function that builds the computation to
  place on the host.
* <b>`*args`</b>: the positional arguments for the computation.
* <b>`**kwargs`</b>: the keyword arguments for the computation.


#### Returns:

The Tensors returned by computation.

<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.disable_eager_execution" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.disable_eager_execution

Disables eager execution.

``` python
tf.compat.v1.disable_eager_execution()
```



Defined in [`python/framework/ops.py`](/code/stable/tensorflow/python/framework/ops.py).

<!-- Placeholder for "Used in" -->

This function can only be called before any Graphs, Ops, or Tensors have been
created. It can be used at the beginning of the program for complex migration
projects from TensorFlow 1.x to 2.x.
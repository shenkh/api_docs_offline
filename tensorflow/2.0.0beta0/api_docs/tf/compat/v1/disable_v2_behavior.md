<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.disable_v2_behavior" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.disable_v2_behavior

Disables TensorFlow 2.x behaviors.

``` python
tf.compat.v1.disable_v2_behavior()
```



Defined in [`python/compat/v2_compat.py`](/code/stable/tensorflow/python/compat/v2_compat.py).

<!-- Placeholder for "Used in" -->

This function can be called at the beginning of the program (before `Tensors`,
`Graphs` or other structures have been created, and before devices have been
initialized. It switches all global behaviors that are different between
TensorFlow 1.x and 2.x to behave as intended for 1.x.

User can call this function to disable 2.x behavior during complex migrations.
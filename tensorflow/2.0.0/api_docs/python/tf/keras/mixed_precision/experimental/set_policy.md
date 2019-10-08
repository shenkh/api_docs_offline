<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.mixed_precision.experimental.set_policy" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.mixed_precision.experimental.set_policy

``` python
tf.keras.mixed_precision.experimental.set_policy(policy)
```



Defined in [`tensorflow/python/keras/mixed_precision/experimental/policy.py`](/code/stable/tensorflow/python/keras/mixed_precision/experimental/policy.py).

Sets the global Policy.

The global policy is the default policy used for layers, if no policy is
passed to the layer constructor. If no global policy is set, layers will
instead default to a Policy constructed from `tf.keras.backend.floatx()` in
TensorFlow 2. In TensorFlow 1, layers default to an "infer" policy.

See `keras.mixed_precision.experimental.Policy` for more information.

#### Args:

* <b>`policy`</b>: A Policy, or a string that will be converted to a Policy..
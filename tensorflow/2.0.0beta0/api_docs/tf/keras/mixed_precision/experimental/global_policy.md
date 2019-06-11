<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.mixed_precision.experimental.global_policy" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.mixed_precision.experimental.global_policy

Returns the global Policy.

### Aliases:

* `tf.compat.v1.keras.mixed_precision.experimental.global_policy`
* `tf.compat.v2.keras.mixed_precision.experimental.global_policy`
* `tf.keras.mixed_precision.experimental.global_policy`

``` python
tf.keras.mixed_precision.experimental.global_policy()
```



Defined in [`python/keras/mixed_precision/experimental/policy.py`](/code/stable/tensorflow/python/keras/mixed_precision/experimental/policy.py).

<!-- Placeholder for "Used in" -->

The global policy is the default policy used for layers, if no policy is
passed to the layer constructor. When TensorFlow starts, the global policy is
set to an "infer" policy, and can be changed with `set_policy`.

#### Returns:

The global Policy.

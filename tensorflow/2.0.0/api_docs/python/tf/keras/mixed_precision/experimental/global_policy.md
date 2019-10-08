<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.mixed_precision.experimental.global_policy" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.mixed_precision.experimental.global_policy

``` python
tf.keras.mixed_precision.experimental.global_policy()
```



Defined in [`tensorflow/python/keras/mixed_precision/experimental/policy.py`](/code/stable/tensorflow/python/keras/mixed_precision/experimental/policy.py).

Returns the global Policy.

The global policy is the default policy used for layers, if no policy is
passed to the layer constructor. If no policy has been set with
`keras.mixed_precision.experimental.set_policy`, this will return a policy
constructed from `tf.keras.backend.floatx()` in TensorFlow 2, or an "infer"
policy in TensorFlow 1.

See `keras.mixed_precision.experimental.Policy` for more information.

#### Returns:

The global Policy.
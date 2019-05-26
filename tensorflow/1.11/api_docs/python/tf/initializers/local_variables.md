<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.initializers.local_variables" />
<meta itemprop="path" content="Stable" />
</div>

# tf.initializers.local_variables

### Aliases:

* `tf.initializers.local_variables`
* `tf.local_variables_initializer`

``` python
tf.initializers.local_variables()
```



Defined in [`tensorflow/python/ops/variables.py`](https://www.tensorflow.org/code/tensorflow/python/ops/variables.py).

See the guide: [Upgrade to TensorFlow 1.0 > Upgrading your code manually](../../../../api_guides/python/upgrade.md#Upgrading_your_code_manually)

Returns an Op that initializes all local variables.

This is just a shortcut for `variables_initializer(local_variables())`

#### Returns:

An Op that initializes all local variables in the graph.
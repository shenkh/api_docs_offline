<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.eager.get_optimizer_variables" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.eager.get_optimizer_variables

``` python
tf.contrib.eager.get_optimizer_variables(optimizer)
```



Defined in [`tensorflow/contrib/eager/python/saver.py`](https://www.tensorflow.org/code/tensorflow/contrib/eager/python/saver.py).

Returns a list of variables for the given <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>.

Equivalent to `optimizer.variables()`.

#### Args:

* <b>`optimizer`</b>: An instance of <a href="../../../tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a> which has created variables
    (typically after a call to `Optimizer.minimize`).

#### Returns:

A list of variables which have been created by the `Optimizer`.
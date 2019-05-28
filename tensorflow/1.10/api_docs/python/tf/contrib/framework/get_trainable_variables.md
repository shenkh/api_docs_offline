<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.get_trainable_variables" />
</div>

# tf.contrib.framework.get_trainable_variables

``` python
tf.contrib.framework.get_trainable_variables(
    scope=None,
    suffix=None
)
```



Defined in [`tensorflow/contrib/framework/python/ops/variables.py`](https://www.tensorflow.org/code/tensorflow/contrib/framework/python/ops/variables.py).

Gets the list of trainable variables, filtered by scope and/or suffix.

#### Args:

* <b>`scope`</b>: an optional scope for filtering the variables to return.
* <b>`suffix`</b>: an optional suffix for filtering the variables to return.


#### Returns:

a list of variables in the trainable collection with scope and suffix.
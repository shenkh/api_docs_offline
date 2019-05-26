<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.get_variables" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.framework.get_variables

``` python
tf.contrib.framework.get_variables(
    scope=None,
    suffix=None,
    collection=tf.GraphKeys.GLOBAL_VARIABLES
)
```



Defined in [`tensorflow/contrib/framework/python/ops/variables.py`](/code/stable/tensorflow/contrib/framework/python/ops/variables.py).

Gets the list of variables, filtered by scope and/or suffix.

#### Args:

* <b>`scope`</b>: an optional scope for filtering the variables to return. Can be a
    variable scope or a string.
* <b>`suffix`</b>: an optional suffix for filtering the variables to return.
* <b>`collection`</b>: in which collection search for. Defaults to
    `GraphKeys.GLOBAL_VARIABLES`.


#### Returns:

a list of variables in collection with scope and suffix.
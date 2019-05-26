<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.get_variables_by_suffix" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.framework.get_variables_by_suffix

``` python
tf.contrib.framework.get_variables_by_suffix(
    suffix,
    scope=None
)
```



Defined in [`tensorflow/contrib/framework/python/ops/variables.py`](/code/stable/tensorflow/contrib/framework/python/ops/variables.py).

Gets the list of variables that end with the given suffix.

#### Args:

* <b>`suffix`</b>: suffix for filtering the variables to return.
* <b>`scope`</b>: an optional scope for filtering the variables to return.


#### Returns:

a copied list of variables with the given name and prefix.
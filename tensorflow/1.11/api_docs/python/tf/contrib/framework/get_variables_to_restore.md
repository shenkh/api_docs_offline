<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.framework.get_variables_to_restore" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.framework.get_variables_to_restore

``` python
tf.contrib.framework.get_variables_to_restore(
    include=None,
    exclude=None
)
```



Defined in [`tensorflow/contrib/framework/python/ops/variables.py`](https://www.tensorflow.org/code/tensorflow/contrib/framework/python/ops/variables.py).

Gets the list of the variables to restore.

#### Args:

* <b>`include`</b>: an optional list/tuple of scope strings for filtering which
    variables from the VARIABLES collection to include. None would include all
    the variables.
* <b>`exclude`</b>: an optional list/tuple of scope strings for filtering which
    variables from the VARIABLES collection to exclude. None it would not
    exclude any.


#### Returns:

a list of variables to restore.


#### Raises:

* <b>`TypeError`</b>: include or exclude is provided but is not a list or a tuple.
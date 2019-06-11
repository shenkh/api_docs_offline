<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.tf_decorator.unwrap" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.flags.tf_decorator.unwrap

Unwraps an object into a list of TFDecorators and a final target.

### Aliases:

* `tf.compat.v1.app.flags.tf_decorator.unwrap`
* `tf.compat.v1.flags.tf_decorator.unwrap`

``` python
tf.compat.v1.flags.tf_decorator.unwrap(maybe_tf_decorator)
```



Defined in [`python/util/tf_decorator.py`](/code/stable/tensorflow/python/util/tf_decorator.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`maybe_tf_decorator`</b>: Any callable object.


#### Returns:

A tuple whose first element is an list of TFDecorator-derived objects that
were applied to the final callable target, and whose second element is the
final undecorated callable target. If the `maybe_tf_decorator` parameter is
not decorated by any TFDecorators, the first tuple element will be an empty
list. The `TFDecorator` list is ordered from outermost to innermost
decorators.

<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.recompute_grad" />
<meta itemprop="path" content="Stable" />
</div>

# tf.recompute_grad

``` python
tf.recompute_grad(f)
```



Defined in [`tensorflow/python/ops/custom_gradient.py`](/code/stable/tensorflow/python/ops/custom_gradient.py).

An eager-compatible version of recompute_grad.

For f(*args, **kwargs), this supports gradients with respect to args, or to
gradients with respect to any variables residing in the kwarg 'variables'.
Note that for keras layer and model objects, this is handled automatically.

Warning: If `f` was originally a tf.keras Model or Layer object, `g` will not
be able to access the member variables of that object, because `g` returns
through the wrapper function `inner`.  When recomputing gradients through
objects that inherit from keras, we suggest keeping a reference to the
underlying object around for the purpose of accessing these variables.

#### Args:

* <b>`f`</b>: function `f(*x)` that returns a `Tensor` or sequence of `Tensor` outputs.


#### Returns:

A function `g` that wraps `f`, but which recomputes `f` on the backwards
pass of a gradient call.
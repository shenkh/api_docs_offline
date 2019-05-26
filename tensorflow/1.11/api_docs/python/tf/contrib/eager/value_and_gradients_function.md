<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.eager.value_and_gradients_function" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.eager.value_and_gradients_function

``` python
tf.contrib.eager.value_and_gradients_function(
    f,
    params=None
)
```



Defined in [`tensorflow/python/eager/backprop.py`](https://www.tensorflow.org/code/tensorflow/python/eager/backprop.py).

Returns a function that computes f and its derivative w.r.t. params.

Example:
```python
# f(x, y) = (x ^ 3) * y - x * (y ^ 2)
# Therefore, the 1st order derivatives are:
#   df / dx = 3 * (x ^ 2) * y - y ^ 2
#   df / dy = x ^ 3 - 2 * x * y
def f(x, y):
  return x * x * x * y - x * y * y

# Obtain a function that returns the function value and the 1st order
# gradients.
val_grads_fn = tfe.value_and_gradients_function(f)

x = 2.0
y = 3.0

# Invoke the value-and-gradients function.
f_val, (x_grad, y_grad) = val_grads_fn(x, y)
assert f_val.numpy() == (2 ** 3) * 3 - 2 * (3 ** 2)
assert x_grad.numpy() == 3 * (2 ** 2) * 3 - 3 ** 2
assert y_grad.numpy() == (2 ** 3) - 2 * 2 * 3

# To obtain a callable that returns the value of `f` and the gradient(s) of
# `f` with respect to a subset of its inputs, use the `params` keyword
# argument with `value_and_gradients_function()`.
val_ygrad_fn = tfe.value_and_gradients_function(f, params=[1])

f_val, (y_grad,) = val_ygrad_fn(x, y)
assert f_val.numpy() == (2 ** 3) * 3 - 2 * (3 ** 2)
assert y_grad.numpy() == (2 ** 3) - 2 * 2 * 3
```

#### Args:

* <b>`f`</b>: function to be differentiated. If `f` returns a scalar, this scalar will
    be differentiated. If `f` returns a tensor or list of tensors, by default
    a scalar will be computed by adding all their values to produce a single
    scalar. If desired, the tensors can be elementwise multiplied by the
    tensors passed as the `dy` keyword argument to the returned gradient
    function.
* <b>`params`</b>: list of parameter names of f or list of integers indexing the
    parameters with respect to which we'll differentiate. Passing `None`
    differentiates with respect to all parameters.


#### Returns:

function which, when called, returns the value of f and the gradient
of f with respect to all of `params`. The function takes an extra optional
keyword argument "dy". Setting it allows computation of vector jacobian
products for vectors other than the vector of ones.


#### Raises:

* <b>`ValueError`</b>: if the params are not all strings or all integers.
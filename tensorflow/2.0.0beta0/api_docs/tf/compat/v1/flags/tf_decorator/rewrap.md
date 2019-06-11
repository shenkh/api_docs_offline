<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.flags.tf_decorator.rewrap" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.flags.tf_decorator.rewrap

Injects a new target into a function built by make_decorator.

### Aliases:

* `tf.compat.v1.app.flags.tf_decorator.rewrap`
* `tf.compat.v1.flags.tf_decorator.rewrap`

``` python
tf.compat.v1.flags.tf_decorator.rewrap(
    decorator_func,
    previous_target,
    new_target
)
```



Defined in [`python/util/tf_decorator.py`](/code/stable/tensorflow/python/util/tf_decorator.py).

<!-- Placeholder for "Used in" -->

This function allows replacing a function wrapped by `decorator_func`,
assuming the decorator that wraps the function is written as described below.

The decorator function must use `<decorator name>.__wrapped__` instead of the
wrapped function that is normally used:

#### Example:


# Instead of this:
def simple_parametrized_wrapper(*args, **kwds):
  return wrapped_fn(*args, **kwds)

tf_decorator.make_decorator(simple_parametrized_wrapper, wrapped_fn)

# Write this:
def simple_parametrized_wrapper(*args, **kwds):
  return simple_parametrized_wrapper.__wrapped__(*args, **kwds)

tf_decorator.make_decorator(simple_parametrized_wrapper, wrapped_fn)


Note that this process modifies decorator_func.

#### Args:


* <b>`decorator_func`</b>: Callable returned by `wrap`.
* <b>`previous_target`</b>: Callable that needs to be replaced.
* <b>`new_target`</b>: Callable to replace previous_target with.


#### Returns:

The updated decorator. If decorator_func is not a tf_decorator, new_target
is returned.

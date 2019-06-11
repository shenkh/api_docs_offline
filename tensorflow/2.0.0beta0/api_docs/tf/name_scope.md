<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.name_scope" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="__enter__"/>
<meta itemprop="property" content="__exit__"/>
<meta itemprop="property" content="__init__"/>
</div>

# tf.name_scope

## Class `name_scope`

A context manager for use when defining a Python op.

Inherits From: [`name_scope`](../tf/compat/v1/keras/backend/name_scope.md)

### Aliases:

* Class `tf.compat.v2.name_scope`
* Class `tf.name_scope`



Defined in [`python/framework/ops.py`](/code/stable/tensorflow/python/framework/ops.py).

<!-- Placeholder for "Used in" -->

This context manager pushes a name scope, which will make the name of all
operations added within it have a prefix.

For example, to define a new Python op called `my_op`:

```python
def my_op(a, b, c, name=None):
  with tf.name_scope("MyOp") as scope:
    a = tf.convert_to_tensor(a, name="a")
    b = tf.convert_to_tensor(b, name="b")
    c = tf.convert_to_tensor(c, name="c")
    # Define some computation that uses `a`, `b`, and `c`.
    return foo_op(..., name=scope)
```

When executed, the Tensors `a`, `b`, `c`, will have names `MyOp/a`, `MyOp/b`,
and `MyOp/c`.

If the scope name already exists, the name will be made unique by appending
`_n`. For example, calling `my_op` the second time will generate `MyOp_1/a`,
etc.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(name)
```

Initialize the context manager.


#### Args:


* <b>`name`</b>: The prefix to use on all names created within the name scope.


#### Raises:


* <b>`ValueError`</b>: If name is None, or not a string.



## Properties

<h3 id="name"><code>name</code></h3>






## Methods

<h3 id="__enter__"><code>__enter__</code></h3>

``` python
__enter__()
```

Start the scope block.


#### Returns:

The scope name.



#### Raises:


* <b>`ValueError`</b>: if neither `name` nor `default_name` is provided
  but `values` are.

<h3 id="__exit__"><code>__exit__</code></h3>

``` python
__exit__(
    type_arg,
    value_arg,
    traceback_arg
)
```







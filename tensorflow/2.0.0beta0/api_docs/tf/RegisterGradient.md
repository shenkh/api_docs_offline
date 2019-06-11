<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.RegisterGradient" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="__init__"/>
</div>

# tf.RegisterGradient

## Class `RegisterGradient`

A decorator for registering the gradient function for an op type.



### Aliases:

* Class `tf.RegisterGradient`
* Class `tf.compat.v1.RegisterGradient`
* Class `tf.compat.v2.RegisterGradient`



Defined in [`python/framework/ops.py`](/code/stable/tensorflow/python/framework/ops.py).

<!-- Placeholder for "Used in" -->

This decorator is only used when defining a new op type. For an op
with `m` inputs and `n` outputs, the gradient function is a function
that takes the original `Operation` and `n` `Tensor` objects
(representing the gradients with respect to each output of the op),
and returns `m` `Tensor` objects (representing the partial gradients
with respect to each input of the op).

For example, assuming that operations of type `"Sub"` take two
inputs `x` and `y`, and return a single output `x - y`, the
following gradient function would be registered:

```python
@tf.RegisterGradient("Sub")
def _sub_grad(unused_op, grad):
  return grad, tf.negative(grad)
```

The decorator argument `op_type` is the string type of an
operation. This corresponds to the `OpDef.name` field for the proto
that defines the operation.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(op_type)
```

Creates a new decorator with `op_type` as the Operation type.


#### Args:


* <b>`op_type`</b>: The string type of an operation. This corresponds to the
  `OpDef.name` field for the proto that defines the operation.



## Methods

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(f)
```

Registers the function `f` as gradient function for `op_type`.





<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.layers.rev_block" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.layers.rev_block

``` python
tf.contrib.layers.rev_block(
    x1,
    x2,
    f,
    g,
    num_layers=1,
    f_side_input=None,
    g_side_input=None,
    is_training=True
)
```



Defined in [`tensorflow/contrib/layers/python/layers/rev_block_lib.py`](/code/stable/tensorflow/contrib/layers/python/layers/rev_block_lib.py).

A block of reversible residual layers.

A reversible residual layer is defined as:

```
y1 = x1 + f(x2, f_side_input)
y2 = x2 + g(y1, g_side_input)
```

A reversible residual block, defined here, is a series of reversible residual
layers.

Limitations:
* f and g must not close over any Tensors; all side inputs to f and g should
  be passed in with f_side_input and g_side_input which will be forwarded to
  f and g.
* f and g must not change the dimensionality of their inputs in order for the
  addition in the equations above to work.

#### Args:

* <b>`x1`</b>: a float Tensor.
* <b>`x2`</b>: a float Tensor.
* <b>`f`</b>: a function, (Tensor) -> (Tensor) (or list of such of length num_layers).
    Should not change the shape of the Tensor. Can make calls to get_variable.
    See f_side_input if there are side inputs.
* <b>`g`</b>: a function, (Tensor) -> (Tensor) (or list of such of length num_layers).
    Should not change the shape of the Tensor. Can make calls to get_variable.
    See g_side_input if there are side inputs.
* <b>`num_layers`</b>: int, number of reversible residual layers. Each layer will
    apply f and g according to the equations above, with new variables in each
    layer.
* <b>`f_side_input`</b>: list of Tensors, side input to f. If not None, signature of f
    should be (Tensor, list<Tensor>) -> (Tensor).
* <b>`g_side_input`</b>: list of Tensors, side input to g. If not None, signature of g
    should be (Tensor, list<Tensor>) -> (Tensor).
* <b>`is_training`</b>: bool, whether to actually use the efficient backprop codepath.


#### Returns:

y1, y2: tuple of float Tensors.
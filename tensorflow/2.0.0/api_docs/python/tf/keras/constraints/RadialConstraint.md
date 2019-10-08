<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.constraints.RadialConstraint" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__call__"/>
<meta itemprop="property" content="get_config"/>
</div>

# tf.keras.constraints.RadialConstraint

## Class `RadialConstraint`

Inherits From: [`Constraint`](../../../tf/keras/constraints/Constraint.md)

### Aliases:

* Class `tf.keras.constraints.RadialConstraint`
* Class `tf.keras.constraints.radial_constraint`



Defined in [`tensorflow/python/keras/constraints.py`](/code/stable/tensorflow/python/keras/constraints.py).

Constrains `Conv2D` kernel weights to be the same for each radius.

For example, the desired output for the following 4-by-4 kernel::

```
    kernel = [[v_00, v_01, v_02, v_03],
              [v_10, v_11, v_12, v_13],
              [v_20, v_21, v_22, v_23],
              [v_30, v_31, v_32, v_33]]
```

is this::

```
    kernel = [[v_11, v_11, v_11, v_11],
              [v_11, v_33, v_33, v_11],
              [v_11, v_33, v_33, v_11],
              [v_11, v_11, v_11, v_11]]
```

This constraint can be applied to any `Conv2D` layer version, including
`Conv2DTranspose` and `SeparableConv2D`, and with either `"channels_last"` or
`"channels_first"` data format. The method assumes the weight tensor is of
shape `(rows, cols, input_depth, output_depth)`.

## Methods

<h3 id="__call__"><code>__call__</code></h3>

``` python
__call__(w)
```

Call self as a function.

<h3 id="get_config"><code>get_config</code></h3>

``` python
get_config()
```






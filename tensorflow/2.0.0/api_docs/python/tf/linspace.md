<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.linspace" />
<meta itemprop="path" content="Stable" />
</div>

# tf.linspace

``` python
tf.linspace(
    start,
    stop,
    num,
    name=None
)
```



Defined in generated file: `tensorflow/python/ops/gen_math_ops.py`.

Generates values in an interval.

A sequence of `num` evenly-spaced values are generated beginning at `start`.
If `num > 1`, the values in the sequence increase by `stop - start / num - 1`,
so that the last one is exactly `stop`.

For example:

```
tf.linspace(10.0, 12.0, 3, name="linspace") => [ 10.0  11.0  12.0]
```

#### Args:

* <b>`start`</b>: A `Tensor`. Must be one of the following types: `bfloat16`, `float32`, `float64`.
    0-D tensor. First entry in the range.
* <b>`stop`</b>: A `Tensor`. Must have the same type as `start`.
    0-D tensor. Last entry in the range.
* <b>`num`</b>: A `Tensor`. Must be one of the following types: `int32`, `int64`.
    0-D tensor. Number of values to generate.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

A `Tensor`. Has the same type as `start`.
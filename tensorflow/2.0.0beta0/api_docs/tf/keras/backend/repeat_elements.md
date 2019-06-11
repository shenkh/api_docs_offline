<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.repeat_elements" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.repeat_elements

Repeats the elements of a tensor along an axis, like `np.repeat`.

### Aliases:

* `tf.compat.v1.keras.backend.repeat_elements`
* `tf.compat.v2.keras.backend.repeat_elements`
* `tf.keras.backend.repeat_elements`

``` python
tf.keras.backend.repeat_elements(
    x,
    rep,
    axis
)
```



Defined in [`python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

<!-- Placeholder for "Used in" -->

If `x` has shape `(s1, s2, s3)` and `axis` is `1`, the output
will have shape `(s1, s2 * rep, s3)`.

#### Arguments:


* <b>`x`</b>: Tensor or variable.
* <b>`rep`</b>: Python integer, number of times to repeat.
* <b>`axis`</b>: Axis along which to repeat.


#### Returns:

A tensor.

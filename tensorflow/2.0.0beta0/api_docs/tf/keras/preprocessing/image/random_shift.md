<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.preprocessing.image.random_shift" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.preprocessing.image.random_shift

Performs a random spatial shift of a Numpy image tensor.

### Aliases:

* `tf.compat.v1.keras.preprocessing.image.random_shift`
* `tf.compat.v2.keras.preprocessing.image.random_shift`
* `tf.keras.preprocessing.image.random_shift`

``` python
tf.keras.preprocessing.image.random_shift(
    x,
    wrg,
    hrg,
    row_axis=1,
    col_axis=2,
    channel_axis=0,
    fill_mode='nearest',
    cval=0.0,
    interpolation_order=1
)
```

<!-- Placeholder for "Used in" -->

# Arguments
    x: Input tensor. Must be 3D.
    wrg: Width shift range, as a float fraction of the width.
    hrg: Height shift range, as a float fraction of the height.
    row_axis: Index of axis for rows in the input tensor.
    col_axis: Index of axis for columns in the input tensor.
    channel_axis: Index of axis for channels in the input tensor.
    fill_mode: Points outside the boundaries of the input
        are filled according to the given mode
        (one of `{'constant', 'nearest', 'reflect', 'wrap'}`).
    cval: Value used for points outside the boundaries
        of the input if `mode='constant'`.
    interpolation_order: int, order of spline interpolation.
        see `ndimage.interpolation.affine_transform`

# Returns
    Shifted Numpy image tensor.
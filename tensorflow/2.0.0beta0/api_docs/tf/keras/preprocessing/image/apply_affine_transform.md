<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.preprocessing.image.apply_affine_transform" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.preprocessing.image.apply_affine_transform

Applies an affine transformation specified by the parameters given.

### Aliases:

* `tf.compat.v1.keras.preprocessing.image.apply_affine_transform`
* `tf.compat.v2.keras.preprocessing.image.apply_affine_transform`
* `tf.keras.preprocessing.image.apply_affine_transform`

``` python
tf.keras.preprocessing.image.apply_affine_transform(
    x,
    theta=0,
    tx=0,
    ty=0,
    shear=0,
    zx=1,
    zy=1,
    row_axis=0,
    col_axis=1,
    channel_axis=2,
    fill_mode='nearest',
    cval=0.0,
    order=1
)
```

<!-- Placeholder for "Used in" -->

# Arguments
    x: 2D numpy array, single image.
    theta: Rotation angle in degrees.
    tx: Width shift.
    ty: Heigh shift.
    shear: Shear angle in degrees.
    zx: Zoom in x direction.
    zy: Zoom in y direction
    row_axis: Index of axis for rows in the input image.
    col_axis: Index of axis for columns in the input image.
    channel_axis: Index of axis for channels in the input image.
    fill_mode: Points outside the boundaries of the input
        are filled according to the given mode
        (one of `{'constant', 'nearest', 'reflect', 'wrap'}`).
    cval: Value used for points outside the boundaries
        of the input if `mode='constant'`.
    order: int, order of interpolation

# Returns
    The transformed version of the input.
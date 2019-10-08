<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.signal.overlap_and_add" />
<meta itemprop="path" content="Stable" />
</div>

# tf.signal.overlap_and_add

``` python
tf.signal.overlap_and_add(
    signal,
    frame_step,
    name=None
)
```



Defined in [`tensorflow/python/ops/signal/reconstruction_ops.py`](/code/stable/tensorflow/python/ops/signal/reconstruction_ops.py).

Reconstructs a signal from a framed representation.

Adds potentially overlapping frames of a signal with shape
`[..., frames, frame_length]`, offsetting subsequent frames by `frame_step`.
The resulting tensor has shape `[..., output_size]` where

    output_size = (frames - 1) * frame_step + frame_length

#### Args:

* <b>`signal`</b>: A [..., frames, frame_length] `Tensor`. All dimensions may be
    unknown, and rank must be at least 2.
* <b>`frame_step`</b>: An integer or scalar `Tensor` denoting overlap offsets. Must be
    less than or equal to `frame_length`.
* <b>`name`</b>: An optional name for the operation.


#### Returns:

A `Tensor` with shape `[..., output_size]` containing the overlap-added
frames of `signal`'s inner-most two dimensions.


#### Raises:

* <b>`ValueError`</b>: If `signal`'s rank is less than 2, or `frame_step` is not a
    scalar integer.
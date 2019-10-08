<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.summary.audio" />
<meta itemprop="path" content="Stable" />
</div>

# tf.summary.audio

``` python
tf.summary.audio(
    name,
    data,
    sample_rate,
    step=None,
    max_outputs=3,
    encoding=None,
    description=None
)
```

Write an audio summary.

#### Arguments:

* <b>`name`</b>: A name for this summary. The summary tag used for TensorBoard will
    be this name prefixed by any active name scopes.
* <b>`data`</b>: A `Tensor` representing audio data with shape `[k, t, c]`,
    where `k` is the number of audio clips, `t` is the number of
    frames, and `c` is the number of channels. Elements should be
    floating-point values in `[-1.0, 1.0]`. Any of the dimensions may
    be statically unknown (i.e., `None`).
* <b>`sample_rate`</b>: An `int` or rank-0 `int32` `Tensor` that represents the
    sample rate, in Hz. Must be positive.
* <b>`step`</b>: Explicit `int64`-castable monotonic step value for this summary. If
    omitted, this defaults to `tf.summary.experimental.get_step()`, which must
    not be None.
* <b>`max_outputs`</b>: Optional `int` or rank-0 integer `Tensor`. At most this
    many audio clips will be emitted at each step. When more than
    `max_outputs` many clips are provided, the first `max_outputs`
    many clips will be used and the rest silently discarded.
* <b>`encoding`</b>: Optional constant `str` for the desired encoding. Only "wav"
    is currently supported, but this is not guaranteed to remain the
    default, so if you want "wav" in particular, set this explicitly.
* <b>`description`</b>: Optional long-form description for this summary, as a
    constant `str`. Markdown is supported. Defaults to empty.


#### Returns:

True on success, or false if no summary was emitted because no default
summary writer was available.


#### Raises:

* <b>`ValueError`</b>: if a default writer exists, but no step was provided and
    `tf.summary.experimental.get_step()` is None.
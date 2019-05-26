<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.eager.nan_callback" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.eager.nan_callback

``` python
tf.contrib.eager.nan_callback(
    op_type,
    inputs,
    attrs,
    outputs,
    op_name,
    action=_DEFAULT_CALLBACK_ACTION
)
```



Defined in [`tensorflow/python/eager/execution_callbacks.py`](https://www.tensorflow.org/code/tensorflow/python/eager/execution_callbacks.py).

A specialization of `inf_nan_callback` that checks for `nan`s only.
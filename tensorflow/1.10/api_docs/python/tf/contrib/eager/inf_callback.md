<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.eager.inf_callback" />
</div>

# tf.contrib.eager.inf_callback

``` python
tf.contrib.eager.inf_callback(
    op_type,
    inputs,
    attrs,
    outputs,
    op_name,
    action=_DEFAULT_CALLBACK_ACTION
)
```



Defined in [`tensorflow/python/eager/execution_callbacks.py`](https://www.tensorflow.org/code/tensorflow/python/eager/execution_callbacks.py).

A specialization of `inf_nan_callback` that checks for `inf`s only.
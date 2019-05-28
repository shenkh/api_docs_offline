<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.logging.log_if" />
</div>

# tf.logging.log_if

``` python
tf.logging.log_if(
    level,
    msg,
    condition,
    *args
)
```



Defined in [`tensorflow/python/platform/tf_logging.py`](https://www.tensorflow.org/code/tensorflow/python/platform/tf_logging.py).

Log 'msg % args' at level 'level' only if condition is fulfilled.
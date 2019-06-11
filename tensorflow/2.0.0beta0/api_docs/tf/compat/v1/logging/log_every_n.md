<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.logging.log_every_n" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.logging.log_every_n

Log 'msg % args' at level 'level' once per 'n' times.

``` python
tf.compat.v1.logging.log_every_n(
    level,
    msg,
    n,
    *args
)
```



Defined in [`python/platform/tf_logging.py`](/code/stable/tensorflow/python/platform/tf_logging.py).

<!-- Placeholder for "Used in" -->

Logs the 1st call, (N+1)st call, (2N+1)st call,  etc.
Not threadsafe.

#### Args:


* <b>`level`</b>: The level at which to log.
* <b>`msg`</b>: The message to be logged.
* <b>`n`</b>: The number of times this should be called before it is logged.
* <b>`*args`</b>: The args to be substituted into the msg.
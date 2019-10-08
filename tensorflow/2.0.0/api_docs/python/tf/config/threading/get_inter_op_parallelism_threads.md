<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.threading.get_inter_op_parallelism_threads" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.threading.get_inter_op_parallelism_threads

``` python
tf.config.threading.get_inter_op_parallelism_threads()
```



Defined in [`tensorflow/python/framework/config.py`](/code/stable/tensorflow/python/framework/config.py).

Get number of threads used for parallelism between independent operations.

Determines the number of threads used by independent non-blocking operations.
0 means the system picks an appropriate number.

#### Returns:

Number of parallel threads
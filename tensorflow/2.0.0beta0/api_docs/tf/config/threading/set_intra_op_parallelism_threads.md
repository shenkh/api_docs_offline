<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.threading.set_intra_op_parallelism_threads" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.threading.set_intra_op_parallelism_threads

Set number of threads used within an individual op for parallelism.

### Aliases:

* `tf.compat.v1.config.threading.set_intra_op_parallelism_threads`
* `tf.compat.v2.config.threading.set_intra_op_parallelism_threads`
* `tf.config.threading.set_intra_op_parallelism_threads`

``` python
tf.config.threading.set_intra_op_parallelism_threads(num_threads)
```



Defined in [`python/framework/config.py`](/code/stable/tensorflow/python/framework/config.py).

<!-- Placeholder for "Used in" -->

Certain operations like matrix multiplication and reductions can utilize
parallel threads for speed ups. A value of 0 means the system picks an
appropriate number.

#### Args:


* <b>`num_threads`</b>: Number of parallel threads
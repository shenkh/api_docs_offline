<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.summary.record_summaries_every_n_global_steps" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.summary.record_summaries_every_n_global_steps

``` python
tf.contrib.summary.record_summaries_every_n_global_steps(
    n,
    global_step=None
)
```



Defined in [`tensorflow/python/ops/summary_ops_v2.py`](/code/stable/tensorflow/python/ops/summary_ops_v2.py).

Sets the should_record_summaries Tensor to true if global_step % n == 0.
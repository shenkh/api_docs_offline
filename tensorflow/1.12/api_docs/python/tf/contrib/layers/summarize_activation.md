<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.layers.summarize_activation" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.layers.summarize_activation

``` python
tf.contrib.layers.summarize_activation(op)
```



Defined in [`tensorflow/contrib/layers/python/layers/summaries.py`](/code/stable/tensorflow/contrib/layers/python/layers/summaries.py).

Summarize an activation.

This applies the given activation and adds useful summaries specific to the
activation.

#### Args:

* <b>`op`</b>: The tensor to summarize (assumed to be a layer activation).

#### Returns:

The summary op created to summarize `op`.
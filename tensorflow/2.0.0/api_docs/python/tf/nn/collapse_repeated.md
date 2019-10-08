<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.collapse_repeated" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nn.collapse_repeated

``` python
tf.nn.collapse_repeated(
    labels,
    seq_length,
    name=None
)
```



Defined in [`tensorflow/python/ops/ctc_ops.py`](/code/stable/tensorflow/python/ops/ctc_ops.py).

Merge repeated labels into single labels.

#### Args:

* <b>`labels`</b>: Tensor of shape [batch, max value in seq_length]
* <b>`seq_length`</b>: Tensor of shape [batch], sequence length of each batch element.
* <b>`name`</b>: A name for this `Op`. Defaults to "collapse_repeated_labels".


#### Returns:

A tuple `(collapsed_labels, new_seq_length)` where

* <b>`collapsed_labels`</b>: Tensor of shape [batch, max_seq_length] with repeated
  labels collapsed and padded to max_seq_length, eg:
  `[[A, A, B, B, A], [A, B, C, D, E]] => [[A, B, A, 0, 0], [A, B, C, D, E]]`

* <b>`new_seq_length`</b>: int tensor of shape [batch] with new sequence lengths.
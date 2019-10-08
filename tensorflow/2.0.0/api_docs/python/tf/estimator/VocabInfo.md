<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.estimator.VocabInfo" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="new_vocab"/>
<meta itemprop="property" content="new_vocab_size"/>
<meta itemprop="property" content="num_oov_buckets"/>
<meta itemprop="property" content="old_vocab"/>
<meta itemprop="property" content="old_vocab_size"/>
<meta itemprop="property" content="backup_initializer"/>
<meta itemprop="property" content="axis"/>
<meta itemprop="property" content="__new__"/>
</div>

# tf.estimator.VocabInfo

## Class `VocabInfo`





Defined in [`tensorflow/python/training/warm_starting_util.py`](/code/stable/tensorflow/python/training/warm_starting_util.py).

Vocabulary information for warm-starting.

  See <a href="../../tf/estimator/WarmStartSettings.md"><code>tf.estimator.WarmStartSettings</code></a> for examples of using
  VocabInfo to warm-start.

  Args:
    new_vocab: [Required] A path to the new vocabulary file (used with the model
      to be trained).
    new_vocab_size: [Required] An integer indicating how many entries of the new
      vocabulary will used in training.
    num_oov_buckets: [Required] An integer indicating how many OOV buckets are
      associated with the vocabulary.
    old_vocab: [Required] A path to the old vocabulary file (used with the
      checkpoint to be warm-started from).
    old_vocab_size: [Optional] An integer indicating how many entries of the old
      vocabulary were used in the creation of the checkpoint. If not provided,
      the entire old vocabulary will be used.
    backup_initializer: [Optional] A variable initializer used for variables
      corresponding to new vocabulary entries and OOV. If not provided, these
      entries will be zero-initialized.
    axis: [Optional] Denotes what axis the vocabulary corresponds to.  The
      default, 0, corresponds to the most common use case (embeddings or
      linear weights for binary classification / regression).  An axis of 1
      could be used for warm-starting output layers with class vocabularies.

  Returns:
    A `VocabInfo` which represents the vocabulary information for warm-starting.

  Raises:
    ValueError: `axis` is neither 0 or 1.

      Example Usage:
```python
      embeddings_vocab_info = tf.VocabInfo(
          new_vocab='embeddings_vocab',
          new_vocab_size=100,
          num_oov_buckets=1,
          old_vocab='pretrained_embeddings_vocab',
          old_vocab_size=10000,
          backup_initializer=tf.compat.v1.truncated_normal_initializer(
              mean=0.0, stddev=(1 / math.sqrt(embedding_dim))),
          axis=0)

      softmax_output_layer_kernel_vocab_info = tf.VocabInfo(
          new_vocab='class_vocab',
          new_vocab_size=5,
          num_oov_buckets=0,  # No OOV for classes.
          old_vocab='old_class_vocab',
          old_vocab_size=8,
          backup_initializer=tf.compat.v1.glorot_uniform_initializer(),
          axis=1)

      softmax_output_layer_bias_vocab_info = tf.VocabInfo(
          new_vocab='class_vocab',
          new_vocab_size=5,
          num_oov_buckets=0,  # No OOV for classes.
          old_vocab='old_class_vocab',
          old_vocab_size=8,
          backup_initializer=tf.compat.v1.zeros_initializer(),
          axis=0)

      #Currently, only axis=0 and axis=1 are supported.
  ```
  

<h2 id="__new__"><code>__new__</code></h2>

``` python
@staticmethod
__new__(
    cls,
    new_vocab,
    new_vocab_size,
    num_oov_buckets,
    old_vocab,
    old_vocab_size=-1,
    backup_initializer=None,
    axis=0
)
```

Create new instance of VocabInfo(new_vocab, new_vocab_size, num_oov_buckets, old_vocab, old_vocab_size, backup_initializer, axis)



## Properties

<h3 id="new_vocab"><code>new_vocab</code></h3>



<h3 id="new_vocab_size"><code>new_vocab_size</code></h3>



<h3 id="num_oov_buckets"><code>num_oov_buckets</code></h3>



<h3 id="old_vocab"><code>old_vocab</code></h3>



<h3 id="old_vocab_size"><code>old_vocab_size</code></h3>



<h3 id="backup_initializer"><code>backup_initializer</code></h3>



<h3 id="axis"><code>axis</code></h3>






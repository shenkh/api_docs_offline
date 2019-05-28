# Training (contrib)
[TOC]

Training and input utilities.

<h2 id="Splitting_sequence_inputs_into_minibatches_with_state_saving">Splitting sequence inputs into minibatches with state saving</h2>

Use <a href="../../api_docs/python/tf/contrib/training/SequenceQueueingStateSaver.md"><code>tf.contrib.training.SequenceQueueingStateSaver</code></a> or
its wrapper <a href="../../api_docs/python/tf/contrib/training/batch_sequences_with_states.md"><code>tf.contrib.training.batch_sequences_with_states</code></a> if
you have input data with a dynamic primary time / frame count axis which
you'd like to convert into fixed size segments during minibatching, and would
like to store state in the forward direction across segments of an example.

*   <a href="../../api_docs/python/tf/contrib/training/batch_sequences_with_states.md"><code>tf.contrib.training.batch_sequences_with_states</code></a>
*   <a href="../../api_docs/python/tf/contrib/training/NextQueuedSequenceBatch.md"><code>tf.contrib.training.NextQueuedSequenceBatch</code></a>
*   <a href="../../api_docs/python/tf/contrib/training/SequenceQueueingStateSaver.md"><code>tf.contrib.training.SequenceQueueingStateSaver</code></a>


<h2 id="Online_data_resampling">Online data resampling</h2>

To resample data with replacement on a per-example basis, use
<a href="../../api_docs/python/tf/contrib/training/rejection_sample.md"><code>tf.contrib.training.rejection_sample</code></a> or
<a href="../../api_docs/python/tf/contrib/training/resample_at_rate.md"><code>tf.contrib.training.resample_at_rate</code></a>. For `rejection_sample`, provide
a boolean Tensor describing whether to accept or reject. Resulting batch sizes
are always the same. For `resample_at_rate`, provide the desired rate for each
example. Resulting batch sizes may vary. If you wish to specify relative
rates, rather than absolute ones, use <a href="../../api_docs/python/tf/contrib/training/weighted_resample.md"><code>tf.contrib.training.weighted_resample</code></a>
(which also returns the actual resampling rate used for each output example).

Use <a href="../../api_docs/python/tf/contrib/training/stratified_sample.md"><code>tf.contrib.training.stratified_sample</code></a> to resample without replacement
from the data to achieve a desired mix of class proportions that the Tensorflow
graph sees. For instance, if you have a binary classification dataset that is
99.9% class 1, a common approach is to resample from the data so that the data
is more balanced.

*   <a href="../../api_docs/python/tf/contrib/training/rejection_sample.md"><code>tf.contrib.training.rejection_sample</code></a>
*   <a href="../../api_docs/python/tf/contrib/training/resample_at_rate.md"><code>tf.contrib.training.resample_at_rate</code></a>
*   <a href="../../api_docs/python/tf/contrib/training/stratified_sample.md"><code>tf.contrib.training.stratified_sample</code></a>
*   <a href="../../api_docs/python/tf/contrib/training/weighted_resample.md"><code>tf.contrib.training.weighted_resample</code></a>

<h2 id="Bucketing">Bucketing</h2>

Use <a href="../../api_docs/python/tf/contrib/training/bucket.md"><code>tf.contrib.training.bucket</code></a> or
<a href="../../api_docs/python/tf/contrib/training/bucket_by_sequence_length.md"><code>tf.contrib.training.bucket_by_sequence_length</code></a> to stratify
minibatches into groups ("buckets").  Use `bucket_by_sequence_length`
with the argument `dynamic_pad=True` to receive minibatches of similarly
sized sequences for efficient training via `dynamic_rnn`.

*   <a href="../../api_docs/python/tf/contrib/training/bucket.md"><code>tf.contrib.training.bucket</code></a>
*   <a href="../../api_docs/python/tf/contrib/training/bucket_by_sequence_length.md"><code>tf.contrib.training.bucket_by_sequence_length</code></a>

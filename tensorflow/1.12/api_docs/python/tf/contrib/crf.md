<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.crf" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.contrib.crf



Defined in [`tensorflow/contrib/crf/__init__.py`](/code/stable/tensorflow/contrib/crf/__init__.py).

Linear-chain CRF layer.

See the [CRF](https://tensorflow.org/api_guides/python/contrib.crf) guide.


## Classes

[`class CrfDecodeBackwardRnnCell`](../../tf/contrib/crf/CrfDecodeBackwardRnnCell.md): Computes backward decoding in a linear-chain CRF.

[`class CrfDecodeForwardRnnCell`](../../tf/contrib/crf/CrfDecodeForwardRnnCell.md): Computes the forward decoding in a linear-chain CRF.

[`class CrfForwardRnnCell`](../../tf/contrib/crf/CrfForwardRnnCell.md): Computes the alpha values in a linear-chain CRF.

## Functions

[`crf_binary_score(...)`](../../tf/contrib/crf/crf_binary_score.md): Computes the binary scores of tag sequences.

[`crf_decode(...)`](../../tf/contrib/crf/crf_decode.md): Decode the highest scoring sequence of tags in TensorFlow.

[`crf_log_likelihood(...)`](../../tf/contrib/crf/crf_log_likelihood.md): Computes the log-likelihood of tag sequences in a CRF.

[`crf_log_norm(...)`](../../tf/contrib/crf/crf_log_norm.md): Computes the normalization for a CRF.

[`crf_multitag_sequence_score(...)`](../../tf/contrib/crf/crf_multitag_sequence_score.md): Computes the unnormalized score of all tag sequences matching tag_bitmap.

[`crf_sequence_score(...)`](../../tf/contrib/crf/crf_sequence_score.md): Computes the unnormalized score for a tag sequence.

[`crf_unary_score(...)`](../../tf/contrib/crf/crf_unary_score.md): Computes the unary scores of tag sequences.

[`viterbi_decode(...)`](../../tf/contrib/crf/viterbi_decode.md): Decode the highest scoring sequence of tags outside of TensorFlow.


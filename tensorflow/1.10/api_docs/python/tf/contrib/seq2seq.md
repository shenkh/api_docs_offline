<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.seq2seq" />
</div>

# Module: tf.contrib.seq2seq



Defined in [`tensorflow/contrib/seq2seq/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/seq2seq/__init__.py).

Ops for building neural network seq2seq decoders and losses.

See the <a href="../../../../api_guides/python/contrib.seq2seq.md">Seq2seq Library (contrib)</a> guide.

## Classes

[`class AttentionMechanism`](../../tf/contrib/seq2seq/AttentionMechanism.md)

[`class AttentionWrapper`](../../tf/contrib/seq2seq/AttentionWrapper.md): Wraps another `RNNCell` with attention.

[`class AttentionWrapperState`](../../tf/contrib/seq2seq/AttentionWrapperState.md): `namedtuple` storing the state of a `AttentionWrapper`.

[`class BahdanauAttention`](../../tf/contrib/seq2seq/BahdanauAttention.md): Implements Bahdanau-style (additive) attention.

[`class BahdanauMonotonicAttention`](../../tf/contrib/seq2seq/BahdanauMonotonicAttention.md): Monotonic attention mechanism with Bahadanau-style energy function.

[`class BasicDecoder`](../../tf/contrib/seq2seq/BasicDecoder.md): Basic sampling decoder.

[`class BasicDecoderOutput`](../../tf/contrib/seq2seq/BasicDecoderOutput.md): BasicDecoderOutput(rnn_output, sample_id)

[`class BeamSearchDecoder`](../../tf/contrib/seq2seq/BeamSearchDecoder.md): BeamSearch sampling decoder.

[`class BeamSearchDecoderOutput`](../../tf/contrib/seq2seq/BeamSearchDecoderOutput.md): BeamSearchDecoderOutput(scores, predicted_ids, parent_ids)

[`class BeamSearchDecoderState`](../../tf/contrib/seq2seq/BeamSearchDecoderState.md): BeamSearchDecoderState(cell_state, log_probs, finished, lengths)

[`class CustomHelper`](../../tf/contrib/seq2seq/CustomHelper.md): Base abstract class that allows the user to customize sampling.

[`class Decoder`](../../tf/contrib/seq2seq/Decoder.md): An RNN Decoder abstract interface object.

[`class FinalBeamSearchDecoderOutput`](../../tf/contrib/seq2seq/FinalBeamSearchDecoderOutput.md): Final outputs returned by the beam search after all decoding is finished.

[`class GreedyEmbeddingHelper`](../../tf/contrib/seq2seq/GreedyEmbeddingHelper.md): A helper for use during inference.

[`class Helper`](../../tf/contrib/seq2seq/Helper.md): Interface for implementing sampling in seq2seq decoders.

[`class InferenceHelper`](../../tf/contrib/seq2seq/InferenceHelper.md): A helper to use during inference with a custom sampling function.

[`class LuongAttention`](../../tf/contrib/seq2seq/LuongAttention.md): Implements Luong-style (multiplicative) attention scoring.

[`class LuongMonotonicAttention`](../../tf/contrib/seq2seq/LuongMonotonicAttention.md): Monotonic attention mechanism with Luong-style energy function.

[`class SampleEmbeddingHelper`](../../tf/contrib/seq2seq/SampleEmbeddingHelper.md): A helper for use during inference.

[`class ScheduledEmbeddingTrainingHelper`](../../tf/contrib/seq2seq/ScheduledEmbeddingTrainingHelper.md): A training helper that adds scheduled sampling.

[`class ScheduledOutputTrainingHelper`](../../tf/contrib/seq2seq/ScheduledOutputTrainingHelper.md): A training helper that adds scheduled sampling directly to outputs.

[`class TrainingHelper`](../../tf/contrib/seq2seq/TrainingHelper.md): A helper for use during training.  Only reads inputs.

## Functions

[`dynamic_decode(...)`](../../tf/contrib/seq2seq/dynamic_decode.md): Perform dynamic decoding with `decoder`.

[`gather_tree(...)`](../../tf/contrib/seq2seq/gather_tree.md): Calculates the full beams from the per-step ids and parent beam ids.

[`hardmax(...)`](../../tf/contrib/seq2seq/hardmax.md): Returns batched one-hot vectors.

[`monotonic_attention(...)`](../../tf/contrib/seq2seq/monotonic_attention.md): Compute monotonic attention distribution from choosing probabilities.

[`safe_cumprod(...)`](../../tf/contrib/seq2seq/safe_cumprod.md): Computes cumprod of x in logspace using cumsum to avoid underflow.

[`sequence_loss(...)`](../../tf/contrib/seq2seq/sequence_loss.md): Weighted cross-entropy loss for a sequence of logits.

[`tile_batch(...)`](../../tf/contrib/seq2seq/tile_batch.md): Tile the batch dimension of a (possibly nested structure of) tensor(s) t.


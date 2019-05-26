# Seq2seq Library (contrib)
[TOC]

Module for constructing seq2seq models and dynamic decoding.  Builds on top of
libraries in <a href="../../api_docs/python/tf/contrib/rnn.md"><code>tf.contrib.rnn</code></a>.

This library is composed of two primary components:

*   New attention wrappers for <a href="../../api_docs/python/tf/nn/rnn_cell/RNNCell.md"><code>tf.contrib.rnn.RNNCell</code></a> objects.
*   A new object-oriented dynamic decoding framework.

<h2 id="Attention">Attention</h2>

Attention wrappers are `RNNCell` objects that wrap other `RNNCell` objects and
implement attention.  The form of attention is determined by a subclass of
<a href="../../api_docs/python/tf/contrib/seq2seq/AttentionMechanism.md"><code>tf.contrib.seq2seq.AttentionMechanism</code></a>.  These subclasses describe the form
of attention (e.g. additive vs. multiplicative) to use when creating the
wrapper.  An instance of an `AttentionMechanism` is constructed with a
`memory` tensor, from which lookup keys and values tensors are created.

### Attention Mechanisms

The two basic attention mechanisms are:

*   <a href="../../api_docs/python/tf/contrib/seq2seq/BahdanauAttention.md"><code>tf.contrib.seq2seq.BahdanauAttention</code></a> (additive attention,
    [ref.](https://arxiv.org/abs/1409.0473))
*   <a href="../../api_docs/python/tf/contrib/seq2seq/LuongAttention.md"><code>tf.contrib.seq2seq.LuongAttention</code></a> (multiplicative attention,
    [ref.](https://arxiv.org/abs/1508.04025))

The `memory` tensor passed the attention mechanism's constructor is expected to
be shaped `[batch_size, memory_max_time, memory_depth]`; and often an additional
`memory_sequence_length` vector is accepted.  If provided, the `memory`
tensors' rows are masked with zeros past their true sequence lengths.

Attention mechanisms also have a concept of depth, usually determined as a
construction parameter `num_units`.  For some kinds of attention (like
`BahdanauAttention`), both queries and memory are projected to tensors of depth
`num_units`.  For other kinds (like `LuongAttention`), `num_units` should match
the depth of the queries; and the `memory` tensor will be projected to this
depth.

### Attention Wrappers

The basic attention wrapper is <a href="../../api_docs/python/tf/contrib/seq2seq/AttentionWrapper.md"><code>tf.contrib.seq2seq.AttentionWrapper</code></a>.
This wrapper accepts an `RNNCell` instance, an instance of `AttentionMechanism`,
and an attention depth parameter (`attention_size`); as well as several
optional arguments that allow one to customize intermediate calculations.

At each time step, the basic calculation performed by this wrapper is:

```python
cell_inputs = concat([inputs, prev_state.attention], -1)
cell_output, next_cell_state = cell(cell_inputs, prev_state.cell_state)
score = attention_mechanism(cell_output)
alignments = softmax(score)
context = matmul(alignments, attention_mechanism.values)
attention = tf.layers.Dense(attention_size)(concat([cell_output, context], 1))
next_state = AttentionWrapperState(
  cell_state=next_cell_state,
  attention=attention)
output = attention
return output, next_state
```

In practice, a number of the intermediate calculations are configurable.
For example, the initial concatenation of `inputs` and `prev_state.attention`
can be replaced with another mixing function.  The function `softmax` can
be replaced with alternative options when calculating `alignments` from the
`score`.  Finally, the outputs returned by the wrapper can be configured to
be the value `cell_output` instead of `attention`.

The benefit of using a `AttentionWrapper` is that it plays nicely with
other wrappers and the dynamic decoder described below.  For example, one can
write:

```python
cell = tf.contrib.rnn.DeviceWrapper(LSTMCell(512), "/device:GPU:0")
attention_mechanism = tf.contrib.seq2seq.LuongAttention(512, encoder_outputs)
attn_cell = tf.contrib.seq2seq.AttentionWrapper(
  cell, attention_mechanism, attention_size=256)
attn_cell = tf.contrib.rnn.DeviceWrapper(attn_cell, "/device:GPU:1")
top_cell = tf.contrib.rnn.DeviceWrapper(LSTMCell(512), "/device:GPU:1")
multi_cell = MultiRNNCell([attn_cell, top_cell])
```

The `multi_rnn` cell will perform the bottom layer calculations on GPU 0;
attention calculations will be performed on GPU 1 and immediately passed
up to the top layer which is also calculated on GPU 1.  The attention is
also passed forward in time to the next time step and copied to GPU 0 for the
next time step of `cell`.  (*Note*: This is just an example of use,
not a suggested device partitioning strategy.)

<h2 id="Dynamic_Decoding">Dynamic Decoding</h2>

Example usage:

``` python
cell = # instance of RNNCell

if mode == "train":
  helper = tf.contrib.seq2seq.TrainingHelper(
    input=input_vectors,
    sequence_length=input_lengths)
elif mode == "infer":
  helper = tf.contrib.seq2seq.GreedyEmbeddingHelper(
      embedding=embedding,
      start_tokens=tf.tile([GO_SYMBOL], [batch_size]),
      end_token=END_SYMBOL)

decoder = tf.contrib.seq2seq.BasicDecoder(
    cell=cell,
    helper=helper,
    initial_state=cell.zero_state(batch_size, tf.float32))
outputs, _ = tf.contrib.seq2seq.dynamic_decode(
   decoder=decoder,
   output_time_major=False,
   impute_finished=True,
   maximum_iterations=20)
```

### Decoder base class and functions

*   <a href="../../api_docs/python/tf/contrib/seq2seq/Decoder.md"><code>tf.contrib.seq2seq.Decoder</code></a>
*   <a href="../../api_docs/python/tf/contrib/seq2seq/dynamic_decode.md"><code>tf.contrib.seq2seq.dynamic_decode</code></a>

### Basic Decoder

*   <a href="../../api_docs/python/tf/contrib/seq2seq/BasicDecoderOutput.md"><code>tf.contrib.seq2seq.BasicDecoderOutput</code></a>
*   <a href="../../api_docs/python/tf/contrib/seq2seq/BasicDecoder.md"><code>tf.contrib.seq2seq.BasicDecoder</code></a>

### Decoder Helpers

*   <a href="../../api_docs/python/tf/contrib/seq2seq/Helper.md"><code>tf.contrib.seq2seq.Helper</code></a>
*   <a href="../../api_docs/python/tf/contrib/seq2seq/CustomHelper.md"><code>tf.contrib.seq2seq.CustomHelper</code></a>
*   <a href="../../api_docs/python/tf/contrib/seq2seq/GreedyEmbeddingHelper.md"><code>tf.contrib.seq2seq.GreedyEmbeddingHelper</code></a>
*   <a href="../../api_docs/python/tf/contrib/seq2seq/ScheduledEmbeddingTrainingHelper.md"><code>tf.contrib.seq2seq.ScheduledEmbeddingTrainingHelper</code></a>
*   <a href="../../api_docs/python/tf/contrib/seq2seq/ScheduledOutputTrainingHelper.md"><code>tf.contrib.seq2seq.ScheduledOutputTrainingHelper</code></a>
*   <a href="../../api_docs/python/tf/contrib/seq2seq/TrainingHelper.md"><code>tf.contrib.seq2seq.TrainingHelper</code></a>

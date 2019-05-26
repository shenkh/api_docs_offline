<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.rnn" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.contrib.rnn



Defined in [`tensorflow/contrib/rnn/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/rnn/__init__.py).

RNN Cells and additional RNN operations.

See [Contrib RNN](https://tensorflow.org/api_guides/python/contrib.rnn) guide.

<!--From core-->

<!--Used to be in core, but kept in contrib.-->

<!--Created in contrib, eventual plans to move to core.-->

<!--RNNCell wrappers-->

<!--RNN functions-->

<!--RNN utilities-->

## Classes

[`class AttentionCellWrapper`](../../tf/contrib/rnn/AttentionCellWrapper.md): Basic attention cell wrapper.

[`class BasicLSTMCell`](../../tf/nn/rnn_cell/BasicLSTMCell.md): DEPRECATED: Please use <a href="../../tf/nn/rnn_cell/LSTMCell.md"><code>tf.nn.rnn_cell.LSTMCell</code></a> instead.

[`class BasicRNNCell`](../../tf/nn/rnn_cell/BasicRNNCell.md): The most basic RNN cell.

[`class BidirectionalGridLSTMCell`](../../tf/contrib/rnn/BidirectionalGridLSTMCell.md): Bidirectional GridLstm cell.

[`class CompiledWrapper`](../../tf/contrib/rnn/CompiledWrapper.md): Wraps step execution in an XLA JIT scope.

[`class Conv1DLSTMCell`](../../tf/contrib/rnn/Conv1DLSTMCell.md): 1D Convolutional LSTM recurrent network cell.

[`class Conv2DLSTMCell`](../../tf/contrib/rnn/Conv2DLSTMCell.md): 2D Convolutional LSTM recurrent network cell.

[`class Conv3DLSTMCell`](../../tf/contrib/rnn/Conv3DLSTMCell.md): 3D Convolutional LSTM recurrent network cell.

[`class ConvLSTMCell`](../../tf/contrib/rnn/ConvLSTMCell.md): Convolutional LSTM recurrent network cell.

[`class CoupledInputForgetGateLSTMCell`](../../tf/contrib/rnn/CoupledInputForgetGateLSTMCell.md): Long short-term memory unit (LSTM) recurrent network cell.

[`class DeviceWrapper`](../../tf/nn/rnn_cell/DeviceWrapper.md): Operator that ensures an RNNCell runs on a particular device.

[`class DropoutWrapper`](../../tf/nn/rnn_cell/DropoutWrapper.md): Operator adding dropout to inputs and outputs of the given cell.

[`class EmbeddingWrapper`](../../tf/contrib/rnn/EmbeddingWrapper.md): Operator adding input embedding to the given cell.

[`class FusedRNNCell`](../../tf/contrib/rnn/FusedRNNCell.md): Abstract object representing a fused RNN cell.

[`class FusedRNNCellAdaptor`](../../tf/contrib/rnn/FusedRNNCellAdaptor.md): This is an adaptor for RNNCell classes to be used with `FusedRNNCell`.

[`class GLSTMCell`](../../tf/contrib/rnn/GLSTMCell.md): Group LSTM cell (G-LSTM).

[`class GRUBlockCell`](../../tf/contrib/rnn/GRUBlockCell.md): Block GRU cell implementation.

[`class GRUBlockCellV2`](../../tf/contrib/rnn/GRUBlockCellV2.md): Temporary GRUBlockCell impl with a different variable naming scheme.

[`class GRUCell`](../../tf/nn/rnn_cell/GRUCell.md): Gated Recurrent Unit cell (cf. http://arxiv.org/abs/1406.1078).

[`class GridLSTMCell`](../../tf/contrib/rnn/GridLSTMCell.md): Grid Long short-term memory unit (LSTM) recurrent network cell.

[`class HighwayWrapper`](../../tf/contrib/rnn/HighwayWrapper.md): RNNCell wrapper that adds highway connection on cell input and output.

[`class IndRNNCell`](../../tf/contrib/rnn/IndRNNCell.md): Independently Recurrent Neural Network (IndRNN) cell

[`class IndyGRUCell`](../../tf/contrib/rnn/IndyGRUCell.md): Independently Gated Recurrent Unit cell.

[`class IndyLSTMCell`](../../tf/contrib/rnn/IndyLSTMCell.md): Basic IndyLSTM recurrent network cell.

[`class InputProjectionWrapper`](../../tf/contrib/rnn/InputProjectionWrapper.md): Operator adding an input projection to the given cell.

[`class IntersectionRNNCell`](../../tf/contrib/rnn/IntersectionRNNCell.md): Intersection Recurrent Neural Network (+RNN) cell.

[`class LSTMBlockCell`](../../tf/contrib/rnn/LSTMBlockCell.md): Basic LSTM recurrent network cell.

[`class LSTMBlockFusedCell`](../../tf/contrib/rnn/LSTMBlockFusedCell.md): FusedRNNCell implementation of LSTM.

[`class LSTMBlockWrapper`](../../tf/contrib/rnn/LSTMBlockWrapper.md): This is a helper class that provides housekeeping for LSTM cells.

[`class LSTMCell`](../../tf/nn/rnn_cell/LSTMCell.md): Long short-term memory unit (LSTM) recurrent network cell.

[`class LSTMStateTuple`](../../tf/nn/rnn_cell/LSTMStateTuple.md): Tuple used by LSTM Cells for `state_size`, `zero_state`, and output state.

[`class LayerNormBasicLSTMCell`](../../tf/contrib/rnn/LayerNormBasicLSTMCell.md): LSTM unit with layer normalization and recurrent dropout.

[`class LayerRNNCell`](../../tf/contrib/rnn/LayerRNNCell.md): Subclass of RNNCells that act like proper `tf.Layer` objects.

[`class MultiRNNCell`](../../tf/nn/rnn_cell/MultiRNNCell.md): RNN cell composed sequentially of multiple simple cells.

[`class NASCell`](../../tf/contrib/rnn/NASCell.md): Neural Architecture Search (NAS) recurrent network cell.

[`class OutputProjectionWrapper`](../../tf/contrib/rnn/OutputProjectionWrapper.md): Operator adding an output projection to the given cell.

[`class PhasedLSTMCell`](../../tf/contrib/rnn/PhasedLSTMCell.md): Phased LSTM recurrent network cell.

[`class RNNCell`](../../tf/nn/rnn_cell/RNNCell.md): Abstract object representing an RNN cell.

[`class ResidualWrapper`](../../tf/nn/rnn_cell/ResidualWrapper.md): RNNCell wrapper that ensures cell inputs are added to the outputs.

[`class SRUCell`](../../tf/contrib/rnn/SRUCell.md): SRU, Simple Recurrent Unit.

[`class TimeFreqLSTMCell`](../../tf/contrib/rnn/TimeFreqLSTMCell.md): Time-Frequency Long short-term memory unit (LSTM) recurrent network cell.

[`class TimeReversedFusedRNN`](../../tf/contrib/rnn/TimeReversedFusedRNN.md): This is an adaptor to time-reverse a FusedRNNCell.

[`class UGRNNCell`](../../tf/contrib/rnn/UGRNNCell.md): Update Gate Recurrent Neural Network (UGRNN) cell.

## Functions

[`best_effort_input_batch_size(...)`](../../tf/contrib/rnn/best_effort_input_batch_size.md): Get static input batch size if available, with fallback to the dynamic one.

[`stack_bidirectional_dynamic_rnn(...)`](../../tf/contrib/rnn/stack_bidirectional_dynamic_rnn.md): Creates a dynamic bidirectional recurrent neural network.

[`stack_bidirectional_rnn(...)`](../../tf/contrib/rnn/stack_bidirectional_rnn.md): Creates a bidirectional recurrent neural network.

[`static_bidirectional_rnn(...)`](../../tf/nn/static_bidirectional_rnn.md): Creates a bidirectional recurrent neural network.

[`static_rnn(...)`](../../tf/nn/static_rnn.md): Creates a recurrent neural network specified by RNNCell `cell`.

[`static_state_saving_rnn(...)`](../../tf/nn/static_state_saving_rnn.md): RNN that accepts a state saver for time-truncated RNN calculation.

[`transpose_batch_time(...)`](../../tf/contrib/rnn/transpose_batch_time.md): Transposes the batch and time dimensions of a Tensor.


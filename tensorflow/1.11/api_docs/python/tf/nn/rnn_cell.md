<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.rnn_cell" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.nn.rnn_cell



Defined in [`tensorflow/nn/rnn_cell/__init__.py`](https://www.tensorflow.org/code/tensorflow/nn/rnn_cell/__init__.py).

Module for constructing RNN Cells.

## Classes

[`class BasicLSTMCell`](../../tf/nn/rnn_cell/BasicLSTMCell.md): DEPRECATED: Please use <a href="../../tf/nn/rnn_cell/LSTMCell.md"><code>tf.nn.rnn_cell.LSTMCell</code></a> instead.

[`class BasicRNNCell`](../../tf/nn/rnn_cell/BasicRNNCell.md): The most basic RNN cell.

[`class DeviceWrapper`](../../tf/nn/rnn_cell/DeviceWrapper.md): Operator that ensures an RNNCell runs on a particular device.

[`class DropoutWrapper`](../../tf/nn/rnn_cell/DropoutWrapper.md): Operator adding dropout to inputs and outputs of the given cell.

[`class GRUCell`](../../tf/nn/rnn_cell/GRUCell.md): Gated Recurrent Unit cell (cf. http://arxiv.org/abs/1406.1078).

[`class LSTMCell`](../../tf/nn/rnn_cell/LSTMCell.md): Long short-term memory unit (LSTM) recurrent network cell.

[`class LSTMStateTuple`](../../tf/nn/rnn_cell/LSTMStateTuple.md): Tuple used by LSTM Cells for `state_size`, `zero_state`, and output state.

[`class MultiRNNCell`](../../tf/nn/rnn_cell/MultiRNNCell.md): RNN cell composed sequentially of multiple simple cells.

[`class RNNCell`](../../tf/nn/rnn_cell/RNNCell.md): Abstract object representing an RNN cell.

[`class ResidualWrapper`](../../tf/nn/rnn_cell/ResidualWrapper.md): RNNCell wrapper that ensures cell inputs are added to the outputs.


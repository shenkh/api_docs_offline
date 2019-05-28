<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nn.rnn_cell" />
</div>

# Module: tf.nn.rnn_cell



Defined in [`tensorflow/nn/rnn_cell/__init__.py`](https://www.tensorflow.org/code/tensorflow/nn/rnn_cell/__init__.py).

Module for constructing RNN Cells.

## Classes

[`class BasicLSTMCell`](../../tf/contrib/rnn/BasicLSTMCell.md): Basic LSTM recurrent network cell.

[`class BasicRNNCell`](../../tf/contrib/rnn/BasicRNNCell.md): The most basic RNN cell.

[`class DeviceWrapper`](../../tf/contrib/rnn/DeviceWrapper.md): Operator that ensures an RNNCell runs on a particular device.

[`class DropoutWrapper`](../../tf/contrib/rnn/DropoutWrapper.md): Operator adding dropout to inputs and outputs of the given cell.

[`class GRUCell`](../../tf/contrib/rnn/GRUCell.md): Gated Recurrent Unit cell (cf. http://arxiv.org/abs/1406.1078).

[`class LSTMCell`](../../tf/contrib/rnn/LSTMCell.md): Long short-term memory unit (LSTM) recurrent network cell.

[`class LSTMStateTuple`](../../tf/contrib/rnn/LSTMStateTuple.md): Tuple used by LSTM Cells for `state_size`, `zero_state`, and output state.

[`class MultiRNNCell`](../../tf/contrib/rnn/MultiRNNCell.md): RNN cell composed sequentially of multiple simple cells.

[`class RNNCell`](../../tf/contrib/rnn/RNNCell.md): Abstract object representing an RNN cell.

[`class ResidualWrapper`](../../tf/contrib/rnn/ResidualWrapper.md): RNNCell wrapper that ensures cell inputs are added to the outputs.


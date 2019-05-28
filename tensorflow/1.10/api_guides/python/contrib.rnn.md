# RNN and Cells (contrib)
[TOC]

Module for constructing RNN Cells and additional RNN operations.

<h2 id="Base_interface_for_all_RNN_Cells">Base interface for all RNN Cells</h2>

*   <a href="../../api_docs/python/tf/contrib/rnn/RNNCell.md"><code>tf.contrib.rnn.RNNCell</code></a>

<h2 id="Core_RNN_Cells_for_use_with_TensorFlow_s_core_RNN_methods">Core RNN Cells for use with TensorFlow's core RNN methods</h2>

*   <a href="../../api_docs/python/tf/contrib/rnn/BasicRNNCell.md"><code>tf.contrib.rnn.BasicRNNCell</code></a>
*   <a href="../../api_docs/python/tf/contrib/rnn/BasicLSTMCell.md"><code>tf.contrib.rnn.BasicLSTMCell</code></a>
*   <a href="../../api_docs/python/tf/contrib/rnn/GRUCell.md"><code>tf.contrib.rnn.GRUCell</code></a>
*   <a href="../../api_docs/python/tf/contrib/rnn/LSTMCell.md"><code>tf.contrib.rnn.LSTMCell</code></a>
*   <a href="../../api_docs/python/tf/contrib/rnn/LayerNormBasicLSTMCell.md"><code>tf.contrib.rnn.LayerNormBasicLSTMCell</code></a>

<h2 id="Classes_storing_split_RNNCell_state">Classes storing split `RNNCell` state</h2>

*   <a href="../../api_docs/python/tf/contrib/rnn/LSTMStateTuple.md"><code>tf.contrib.rnn.LSTMStateTuple</code></a>

<h2 id="Core_RNN_Cell_wrappers_RNNCells_that_wrap_other_RNNCells_">Core RNN Cell wrappers (RNNCells that wrap other RNNCells)</h2>

*   <a href="../../api_docs/python/tf/contrib/rnn/MultiRNNCell.md"><code>tf.contrib.rnn.MultiRNNCell</code></a>
*   <a href="../../api_docs/python/tf/contrib/rnn/LSTMBlockWrapper.md"><code>tf.contrib.rnn.LSTMBlockWrapper</code></a>
*   <a href="../../api_docs/python/tf/contrib/rnn/DropoutWrapper.md"><code>tf.contrib.rnn.DropoutWrapper</code></a>
*   <a href="../../api_docs/python/tf/contrib/rnn/EmbeddingWrapper.md"><code>tf.contrib.rnn.EmbeddingWrapper</code></a>
*   <a href="../../api_docs/python/tf/contrib/rnn/InputProjectionWrapper.md"><code>tf.contrib.rnn.InputProjectionWrapper</code></a>
*   <a href="../../api_docs/python/tf/contrib/rnn/OutputProjectionWrapper.md"><code>tf.contrib.rnn.OutputProjectionWrapper</code></a>
*   <a href="../../api_docs/python/tf/contrib/rnn/DeviceWrapper.md"><code>tf.contrib.rnn.DeviceWrapper</code></a>
*   <a href="../../api_docs/python/tf/contrib/rnn/ResidualWrapper.md"><code>tf.contrib.rnn.ResidualWrapper</code></a>

### Block RNNCells
*   <a href="../../api_docs/python/tf/contrib/rnn/LSTMBlockCell.md"><code>tf.contrib.rnn.LSTMBlockCell</code></a>
*   <a href="../../api_docs/python/tf/contrib/rnn/GRUBlockCell.md"><code>tf.contrib.rnn.GRUBlockCell</code></a>

### Fused RNNCells
*   <a href="../../api_docs/python/tf/contrib/rnn/FusedRNNCell.md"><code>tf.contrib.rnn.FusedRNNCell</code></a>
*   <a href="../../api_docs/python/tf/contrib/rnn/FusedRNNCellAdaptor.md"><code>tf.contrib.rnn.FusedRNNCellAdaptor</code></a>
*   <a href="../../api_docs/python/tf/contrib/rnn/TimeReversedFusedRNN.md"><code>tf.contrib.rnn.TimeReversedFusedRNN</code></a>
*   <a href="../../api_docs/python/tf/contrib/rnn/LSTMBlockFusedCell.md"><code>tf.contrib.rnn.LSTMBlockFusedCell</code></a>

### LSTM-like cells
*   <a href="../../api_docs/python/tf/contrib/rnn/CoupledInputForgetGateLSTMCell.md"><code>tf.contrib.rnn.CoupledInputForgetGateLSTMCell</code></a>
*   <a href="../../api_docs/python/tf/contrib/rnn/TimeFreqLSTMCell.md"><code>tf.contrib.rnn.TimeFreqLSTMCell</code></a>
*   <a href="../../api_docs/python/tf/contrib/rnn/GridLSTMCell.md"><code>tf.contrib.rnn.GridLSTMCell</code></a>

### RNNCell wrappers
*   <a href="../../api_docs/python/tf/contrib/rnn/AttentionCellWrapper.md"><code>tf.contrib.rnn.AttentionCellWrapper</code></a>
*   <a href="../../api_docs/python/tf/contrib/rnn/CompiledWrapper.md"><code>tf.contrib.rnn.CompiledWrapper</code></a>


<h2 id="Recurrent_Neural_Networks">Recurrent Neural Networks</h2>

TensorFlow provides a number of methods for constructing Recurrent Neural
Networks.

*   <a href="../../api_docs/python/tf/nn/static_rnn.md"><code>tf.contrib.rnn.static_rnn</code></a>
*   <a href="../../api_docs/python/tf/nn/static_state_saving_rnn.md"><code>tf.contrib.rnn.static_state_saving_rnn</code></a>
*   <a href="../../api_docs/python/tf/nn/static_bidirectional_rnn.md"><code>tf.contrib.rnn.static_bidirectional_rnn</code></a>
*   <a href="../../api_docs/python/tf/contrib/rnn/stack_bidirectional_dynamic_rnn.md"><code>tf.contrib.rnn.stack_bidirectional_dynamic_rnn</code></a>

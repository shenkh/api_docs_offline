# Training
[TOC]

<a href="../../api_docs/python/tf/train.md"><code>tf.train</code></a> provides a set of classes and functions that help train models.

<h2 id="Optimizers">Optimizers</h2>

The Optimizer base class provides methods to compute gradients for a loss and
apply gradients to variables.  A collection of subclasses implement classic
optimization algorithms such as GradientDescent and Adagrad.

You never instantiate the Optimizer class itself, but instead instantiate one
of the subclasses.

*   <a href="../../api_docs/python/tf/train/Optimizer.md"><code>tf.train.Optimizer</code></a>
*   <a href="../../api_docs/python/tf/train/GradientDescentOptimizer.md"><code>tf.train.GradientDescentOptimizer</code></a>
*   <a href="../../api_docs/python/tf/train/AdadeltaOptimizer.md"><code>tf.train.AdadeltaOptimizer</code></a>
*   <a href="../../api_docs/python/tf/train/AdagradOptimizer.md"><code>tf.train.AdagradOptimizer</code></a>
*   <a href="../../api_docs/python/tf/train/AdagradDAOptimizer.md"><code>tf.train.AdagradDAOptimizer</code></a>
*   <a href="../../api_docs/python/tf/train/MomentumOptimizer.md"><code>tf.train.MomentumOptimizer</code></a>
*   <a href="../../api_docs/python/tf/train/AdamOptimizer.md"><code>tf.train.AdamOptimizer</code></a>
*   <a href="../../api_docs/python/tf/train/FtrlOptimizer.md"><code>tf.train.FtrlOptimizer</code></a>
*   <a href="../../api_docs/python/tf/train/ProximalGradientDescentOptimizer.md"><code>tf.train.ProximalGradientDescentOptimizer</code></a>
*   <a href="../../api_docs/python/tf/train/ProximalAdagradOptimizer.md"><code>tf.train.ProximalAdagradOptimizer</code></a>
*   <a href="../../api_docs/python/tf/train/RMSPropOptimizer.md"><code>tf.train.RMSPropOptimizer</code></a>

See <a href="../../api_docs/python/tf/contrib/opt.md"><code>tf.contrib.opt</code></a> for more optimizers.

<h2 id="Gradient_Computation">Gradient Computation</h2>

TensorFlow provides functions to compute the derivatives for a given
TensorFlow computation graph, adding operations to the graph. The
optimizer classes automatically compute derivatives on your graph, but
creators of new Optimizers or expert users can call the lower-level
functions below.

*   <a href="../../api_docs/python/tf/gradients.md"><code>tf.gradients</code></a>
*   <a href="../../api_docs/python/tf/AggregationMethod.md"><code>tf.AggregationMethod</code></a>
*   <a href="../../api_docs/python/tf/stop_gradient.md"><code>tf.stop_gradient</code></a>
*   <a href="../../api_docs/python/tf/hessians.md"><code>tf.hessians</code></a>


<h2 id="Gradient_Clipping">Gradient Clipping</h2>

TensorFlow provides several operations that you can use to add clipping
functions to your graph. You can use these functions to perform general data
clipping, but they're particularly useful for handling exploding or vanishing
gradients.

*   <a href="../../api_docs/python/tf/clip_by_value.md"><code>tf.clip_by_value</code></a>
*   <a href="../../api_docs/python/tf/clip_by_norm.md"><code>tf.clip_by_norm</code></a>
*   <a href="../../api_docs/python/tf/clip_by_average_norm.md"><code>tf.clip_by_average_norm</code></a>
*   <a href="../../api_docs/python/tf/clip_by_global_norm.md"><code>tf.clip_by_global_norm</code></a>
*   <a href="../../api_docs/python/tf/global_norm.md"><code>tf.global_norm</code></a>

<h2 id="Decaying_the_learning_rate">Decaying the learning rate</h2>

*   <a href="../../api_docs/python/tf/train/exponential_decay.md"><code>tf.train.exponential_decay</code></a>
*   <a href="../../api_docs/python/tf/train/inverse_time_decay.md"><code>tf.train.inverse_time_decay</code></a>
*   <a href="../../api_docs/python/tf/train/natural_exp_decay.md"><code>tf.train.natural_exp_decay</code></a>
*   <a href="../../api_docs/python/tf/train/piecewise_constant.md"><code>tf.train.piecewise_constant</code></a>
*   <a href="../../api_docs/python/tf/train/polynomial_decay.md"><code>tf.train.polynomial_decay</code></a>
*   <a href="../../api_docs/python/tf/train/cosine_decay.md"><code>tf.train.cosine_decay</code></a>
*   <a href="../../api_docs/python/tf/train/linear_cosine_decay.md"><code>tf.train.linear_cosine_decay</code></a>
*   <a href="../../api_docs/python/tf/train/noisy_linear_cosine_decay.md"><code>tf.train.noisy_linear_cosine_decay</code></a>

<h2 id="Moving_Averages">Moving Averages</h2>

Some training algorithms, such as GradientDescent and Momentum often benefit
from maintaining a moving average of variables during optimization.  Using the
moving averages for evaluations often improve results significantly.

*   <a href="../../api_docs/python/tf/train/ExponentialMovingAverage.md"><code>tf.train.ExponentialMovingAverage</code></a>

<h2 id="Coordinator_and_QueueRunner">Coordinator and QueueRunner</h2>

See <a href="../../api_guides/python/threading_and_queues.md">Threading and Queues</a>
for how to use threads and queues.  For documentation on the Queue API,
see <a href="../../api_guides/python/io_ops.md#queues">Queues</a>.


*   <a href="../../api_docs/python/tf/train/Coordinator.md"><code>tf.train.Coordinator</code></a>
*   <a href="../../api_docs/python/tf/train/QueueRunner.md"><code>tf.train.QueueRunner</code></a>
*   <a href="../../api_docs/python/tf/train/LooperThread.md"><code>tf.train.LooperThread</code></a>
*   <a href="../../api_docs/python/tf/train/add_queue_runner.md"><code>tf.train.add_queue_runner</code></a>
*   <a href="../../api_docs/python/tf/train/start_queue_runners.md"><code>tf.train.start_queue_runners</code></a>

<h2 id="Distributed_execution">Distributed execution</h2>

See <a href="../../deploy/distributed.md">Distributed TensorFlow</a> for
more information about how to configure a distributed TensorFlow program.

*   <a href="../../api_docs/python/tf/train/Server.md"><code>tf.train.Server</code></a>
*   <a href="../../api_docs/python/tf/train/Supervisor.md"><code>tf.train.Supervisor</code></a>
*   <a href="../../api_docs/python/tf/train/SessionManager.md"><code>tf.train.SessionManager</code></a>
*   <a href="../../api_docs/python/tf/train/ClusterSpec.md"><code>tf.train.ClusterSpec</code></a>
*   <a href="../../api_docs/python/tf/train/replica_device_setter.md"><code>tf.train.replica_device_setter</code></a>
*   <a href="../../api_docs/python/tf/train/MonitoredTrainingSession.md"><code>tf.train.MonitoredTrainingSession</code></a>
*   <a href="../../api_docs/python/tf/train/MonitoredSession.md"><code>tf.train.MonitoredSession</code></a>
*   <a href="../../api_docs/python/tf/train/SingularMonitoredSession.md"><code>tf.train.SingularMonitoredSession</code></a>
*   <a href="../../api_docs/python/tf/train/Scaffold.md"><code>tf.train.Scaffold</code></a>
*   <a href="../../api_docs/python/tf/train/SessionCreator.md"><code>tf.train.SessionCreator</code></a>
*   <a href="../../api_docs/python/tf/train/ChiefSessionCreator.md"><code>tf.train.ChiefSessionCreator</code></a>
*   <a href="../../api_docs/python/tf/train/WorkerSessionCreator.md"><code>tf.train.WorkerSessionCreator</code></a>

<h2 id="Reading_Summaries_from_Event_Files">Reading Summaries from Event Files</h2>

See <a href="../../guide/summaries_and_tensorboard.md">Summaries and TensorBoard</a> for an
overview of summaries, event files, and visualization in TensorBoard.

*   <a href="../../api_docs/python/tf/train/summary_iterator.md"><code>tf.train.summary_iterator</code></a>

<h2 id="Training_Hooks">Training Hooks</h2>

Hooks are tools that run in the process of training/evaluation of the model.

*   <a href="../../api_docs/python/tf/train/SessionRunHook.md"><code>tf.train.SessionRunHook</code></a>
*   <a href="../../api_docs/python/tf/train/SessionRunArgs.md"><code>tf.train.SessionRunArgs</code></a>
*   <a href="../../api_docs/python/tf/train/SessionRunContext.md"><code>tf.train.SessionRunContext</code></a>
*   <a href="../../api_docs/python/tf/train/SessionRunValues.md"><code>tf.train.SessionRunValues</code></a>
*   <a href="../../api_docs/python/tf/train/LoggingTensorHook.md"><code>tf.train.LoggingTensorHook</code></a>
*   <a href="../../api_docs/python/tf/train/StopAtStepHook.md"><code>tf.train.StopAtStepHook</code></a>
*   <a href="../../api_docs/python/tf/train/CheckpointSaverHook.md"><code>tf.train.CheckpointSaverHook</code></a>
*   <a href="../../api_docs/python/tf/train/NewCheckpointReader.md"><code>tf.train.NewCheckpointReader</code></a>
*   <a href="../../api_docs/python/tf/train/StepCounterHook.md"><code>tf.train.StepCounterHook</code></a>
*   <a href="../../api_docs/python/tf/train/NanLossDuringTrainingError.md"><code>tf.train.NanLossDuringTrainingError</code></a>
*   <a href="../../api_docs/python/tf/train/NanTensorHook.md"><code>tf.train.NanTensorHook</code></a>
*   <a href="../../api_docs/python/tf/train/SummarySaverHook.md"><code>tf.train.SummarySaverHook</code></a>
*   <a href="../../api_docs/python/tf/train/GlobalStepWaiterHook.md"><code>tf.train.GlobalStepWaiterHook</code></a>
*   <a href="../../api_docs/python/tf/train/FinalOpsHook.md"><code>tf.train.FinalOpsHook</code></a>
*   <a href="../../api_docs/python/tf/train/FeedFnHook.md"><code>tf.train.FeedFnHook</code></a>

<h2 id="Training_Utilities">Training Utilities</h2>

*   <a href="../../api_docs/python/tf/train/global_step.md"><code>tf.train.global_step</code></a>
*   <a href="../../api_docs/python/tf/train/basic_train_loop.md"><code>tf.train.basic_train_loop</code></a>
*   <a href="../../api_docs/python/tf/train/get_global_step.md"><code>tf.train.get_global_step</code></a>
*   <a href="../../api_docs/python/tf/train/assert_global_step.md"><code>tf.train.assert_global_step</code></a>
*   <a href="../../api_docs/python/tf/train/write_graph.md"><code>tf.train.write_graph</code></a>

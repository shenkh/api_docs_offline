<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.training" />
</div>

# Module: tf.contrib.training



Defined in [`tensorflow/contrib/training/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/training/__init__.py).

Training and input utilities.

See <a href="../../../../api_guides/python/contrib.training.md">Training (contrib)</a> guide.


## Classes

[`class FeedingQueueRunner`](../../tf/contrib/training/FeedingQueueRunner.md): A queue runner that allows the feeding of values such as numpy arrays.

[`class GreedyLoadBalancingStrategy`](../../tf/contrib/training/GreedyLoadBalancingStrategy.md): Returns the least-loaded ps task for op placement.

[`class HParams`](../../tf/contrib/training/HParams.md): Class to hold a set of hyperparameters as name-value pairs.

[`class NextQueuedSequenceBatch`](../../tf/contrib/training/NextQueuedSequenceBatch.md): NextQueuedSequenceBatch stores deferred SequenceQueueingStateSaver data.

[`class RandomStrategy`](../../tf/contrib/training/RandomStrategy.md): Returns a random PS task for op placement.

[`class SequenceQueueingStateSaver`](../../tf/contrib/training/SequenceQueueingStateSaver.md): SequenceQueueingStateSaver provides access to stateful values from input.

[`class StopAfterNEvalsHook`](../../tf/contrib/training/StopAfterNEvalsHook.md): Run hook used by the evaluation routines to run the `eval_ops` N times.

[`class SummaryAtEndHook`](../../tf/contrib/training/SummaryAtEndHook.md): A run hook that saves a summary with the results of evaluation.

## Functions

[`add_gradients_summaries(...)`](../../tf/contrib/training/add_gradients_summaries.md): Add summaries to gradients.

[`batch_sequences_with_states(...)`](../../tf/contrib/training/batch_sequences_with_states.md): Creates batches of segments of sequential input.

[`bucket(...)`](../../tf/contrib/training/bucket.md): Lazy bucketing of input tensors according to `which_bucket`.

[`bucket_by_sequence_length(...)`](../../tf/contrib/training/bucket_by_sequence_length.md): Lazy bucketing of inputs according to their length.

[`byte_size_load_fn(...)`](../../tf/contrib/training/byte_size_load_fn.md): Load function that computes the byte size of a single-output `Operation`.

[`checkpoints_iterator(...)`](../../tf/contrib/training/checkpoints_iterator.md): Continuously yield new checkpoint files as they appear.

[`clip_gradient_norms(...)`](../../tf/contrib/training/clip_gradient_norms.md): Clips the gradients by the given value.

[`clip_gradient_norms_fn(...)`](../../tf/contrib/training/clip_gradient_norms_fn.md): Returns a `transform_grads_fn` function for gradient clipping.

[`create_train_op(...)`](../../tf/contrib/training/create_train_op.md): Creates an `Operation` that evaluates the gradients and returns the loss.

[`enqueue_in_queue_dataset(...)`](../../tf/contrib/training/enqueue_in_queue_dataset.md): Enqueue components into queue from `PrependFromQueueAndPaddedBatchDataset`.

[`evaluate_once(...)`](../../tf/contrib/training/evaluate_once.md): Evaluates the model at the given checkpoint path.

[`evaluate_repeatedly(...)`](../../tf/contrib/training/evaluate_repeatedly.md): Repeatedly searches for a checkpoint in `checkpoint_dir` and evaluates it.

[`get_or_create_eval_step(...)`](../../tf/contrib/training/get_or_create_eval_step.md): Gets or creates the eval step `Tensor`.

[`multiply_gradients(...)`](../../tf/contrib/training/multiply_gradients.md): Multiply specified gradients.

[`parse_values(...)`](../../tf/contrib/training/parse_values.md): Parses hyperparameter values from a string into a python map.

[`prepend_from_queue_and_padded_batch_dataset(...)`](../../tf/contrib/training/prepend_from_queue_and_padded_batch_dataset.md): A transformation that prepends a queue to a `Dataset` and batches results.

[`rejection_sample(...)`](../../tf/contrib/training/rejection_sample.md): Stochastically creates batches by rejection sampling.

[`resample_at_rate(...)`](../../tf/contrib/training/resample_at_rate.md): Given `inputs` tensors, stochastically resamples each at a given rate.

[`stratified_sample(...)`](../../tf/contrib/training/stratified_sample.md): Stochastically creates batches based on per-class probabilities.

[`train(...)`](../../tf/contrib/training/train.md): Runs the training loop.

[`wait_for_new_checkpoint(...)`](../../tf/contrib/training/wait_for_new_checkpoint.md): Waits until a new checkpoint file is found.

[`weighted_resample(...)`](../../tf/contrib/training/weighted_resample.md): Performs an approximate weighted resampling of `inputs`.


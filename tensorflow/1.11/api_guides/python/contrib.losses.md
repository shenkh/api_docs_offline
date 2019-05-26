# Losses (contrib)

<h2 id="Deprecated">Deprecated</h2>

This module is deprecated. Instructions for updating: Use <a href="../../api_docs/python/tf/losses.md"><code>tf.losses</code></a> instead.

<h2 id="Loss_operations_for_use_in_neural_networks_">Loss operations for use in neural networks.</h2>

Note: By default, all the losses are collected into the `GraphKeys.LOSSES`
collection.

All of the loss functions take a pair of predictions and ground truth labels,
from which the loss is computed. It is assumed that the shape of both these
tensors is of the form [batch_size, d1, ... dN] where `batch_size` is the number
of samples in the batch and `d1` ... `dN` are the remaining dimensions.

It is common, when training with multiple loss functions, to adjust the relative
strengths of individual losses. This is performed by rescaling the losses via
a `weight` parameter passed to the loss functions. For example, if we were
training with both log_loss and mean_squared_error, and we wished that the
log_loss penalty be twice as severe as the mean_squared_error, we would
implement this as:

```python
  # Explicitly set the weight.
  tf.contrib.losses.log(predictions, labels, weight=2.0)

  # Uses default weight of 1.0
  tf.contrib.losses.mean_squared_error(predictions, labels)

  # All the losses are collected into the `GraphKeys.LOSSES` collection.
  losses = tf.get_collection(tf.GraphKeys.LOSSES)
```

While specifying a scalar loss rescales the loss over the entire batch,
we sometimes want to rescale the loss per batch sample. For example, if we have
certain examples that matter more to us to get correctly, we might want to have
a higher loss that other samples whose mistakes matter less. In this case, we
can provide a weight vector of length `batch_size` which results in the loss
for each sample in the batch being scaled by the corresponding weight element.
For example, consider the case of a classification problem where we want to
maximize our accuracy but we especially interested in obtaining high accuracy
for a specific class:

```python
  inputs, labels = LoadData(batch_size=3)
  logits = MyModelPredictions(inputs)

  # Ensures that the loss for examples whose ground truth class is `3` is 5x
  # higher than the loss for all other examples.
  weight = tf.multiply(4, tf.cast(tf.equal(labels, 3), tf.float32)) + 1

  onehot_labels = tf.one_hot(labels, num_classes=5)
  tf.contrib.losses.softmax_cross_entropy(logits, onehot_labels, weight=weight)
```

Finally, in certain cases, we may want to specify a different loss for every
single measurable value. For example, if we are performing per-pixel depth
prediction, or per-pixel denoising, a single batch sample has P values where P
is the number of pixels in the image. For many losses, the number of measurable
values matches the number of elements in the predictions and labels tensors.
For others, such as softmax_cross_entropy and cosine_distance, the
loss functions reduces the dimensions of the inputs to produces a tensor of
losses for each measurable value. For example, softmax_cross_entropy takes as
input predictions and labels of dimension [batch_size, num_classes] but the
number of measurable values is [batch_size]. Consequently, when passing a weight
tensor to specify a different loss for every measurable value, the dimension of
the tensor will depend on the loss being used.

For a concrete example, consider the case of per-pixel depth prediction where
certain ground truth depth values are missing (due to sensor noise in the
capture process). In this case, we want to assign zero weight to losses for
these predictions.

```python
  # 'depths' that are missing have a value of 0:
  images, depths = LoadData(...)
  predictions = MyModelPredictions(images)

  weight = tf.cast(tf.greater(depths, 0), tf.float32)
  loss  = tf.contrib.losses.mean_squared_error(predictions, depths, weight)
```

Note that when using weights for the losses, the final average is computed
by rescaling the losses by the weights and then dividing by the total number of
non-zero samples. For an arbitrary set of weights, this may not necessarily
produce a weighted average. Instead, it simply and transparently rescales the
per-element losses before averaging over the number of observations. For example
if the losses computed by the loss function is an array [4, 1, 2, 3] and the
weights are an array [1, 0.5, 3, 9], then the average loss is:

```python
  (4*1 + 1*0.5 + 2*3 + 3*9) / 4
```

However, with a single loss function and an arbitrary set of weights, one can
still easily create a loss function such that the resulting loss is a
weighted average over the individual prediction errors:


```python
  images, labels = LoadData(...)
  predictions = MyModelPredictions(images)

  weight = MyComplicatedWeightingFunction(labels)
  weight = tf.div(weight, tf.size(weight))
  loss = tf.contrib.losses.mean_squared_error(predictions, depths, weight)
```

* <a href="../../api_docs/python/tf/contrib/losses/absolute_difference.md"><code>tf.contrib.losses.absolute_difference</code></a>
* <a href="../../api_docs/python/tf/contrib/losses/add_loss.md"><code>tf.contrib.losses.add_loss</code></a>
* <a href="../../api_docs/python/tf/contrib/losses/hinge_loss.md"><code>tf.contrib.losses.hinge_loss</code></a>
* <a href="../../api_docs/python/tf/contrib/losses/compute_weighted_loss.md"><code>tf.contrib.losses.compute_weighted_loss</code></a>
* <a href="../../api_docs/python/tf/contrib/losses/cosine_distance.md"><code>tf.contrib.losses.cosine_distance</code></a>
* <a href="../../api_docs/python/tf/contrib/losses/get_losses.md"><code>tf.contrib.losses.get_losses</code></a>
* <a href="../../api_docs/python/tf/contrib/losses/get_regularization_losses.md"><code>tf.contrib.losses.get_regularization_losses</code></a>
* <a href="../../api_docs/python/tf/contrib/losses/get_total_loss.md"><code>tf.contrib.losses.get_total_loss</code></a>
* <a href="../../api_docs/python/tf/contrib/losses/log_loss.md"><code>tf.contrib.losses.log_loss</code></a>
* <a href="../../api_docs/python/tf/contrib/losses/mean_pairwise_squared_error.md"><code>tf.contrib.losses.mean_pairwise_squared_error</code></a>
* <a href="../../api_docs/python/tf/contrib/losses/mean_squared_error.md"><code>tf.contrib.losses.mean_squared_error</code></a>
* <a href="../../api_docs/python/tf/contrib/losses/sigmoid_cross_entropy.md"><code>tf.contrib.losses.sigmoid_cross_entropy</code></a>
* <a href="../../api_docs/python/tf/contrib/losses/softmax_cross_entropy.md"><code>tf.contrib.losses.softmax_cross_entropy</code></a>
* <a href="../../api_docs/python/tf/contrib/losses/sparse_softmax_cross_entropy.md"><code>tf.contrib.losses.sparse_softmax_cross_entropy</code></a>



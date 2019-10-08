<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.image.non_max_suppression_padded" />
<meta itemprop="path" content="Stable" />
</div>

# tf.image.non_max_suppression_padded

``` python
tf.image.non_max_suppression_padded(
    boxes,
    scores,
    max_output_size,
    iou_threshold=0.5,
    score_threshold=float('-inf'),
    pad_to_max_output_size=False,
    name=None
)
```



Defined in [`tensorflow/python/ops/image_ops_impl.py`](/code/stable/tensorflow/python/ops/image_ops_impl.py).

Greedily selects a subset of bounding boxes in descending order of score.

Performs algorithmically equivalent operation to tf.image.non_max_suppression,
with the addition of an optional parameter which zero-pads the output to
be of size `max_output_size`.
The output of this operation is a tuple containing the set of integers
indexing into the input collection of bounding boxes representing the selected
boxes and the number of valid indices in the index set.  The bounding box
coordinates corresponding to the selected indices can then be obtained using
the <a href="../../tf/slice.md"><code>tf.slice</code></a> and <a href="../../tf/gather.md"><code>tf.gather</code></a> operations.  For example:
  ```python
  selected_indices_padded, num_valid = tf.image.non_max_suppression_padded(
      boxes, scores, max_output_size, iou_threshold,
      score_threshold, pad_to_max_output_size=True)
  selected_indices = tf.slice(
      selected_indices_padded, tf.constant([0]), num_valid)
  selected_boxes = tf.gather(boxes, selected_indices)
  ```

#### Args:

* <b>`boxes`</b>: A 2-D float `Tensor` of shape `[num_boxes, 4]`.
* <b>`scores`</b>: A 1-D float `Tensor` of shape `[num_boxes]` representing a single
    score corresponding to each box (each row of boxes).
* <b>`max_output_size`</b>: A scalar integer `Tensor` representing the maximum number
    of boxes to be selected by non max suppression.
* <b>`iou_threshold`</b>: A float representing the threshold for deciding whether boxes
    overlap too much with respect to IOU.
* <b>`score_threshold`</b>: A float representing the threshold for deciding when to
    remove boxes based on score.
* <b>`pad_to_max_output_size`</b>: bool.  If True, size of `selected_indices` output is
    padded to `max_output_size`.
* <b>`name`</b>: A name for the operation (optional).


#### Returns:

* <b>`selected_indices`</b>: A 1-D integer `Tensor` of shape `[M]` representing the
    selected indices from the boxes tensor, where `M <= max_output_size`.
* <b>`valid_outputs`</b>: A scalar integer `Tensor` denoting how many elements in
  `selected_indices` are valid.  Valid elements occur first, then padding.
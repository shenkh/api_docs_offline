<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.losses.cosine_similarity" />
<meta itemprop="path" content="Stable" />
</div>

# tf.losses.cosine_similarity

### Aliases:

* `tf.keras.losses.cosine_similarity`
* `tf.losses.cosine_similarity`

``` python
tf.losses.cosine_similarity(
    y_true,
    y_pred,
    axis=-1
)
```



Defined in [`tensorflow/python/keras/losses.py`](/code/stable/tensorflow/python/keras/losses.py).

Computes the cosine similarity between labels and predictions.

Note that it is a negative quantity between -1 and 0, where 0 indicates
orthogonality and values closer to -1 indicate greater similarity. This makes
it usable as a loss function in a setting where you try to maximize the
proximity between predictions and targets.

`loss = -sum(y_true * y_pred)`

#### Args:

* <b>`y_true`</b>: Tensor of true targets.
* <b>`y_pred`</b>: Tensor of predicted targets.
* <b>`axis`</b>: Axis along which to determine similarity.


#### Returns:

Cosine similarity tensor.
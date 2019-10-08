<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.ctc_label_dense_to_sparse" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.ctc_label_dense_to_sparse

``` python
tf.keras.backend.ctc_label_dense_to_sparse(
    labels,
    label_lengths
)
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Converts CTC labels from dense to sparse.

#### Arguments:

* <b>`labels`</b>: dense CTC labels.
* <b>`label_lengths`</b>: length of the labels.


#### Returns:

A sparse tensor representation of the labels.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.layers.make_place_holder_tensors_for_base_features" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.layers.make_place_holder_tensors_for_base_features

``` python
tf.contrib.layers.make_place_holder_tensors_for_base_features(feature_columns)
```



Defined in [`tensorflow/contrib/layers/python/layers/feature_column.py`](/code/stable/tensorflow/contrib/layers/python/layers/feature_column.py).

Returns placeholder tensors for inference.

#### Args:

* <b>`feature_columns`</b>: An iterable containing all the feature columns. All items
    should be instances of classes derived from _FeatureColumn.

#### Returns:

A dict mapping feature keys to SparseTensors (sparse columns) or
placeholder Tensors (dense columns).
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.learn.extract_pandas_labels" />
</div>

# tf.contrib.learn.extract_pandas_labels

``` python
tf.contrib.learn.extract_pandas_labels(labels)
```



Defined in [`tensorflow/contrib/learn/python/learn/learn_io/pandas_io.py`](https://www.tensorflow.org/code/tensorflow/contrib/learn/python/learn/learn_io/pandas_io.py).

See the guide: [Learn (contrib) > Input processing](../../../../../api_guides/python/contrib.learn.md#Input_processing)

Extract data from pandas.DataFrame for labels. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Please access pandas data directly.

#### Args:

* <b>`labels`</b>: `pandas.DataFrame` or `pandas.Series` containing one column of
    labels to be extracted.


#### Returns:

A numpy `ndarray` of labels from the DataFrame.


#### Raises:

* <b>`ValueError`</b>: if more than one column is found or type is not int, float or
    bool.
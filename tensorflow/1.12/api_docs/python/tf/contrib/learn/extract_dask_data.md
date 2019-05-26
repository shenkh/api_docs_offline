<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.learn.extract_dask_data" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.learn.extract_dask_data

``` python
tf.contrib.learn.extract_dask_data(data)
```



Defined in [`tensorflow/contrib/learn/python/learn/learn_io/dask_io.py`](/code/stable/tensorflow/contrib/learn/python/learn/learn_io/dask_io.py).

Extract data from dask.Series or dask.DataFrame for predictors. (deprecated)

THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Please feed input to tf.data to support dask.

Given a distributed dask.DataFrame or dask.Series containing columns or names
for one or more predictors, this operation returns a single dask.DataFrame or
dask.Series that can be iterated over.

#### Args:

* <b>`data`</b>: A distributed dask.DataFrame or dask.Series.


#### Returns:

A dask.DataFrame or dask.Series that can be iterated over.
If the supplied argument is neither a dask.DataFrame nor a dask.Series this
operation returns it without modification.
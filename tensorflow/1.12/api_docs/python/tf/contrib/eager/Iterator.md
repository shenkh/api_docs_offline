<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.eager.Iterator" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="output_classes"/>
<meta itemprop="property" content="output_shapes"/>
<meta itemprop="property" content="output_types"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__iter__"/>
<meta itemprop="property" content="__next__"/>
<meta itemprop="property" content="get_next"/>
<meta itemprop="property" content="next"/>
</div>

# tf.contrib.eager.Iterator

## Class `Iterator`





Defined in [`tensorflow/contrib/eager/python/datasets.py`](/code/stable/tensorflow/contrib/eager/python/datasets.py).

An iterator producing tf.Tensor objects from a tf.data.Dataset.

NOTE: Unlike the iterator created by the
<a href="../../../tf/data/Dataset.md#make_one_shot_iterator"><code>tf.data.Dataset.make_one_shot_iterator</code></a> method, this class enables
additional experimental functionality, such as prefetching to the GPU.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(dataset)
```

Creates a new iterator over the given dataset.

For example:
```python
dataset = tf.data.Dataset.range(4)
for x in Iterator(dataset):
  print(x)
```

Tensors produced will be placed on the device on which this iterator object
was created.

#### Args:

* <b>`dataset`</b>: A <a href="../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> object.


#### Raises:

* <b>`TypeError`</b>: If `dataset` is an unsupported type.
* <b>`RuntimeError`</b>: When invoked without eager execution enabled.



## Properties

<h3 id="output_classes"><code>output_classes</code></h3>

Returns the class of each component of an element of this iterator.

The expected values are <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a> and <a href="../../../tf/sparse/SparseTensor.md"><code>tf.SparseTensor</code></a>.

#### Returns:

A nested structure of Python `type` objects corresponding to each
component of an element of this dataset.

<h3 id="output_shapes"><code>output_shapes</code></h3>

Returns the shape of each component of an element of this iterator.

#### Returns:

A nested structure of <a href="../../../tf/TensorShape.md"><code>tf.TensorShape</code></a> objects corresponding to each
component of an element of this dataset.

<h3 id="output_types"><code>output_types</code></h3>

Returns the type of each component of an element of this iterator.

#### Returns:

A nested structure of <a href="../../../tf/dtypes/DType.md"><code>tf.DType</code></a> objects corresponding to each component
of an element of this dataset.



## Methods

<h3 id="__iter__"><code>__iter__</code></h3>

``` python
__iter__()
```



<h3 id="__next__"><code>__next__</code></h3>

``` python
__next__()
```



<h3 id="get_next"><code>get_next</code></h3>

``` python
get_next(name=None)
```

Returns a nested structure of <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>s containing the next element.

#### Args:

* <b>`name`</b>: (Optional.) A name for the created operation. Currently unused.


#### Returns:

A nested structure of <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a> objects.


#### Raises:

<a href="../../../tf/errors/OutOfRangeError.md"><code>tf.errors.OutOfRangeError</code></a>: If the end of the dataset has been reached.

<h3 id="next"><code>next</code></h3>

``` python
next()
```

Returns a nested structure of <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a>s containing the next element.
    




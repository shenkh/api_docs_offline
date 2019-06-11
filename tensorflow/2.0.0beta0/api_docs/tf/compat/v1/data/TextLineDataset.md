<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.data.TextLineDataset" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="output_classes"/>
<meta itemprop="property" content="output_shapes"/>
<meta itemprop="property" content="output_types"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__iter__"/>
<meta itemprop="property" content="apply"/>
<meta itemprop="property" content="batch"/>
<meta itemprop="property" content="cache"/>
<meta itemprop="property" content="concatenate"/>
<meta itemprop="property" content="enumerate"/>
<meta itemprop="property" content="filter"/>
<meta itemprop="property" content="filter_with_legacy_function"/>
<meta itemprop="property" content="flat_map"/>
<meta itemprop="property" content="from_generator"/>
<meta itemprop="property" content="from_sparse_tensor_slices"/>
<meta itemprop="property" content="from_tensor_slices"/>
<meta itemprop="property" content="from_tensors"/>
<meta itemprop="property" content="interleave"/>
<meta itemprop="property" content="list_files"/>
<meta itemprop="property" content="make_initializable_iterator"/>
<meta itemprop="property" content="make_one_shot_iterator"/>
<meta itemprop="property" content="map"/>
<meta itemprop="property" content="map_with_legacy_function"/>
<meta itemprop="property" content="options"/>
<meta itemprop="property" content="padded_batch"/>
<meta itemprop="property" content="prefetch"/>
<meta itemprop="property" content="range"/>
<meta itemprop="property" content="reduce"/>
<meta itemprop="property" content="repeat"/>
<meta itemprop="property" content="shard"/>
<meta itemprop="property" content="shuffle"/>
<meta itemprop="property" content="skip"/>
<meta itemprop="property" content="take"/>
<meta itemprop="property" content="unbatch"/>
<meta itemprop="property" content="window"/>
<meta itemprop="property" content="with_options"/>
<meta itemprop="property" content="zip"/>
</div>

# tf.compat.v1.data.TextLineDataset

## Class `TextLineDataset`

A `Dataset` comprising lines from one or more text files.





Defined in [`python/data/ops/readers.py`](/code/stable/tensorflow/python/data/ops/readers.py).

<!-- Placeholder for "Used in" -->


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    filenames,
    compression_type=None,
    buffer_size=None,
    num_parallel_reads=None
)
```

Creates a `TextLineDataset`.


#### Args:


* <b>`filenames`</b>: A <a href="../../../../tf.md#string"><code>tf.string</code></a> tensor or <a href="../../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> containing one or
  more filenames.
* <b>`compression_type`</b>: (Optional.) A <a href="../../../../tf.md#string"><code>tf.string</code></a> scalar evaluating to one of
  `""` (no compression), `"ZLIB"`, or `"GZIP"`.
* <b>`buffer_size`</b>: (Optional.) A <a href="../../../../tf.md#int64"><code>tf.int64</code></a> scalar denoting the number of bytes
  to buffer. A value of 0 results in the default buffering values chosen
  based on the compression type.
* <b>`num_parallel_reads`</b>: (Optional.) A <a href="../../../../tf.md#int64"><code>tf.int64</code></a> scalar representing the
  number of files to read in parallel. If greater than one, the records of
  files read in parallel are outputted in an interleaved order. If your
  input pipeline is I/O bottlenecked, consider setting this parameter to a
  value greater than one to parallelize the I/O. If `None`, files will be
  read sequentially.



## Properties

<h3 id="output_classes"><code>output_classes</code></h3>

Returns the class of each component of an element of this dataset. (deprecated)

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `tf.compat.v1.data.get_output_classes(dataset)`.

The expected values are <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a> and <a href="../../../../tf/sparse/SparseTensor.md"><code>tf.SparseTensor</code></a>.

#### Returns:

A nested structure of Python `type` objects corresponding to each
component of an element of this dataset.


<h3 id="output_shapes"><code>output_shapes</code></h3>

Returns the shape of each component of an element of this dataset. (deprecated)

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `tf.compat.v1.data.get_output_shapes(dataset)`.

#### Returns:

A nested structure of <a href="../../../../tf/TensorShape.md"><code>tf.TensorShape</code></a> objects corresponding to each
component of an element of this dataset.


<h3 id="output_types"><code>output_types</code></h3>

Returns the type of each component of an element of this dataset. (deprecated)

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `tf.compat.v1.data.get_output_types(dataset)`.

#### Returns:

A nested structure of <a href="../../../../tf/dtypes/DType.md"><code>tf.DType</code></a> objects corresponding to each component
of an element of this dataset.




## Methods

<h3 id="__iter__"><code>__iter__</code></h3>

``` python
__iter__()
```

Creates an `Iterator` for enumerating the elements of this dataset.

The returned iterator implements the Python iterator protocol and therefore
can only be used in eager mode.

#### Returns:

An `Iterator` over the elements of this dataset.



#### Raises:


* <b>`RuntimeError`</b>: If not inside of tf.function and not executing eagerly.

<h3 id="apply"><code>apply</code></h3>

``` python
apply(transformation_func)
```

Applies a transformation function to this dataset.

`apply` enables chaining of custom `Dataset` transformations, which are
represented as functions that take one `Dataset` argument and return a
transformed `Dataset`.

#### For example:



```
dataset = (dataset.map(lambda x: x ** 2)
           .apply(group_by_window(key_func, reduce_func, window_size))
           .map(lambda x: x ** 3))
```

#### Args:


* <b>`transformation_func`</b>: A function that takes one `Dataset` argument and
  returns a `Dataset`.


#### Returns:


* <b>`Dataset`</b>: The `Dataset` returned by applying `transformation_func` to this
    dataset.

<h3 id="batch"><code>batch</code></h3>

``` python
batch(
    batch_size,
    drop_remainder=False
)
```

Combines consecutive elements of this dataset into batches.

The tensors in the resulting element will have an additional outer
dimension, which will be `batch_size` (or `N % batch_size` for the last
element if `batch_size` does not divide the number of input elements `N`
evenly and `drop_remainder` is `False`). If your program depends on the
batches having the same outer dimension, you should set the `drop_remainder`
argument to `True` to prevent the smaller batch from being produced.

#### Args:


* <b>`batch_size`</b>: A <a href="../../../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the number of
  consecutive elements of this dataset to combine in a single batch.
* <b>`drop_remainder`</b>: (Optional.) A <a href="../../../../tf.md#bool"><code>tf.bool</code></a> scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing
  whether the last batch should be dropped in the case it has fewer than
  `batch_size` elements; the default behavior is not to drop the smaller
  batch.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="cache"><code>cache</code></h3>

``` python
cache(filename='')
```

Caches the elements in this dataset.


#### Args:


* <b>`filename`</b>: A <a href="../../../../tf.md#string"><code>tf.string</code></a> scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the name of a
  directory on the filesystem to use for caching tensors in this Dataset.
  If a filename is not provided, the dataset will be cached in memory.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="concatenate"><code>concatenate</code></h3>

``` python
concatenate(dataset)
```

Creates a `Dataset` by concatenating given dataset with this dataset.

```python
a = Dataset.range(1, 4)  # ==> [ 1, 2, 3 ]
b = Dataset.range(4, 8)  # ==> [ 4, 5, 6, 7 ]

# Input dataset and dataset to be concatenated should have same
# nested structures and output types.
# c = Dataset.range(8, 14).batch(2)  # ==> [ [8, 9], [10, 11], [12, 13] ]
# d = Dataset.from_tensor_slices([14.0, 15.0, 16.0])
# a.concatenate(c) and a.concatenate(d) would result in error.

a.concatenate(b)  # ==> [ 1, 2, 3, 4, 5, 6, 7 ]
```

#### Args:


* <b>`dataset`</b>: `Dataset` to be concatenated.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="enumerate"><code>enumerate</code></h3>

``` python
enumerate(start=0)
```

Enumerates the elements of this dataset.

It is similar to python's `enumerate`.

#### For example:



```python
# NOTE: The following examples use `{ ... }` to represent the
# contents of a dataset.
a = { 1, 2, 3 }
b = { (7, 8), (9, 10) }

# The nested structure of the `datasets` argument determines the
# structure of elements in the resulting dataset.
a.enumerate(start=5)) == { (5, 1), (6, 2), (7, 3) }
b.enumerate() == { (0, (7, 8)), (1, (9, 10)) }
```

#### Args:


* <b>`start`</b>: A <a href="../../../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the start value for
  enumeration.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="filter"><code>filter</code></h3>

``` python
filter(predicate)
```

Filters this dataset according to `predicate`.

```python
d = tf.data.Dataset.from_tensor_slices([1, 2, 3])

d = d.filter(lambda x: x < 3)  # ==> [1, 2]

# `tf.math.equal(x, y)` is required for equality comparison
def filter_fn(x):
  return tf.math.equal(x, 1)

d = d.filter(filter_fn)  # ==> [1]
```

#### Args:


* <b>`predicate`</b>: A function mapping a nested structure of tensors (having shapes
  and types defined by `self.output_shapes` and `self.output_types`) to a
  scalar <a href="../../../../tf.md#bool"><code>tf.bool</code></a> tensor.


#### Returns:


* <b>`Dataset`</b>: The `Dataset` containing the elements of this dataset for which
    `predicate` is `True`.

<h3 id="filter_with_legacy_function"><code>filter_with_legacy_function</code></h3>

``` python
filter_with_legacy_function(predicate)
```

Filters this dataset according to `predicate`. (deprecated)

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `tf.data.Dataset.filter()

NOTE: This is an escape hatch for existing uses of `filter` that do not work
with V2 functions. New uses are strongly discouraged and existing uses
should migrate to `filter` as this method will be removed in V2.

#### Args:


* <b>`predicate`</b>: A function mapping a nested structure of tensors (having shapes
  and types defined by `self.output_shapes` and `self.output_types`) to a
  scalar <a href="../../../../tf.md#bool"><code>tf.bool</code></a> tensor.


#### Returns:


* <b>`Dataset`</b>: The `Dataset` containing the elements of this dataset for which
    `predicate` is `True`.

<h3 id="flat_map"><code>flat_map</code></h3>

``` python
flat_map(map_func)
```

Maps `map_func` across this dataset and flattens the result.

Use `flat_map` if you want to make sure that the order of your dataset
stays the same. For example, to flatten a dataset of batches into a
dataset of their elements:

```python
a = Dataset.from_tensor_slices([ [1, 2, 3], [4, 5, 6], [7, 8, 9] ])

a.flat_map(lambda x: Dataset.from_tensor_slices(x + 1)) # ==>
#  [ 2, 3, 4, 5, 6, 7, 8, 9, 10 ]
```

`tf.data.Dataset.interleave()` is a generalization of `flat_map`, since
`flat_map` produces the same output as
`tf.data.Dataset.interleave(cycle_length=1)`

#### Args:


* <b>`map_func`</b>: A function mapping a nested structure of tensors (having shapes
  and types defined by `self.output_shapes` and `self.output_types`) to a
  `Dataset`.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="from_generator"><code>from_generator</code></h3>

``` python
from_generator(
    generator,
    output_types,
    output_shapes=None,
    args=None
)
```

Creates a `Dataset` whose elements are generated by `generator`.

The `generator` argument must be a callable object that returns
an object that support the `iter()` protocol (e.g. a generator function).
The elements generated by `generator` must be compatible with the given
`output_types` and (optional) `output_shapes` arguments.

#### For example:



```python
import itertools
tf.compat.v1.enable_eager_execution()

def gen():
  for i in itertools.count(1):
    yield (i, [1] * i)

ds = tf.data.Dataset.from_generator(
    gen, (tf.int64, tf.int64), (tf.TensorShape([]), tf.TensorShape([None])))

for value in ds.take(2):
  print value
# (1, array([1]))
# (2, array([1, 1]))
```

NOTE: The current implementation of `Dataset.from_generator()` uses
<a href="../../../../tf/compat/v1/py_func.md"><code>tf.compat.v1.py_func</code></a> and inherits the same constraints. In particular, it
requires the `Dataset`- and `Iterator`-related operations to be placed
on a device in the same process as the Python program that called
`Dataset.from_generator()`. The body of `generator` will not be
serialized in a `GraphDef`, and you should not use this method if you
need to serialize your model and restore it in a different environment.

NOTE: If `generator` depends on mutable global variables or other external
state, be aware that the runtime may invoke `generator` multiple times
(in order to support repeating the `Dataset`) and at any time
between the call to `Dataset.from_generator()` and the production of the
first element from the generator. Mutating global variables or external
state can cause undefined behavior, and we recommend that you explicitly
cache any external state in `generator` before calling
`Dataset.from_generator()`.

#### Args:


* <b>`generator`</b>: A callable object that returns an object that supports the
  `iter()` protocol. If `args` is not specified, `generator` must take no
  arguments; otherwise it must take as many arguments as there are values
  in `args`.
* <b>`output_types`</b>: A nested structure of <a href="../../../../tf/dtypes/DType.md"><code>tf.DType</code></a> objects corresponding to
  each component of an element yielded by `generator`.
* <b>`output_shapes`</b>: (Optional.) A nested structure of <a href="../../../../tf/TensorShape.md"><code>tf.TensorShape</code></a> objects
  corresponding to each component of an element yielded by `generator`.
* <b>`args`</b>: (Optional.) A tuple of <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a> objects that will be evaluated
  and passed to `generator` as NumPy-array arguments.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="from_sparse_tensor_slices"><code>from_sparse_tensor_slices</code></h3>

``` python
from_sparse_tensor_slices(sparse_tensor)
```

Splits each rank-N <a href="../../../../tf/sparse/SparseTensor.md"><code>tf.SparseTensor</code></a> in this dataset row-wise. (deprecated)

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `tf.data.Dataset.from_tensor_slices()`.

#### Args:


* <b>`sparse_tensor`</b>: A <a href="../../../../tf/sparse/SparseTensor.md"><code>tf.SparseTensor</code></a>.


#### Returns:


* <b>`Dataset`</b>: A `Dataset` of rank-(N-1) sparse tensors.

<h3 id="from_tensor_slices"><code>from_tensor_slices</code></h3>

``` python
from_tensor_slices(tensors)
```

Creates a `Dataset` whose elements are slices of the given tensors.

Note that if `tensors` contains a NumPy array, and eager execution is not
enabled, the values will be embedded in the graph as one or more
<a href="../../../../tf/constant.md"><code>tf.constant</code></a> operations. For large datasets (> 1 GB), this can waste
memory and run into byte limits of graph serialization. If `tensors`
contains one or more large NumPy arrays, consider the alternative described
in [this guide](
https://tensorflow.org/guide/datasets#consuming_numpy_arrays).

#### Args:


* <b>`tensors`</b>: A nested structure of tensors, each having the same size in the
  0th dimension.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="from_tensors"><code>from_tensors</code></h3>

``` python
from_tensors(tensors)
```

Creates a `Dataset` with a single element, comprising the given tensors.

Note that if `tensors` contains a NumPy array, and eager execution is not
enabled, the values will be embedded in the graph as one or more
<a href="../../../../tf/constant.md"><code>tf.constant</code></a> operations. For large datasets (> 1 GB), this can waste
memory and run into byte limits of graph serialization. If `tensors`
contains one or more large NumPy arrays, consider the alternative described
in [this
guide](https://tensorflow.org/guide/datasets#consuming_numpy_arrays).

#### Args:


* <b>`tensors`</b>: A nested structure of tensors.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="interleave"><code>interleave</code></h3>

``` python
interleave(
    map_func,
    cycle_length=AUTOTUNE,
    block_length=1,
    num_parallel_calls=None
)
```

Maps `map_func` across this dataset, and interleaves the results.

For example, you can use `Dataset.interleave()` to process many input files
concurrently:

```python
# Preprocess 4 files concurrently, and interleave blocks of 16 records from
# each file.
filenames = ["/var/data/file1.txt", "/var/data/file2.txt", ...]
dataset = (Dataset.from_tensor_slices(filenames)
           .interleave(lambda x:
               TextLineDataset(x).map(parse_fn, num_parallel_calls=1),
               cycle_length=4, block_length=16))
```

The `cycle_length` and `block_length` arguments control the order in which
elements are produced. `cycle_length` controls the number of input elements
that are processed concurrently. If you set `cycle_length` to 1, this
transformation will handle one input element at a time, and will produce
identical results to <a href="../../../../tf/data/Dataset.md#flat_map"><code>tf.data.Dataset.flat_map</code></a>. In general,
this transformation will apply `map_func` to `cycle_length` input elements,
open iterators on the returned `Dataset` objects, and cycle through them
producing `block_length` consecutive elements from each iterator, and
consuming the next input element each time it reaches the end of an
iterator.

#### For example:



```python
a = Dataset.range(1, 6)  # ==> [ 1, 2, 3, 4, 5 ]

# NOTE: New lines indicate "block" boundaries.
a.interleave(lambda x: Dataset.from_tensors(x).repeat(6),
            cycle_length=2, block_length=4)  # ==> [1, 1, 1, 1,
                                             #      2, 2, 2, 2,
                                             #      1, 1,
                                             #      2, 2,
                                             #      3, 3, 3, 3,
                                             #      4, 4, 4, 4,
                                             #      3, 3,
                                             #      4, 4,
                                             #      5, 5, 5, 5,
                                             #      5, 5]
```

NOTE: The order of elements yielded by this transformation is
deterministic, as long as `map_func` is a pure function. If
`map_func` contains any stateful operations, the order in which
that state is accessed is undefined.

#### Args:


* <b>`map_func`</b>: A function mapping a nested structure of tensors (having shapes
  and types defined by `self.output_shapes` and `self.output_types`) to a
  `Dataset`.
* <b>`cycle_length`</b>: (Optional.) The number of input elements that will be
  processed concurrently. If not specified, the value will be derived from
  the number of available CPU cores. If the `num_parallel_calls` argument
  is set to <a href="../../../../tf/data/experimental.md#AUTOTUNE"><code>tf.data.experimental.AUTOTUNE</code></a>, the `cycle_length` argument
  also identifies the maximum degree of parallelism.
* <b>`block_length`</b>: (Optional.) The number of consecutive elements to produce
  from each input element before cycling to another input element.
* <b>`num_parallel_calls`</b>: (Optional.) If specified, the implementation creates a
  threadpool, which is used to fetch inputs from cycle elements
  asynchronously and in parallel. The default behavior is to fetch inputs
  from cycle elements synchronously with no parallelism. If the value
  <a href="../../../../tf/data/experimental.md#AUTOTUNE"><code>tf.data.experimental.AUTOTUNE</code></a> is used, then the number of parallel
  calls is set dynamically based on available CPU.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="list_files"><code>list_files</code></h3>

``` python
list_files(
    file_pattern,
    shuffle=None,
    seed=None
)
```

A dataset of all files matching one or more glob patterns.

NOTE: The default behavior of this method is to return filenames in
a non-deterministic random shuffled order. Pass a `seed` or `shuffle=False`
to get results in a deterministic order.

#### Example:

If we had the following files on our filesystem:
  - /path/to/dir/a.txt
  - /path/to/dir/b.py
  - /path/to/dir/c.py
If we pass "/path/to/dir/*.py" as the directory, the dataset
would produce:
  - /path/to/dir/b.py
  - /path/to/dir/c.py



#### Args:


* <b>`file_pattern`</b>: A string, a list of strings, or a <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a> of string type
  (scalar or vector), representing the filename glob (i.e. shell wildcard)
  pattern(s) that will be matched.
* <b>`shuffle`</b>: (Optional.) If `True`, the file names will be shuffled randomly.
  Defaults to `True`.
* <b>`seed`</b>: (Optional.) A <a href="../../../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the random
  seed that will be used to create the distribution. See
  <a href="../../../../tf/compat/v1/set_random_seed.md"><code>tf.compat.v1.set_random_seed</code></a> for behavior.


#### Returns:


* <b>`Dataset`</b>: A `Dataset` of strings corresponding to file names.

<h3 id="make_initializable_iterator"><code>make_initializable_iterator</code></h3>

``` python
make_initializable_iterator(shared_name=None)
```

Creates an `Iterator` for enumerating the elements of this dataset. (deprecated)

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `for ... in dataset:` to iterate over a dataset. If using <a href="../../../../tf/estimator.md"><code>tf.estimator</code></a>, return the `Dataset` object directly from your input function. As a last resort, you can use `tf.compat.v1.data.make_initializable_iterator(dataset)`.

Note: The returned iterator will be in an uninitialized state,
and you must run the `iterator.initializer` operation before using it:

```python
dataset = ...
iterator = dataset.make_initializable_iterator()
# ...
sess.run(iterator.initializer)
```

#### Args:


* <b>`shared_name`</b>: (Optional.) If non-empty, the returned iterator will be
  shared under the given name across multiple sessions that share the same
  devices (e.g. when using a remote server).


#### Returns:

An `Iterator` over the elements of this dataset.



#### Raises:


* <b>`RuntimeError`</b>: If eager execution is enabled.

<h3 id="make_one_shot_iterator"><code>make_one_shot_iterator</code></h3>

``` python
make_one_shot_iterator()
```

Creates an `Iterator` for enumerating the elements of this dataset. (deprecated)

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `for ... in dataset:` to iterate over a dataset. If using <a href="../../../../tf/estimator.md"><code>tf.estimator</code></a>, return the `Dataset` object directly from your input function. As a last resort, you can use `tf.compat.v1.data.make_one_shot_iterator(dataset)`.

Note: The returned iterator will be initialized automatically.
A "one-shot" iterator does not currently support re-initialization.

#### Returns:

An `Iterator` over the elements of this dataset.


<h3 id="map"><code>map</code></h3>

``` python
map(
    map_func,
    num_parallel_calls=None
)
```

Maps `map_func` across the elements of this dataset.

This transformation applies `map_func` to each element of this dataset, and
returns a new dataset containing the transformed elements, in the same
order as they appeared in the input.

#### For example:



```python
a = Dataset.range(1, 6)  # ==> [ 1, 2, 3, 4, 5 ]

a.map(lambda x: x + 1)  # ==> [ 2, 3, 4, 5, 6 ]
```

The input signature of `map_func` is determined by the structure of each
element in this dataset. For example:

```python
# NOTE: The following examples use `{ ... }` to represent the
# contents of a dataset.
# Each element is a `tf.Tensor` object.
a = { 1, 2, 3, 4, 5 }
# `map_func` takes a single argument of type `tf.Tensor` with the same
# shape and dtype.
result = a.map(lambda x: ...)

# Each element is a tuple containing two `tf.Tensor` objects.
b = { (1, "foo"), (2, "bar"), (3, "baz") }
# `map_func` takes two arguments of type `tf.Tensor`.
result = b.map(lambda x_int, y_str: ...)

# Each element is a dictionary mapping strings to `tf.Tensor` objects.
c = { {"a": 1, "b": "foo"}, {"a": 2, "b": "bar"}, {"a": 3, "b": "baz"} }
# `map_func` takes a single argument of type `dict` with the same keys as
# the elements.
result = c.map(lambda d: ...)
```

The value or values returned by `map_func` determine the structure of each
element in the returned dataset.

```python
# `map_func` returns a scalar `tf.Tensor` of type `tf.float32`.
def f(...):
  return tf.constant(37.0)
result = dataset.map(f)
result.output_classes == tf.Tensor
result.output_types == tf.float32
result.output_shapes == []  # scalar

# `map_func` returns two `tf.Tensor` objects.
def g(...):
  return tf.constant(37.0), tf.constant(["Foo", "Bar", "Baz"])
result = dataset.map(g)
result.output_classes == (tf.Tensor, tf.Tensor)
result.output_types == (tf.float32, tf.string)
result.output_shapes == ([], [3])

# Python primitives, lists, and NumPy arrays are implicitly converted to
# `tf.Tensor`.
def h(...):
  return 37.0, ["Foo", "Bar", "Baz"], np.array([1.0, 2.0] dtype=np.float64)
result = dataset.map(h)
result.output_classes == (tf.Tensor, tf.Tensor, tf.Tensor)
result.output_types == (tf.float32, tf.string, tf.float64)
result.output_shapes == ([], [3], [2])

# `map_func` can return nested structures.
def i(...):
  return {"a": 37.0, "b": [42, 16]}, "foo"
result.output_classes == ({"a": tf.Tensor, "b": tf.Tensor}, tf.Tensor)
result.output_types == ({"a": tf.float32, "b": tf.int32}, tf.string)
result.output_shapes == ({"a": [], "b": [2]}, [])
```

In addition to <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a> objects, `map_func` can accept as arguments and
return <a href="../../../../tf/sparse/SparseTensor.md"><code>tf.SparseTensor</code></a> objects.

Note that irrespective of the context in which `map_func` is defined (eager
vs. graph), tf.data traces the function and executes it as a graph. To use
Python code inside of the function you have two options:

1) Rely on AutoGraph to convert Python code into an equivalent graph
computation. The downside of this approach is that AutoGraph can convert
some but not all Python code.

2) Use <a href="../../../../tf/py_function.md"><code>tf.py_function</code></a>, which allows you to write arbitrary Python code but
will generally result in worse performance than 1).

#### Args:


* <b>`map_func`</b>: A function mapping a nested structure of tensors (having shapes
  and types defined by `self.output_shapes` and `self.output_types`) to
  another nested structure of tensors.
* <b>`num_parallel_calls`</b>: (Optional.) A <a href="../../../../tf.md#int32"><code>tf.int32</code></a> scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>,
  representing the number elements to process asynchronously in parallel.
  If not specified, elements will be processed sequentially. If the value
  <a href="../../../../tf/data/experimental.md#AUTOTUNE"><code>tf.data.experimental.AUTOTUNE</code></a> is used, then the number of parallel
  calls is set dynamically based on available CPU.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="map_with_legacy_function"><code>map_with_legacy_function</code></h3>

``` python
map_with_legacy_function(
    map_func,
    num_parallel_calls=None
)
```

Maps `map_func` across the elements of this dataset. (deprecated)

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `tf.data.Dataset.map()

NOTE: This is an escape hatch for existing uses of `map` that do not work
with V2 functions. New uses are strongly discouraged and existing uses
should migrate to `map` as this method will be removed in V2.

#### Args:


* <b>`map_func`</b>: A function mapping a nested structure of tensors (having shapes
  and types defined by `self.output_shapes` and `self.output_types`) to
  another nested structure of tensors.
* <b>`num_parallel_calls`</b>: (Optional.) A <a href="../../../../tf.md#int32"><code>tf.int32</code></a> scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>,
  representing the number elements to process asynchronously in parallel.
  If not specified, elements will be processed sequentially. If the value
  <a href="../../../../tf/data/experimental.md#AUTOTUNE"><code>tf.data.experimental.AUTOTUNE</code></a> is used, then the number of parallel
  calls is set dynamically based on available CPU.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="options"><code>options</code></h3>

``` python
options()
```

Returns the options for this dataset and its inputs.


#### Returns:

A <a href="../../../../tf/data/Options.md"><code>tf.data.Options</code></a> object representing the dataset options.


<h3 id="padded_batch"><code>padded_batch</code></h3>

``` python
padded_batch(
    batch_size,
    padded_shapes,
    padding_values=None,
    drop_remainder=False
)
```

Combines consecutive elements of this dataset into padded batches.

This transformation combines multiple consecutive elements of the input
dataset into a single element.

Like <a href="../../../../tf/data/Dataset.md#batch"><code>tf.data.Dataset.batch</code></a>, the tensors in the resulting element will
have an additional outer dimension, which will be `batch_size` (or
`N % batch_size` for the last element if `batch_size` does not divide the
number of input elements `N` evenly and `drop_remainder` is `False`). If
your program depends on the batches having the same outer dimension, you
should set the `drop_remainder` argument to `True` to prevent the smaller
batch from being produced.

Unlike <a href="../../../../tf/data/Dataset.md#batch"><code>tf.data.Dataset.batch</code></a>, the input elements to be batched may have
different shapes, and this transformation will pad each component to the
respective shape in `padding_shapes`. The `padding_shapes` argument
determines the resulting shape for each dimension of each component in an
output element:

* If the dimension is a constant (e.g. `tf.compat.v1.Dimension(37)`), the
component
  will be padded out to that length in that dimension.
* If the dimension is unknown (e.g. `tf.compat.v1.Dimension(None)`), the
component
  will be padded out to the maximum length of all elements in that
  dimension.

See also <a href="../../../../tf/data/experimental/dense_to_sparse_batch.md"><code>tf.data.experimental.dense_to_sparse_batch</code></a>, which combines
elements that may have different shapes into a <a href="../../../../tf/sparse/SparseTensor.md"><code>tf.SparseTensor</code></a>.

#### Args:


* <b>`batch_size`</b>: A <a href="../../../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the number of
  consecutive elements of this dataset to combine in a single batch.
* <b>`padded_shapes`</b>: A nested structure of <a href="../../../../tf/TensorShape.md"><code>tf.TensorShape</code></a> or <a href="../../../../tf.md#int64"><code>tf.int64</code></a> vector
  tensor-like objects representing the shape to which the respective
  component of each input element should be padded prior to batching. Any
  unknown dimensions (e.g. `tf.compat.v1.Dimension(None)` in a
  <a href="../../../../tf/TensorShape.md"><code>tf.TensorShape</code></a> or `-1` in a tensor-like object) will be padded to the
  maximum size of that dimension in each batch.
* <b>`padding_values`</b>: (Optional.) A nested structure of scalar-shaped
  <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the padding values to use for the respective
  components.  Defaults are `0` for numeric types and the empty string for
  string types.
* <b>`drop_remainder`</b>: (Optional.) A <a href="../../../../tf.md#bool"><code>tf.bool</code></a> scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing
  whether the last batch should be dropped in the case it has fewer than
  `batch_size` elements; the default behavior is not to drop the smaller
  batch.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="prefetch"><code>prefetch</code></h3>

``` python
prefetch(buffer_size)
```

Creates a `Dataset` that prefetches elements from this dataset.

Note: Like other `Dataset` methods, prefetch operates on the
elements of the input dataset. It has no concept of examples vs. batches.
`examples.prefetch(2)` will prefetch two elements (2 examples),
while `examples.batch(20).prefetch(2)` will prefetch 2 elements
(2 batches, of 20 examples each).

#### Args:


* <b>`buffer_size`</b>: A <a href="../../../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the maximum
  number of elements that will be buffered when prefetching.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="range"><code>range</code></h3>

``` python
range(*args)
```

Creates a `Dataset` of a step-separated range of values.


#### For example:



```python
Dataset.range(5) == [0, 1, 2, 3, 4]
Dataset.range(2, 5) == [2, 3, 4]
Dataset.range(1, 5, 2) == [1, 3]
Dataset.range(1, 5, -2) == []
Dataset.range(5, 1) == []
Dataset.range(5, 1, -2) == [5, 3]
```

#### Args:


* <b>`*args`</b>: follows the same semantics as python's xrange.
  len(args) == 1 -> start = 0, stop = args[0], step = 1
  len(args) == 2 -> start = args[0], stop = args[1], step = 1
  len(args) == 3 -> start = args[0], stop = args[1, stop = args[2]


#### Returns:


* <b>`Dataset`</b>: A `RangeDataset`.


#### Raises:


* <b>`ValueError`</b>: if len(args) == 0.

<h3 id="reduce"><code>reduce</code></h3>

``` python
reduce(
    initial_state,
    reduce_func
)
```

Reduces the input dataset to a single element.

The transformation calls `reduce_func` successively on every element of
the input dataset until the dataset is exhausted, aggregating information in
its internal state. The `initial_state` argument is used for the initial
state and the final state is returned as the result.

#### For example:


- `tf.data.Dataset.range(5).reduce(np.int64(0), lambda x, _: x + 1)`
  produces `5`
- `tf.data.Dataset.range(5).reduce(np.int64(0), lambda x, y: x + y)`
  produces `10`

#### Args:


* <b>`initial_state`</b>: A nested structure of tensors, representing the initial
  state of the transformation.
* <b>`reduce_func`</b>: A function that maps `(old_state, input_element)` to
  `new_state`. It must take two arguments and return a nested structure of
  tensors. The structure of `new_state` must match the structure of
  `initial_state`.


#### Returns:

A nested structure of <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a> objects, corresponding to the final
state of the transformation.


<h3 id="repeat"><code>repeat</code></h3>

``` python
repeat(count=None)
```

Repeats this dataset `count` times.

NOTE: If this dataset is a function of global state (e.g. a random number
generator), then different repetitions may produce different elements.

#### Args:


* <b>`count`</b>: (Optional.) A <a href="../../../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the
  number of times the dataset should be repeated. The default behavior (if
  `count` is `None` or `-1`) is for the dataset be repeated indefinitely.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="shard"><code>shard</code></h3>

``` python
shard(
    num_shards,
    index
)
```

Creates a `Dataset` that includes only 1/`num_shards` of this dataset.

This dataset operator is very useful when running distributed training, as
it allows each worker to read a unique subset.

When reading a single input file, you can skip elements as follows:

```python
d = tf.data.TFRecordDataset(input_file)
d = d.shard(num_workers, worker_index)
d = d.repeat(num_epochs)
d = d.shuffle(shuffle_buffer_size)
d = d.map(parser_fn, num_parallel_calls=num_map_threads)
```

#### Important caveats:



- Be sure to shard before you use any randomizing operator (such as
  shuffle).
- Generally it is best if the shard operator is used early in the dataset
  pipeline. For example, when reading from a set of TFRecord files, shard
  before converting the dataset to input samples. This avoids reading every
  file on every worker. The following is an example of an efficient
  sharding strategy within a complete pipeline:

```python
d = Dataset.list_files(pattern)
d = d.shard(num_workers, worker_index)
d = d.repeat(num_epochs)
d = d.shuffle(shuffle_buffer_size)
d = d.interleave(tf.data.TFRecordDataset,
                 cycle_length=num_readers, block_length=1)
d = d.map(parser_fn, num_parallel_calls=num_map_threads)
```

#### Args:


* <b>`num_shards`</b>: A <a href="../../../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the number of
  shards operating in parallel.
* <b>`index`</b>: A <a href="../../../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the worker index.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.


#### Raises:


* <b>`InvalidArgumentError`</b>: if `num_shards` or `index` are illegal values.
  Note: error checking is done on a best-effort basis, and errors aren't
  guaranteed to be caught upon dataset creation. (e.g. providing in a
  placeholder tensor bypasses the early checking, and will instead result
  in an error during a session.run call.)

<h3 id="shuffle"><code>shuffle</code></h3>

``` python
shuffle(
    buffer_size,
    seed=None,
    reshuffle_each_iteration=None
)
```

Randomly shuffles the elements of this dataset.

This dataset fills a buffer with `buffer_size` elements, then randomly
samples elements from this buffer, replacing the selected elements with new
elements. For perfect shuffling, a buffer size greater than or equal to the
full size of the dataset is required.

For instance, if your dataset contains 10,000 elements but `buffer_size` is
set to 1,000, then `shuffle` will initially select a random element from
only the first 1,000 elements in the buffer. Once an element is selected,
its space in the buffer is replaced by the next (i.e. 1,001-st) element,
maintaining the 1,000 element buffer.

#### Args:


* <b>`buffer_size`</b>: A <a href="../../../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the number of
  elements from this dataset from which the new dataset will sample.
* <b>`seed`</b>: (Optional.) A <a href="../../../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the random
  seed that will be used to create the distribution. See
  <a href="../../../../tf/compat/v1/set_random_seed.md"><code>tf.compat.v1.set_random_seed</code></a> for behavior.
* <b>`reshuffle_each_iteration`</b>: (Optional.) A boolean, which if true indicates
  that the dataset should be pseudorandomly reshuffled each time it is
  iterated over. (Defaults to `True`.)


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="skip"><code>skip</code></h3>

``` python
skip(count)
```

Creates a `Dataset` that skips `count` elements from this dataset.


#### Args:


* <b>`count`</b>: A <a href="../../../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the number of
  elements of this dataset that should be skipped to form the new dataset.
  If `count` is greater than the size of this dataset, the new dataset
  will contain no elements.  If `count` is -1, skips the entire dataset.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="take"><code>take</code></h3>

``` python
take(count)
```

Creates a `Dataset` with at most `count` elements from this dataset.


#### Args:


* <b>`count`</b>: A <a href="../../../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the number of
  elements of this dataset that should be taken to form the new dataset.
  If `count` is -1, or if `count` is greater than the size of this
  dataset, the new dataset will contain all elements of this dataset.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.

<h3 id="unbatch"><code>unbatch</code></h3>

``` python
unbatch()
```

Splits elements of a dataset into multiple elements.

For example, if elements of the dataset are shaped `[B, a0, a1, ...]`,
where `B` may vary for each input element, then for each element in the
dataset, the unbatched dataset will contain `B` consecutive elements
of shape `[a0, a1, ...]`.

```python
# NOTE: The following example uses `{ ... }` to represent the contents
# of a dataset.
ds = { ['a', 'b', 'c'], ['a', 'b'], ['a', 'b', 'c', 'd'] }

ds.unbatch() == {'a', 'b', 'c', 'a', 'b', 'a', 'b', 'c', 'd'}
```

#### Returns:

A `Dataset` transformation function, which can be passed to
<a href="../../../../tf/data/Dataset.md#apply"><code>tf.data.Dataset.apply</code></a>.


<h3 id="window"><code>window</code></h3>

``` python
window(
    size,
    shift=None,
    stride=1,
    drop_remainder=False
)
```

Combines (nests of) input elements into a dataset of (nests of) windows.

A "window" is a finite dataset of flat elements of size `size` (or possibly
fewer if there are not enough input elements to fill the window and
`drop_remainder` evaluates to false).

The `stride` argument determines the stride of the input elements, and the
`shift` argument determines the shift of the window.

For example, letting {...} to represent a Dataset:

- `tf.data.Dataset.range(7).window(2)` produces
  `{{0, 1}, {2, 3}, {4, 5}, {6}}`
- `tf.data.Dataset.range(7).window(3, 2, 1, True)` produces
  `{{0, 1, 2}, {2, 3, 4}, {4, 5, 6}}`
- `tf.data.Dataset.range(7).window(3, 1, 2, True)` produces
  `{{0, 2, 4}, {1, 3, 5}, {2, 4, 6}}`

Note that when the `window` transformation is applied to a dataset of
nested elements, it produces a dataset of nested windows.

#### For example:



- `tf.data.Dataset.from_tensor_slices((range(4), range(4)).window(2)`
  produces `{({0, 1}, {0, 1}), ({2, 3}, {2, 3})}`
- `tf.data.Dataset.from_tensor_slices({"a": range(4)}).window(2)`
  produces `{{"a": {0, 1}}, {"a": {2, 3}}}`

#### Args:


* <b>`size`</b>: A <a href="../../../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the number of elements
  of the input dataset to combine into a window.
* <b>`shift`</b>: (Optional.) A <a href="../../../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the
  forward shift of the sliding window in each iteration. Defaults to
  `size`.
* <b>`stride`</b>: (Optional.) A <a href="../../../../tf.md#int64"><code>tf.int64</code></a> scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing the
  stride of the input elements in the sliding window.
* <b>`drop_remainder`</b>: (Optional.) A <a href="../../../../tf.md#bool"><code>tf.bool</code></a> scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>, representing
  whether a window should be dropped in case its size is smaller than
  `window_size`.


#### Returns:


* <b>`Dataset`</b>: A `Dataset` of (nests of) windows -- a finite datasets of flat
  elements created from the (nests of) input elements.

<h3 id="with_options"><code>with_options</code></h3>

``` python
with_options(options)
```

Returns a new <a href="../../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> with the given options set.

The options are "global" in the sense they apply to the entire dataset.
If options are set multiple times, they are merged as long as different
options do not use different non-default values.

#### Args:


* <b>`options`</b>: A <a href="../../../../tf/data/Options.md"><code>tf.data.Options</code></a> that identifies the options the use.


#### Returns:


* <b>`Dataset`</b>: A `Dataset` with the given options.


#### Raises:


* <b>`ValueError`</b>: when an option is set more than once to a non-default value

<h3 id="zip"><code>zip</code></h3>

``` python
zip(datasets)
```

Creates a `Dataset` by zipping together the given datasets.

This method has similar semantics to the built-in `zip()` function
in Python, with the main difference being that the `datasets`
argument can be an arbitrary nested structure of `Dataset` objects.
For example:

```python
a = Dataset.range(1, 4)  # ==> [ 1, 2, 3 ]
b = Dataset.range(4, 7)  # ==> [ 4, 5, 6 ]
c = Dataset.range(7, 13).batch(2)  # ==> [ [7, 8], [9, 10], [11, 12] ]
d = Dataset.range(13, 15)  # ==> [ 13, 14 ]

# The nested structure of the `datasets` argument determines the
# structure of elements in the resulting dataset.
Dataset.zip((a, b))  # ==> [ (1, 4), (2, 5), (3, 6) ]
Dataset.zip((b, a))  # ==> [ (4, 1), (5, 2), (6, 3) ]

# The `datasets` argument may contain an arbitrary number of
# datasets.
Dataset.zip((a, b, c))  # ==> [ (1, 4, [7, 8]),
                        #       (2, 5, [9, 10]),
                        #       (3, 6, [11, 12]) ]

# The number of elements in the resulting dataset is the same as
# the size of the smallest dataset in `datasets`.
Dataset.zip((a, d))  # ==> [ (1, 13), (2, 14) ]
```

#### Args:


* <b>`datasets`</b>: A nested structure of datasets.


#### Returns:


* <b>`Dataset`</b>: A `Dataset`.




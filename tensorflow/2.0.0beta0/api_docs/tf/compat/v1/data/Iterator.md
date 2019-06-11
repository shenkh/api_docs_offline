<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.data.Iterator" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="initializer"/>
<meta itemprop="property" content="output_classes"/>
<meta itemprop="property" content="output_shapes"/>
<meta itemprop="property" content="output_types"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="from_string_handle"/>
<meta itemprop="property" content="from_structure"/>
<meta itemprop="property" content="get_next"/>
<meta itemprop="property" content="make_initializer"/>
<meta itemprop="property" content="string_handle"/>
</div>

# tf.compat.v1.data.Iterator

## Class `Iterator`

Represents the state of iterating through a `Dataset`.





Defined in [`python/data/ops/iterator_ops.py`](/code/stable/tensorflow/python/data/ops/iterator_ops.py).

<!-- Placeholder for "Used in" -->


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    iterator_resource,
    initializer,
    output_types,
    output_shapes,
    output_classes
)
```

Creates a new iterator from the given iterator resource.

Note: Most users will not call this initializer directly, and will
instead use `Dataset.make_initializable_iterator()` or
`Dataset.make_one_shot_iterator()`.

#### Args:


* <b>`iterator_resource`</b>: A <a href="../../../../tf.md#resource"><code>tf.resource</code></a> scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a> representing the
  iterator.
* <b>`initializer`</b>: A <a href="../../../../tf/Operation.md"><code>tf.Operation</code></a> that should be run to initialize this
  iterator.
* <b>`output_types`</b>: A nested structure of <a href="../../../../tf/dtypes/DType.md"><code>tf.DType</code></a> objects corresponding to
  each component of an element of this iterator.
* <b>`output_shapes`</b>: A nested structure of <a href="../../../../tf/TensorShape.md"><code>tf.TensorShape</code></a> objects
  corresponding to each component of an element of this iterator.
* <b>`output_classes`</b>: A nested structure of Python `type` objects corresponding
  to each component of an element of this iterator.



## Properties

<h3 id="initializer"><code>initializer</code></h3>

A <a href="../../../../tf/Operation.md"><code>tf.Operation</code></a> that should be run to initialize this iterator.


#### Returns:

A <a href="../../../../tf/Operation.md"><code>tf.Operation</code></a> that should be run to initialize this iterator



#### Raises:


* <b>`ValueError`</b>: If this iterator initializes itself automatically.

<h3 id="output_classes"><code>output_classes</code></h3>

Returns the class of each component of an element of this iterator. (deprecated)

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `tf.compat.v1.data.get_output_classes(iterator)`.

The expected values are <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a> and <a href="../../../../tf/sparse/SparseTensor.md"><code>tf.SparseTensor</code></a>.

#### Returns:

A nested structure of Python `type` objects corresponding to each
component of an element of this dataset.


<h3 id="output_shapes"><code>output_shapes</code></h3>

Returns the shape of each component of an element of this iterator. (deprecated)

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `tf.compat.v1.data.get_output_shapes(iterator)`.

#### Returns:

A nested structure of <a href="../../../../tf/TensorShape.md"><code>tf.TensorShape</code></a> objects corresponding to each
component of an element of this dataset.


<h3 id="output_types"><code>output_types</code></h3>

Returns the type of each component of an element of this iterator. (deprecated)

Warning: THIS FUNCTION IS DEPRECATED. It will be removed in a future version.
Instructions for updating:
Use `tf.compat.v1.data.get_output_types(iterator)`.

#### Returns:

A nested structure of <a href="../../../../tf/dtypes/DType.md"><code>tf.DType</code></a> objects corresponding to each component
of an element of this dataset.




## Methods

<h3 id="from_string_handle"><code>from_string_handle</code></h3>

``` python
@staticmethod
from_string_handle(
    string_handle,
    output_types,
    output_shapes=None,
    output_classes=None
)
```

Creates a new, uninitialized `Iterator` based on the given handle.

This method allows you to define a "feedable" iterator where you can choose
between concrete iterators by feeding a value in a `tf.Session.run` call.
In that case, `string_handle` would be a <a href="../../../../tf/compat/v1/placeholder.md"><code>tf.compat.v1.placeholder</code></a>, and you
would
feed it with the value of `tf.data.Iterator.string_handle` in each step.

For example, if you had two iterators that marked the current position in
a training dataset and a test dataset, you could choose which to use in
each step as follows:

```python
train_iterator = tf.data.Dataset(...).make_one_shot_iterator()
train_iterator_handle = sess.run(train_iterator.string_handle())

test_iterator = tf.data.Dataset(...).make_one_shot_iterator()
test_iterator_handle = sess.run(test_iterator.string_handle())

handle = tf.compat.v1.placeholder(tf.string, shape=[])
iterator = tf.data.Iterator.from_string_handle(
    handle, train_iterator.output_types)

next_element = iterator.get_next()
loss = f(next_element)

train_loss = sess.run(loss, feed_dict={handle: train_iterator_handle})
test_loss = sess.run(loss, feed_dict={handle: test_iterator_handle})
```

#### Args:


* <b>`string_handle`</b>: A scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a> of type <a href="../../../../tf.md#string"><code>tf.string</code></a> that evaluates to
  a handle produced by the `Iterator.string_handle()` method.
* <b>`output_types`</b>: A nested structure of <a href="../../../../tf/dtypes/DType.md"><code>tf.DType</code></a> objects corresponding to
  each component of an element of this dataset.
* <b>`output_shapes`</b>: (Optional.) A nested structure of <a href="../../../../tf/TensorShape.md"><code>tf.TensorShape</code></a> objects
  corresponding to each component of an element of this dataset. If
  omitted, each component will have an unconstrainted shape.
* <b>`output_classes`</b>: (Optional.) A nested structure of Python `type` objects
  corresponding to each component of an element of this iterator. If
  omitted, each component is assumed to be of type <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>.


#### Returns:

An `Iterator`.


<h3 id="from_structure"><code>from_structure</code></h3>

``` python
@staticmethod
from_structure(
    output_types,
    output_shapes=None,
    shared_name=None,
    output_classes=None
)
```

Creates a new, uninitialized `Iterator` with the given structure.

This iterator-constructing method can be used to create an iterator that
is reusable with many different datasets.

The returned iterator is not bound to a particular dataset, and it has
no `initializer`. To initialize the iterator, run the operation returned by
`Iterator.make_initializer(dataset)`.

The following is an example

```python
iterator = Iterator.from_structure(tf.int64, tf.TensorShape([]))

dataset_range = Dataset.range(10)
range_initializer = iterator.make_initializer(dataset_range)

dataset_evens = dataset_range.filter(lambda x: x % 2 == 0)
evens_initializer = iterator.make_initializer(dataset_evens)

# Define a model based on the iterator; in this example, the model_fn
# is expected to take scalar tf.int64 Tensors as input (see
# the definition of 'iterator' above).
prediction, loss = model_fn(iterator.get_next())

# Train for `num_epochs`, where for each epoch, we first iterate over
# dataset_range, and then iterate over dataset_evens.
for _ in range(num_epochs):
  # Initialize the iterator to `dataset_range`
  sess.run(range_initializer)
  while True:
    try:
      pred, loss_val = sess.run([prediction, loss])
    except tf.errors.OutOfRangeError:
      break

  # Initialize the iterator to `dataset_evens`
  sess.run(evens_initializer)
  while True:
    try:
      pred, loss_val = sess.run([prediction, loss])
    except tf.errors.OutOfRangeError:
      break
```

#### Args:


* <b>`output_types`</b>: A nested structure of <a href="../../../../tf/dtypes/DType.md"><code>tf.DType</code></a> objects corresponding to
  each component of an element of this dataset.
* <b>`output_shapes`</b>: (Optional.) A nested structure of <a href="../../../../tf/TensorShape.md"><code>tf.TensorShape</code></a> objects
  corresponding to each component of an element of this dataset. If
  omitted, each component will have an unconstrainted shape.
* <b>`shared_name`</b>: (Optional.) If non-empty, this iterator will be shared under
  the given name across multiple sessions that share the same devices
  (e.g. when using a remote server).
* <b>`output_classes`</b>: (Optional.) A nested structure of Python `type` objects
  corresponding to each component of an element of this iterator. If
  omitted, each component is assumed to be of type <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>.


#### Returns:

An `Iterator`.



#### Raises:


* <b>`TypeError`</b>: If the structures of `output_shapes` and `output_types` are
  not the same.

<h3 id="get_next"><code>get_next</code></h3>

``` python
get_next(name=None)
```

Returns a nested structure of <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a>s representing the next element.

In graph mode, you should typically call this method *once* and use its
result as the input to another computation. A typical loop will then call
`tf.Session.run` on the result of that computation. The loop will terminate
when the `Iterator.get_next()` operation raises
<a href="../../../../tf/errors/OutOfRangeError.md"><code>tf.errors.OutOfRangeError</code></a>. The following skeleton shows how to use
this method when building a training loop:

```python
dataset = ...  # A <a href="../../../../tf/data/Dataset.md"><code>tf.data.Dataset</code></a> object.
iterator = dataset.make_initializable_iterator()
next_element = iterator.get_next()

# Build a TensorFlow graph that does something with each element.
loss = model_function(next_element)
optimizer = ...  # A <a href="../../../../tf/compat/v1/train/Optimizer.md"><code>tf.compat.v1.train.Optimizer</code></a> object.
train_op = optimizer.minimize(loss)

with tf.compat.v1.Session() as sess:
  try:
    while True:
      sess.run(train_op)
  except tf.errors.OutOfRangeError:
    pass
```

NOTE: It is legitimate to call `Iterator.get_next()` multiple times, e.g.
when you are distributing different elements to multiple devices in a single
step. However, a common pitfall arises when users call `Iterator.get_next()`
in each iteration of their training loop. `Iterator.get_next()` adds ops to
the graph, and executing each op allocates resources (including threads); as
a consequence, invoking it in every iteration of a training loop causes
slowdown and eventual resource exhaustion. To guard against this outcome, we
log a warning when the number of uses crosses a fixed threshold of
suspiciousness.

#### Args:


* <b>`name`</b>: (Optional.) A name for the created operation.


#### Returns:

A nested structure of <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a> objects.


<h3 id="make_initializer"><code>make_initializer</code></h3>

``` python
make_initializer(
    dataset,
    name=None
)
```

Returns a <a href="../../../../tf/Operation.md"><code>tf.Operation</code></a> that initializes this iterator on `dataset`.


#### Args:


* <b>`dataset`</b>: A `Dataset` with compatible structure to this iterator.
* <b>`name`</b>: (Optional.) A name for the created operation.


#### Returns:

A <a href="../../../../tf/Operation.md"><code>tf.Operation</code></a> that can be run to initialize this iterator on the given
`dataset`.



#### Raises:


* <b>`TypeError`</b>: If `dataset` and this iterator do not have a compatible
  element structure.

<h3 id="string_handle"><code>string_handle</code></h3>

``` python
string_handle(name=None)
```

Returns a string-valued <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a> that represents this iterator.


#### Args:


* <b>`name`</b>: (Optional.) A name for the created operation.


#### Returns:

A scalar <a href="../../../../tf/Tensor.md"><code>tf.Tensor</code></a> of type <a href="../../../../tf.md#string"><code>tf.string</code></a>.





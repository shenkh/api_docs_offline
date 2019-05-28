# Frequently Asked Questions

This document provides answers to some of the frequently asked questions about
TensorFlow. If you have a question that is not covered here, you might find an
answer on one of the TensorFlow <a href="../about/index.md">community resources</a>.

[TOC]

## Features and Compatibility

#### Can I run distributed training on multiple computers?

Yes! TensorFlow gained
<a href="../deploy/distributed.md">support for distributed computation</a> in
version 0.8. TensorFlow now supports multiple devices (CPUs and GPUs) in one or
more computers.

#### Does TensorFlow work with Python 3?

As of the 0.6.0 release timeframe (Early December 2015), we do support Python
3.3+.

## Building a TensorFlow graph

See also the
<a href="../api_guides/python/framework.md">API documentation on building graphs</a>.

#### Why does `c = tf.matmul(a, b)` not execute the matrix multiplication immediately?

In the TensorFlow Python API, `a`, `b`, and `c` are
<a href="../api_docs/python/tf/Tensor.md"><code>tf.Tensor</code></a> objects. A `Tensor` object is
a symbolic handle to the result of an operation, but does not actually hold the
values of the operation's output. Instead, TensorFlow encourages users to build
up complicated expressions (such as entire neural networks and its gradients) as
a dataflow graph. You then offload the computation of the entire dataflow graph
(or a subgraph of it) to a TensorFlow
<a href="../api_docs/python/tf/Session.md"><code>tf.Session</code></a>, which is able to execute the
whole computation much more efficiently than executing the operations
one-by-one.

#### How are devices named?

The supported device names are `"/device:CPU:0"` (or `"/cpu:0"`) for the CPU
device, and `"/device:GPU:i"` (or `"/gpu:i"`) for the *i*th GPU device.

#### How do I place operations on a particular device?

To place a group of operations on a device, create them within a
<a href="../api_docs/python/tf/device.md"><code>with tf.device(name):</code></a> context.  See
the how-to documentation on
<a href="../guide/using_gpu.md">using GPUs with TensorFlow</a> for details of how
TensorFlow assigns operations to devices, and the
<a href="../tutorials/images/deep_cnn.md">CIFAR-10 tutorial</a> for an example model that
uses multiple GPUs.


## Running a TensorFlow computation

See also the
<a href="../api_guides/python/client.md">API documentation on running graphs</a>.

#### What's the deal with feeding and placeholders?

Feeding is a mechanism in the TensorFlow Session API that allows you to
substitute different values for one or more tensors at run time. The `feed_dict`
argument to <a href="../api_docs/python/tf/InteractiveSession.md#run"><code>tf.Session.run</code></a> is a
dictionary that maps <a href="../api_docs/python/tf/Tensor.md"><code>tf.Tensor</code></a> objects to
numpy arrays (and some other types), which will be used as the values of those
tensors in the execution of a step.

#### What is the difference between `Session.run()` and `Tensor.eval()`?

If `t` is a <a href="../api_docs/python/tf/Tensor.md"><code>tf.Tensor</code></a> object,
<a href="../api_docs/python/tf/Tensor.md#eval"><code>tf.Tensor.eval</code></a> is shorthand for
<a href="../api_docs/python/tf/InteractiveSession.md#run"><code>tf.Session.run</code></a>, where `sess` is the
current <a href="../api_docs/python/tf/get_default_session.md"><code>tf.get_default_session</code></a>. The
two following snippets of code are equivalent:

```python
# Using `Session.run()`.
sess = tf.Session()
c = tf.constant(5.0)
print(sess.run(c))

# Using `Tensor.eval()`.
c = tf.constant(5.0)
with tf.Session():
  print(c.eval())
```

In the second example, the session acts as a
[context manager](https://docs.python.org/2.7/reference/compound_stmts.html#with),
which has the effect of installing it as the default session for the lifetime of
the `with` block. The context manager approach can lead to more concise code for
simple use cases (like unit tests); if your code deals with multiple graphs and
sessions, it may be more straightforward to make explicit calls to
`Session.run()`.

#### Do Sessions have a lifetime? What about intermediate tensors?

Sessions can own resources, such as
<a href="../api_docs/python/tf/Variable.md"><code>tf.Variable</code></a>,
<a href="../api_docs/python/tf/QueueBase.md"><code>tf.QueueBase</code></a>, and
<a href="../api_docs/python/tf/ReaderBase.md"><code>tf.ReaderBase</code></a>. These resources can sometimes use
a significant amount of memory, and can be released when the session is closed by calling
<a href="../api_docs/python/tf/Session.md#close"><code>tf.Session.close</code></a>.

The intermediate tensors that are created as part of a call to
<a href="../api_guides/python/client.md"><code>Session.run()</code></a> will be freed at or before the
end of the call.

#### Does the runtime parallelize parts of graph execution?

The TensorFlow runtime parallelizes graph execution across many different
dimensions:

* The individual ops have parallel implementations, using multiple cores in a
  CPU, or multiple threads in a GPU.
* Independent nodes in a TensorFlow graph can run in parallel on multiple
  devices, which makes it possible to speed up
  <a href="../tutorials/images/deep_cnn.md">CIFAR-10 training using multiple GPUs</a>.
* The Session API allows multiple concurrent steps (i.e. calls to
  <a href="../api_docs/python/tf/InteractiveSession.md#run"><code>tf.Session.run</code></a> in parallel). This
  enables the runtime to get higher throughput, if a single step does not use
  all of the resources in your computer.

#### Which client languages are supported in TensorFlow?

TensorFlow is designed to support multiple client languages.
Currently, the best-supported client language is [Python](../api_docs/python/index.md). Experimental interfaces for
executing and constructing graphs are also available for
[C++](../api_docs/cc/index.md), [Java](../api_docs/java/reference/org/tensorflow/package-summary.html) and [Go](https://godoc.org/github.com/tensorflow/tensorflow/tensorflow/go).

TensorFlow also has a
[C-based client API](https://www.tensorflow.org/code/tensorflow/c/c_api.h)
to help build support for more client languages.  We invite contributions of new
language bindings.

Bindings for various other languages (such as [C#](https://github.com/migueldeicaza/TensorFlowSharp), [Julia](https://github.com/malmaud/TensorFlow.jl), [Ruby](https://github.com/somaticio/tensorflow.rb) and [Scala](https://github.com/eaplatanios/tensorflow_scala)) created and supported by the open source community build on top of the C API supported by the TensorFlow maintainers.

#### Does TensorFlow make use of all the devices (GPUs and CPUs) available on my machine?

TensorFlow supports multiple GPUs and CPUs. See the how-to documentation on
<a href="../guide/using_gpu.md">using GPUs with TensorFlow</a> for details of how
TensorFlow assigns operations to devices, and the
<a href="../tutorials/images/deep_cnn.md">CIFAR-10 tutorial</a> for an example model that
uses multiple GPUs.

Note that TensorFlow only uses GPU devices with a compute capability greater
than 3.5.

#### Why does `Session.run()` hang when using a reader or a queue?

The <a href="../api_docs/python/tf/ReaderBase.md"><code>tf.ReaderBase</code></a> and
<a href="../api_docs/python/tf/QueueBase.md"><code>tf.QueueBase</code></a> classes provide special operations that
can *block* until input (or free space in a bounded queue) becomes
available. These operations allow you to build sophisticated
<a href="../api_guides/python/reading_data.md">input pipelines</a>, at the cost of making the
TensorFlow computation somewhat more complicated. See the how-to documentation
for
<a href="../api_guides/python/reading_data.md#creating_threads_to_prefetch_using_queuerunner_objects">using <code>QueueRunner</code> objects to drive queues and readers</a>
for more information on how to use them.

## Variables

See also the how-to documentation on <a href="../guide/variables.md">variables</a> and
<a href="../api_guides/python/state_ops.md">the API documentation for variables</a>.

#### What is the lifetime of a variable?

A variable is created when you first run the
<a href="../api_docs/python/tf/Variable.md#initializer"><code>tf.Variable.initializer</code></a>
operation for that variable in a session. It is destroyed when that
<a href="../api_docs/python/tf/Session.md#close"><code>tf.Session.close</code></a>.

#### How do variables behave when they are concurrently accessed?

Variables allow concurrent read and write operations. The value read from a
variable may change if it is concurrently updated. By default, concurrent
assignment operations to a variable are allowed to run with no mutual exclusion.
To acquire a lock when assigning to a variable, pass `use_locking=True` to
<a href="../api_docs/python/tf/Variable.md#assign"><code>tf.Variable.assign</code></a>.

## Tensor shapes

See also the
<a href="../api_docs/python/tf/TensorShape.md"><code>tf.TensorShape</code></a>.

#### How can I determine the shape of a tensor in Python?

In TensorFlow, a tensor has both a static (inferred) shape and a dynamic (true)
shape. The static shape can be read using the
<a href="../api_docs/python/tf/Tensor.md#get_shape"><code>tf.Tensor.get_shape</code></a>
method: this shape is inferred from the operations that were used to create the
tensor, and may be
<a href="../api_docs/python/tf/TensorShape.md">partially complete</a>. If the static
shape is not fully defined, the dynamic shape of a `Tensor` `t` can be
determined by evaluating <a href="../api_docs/python/tf/shape.md"><code>tf.shape(t)</code></a>.

#### What is the difference between `x.set_shape()` and `x = tf.reshape(x)`?

The <a href="../api_docs/python/tf/Tensor.md#set_shape"><code>tf.Tensor.set_shape</code></a> method updates
the static shape of a `Tensor` object, and it is typically used to provide
additional shape information when this cannot be inferred directly. It does not
change the dynamic shape of the tensor.

The <a href="../api_docs/python/tf/reshape.md"><code>tf.reshape</code></a> operation creates
a new tensor with a different dynamic shape.

#### How do I build a graph that works with variable batch sizes?

It is often useful to build a graph that works with variable batch sizes 
so that the same code can be used for (mini-)batch training, and
single-instance inference. The resulting graph can be
<a href="../api_docs/python/tf/Graph.md#as_graph_def">saved as a protocol buffer</a>
and
<a href="../api_docs/python/tf/import_graph_def.md">imported into another program</a>.

When building a variable-size graph, the most important thing to remember is not
to encode the batch size as a Python constant, but instead to use a symbolic
`Tensor` to represent it. The following tips may be useful:

* Use [`batch_size = tf.shape(input)[0]`](../api_docs/python/array_ops.md#shape)
  to extract the batch dimension from a `Tensor` called `input`, and store it in
  a `Tensor` called `batch_size`.

* Use <a href="../api_docs/python/tf/reduce_mean.md"><code>tf.reduce_mean</code></a> instead
  of `tf.reduce_sum(...) / batch_size`.


## TensorBoard

#### How can I visualize a TensorFlow graph?

See the <a href="../guide/graph_viz.md">graph visualization tutorial</a>.

#### What is the simplest way to send data to TensorBoard?

Add summary ops to your TensorFlow graph, and write
these summaries to a log directory.  Then, start TensorBoard using

    python tensorflow/tensorboard/tensorboard.py --logdir=path/to/log-directory

For more details, see the
<a href="../guide/summaries_and_tensorboard.md">Summaries and TensorBoard tutorial</a>.

#### Every time I launch TensorBoard, I get a network security popup!

You can change TensorBoard to serve on localhost rather than '0.0.0.0' by
the flag --host=localhost. This should quiet any security warnings.

## Extending TensorFlow

See the how-to documentation for
<a href="../extend/adding_an_op.md">adding a new operation to TensorFlow</a>.

#### My data is in a custom format. How do I read it using TensorFlow?

There are three main options for dealing with data in a custom format.

The easiest option is to write parsing code in Python that transforms the data
into a numpy array. Then, use <a href="../api_docs/python/tf/data/Dataset.md#from_tensor_slices"><code>tf.data.Dataset.from_tensor_slices</code></a> to
create an input pipeline from the in-memory data.

If your data doesn't fit in memory, try doing the parsing in the Dataset
pipeline. Start with an appropriate file reader, like
<a href="../api_docs/python/tf/data/TextLineDataset.md"><code>tf.data.TextLineDataset</code></a>. Then convert the dataset by mapping
<a href="../api_docs/python/tf/data/Dataset.md#map">mapping</a> appropriate operations over it.
Prefer predefined TensorFlow operations such as <a href="../api_docs/python/tf/decode_raw.md"><code>tf.decode_raw</code></a>,
<a href="../api_docs/python/tf/decode_csv.md"><code>tf.decode_csv</code></a>, <a href="../api_docs/python/tf/parse_example.md"><code>tf.parse_example</code></a>, or <a href="../api_docs/python/tf/image/decode_png.md"><code>tf.image.decode_png</code></a>.

If your data is not easily parsable with the built-in TensorFlow operations,
consider converting it, offline, to a format that is easily parsable, such
as <a href="../api_docs/python/tf/python_io/TFRecordWriter.md"><code>TFRecord</code></a> format.

The most efficient method to customize the parsing behavior is to
<a href="../extend/adding_an_op.md">add a new op written in C++</a> that parses your
data format. The <a href="../extend/new_data_formats.md">guide to handling new data formats</a> has
more information about the steps for doing this.


## Miscellaneous

#### What is TensorFlow's coding style convention?

The TensorFlow Python API adheres to the
[PEP8](https://www.python.org/dev/peps/pep-0008/) conventions.<sup>*</sup> In
particular, we use `CamelCase` names for classes, and `snake_case` names for
functions, methods, and properties. We also adhere to the
[Google Python style guide](https://google.github.io/styleguide/pyguide.html).

The TensorFlow C++ code base adheres to the
[Google C++ style guide](https://google.github.io/styleguide/cppguide.html).

(<sup>*</sup> With one exception: we use 2-space indentation instead of 4-space
indentation.)


# Reading custom file and record formats

PREREQUISITES:

*   Some familiarity with C++.
*   Must have
    <a href="../install/install_sources.md">downloaded TensorFlow source</a>, and be
    able to build it.

We divide the task of supporting a file format into two pieces:

*   File formats: We use a reader <a href="../api_docs/python/tf/data/Dataset.md"><code>tf.data.Dataset</code></a> to read raw *records* (which
    are typically represented by scalar string tensors, but can have more
    structure) from a file.
*   Record formats: We use decoder or parsing ops to turn a string record
    into tensors usable by TensorFlow.

For example, to read a
[CSV file](https://en.wikipedia.org/wiki/Comma-separated_values), we use
<a href="../api_docs/python/tf/data/TextLineDataset.md">a dataset for reading text files line-by-line</a>
and then <a href="../api_docs/python/tf/data/Dataset.md#map">map</a> an
<a href="../api_docs/python/tf/decode_csv.md">op</a> that parses CSV data from each line of text in the dataset.

[TOC]

## Writing a `Dataset` for a file format

A <a href="../api_docs/python/tf/data/Dataset.md"><code>tf.data.Dataset</code></a> represents a sequence of *elements*, which can be the
individual records in a file. There are several examples of "reader" datasets
that are already built into TensorFlow:

*   <a href="../api_docs/python/tf/data/TFRecordDataset.md"><code>tf.data.TFRecordDataset</code></a>
    ([source in `kernels/data/reader_dataset_ops.cc`](https://www.tensorflow.org/code/tensorflow/core/kernels/data/reader_dataset_ops.cc))
*   <a href="../api_docs/python/tf/data/FixedLengthRecordDataset.md"><code>tf.data.FixedLengthRecordDataset</code></a>
    ([source in `kernels/data/reader_dataset_ops.cc`](https://www.tensorflow.org/code/tensorflow/core/kernels/data/reader_dataset_ops.cc))
*   <a href="../api_docs/python/tf/data/TextLineDataset.md"><code>tf.data.TextLineDataset</code></a>
    ([source in `kernels/data/reader_dataset_ops.cc`](https://www.tensorflow.org/code/tensorflow/core/kernels/data/reader_dataset_ops.cc))

Each of these implementations comprises three related classes:

* A `tensorflow::DatasetOpKernel` subclass (e.g. `TextLineDatasetOp`), which
  tells TensorFlow how to construct a dataset object from the inputs to and
  attrs of an op, in its `MakeDataset()` method.

* A `tensorflow::GraphDatasetBase` subclass (e.g. `TextLineDatasetOp::Dataset`),
  which represents the *immutable* definition of the dataset itself, and tells
  TensorFlow how to construct an iterator object over that dataset, in its
  `MakeIteratorInternal()` method.

* A `tensorflow::DatasetIterator<Dataset>` subclass (e.g.
  `TextLineDatasetOp::Dataset::Iterator`), which represents the *mutable* state
  of an iterator over a particular dataset, and tells TensorFlow how to get the
  next element from the iterator, in its `GetNextInternal()` method.

The most important method is the `GetNextInternal()` method, since it defines
how to actually read records from the file and represent them as one or more
`Tensor` objects.

To create a new reader dataset called (for example) `MyReaderDataset`, you will
need to:

1. In C++, define subclasses of `tensorflow::DatasetOpKernel`,
   `tensorflow::GraphDatasetBase`, and `tensorflow::DatasetIterator<Dataset>`
   that implement the reading logic.
2. In C++, register a new reader op and kernel with the name
   `"MyReaderDataset"`.
3. In Python, define a subclass of <a href="../api_docs/python/tf/data/Dataset.md"><code>tf.data.Dataset</code></a> called `MyReaderDataset`.

You can put all the C++ code in a single file, such as
`my_reader_dataset_op.cc`. It will help if you are
familiar with <a href="../extend/adding_an_op.md">the adding an op how-to</a>. The following skeleton
can be used as a starting point for your implementation:

```c++
#include "tensorflow/core/framework/common_shape_fns.h"
#include "tensorflow/core/framework/dataset.h"
#include "tensorflow/core/framework/op.h"
#include "tensorflow/core/framework/shape_inference.h"

namespace myproject {
namespace {

using ::tensorflow::DT_STRING;
using ::tensorflow::PartialTensorShape;
using ::tensorflow::Status;

class MyReaderDatasetOp : public tensorflow::DatasetOpKernel {
 public:

  MyReaderDatasetOp(tensorflow::OpKernelConstruction* ctx)
      : DatasetOpKernel(ctx) {
    // Parse and validate any attrs that define the dataset using
    // `ctx->GetAttr()`, and store them in member variables.
  }

  void MakeDataset(tensorflow::OpKernelContext* ctx,
                   tensorflow::DatasetBase** output) override {
    // Parse and validate any input tensors 0that define the dataset using
    // `ctx->input()` or the utility function
    // `ParseScalarArgument<T>(ctx, &arg)`.

    // Create the dataset object, passing any (already-validated) arguments from
    // attrs or input tensors.
    *output = new Dataset(ctx);
  }

 private:
  class Dataset : public tensorflow::GraphDatasetBase {
   public:
    Dataset(tensorflow::OpKernelContext* ctx) : GraphDatasetBase(ctx) {}

    std::unique_ptr<tensorflow::IteratorBase> MakeIteratorInternal(
        const string& prefix) const override {
      return std::unique_ptr<tensorflow::IteratorBase>(new Iterator(
          {this, tensorflow::strings::StrCat(prefix, "::MyReader")}));
    }

    // Record structure: Each record is represented by a scalar string tensor.
    //
    // Dataset elements can have a fixed number of components of different
    // types and shapes; replace the following two methods to customize this
    // aspect of the dataset.
    const tensorflow::DataTypeVector& output_dtypes() const override {
      static auto* const dtypes = new tensorflow::DataTypeVector({DT_STRING});
      return *dtypes;
    }
    const std::vector<PartialTensorShape>& output_shapes() const override {
      static std::vector<PartialTensorShape>* shapes =
          new std::vector<PartialTensorShape>({{}});
      return *shapes;
    }

    string DebugString() const override { return "MyReaderDatasetOp::Dataset"; }

   protected:
    // Optional: Implementation of `GraphDef` serialization for this dataset.
    //
    // Implement this method if you want to be able to save and restore
    // instances of this dataset (and any iterators over it).
    Status AsGraphDefInternal(DatasetGraphDefBuilder* b,
                              tensorflow::Node** output) const override {
      // Construct nodes to represent any of the input tensors from this
      // object's member variables using `b->AddScalar()` and `b->AddVector()`.
      std::vector<tensorflow::Node*> input_tensors;
      TF_RETURN_IF_ERROR(b->AddDataset(this, input_tensors, output));
      return Status::OK();
    }

   private:
    class Iterator : public tensorflow::DatasetIterator<Dataset> {
     public:
      explicit Iterator(const Params& params)
          : DatasetIterator<Dataset>(params), i_(0) {}

      // Implementation of the reading logic.
      //
      // The example implementation in this file yields the string "MyReader!"
      // ten times. In general there are three cases:
      //
      // 1. If an element is successfully read, store it as one or more tensors
      //    in `*out_tensors`, set `*end_of_sequence = false` and return
      //    `Status::OK()`.
      // 2. If the end of input is reached, set `*end_of_sequence = true` and
      //    return `Status::OK()`.
      // 3. If an error occurs, return an error status using one of the helper
      //    functions from "tensorflow/core/lib/core/errors.h".
      Status GetNextInternal(tensorflow::IteratorContext* ctx,
                             std::vector<tensorflow::Tensor>* out_tensors,
                             bool* end_of_sequence) override {
        // NOTE: `GetNextInternal()` may be called concurrently, so it is
        // recommended that you protect the iterator state with a mutex.
        tensorflow::mutex_lock l(mu_);
        if (i_ < 10) {
          // Create a scalar string tensor and add it to the output.
          tensorflow::Tensor record_tensor(ctx->allocator({}), DT_STRING, {});
          record_tensor.scalar<string>()() = "MyReader!";
          out_tensors->emplace_back(std::move(record_tensor));
          ++i_;
          *end_of_sequence = false;
        } else {
          *end_of_sequence = true;
        }
        return Status::OK();
      }

     protected:
      // Optional: Implementation of iterator state serialization for this
      // iterator.
      //
      // Implement these two methods if you want to be able to save and restore
      // instances of this iterator.
      Status SaveInternal(tensorflow::IteratorStateWriter* writer) override {
        tensorflow::mutex_lock l(mu_);
        TF_RETURN_IF_ERROR(writer->WriteScalar(full_name("i"), i_));
        return Status::OK();
      }
      Status RestoreInternal(tensorflow::IteratorContext* ctx,
                             tensorflow::IteratorStateReader* reader) override {
        tensorflow::mutex_lock l(mu_);
        TF_RETURN_IF_ERROR(reader->ReadScalar(full_name("i"), &i_));
        return Status::OK();
      }

     private:
      tensorflow::mutex mu_;
      int64 i_ GUARDED_BY(mu_);
    };
  };
};

// Register the op definition for MyReaderDataset.
//
// Dataset ops always have a single output, of type `variant`, which represents
// the constructed `Dataset` object.
//
// Add any attrs and input tensors that define the dataset here.
REGISTER_OP("MyReaderDataset")
    .Output("handle: variant")
    .SetIsStateful()
    .SetShapeFn(tensorflow::shape_inference::ScalarShape);

// Register the kernel implementation for MyReaderDataset.
REGISTER_KERNEL_BUILDER(Name("MyReaderDataset").Device(tensorflow::DEVICE_CPU),
                        MyReaderDatasetOp);

}  // namespace
}  // namespace myproject
```

The last step is to build the C++ code and add a Python wrapper. The easiest way
to do this is by <a href="../extend/adding_an_op.md#build_the_op_library">compiling a dynamic
library</a> (e.g. called `"my_reader_dataset_op.so"`), and adding a Python class
that subclasses <a href="../api_docs/python/tf/data/Dataset.md"><code>tf.data.Dataset</code></a> to wrap it. An example Python program is
given here:

```python
import tensorflow as tf

# Assumes the file is in the current working directory.
my_reader_dataset_module = tf.load_op_library("./my_reader_dataset_op.so")

class MyReaderDataset(tf.data.Dataset):

  def __init__(self):
    super(MyReaderDataset, self).__init__()
    # Create any input attrs or tensors as members of this class.

  def _as_variant_tensor(self):
    # Actually construct the graph node for the dataset op.
    #
    # This method will be invoked when you create an iterator on this dataset
    # or a dataset derived from it.
    return my_reader_dataset_module.my_reader_dataset()

  # The following properties define the structure of each element: a scalar
  # <a href="../api_docs/python/tf/string.md"><code>tf.string</code></a> tensor. Change these properties to match the `output_dtypes()`
  # and `output_shapes()` methods of `MyReaderDataset::Dataset` if you modify
  # the structure of each element.
  @property
  def output_types(self):
    return tf.string

  @property
  def output_shapes(self):
    return tf.TensorShape([])

  @property
  def output_classes(self):
    return tf.Tensor

if __name__ == "__main__":
  # Create a MyReaderDataset and print its elements.
  with tf.Session() as sess:
    iterator = MyReaderDataset().make_one_shot_iterator()
    next_element = iterator.get_next()
    try:
      while True:
        print(sess.run(next_element))  # Prints "MyReader!" ten times.
    except tf.errors.OutOfRangeError:
      pass
```

You can see some examples of `Dataset` wrapper classes in
[`tensorflow/python/data/ops/dataset_ops.py`](https://www.tensorflow.org/code/tensorflow/python/data/ops/dataset_ops.py).

## Writing an Op for a record format

Generally this is an ordinary op that takes a scalar string record as input, and
so follow <a href="../extend/adding_an_op.md">the instructions to add an Op</a>.
You may optionally take a scalar string key as input, and include that in error
messages reporting improperly formatted data.  That way users can more easily
track down where the bad data came from.

Examples of Ops useful for decoding records:

*   <a href="../api_docs/python/tf/parse_single_example.md"><code>tf.parse_single_example</code></a> (and <a href="../api_docs/python/tf/parse_example.md"><code>tf.parse_example</code></a>)
*   <a href="../api_docs/python/tf/decode_csv.md"><code>tf.decode_csv</code></a>
*   <a href="../api_docs/python/tf/decode_raw.md"><code>tf.decode_raw</code></a>

Note that it can be useful to use multiple Ops to decode a particular record
format.  For example, you may have an image saved as a string in
[a <a href="../api_docs/python/tf/train/Example.md"><code>tf.train.Example</code></a> protocol buffer](https://www.tensorflow.org/code/tensorflow/core/example/example.proto).
Depending on the format of that image, you might take the corresponding output
from a <a href="../api_docs/python/tf/parse_single_example.md"><code>tf.parse_single_example</code></a> op and call <a href="../api_docs/python/tf/image/decode_jpeg.md"><code>tf.image.decode_jpeg</code></a>,
<a href="../api_docs/python/tf/image/decode_png.md"><code>tf.image.decode_png</code></a>, or <a href="../api_docs/python/tf/decode_raw.md"><code>tf.decode_raw</code></a>.  It is common to take the output
of <a href="../api_docs/python/tf/decode_raw.md"><code>tf.decode_raw</code></a> and use <a href="../api_docs/python/tf/slice.md"><code>tf.slice</code></a> and <a href="../api_docs/python/tf/reshape.md"><code>tf.reshape</code></a> to extract pieces.

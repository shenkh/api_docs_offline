<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.io" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.io



Defined in [`tensorflow/_api/v1/io/__init__.py`](/code/stable/tensorflow/_api/v1/io/__init__.py).

Public API for tf.io namespace.

## Classes

[`class FixedLenFeature`](../tf/io/FixedLenFeature.md): Configuration for parsing a fixed-length input feature.

[`class FixedLenSequenceFeature`](../tf/io/FixedLenSequenceFeature.md): Configuration for parsing a variable-length input feature into a `Tensor`.

[`class PaddingFIFOQueue`](../tf/io/PaddingFIFOQueue.md): A FIFOQueue that supports batching variable-sized tensors by padding.

[`class PriorityQueue`](../tf/io/PriorityQueue.md): A queue implementation that dequeues elements in prioritized order.

[`class QueueBase`](../tf/io/QueueBase.md): Base class for queue implementations.

[`class RandomShuffleQueue`](../tf/io/RandomShuffleQueue.md): A queue implementation that dequeues elements in a random order.

[`class SparseFeature`](../tf/io/SparseFeature.md): Configuration for parsing a sparse input feature from an `Example`.

[`class TFRecordCompressionType`](../tf/io/TFRecordCompressionType.md): The type of compression for the record.

[`class TFRecordOptions`](../tf/io/TFRecordOptions.md): Options used for manipulating TFRecord files.

[`class TFRecordWriter`](../tf/io/TFRecordWriter.md): A class to write records to a TFRecords file.

[`class VarLenFeature`](../tf/io/VarLenFeature.md): Configuration for parsing a variable-length input feature.

## Functions

[`decode_base64(...)`](../tf/io/decode_base64.md): Decode web-safe base64-encoded strings.

[`decode_compressed(...)`](../tf/io/decode_compressed.md): Decompress strings.

[`decode_csv(...)`](../tf/io/decode_csv.md): Convert CSV records to tensors. Each column maps to one tensor.

[`decode_json_example(...)`](../tf/io/decode_json_example.md): Convert JSON-encoded Example records to binary protocol buffer strings.

[`decode_raw(...)`](../tf/io/decode_raw.md): Reinterpret the bytes of a string as a vector of numbers.

[`deserialize_many_sparse(...)`](../tf/io/deserialize_many_sparse.md): Deserialize and concatenate `SparseTensors` from a serialized minibatch.

[`encode_base64(...)`](../tf/io/encode_base64.md): Encode strings into web-safe base64 format.

[`match_filenames_once(...)`](../tf/io/match_filenames_once.md): Save the list of files matching pattern, so it is only computed once.

[`matching_files(...)`](../tf/io/matching_files.md): Returns the set of files matching one or more glob patterns.

[`parse_example(...)`](../tf/io/parse_example.md): Parses `Example` protos into a `dict` of tensors.

[`parse_sequence_example(...)`](../tf/io/parse_sequence_example.md): Parses a batch of `SequenceExample` protos.

[`parse_single_example(...)`](../tf/io/parse_single_example.md): Parses a single `Example` proto.

[`parse_single_sequence_example(...)`](../tf/io/parse_single_sequence_example.md): Parses a single `SequenceExample` proto.

[`parse_tensor(...)`](../tf/io/parse_tensor.md): Transforms a serialized tensorflow.TensorProto proto into a Tensor.

[`read_file(...)`](../tf/io/read_file.md): Reads and outputs the entire contents of the input filename.

[`serialize_many_sparse(...)`](../tf/io/serialize_many_sparse.md): Serialize `N`-minibatch `SparseTensor` into an `[N, 3]` `Tensor`.

[`serialize_sparse(...)`](../tf/io/serialize_sparse.md): Serialize a `SparseTensor` into a 3-vector (1-D `Tensor`) object.

[`tf_record_iterator(...)`](../tf/io/tf_record_iterator.md): An iterator that read the records from a TFRecords file.

[`write_file(...)`](../tf/io/write_file.md): Writes contents to the file at input filename. Creates file and recursively

[`write_graph(...)`](../tf/io/write_graph.md): Writes a graph proto to a file.


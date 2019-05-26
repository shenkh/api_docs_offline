<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.summary" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.summary



Defined in [`tensorflow/summary/__init__.py`](https://www.tensorflow.org/code/tensorflow/summary/__init__.py).

Public API for tf.summary namespace.

## Classes

[`class Event`](../tf/Event.md): A ProtocolMessage

[`class FileWriter`](../tf/summary/FileWriter.md): Writes `Summary` protocol buffers to event files.

[`class FileWriterCache`](../tf/summary/FileWriterCache.md): Cache for file writers.

[`class SessionLog`](../tf/SessionLog.md): A ProtocolMessage

[`class Summary`](../tf/Summary.md): A ProtocolMessage

[`class SummaryDescription`](../tf/summary/SummaryDescription.md): A ProtocolMessage

[`class TaggedRunMetadata`](../tf/summary/TaggedRunMetadata.md): A ProtocolMessage

## Functions

[`audio(...)`](../tf/summary/audio.md): Outputs a `Summary` protocol buffer with audio.

[`get_summary_description(...)`](../tf/summary/get_summary_description.md): Given a TensorSummary node_def, retrieve its SummaryDescription.

[`histogram(...)`](../tf/summary/histogram.md): Outputs a `Summary` protocol buffer with a histogram.

[`image(...)`](../tf/summary/image.md): Outputs a `Summary` protocol buffer with images.

[`merge(...)`](../tf/summary/merge.md): Merges summaries.

[`merge_all(...)`](../tf/summary/merge_all.md): Merges all summaries collected in the default graph.

[`scalar(...)`](../tf/summary/scalar.md): Outputs a `Summary` protocol buffer containing a single scalar value.

[`tensor_summary(...)`](../tf/summary/tensor_summary.md): Outputs a `Summary` protocol buffer with a serialized tensor.proto.

[`text(...)`](../tf/summary/text.md): Summarizes textual data.


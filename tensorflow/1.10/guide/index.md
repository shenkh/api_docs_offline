# TensorFlow Guide

The documents in this unit dive into the details of how TensorFlow
works. The units are as follows:

## High Level APIs

  * <a href="../guide/keras.md">Keras</a>, TensorFlow's high-level API for building and
    training deep learning models.
  * <a href="../guide/eager.md">Eager Execution</a>, an API for writing TensorFlow code
    imperatively, like you would use Numpy.
  * <a href="../guide/estimators.md">Estimators</a>, a high-level API that provides
    fully-packaged models ready for large-scale training and production.
  * <a href="../guide/datasets.md">Importing Data</a>, easy input pipelines to bring your data into
    your TensorFlow program.

## Estimators

* <a href="../guide/estimators.md">Estimators</a>, learn how to use Estimators for machine learning.
* <a href="../guide/premade_estimators.md">Premade Estimators</a>, the basics of premade Estimators.
* <a href="../guide/checkpoints.md">Checkpoints</a>, save training progress and resume where you left off.
* <a href="../guide/feature_columns.md">Feature Columns</a>, handle a variety of input data types without changes to the model.
* <a href="../guide/datasets_for_estimators.md">Datasets for Estimators</a>, use <a href="../api_docs/python/tf/data.md"><code>tf.data</code></a> to input data.
* <a href="../guide/custom_estimators.md">Creating Custom Estimators</a>, write your own Estimator.

## Accelerators

  * <a href="../guide/using_gpu.md">Using GPUs</a> explains how TensorFlow assigns operations to
    devices and how you can change the arrangement manually.
  * <a href="../guide/using_tpu.md">Using TPUs</a> explains how to modify `Estimator` programs to run on a TPU.

## Low Level APIs

  * <a href="../guide/low_level_intro.md">Introduction</a>, which introduces the
    basics of how you can use TensorFlow outside of the high Level APIs.
  * <a href="../guide/tensors.md">Tensors</a>, which explains how to create,
    manipulate, and access Tensors--the fundamental object in TensorFlow.
  * <a href="../guide/variables.md">Variables</a>, which details how
    to represent shared, persistent state in your program.
  * <a href="../guide/graphs.md">Graphs and Sessions</a>, which explains:
      * dataflow graphs, which are TensorFlow's representation of computations
        as dependencies between operations.
      * sessions, which are TensorFlow's mechanism for running dataflow graphs
        across one or more local or remote devices.
    If you are programming with the low-level TensorFlow API, this unit
    is essential. If you are programming with a high-level TensorFlow API
    such as Estimators or Keras, the high-level API creates and manages
    graphs and sessions for you, but understanding graphs and sessions
    can still be helpful.
  * <a href="../guide/saved_model.md">Save and Restore</a>, which
    explains how to save and restore variables and models.

## ML Concepts

  * <a href="../guide/embedding.md">Embeddings</a>, which introduces the concept
    of embeddings, provides a simple example of training an embedding in
    TensorFlow, and explains how to view embeddings with the TensorBoard
    Embedding Projector.

## Debugging

  * <a href="../guide/debugger.md">TensorFlow Debugger</a>, which
    explains how to use the TensorFlow debugger (tfdbg).

## TensorBoard

TensorBoard is a utility to visualize different aspects of machine learning.
The following guides explain how to use TensorBoard:

  * <a href="../guide/summaries_and_tensorboard.md">TensorBoard: Visualizing Learning</a>,
    which introduces TensorBoard.
  * <a href="../guide/graph_viz.md">TensorBoard: Graph Visualization</a>, which
    explains how to visualize the computational graph.
  * <a href="../guide/tensorboard_histograms.md">TensorBoard Histogram Dashboard</a> which demonstrates the how to
    use TensorBoard's histogram dashboard.


## Misc

  * <a href="../guide/version_compat.md">TensorFlow Version Compatibility</a>,
    which explains backward compatibility guarantees and non-guarantees.
  * <a href="../guide/faq.md">Frequently Asked Questions</a>, which contains frequently asked
    questions about TensorFlow.

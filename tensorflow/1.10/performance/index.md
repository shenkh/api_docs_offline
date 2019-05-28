# Performance

Performance is an important consideration when training machine learning
models. Performance speeds up and scales research while
also providing end users with near instant predictions. This section provides
details on the high level APIs to use along with best practices to build
and train high performance models, and quantize models for the least latency
and highest throughput for inference.

  * <a href="../performance/performance_guide.md">Performance Guide</a> contains a collection of best
    practices for optimizing your TensorFlow code.

  * <a href="../performance/datasets_performance.md">Data input pipeline guide</a> describes the tf.data
    API for building efficient data input pipelines for TensorFlow.

  * <a href="../performance/benchmarks.md">Benchmarks</a> contains a collection of
    benchmark results for a variety of hardware configurations.

  * For improving inference efficiency on mobile and
    embedded hardware, see
    <a href="../performance/quantization.md">How to Quantize Neural Networks with TensorFlow</a>, which
    explains how to use quantization to reduce model size, both in storage
    and at runtime.

  * For optimizing inference on GPUs, refer to [NVIDIA TensorRT™
  integration with TensorFlow.](
    https://medium.com/tensorflow/speed-up-tensorflow-inference-on-gpus-with-tensorrt-13b49f3db3fa)


XLA (Accelerated Linear Algebra) is an experimental compiler for linear
algebra that optimizes TensorFlow computations. The following guides explore
XLA:

  * <a href="../performance/xla/index.md">XLA Overview</a>, which introduces XLA.
  * <a href="../performance/xla/broadcasting.md">Broadcasting Semantics</a>, which describes XLA's
    broadcasting semantics.
  * <a href="../performance/xla/developing_new_backend.md">Developing a new back end for XLA</a>, which
    explains how to re-target TensorFlow in order to optimize the performance
    of the computational graph for particular hardware.
  * <a href="../performance/xla/jit.md">Using JIT Compilation</a>, which describes the XLA JIT compiler that
    compiles and runs parts of TensorFlow graphs via XLA in order to optimize
    performance.
  * <a href="../performance/xla/operation_semantics.md">Operation Semantics</a>, which is a reference manual
    describing the semantics of operations in the `ComputationBuilder`
    interface.
  * <a href="../performance/xla/shapes.md">Shapes and Layout</a>, which details the `Shape` protocol buffer.
  * <a href="../performance/xla/tfcompile.md">Using AOT compilation</a>, which explains `tfcompile`, a
    standalone tool that compiles TensorFlow graphs into executable code in
    order to optimize performance.




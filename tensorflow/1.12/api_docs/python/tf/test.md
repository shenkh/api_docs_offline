<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.test" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.test



Defined in [`tensorflow/_api/v1/test/__init__.py`](/code/stable/tensorflow/_api/v1/test/__init__.py).

Testing.

See the [Testing](https://tensorflow.org/api_guides/python/test) guide.

Note: `tf.test.mock` is an alias to the python `mock` or `unittest.mock`
depending on the python version.

## Classes

[`class Benchmark`](../tf/test/Benchmark.md): Abstract class that provides helpers for TensorFlow benchmarks.

[`class StubOutForTesting`](../tf/test/StubOutForTesting.md): Support class for stubbing methods out for unit testing.

[`class TestCase`](../tf/test/TestCase.md): Base class for tests that need to test TensorFlow.

## Functions

[`assert_equal_graph_def(...)`](../tf/test/assert_equal_graph_def.md): Asserts that two `GraphDef`s are (mostly) the same.

[`compute_gradient(...)`](../tf/test/compute_gradient.md): Computes and returns the theoretical and numerical Jacobian.

[`compute_gradient_error(...)`](../tf/test/compute_gradient_error.md): Computes the gradient error.

[`create_local_cluster(...)`](../tf/test/create_local_cluster.md): Create and start local servers and return the associated `Server` objects.

[`get_temp_dir(...)`](../tf/test/get_temp_dir.md): Returns a temporary directory for use during tests.

[`gpu_device_name(...)`](../tf/test/gpu_device_name.md): Returns the name of a GPU device if available or the empty string.

[`is_built_with_cuda(...)`](../tf/test/is_built_with_cuda.md): Returns whether TensorFlow was built with CUDA (GPU) support.

[`is_gpu_available(...)`](../tf/test/is_gpu_available.md): Returns whether TensorFlow can access a GPU.

[`main(...)`](../tf/test/main.md): Runs all unit tests.

[`test_src_dir_path(...)`](../tf/test/test_src_dir_path.md): Creates an absolute test srcdir path given a relative path.


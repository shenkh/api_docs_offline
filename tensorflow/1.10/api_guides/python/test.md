# Testing
[TOC]

<h2 id="Unit_tests">Unit tests</h2>

TensorFlow provides a convenience class inheriting from `unittest.TestCase`
which adds methods relevant to TensorFlow tests.  Here is an example:

```python
    import tensorflow as tf


    class SquareTest(tf.test.TestCase):

      def testSquare(self):
        with self.test_session():
          x = tf.square([2, 3])
          self.assertAllEqual(x.eval(), [4, 9])


    if __name__ == '__main__':
      tf.test.main()
```

<a href="../../api_docs/python/tf/test/TestCase.md"><code>tf.test.TestCase</code></a> inherits from `unittest.TestCase` but adds a few additional
methods.  See <a href="../../api_docs/python/tf/test/TestCase.md"><code>tf.test.TestCase</code></a> for details.

*   <a href="../../api_docs/python/tf/test/main.md"><code>tf.test.main</code></a>
*   <a href="../../api_docs/python/tf/test/TestCase.md"><code>tf.test.TestCase</code></a>
*   <a href="../../api_docs/python/tf/test/test_src_dir_path.md"><code>tf.test.test_src_dir_path</code></a>

<h2 id="Utilities">Utilities</h2>

Note: `tf.test.mock` is an alias to the python `mock` or `unittest.mock`
depending on the python version.

*   <a href="../../api_docs/python/tf/test/assert_equal_graph_def.md"><code>tf.test.assert_equal_graph_def</code></a>
*   <a href="../../api_docs/python/tf/test/get_temp_dir.md"><code>tf.test.get_temp_dir</code></a>
*   <a href="../../api_docs/python/tf/test/is_built_with_cuda.md"><code>tf.test.is_built_with_cuda</code></a>
*   <a href="../../api_docs/python/tf/test/is_gpu_available.md"><code>tf.test.is_gpu_available</code></a>
*   <a href="../../api_docs/python/tf/test/gpu_device_name.md"><code>tf.test.gpu_device_name</code></a>

<h2 id="Gradient_checking">Gradient checking</h2>

<a href="../../api_docs/python/tf/test/compute_gradient.md"><code>tf.test.compute_gradient</code></a> and <a href="../../api_docs/python/tf/test/compute_gradient_error.md"><code>tf.test.compute_gradient_error</code></a> perform
numerical differentiation of graphs for comparison against registered analytic
gradients.

# Constants, Sequences, and Random Values

Note: Functions taking `Tensor` arguments can also take anything accepted by
<a href="../../api_docs/python/tf/convert_to_tensor.md"><code>tf.convert_to_tensor</code></a>.

[TOC]

<h2 id="Constant_Value_Tensors">Constant Value Tensors</h2>

TensorFlow provides several operations that you can use to generate constants.

*   <a href="../../api_docs/python/tf/zeros.md"><code>tf.zeros</code></a>
*   <a href="../../api_docs/python/tf/zeros_like.md"><code>tf.zeros_like</code></a>
*   <a href="../../api_docs/python/tf/ones.md"><code>tf.ones</code></a>
*   <a href="../../api_docs/python/tf/ones_like.md"><code>tf.ones_like</code></a>
*   <a href="../../api_docs/python/tf/fill.md"><code>tf.fill</code></a>
*   <a href="../../api_docs/python/tf/constant.md"><code>tf.constant</code></a>

<h2 id="Sequences">Sequences</h2>

*   <a href="../../api_docs/python/tf/lin_space.md"><code>tf.linspace</code></a>
*   <a href="../../api_docs/python/tf/range.md"><code>tf.range</code></a>

<h2 id="Random_Tensors">Random Tensors</h2>

TensorFlow has several ops that create random tensors with different
distributions.  The random ops are stateful, and create new random values each
time they are evaluated.

The `seed` keyword argument in these functions acts in conjunction with
the graph-level random seed. Changing either the graph-level seed using
<a href="../../api_docs/python/tf/set_random_seed.md"><code>tf.set_random_seed</code></a> or the
op-level seed will change the underlying seed of these operations. Setting
neither graph-level nor op-level seed, results in a random seed for all
operations.
See <a href="../../api_docs/python/tf/set_random_seed.md"><code>tf.set_random_seed</code></a>
for details on the interaction between operation-level and graph-level random
seeds.

### Examples:

```python
# Create a tensor of shape [2, 3] consisting of random normal values, with mean
# -1 and standard deviation 4.
norm = tf.random_normal([2, 3], mean=-1, stddev=4)

# Shuffle the first dimension of a tensor
c = tf.constant([[1, 2], [3, 4], [5, 6]])
shuff = tf.random_shuffle(c)

# Each time we run these ops, different results are generated
sess = tf.Session()
print(sess.run(norm))
print(sess.run(norm))

# Set an op-level seed to generate repeatable sequences across sessions.
norm = tf.random_normal([2, 3], seed=1234)
sess = tf.Session()
print(sess.run(norm))
print(sess.run(norm))
sess = tf.Session()
print(sess.run(norm))
print(sess.run(norm))
```

Another common use of random values is the initialization of variables. Also see
the <a href="../../guide/variables.md">Variables How To</a>.

```python
# Use random uniform values in [0, 1) as the initializer for a variable of shape
# [2, 3]. The default type is float32.
var = tf.Variable(tf.random_uniform([2, 3]), name="var")
init = tf.global_variables_initializer()

sess = tf.Session()
sess.run(init)
print(sess.run(var))
```

*   <a href="../../api_docs/python/tf/random_normal.md"><code>tf.random_normal</code></a>
*   <a href="../../api_docs/python/tf/truncated_normal.md"><code>tf.truncated_normal</code></a>
*   <a href="../../api_docs/python/tf/random_uniform.md"><code>tf.random_uniform</code></a>
*   <a href="../../api_docs/python/tf/random_shuffle.md"><code>tf.random_shuffle</code></a>
*   <a href="../../api_docs/python/tf/random_crop.md"><code>tf.random_crop</code></a>
*   <a href="../../api_docs/python/tf/multinomial.md"><code>tf.multinomial</code></a>
*   <a href="../../api_docs/python/tf/random_gamma.md"><code>tf.random_gamma</code></a>
*   <a href="../../api_docs/python/tf/set_random_seed.md"><code>tf.set_random_seed</code></a>

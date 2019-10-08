<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.function" />
<meta itemprop="path" content="Stable" />
</div>

# tf.function

``` python
tf.function(
    func=None,
    input_signature=None,
    autograph=True,
    experimental_autograph_options=None,
    experimental_relax_shapes=False
)
```



Defined in [`tensorflow/python/eager/def_function.py`](/code/stable/tensorflow/python/eager/def_function.py).

Creates a callable TensorFlow graph from a Python function.

`function` constructs a callable that executes a TensorFlow graph
(<a href="../tf/Graph.md"><code>tf.Graph</code></a>) created by tracing the TensorFlow operations in `func`.
This allows the TensorFlow runtime to apply optimizations and exploit
parallelism in the computation defined by `func`.

_Example Usage_

```python
def f(x, y):
  return tf.reduce_mean(tf.multiply(x ** 2, 3) + y)

g = tf.function(f)

x = tf.constant([[2.0, 3.0]])
y = tf.constant([[3.0, -2.0]])

# `f` and `g` will return the same value, but `g` will be executed as a
# TensorFlow graph.
assert f(x, y).numpy() == g(x, y).numpy()

# Tensors and tf.Variables used by the Python function are captured in the
# graph.
@tf.function
def h():
  return f(x, y)

assert (h().numpy() == f(x, y).numpy()).all()

# Data-dependent control flow is also captured in the graph. Supported
# control flow statements include `if`, `for`, `while`, `break`, `continue`,
# `return`.
@tf.function
def g(x):
  if tf.reduce_sum(x) > 0:
    return x * x
  else:
    return -x // 2

# print and TensorFlow side effects are supported, but exercise caution when
# using Python side effects like mutating objects, saving to files, etc.
l = []

@tf.function
def g(x):
  for i in x:
    print(i)                              # Works
    tf.compat.v1.assign(v, i)                       # Works
    tf.compat.v1.py_func(lambda i: l.append(i))(i)  # Works
    l.append(i)                           # Caution! Doesn't work.
```

Note that unlike other TensorFlow operations, we don't convert python
numerical inputs to tensors. Moreover, a new graph is generated for each
distinct python numerical value, for example calling `g(2)` and `g(3)` will
generate two new graphs (while only one is generated if you call
`g(tf.constant(2))` and `g(tf.constant(3))`). Therefore, python numerical
inputs should be restricted to arguments that will have few distinct values,
such as hyperparameters like the number of layers in a neural network. This
allows TensorFlow to optimize each variant of the neural network.

_Referencing <a href="../tf/Variable.md"><code>tf.Variable</code></a>s_

The Python function `func` may reference stateful objects (such as
<a href="../tf/Variable.md"><code>tf.Variable</code></a>).
These are captured as implicit inputs to the callable returned by `function`.
For example:

```python
c = tf.Variable(0)

@tf.function
def f(x):
  c.assign_add(1)
  return x + tf.compat.v1.to_float(c)

assert int(c) == 0
assert f(1.0) == 2.0
assert int(c) == 1
assert f(1.0) == 3.0
assert int(c) == 2
```

`function` can be applied to methods of an object. For example:

```python
class Dense(object):
  def __init__(self):
    self.W = tf.Variable(tf.compat.v1.glorot_uniform_initializer()((10, 10)))
    self.b = tf.Variable(tf.zeros(10))

  @tf.function
  def compute(self, x):
    return tf.matmul(x, self.W) + self.b

d1 = Dense()
d2 = Dense()
x = tf.random.uniform((10, 10))
# d1 and d2 are using distinct variables
assert not (d1.compute(x).numpy() == d2.compute(x).numpy()).all()
```

_Usage with <a href="../tf/keras.md"><code>tf.keras</code></a>_

The `call` methods of a <a href="../tf/keras/Model.md"><code>tf.keras.Model</code></a> subclass can be decorated with
`function` in order to apply graph execution optimizations on it.
For example:

```python
class MyModel(tf.keras.Model):
  def __init__(self, keep_probability=0.2):
    super(MyModel, self).__init__()
    self.dense1 = tf.keras.layers.Dense(4)
    self.dense2 = tf.keras.layers.Dense(5)
    self.keep_probability = keep_probability

  @tf.function
  def call(self, inputs, training=True):
    y = self.dense2(self.dense1(inputs))
    if training:
      return tf.nn.dropout(y, self.keep_probability)
    else:
      return y

model = MyModel()
model(x, training=True)  # executes a graph, with dropout
model(x, training=False) # executes a graph, without dropout
```

_Input Signatures_

`function` instantiates a separate graph for every unique set of input
shapes and datatypes. For example, the following code snippet will result
in three distinct graphs being traced, as each input has a different
shape.

```python
@tf.function
def f(x): return tf.add(x, 1.)

scalar = tf.constant(1.0)
vector = tf.constant([1.0, 1.0])
matrix = tf.constant([[3.0]])

f(scalar)
f(vector)
f(matrix)
```

An "input signature" can be optionally provided to `function` to control
the graphs traced. The input signature specifies the shape and type of each
`Tensor` argument to the function using a <a href="../tf/TensorSpec.md"><code>tf.TensorSpec</code></a> object. For example,
the following code snippet ensures that a single graph is created where the
input `Tensor` is required to be a floating point tensor with no restrictions
on shape.

```python
@tf.function(input_signature=[tf.TensorSpec(shape=None, dtype=tf.float32)])
def f(x): return tf.add(x, 1.)
```

When an `input_signature` is specified, the callable will convert the inputs
to the specified TensorSpecs.

_Tracing and staging_

When `autograph` is `True`, all Python control flow that depends on `Tensor`
values is staged into a TensorFlow graph. When `autograph` is `False`, the
function is traced and control flow is not allowed to depend on data.

Note that `function` only stages TensorFlow operations, all Python code that
`func` executes and does not depend on data will shape the _construction_ of
the graph.
For example, consider the following:

```python
import numpy as np

def add_noise():
  return tf.eye(5) + np.random.randn(5, 5)

traced = tf.function(add_noise)
```

`add_noise()` will return a different output every time it is invoked.
However, `traced()` will return the same value every time it is called,
since a particular random value generated by the `np.random.randn` call will
be inserted in the traced/staged TensorFlow graph as a constant. In this
particular example, replacing `np.random.randn(5, 5)` with
`tf.random.normal((5, 5))` will result in the same behavior for `add_noise()`
and `traced()`.

_Python Side-Effects_

A corollary of the previous discussion on tracing is the following: If a
Python function `func` has Python side-effects, then executing `func` multiple
times may not be semantically equivalent to executing `F = tf.function(func)`
multiple times; this difference is due to the fact that `function` only
captures the subgraph of TensorFlow operations that is constructed when `func`
is invoked to trace a graph.

The same is true if code with Python side effects is used inside control flow,
such as a loop. If your code uses side effects that are not intended to
control graph construction, wrap them inside `tf.compat.v1.py_func`.

_Retracing_

A single tf.function object might need to map to multiple computation graphs
under the hood. This should be visible only as performance (tracing graphs has
a nonzero computational and memory cost) but should not affect the correctness
of the program. A traced function should return the same result as it would
when run eagerly, assuming no unintended Python side-effects.

Calling a <a href="../tf/function.md"><code>tf.function</code></a> with tensor arguments of different dtypes should lead
to at least one computational graph per distinct set of dtypes. Alternatively,
always calling a <a href="../tf/function.md"><code>tf.function</code></a> with tensor arguments of the same shapes and
dtypes and the same non-tensor arguments should not lead to additional
retracings of your function.

Other than that, TensorFlow reserves the right to retrace functions as many
times as needed, to ensure that traced functions behave as they would when run
eagerly and to provide the best end-to-end performance. For example, the
behavior of how many traces TensorFlow will do when the function is repeatedly
called with different python scalars as arguments is left undefined to allow
for future optimizations.

To control the tracing behavior, use the following tools:
 - different <a href="../tf/function.md"><code>tf.function</code></a> objects are guaranteed to not share traces; and
 - specifying a signature or using concrete function objects returned from
   get_concrete_function() guarantees that only one function graph will be
   built.

#### Args:

* <b>`func`</b>: function to be compiled. If `func` is None, returns a decorator that
    can be invoked with a single argument - `func`. The end result is
    equivalent to providing all the arguments up front. In other words,
    `tf.function(input_signature=...)(func)` is equivalent to
    `tf.function(func, input_signature=...)`. The former can be used to
    decorate Python functions, for example:
      @tf.function(input_signature=...)
      def foo(...): ...
* <b>`input_signature`</b>: A possibly nested sequence of <a href="../tf/TensorSpec.md"><code>tf.TensorSpec</code></a> objects
    specifying the shapes and dtypes of the Tensors that will be supplied to
    this function. If `None`, a separate function is instantiated for each
    inferred input signature.  If input_signature is specified, every input to
    `func` must be a `Tensor`, and `func` cannot accept `**kwargs`.
* <b>`autograph`</b>: Whether autograph should be applied on `func` before tracing a
    graph. This allows for dynamic control flow (Python if's, loops etc.)
    in the traced graph. See https://www.tensorflow.org/guide/autograph for
      more information.
* <b>`experimental_autograph_options`</b>: Experimental knobs (in the form of a tuple
    of tensorflow.autograph.Feature values) to control behavior when
    autograph=True.
* <b>`experimental_relax_shapes`</b>: When true, argument shapes may be relaxed to
    avoid unecessary retracing.


#### Returns:

If `func` is not None, returns a callable that will execute the compiled
function (and return zero or more <a href="../tf/Tensor.md"><code>tf.Tensor</code></a> objects).
If `func` is None, returns a decorator that, when invoked with a single
`func` argument, returns a callable equivalent to the case above.


#### Raises:

* <b>`TypeError`</b>: If `input_signature` is neither `None` nor a sequence of
    `TensorSpec` objects.
# Variables

A TensorFlow **variable** is the best way to represent shared, persistent state
manipulated by your program.

Variables are manipulated via the <a href="../../api_docs/python/tf/Variable.md"><code>tf.Variable</code></a> class. A <a href="../../api_docs/python/tf/Variable.md"><code>tf.Variable</code></a>
represents a tensor whose value can be changed by running ops on it.  Specific
ops allow you to read and modify the values of this tensor. Higher level
libraries like <a href="../../api_docs/python/tf/keras.md"><code>tf.keras</code></a> use <a href="../../api_docs/python/tf/Variable.md"><code>tf.Variable</code></a> to store model parameters. This
guide covers how to create, update, and manage <a href="../../api_docs/python/tf/Variable.md"><code>tf.Variable</code></a>s in TensorFlow.

## Creating a Variable

To create a variable, simply provide the initial value

``` python
my_variable = tf.Variable(tf.zeros([1., 2., 3.]))
```

This creates a variable which is a three-dimensional tensor with shape `[1, 2,
3]` filled with zeros. This variable will, by default, have the `dtype`
<a href="../../api_docs/python/tf/dtypes.md#float32"><code>tf.float32</code></a>. The dtype is, if not specified, inferred from the initial
value. 

If there's a <a href="../../api_docs/python/tf/device.md"><code>tf.device</code></a> scope active, the variable will be placed on that
device; otherwise the variable will be placed on the "fastest" device compatible
with its dtype (this means most variables are automatically placed on a GPU if
one is available). For example, the following snippet creates a variable named
`v` and places it on the second GPU device:

``` python
with tf.device("/device:GPU:1"):
  v = tf.Variable(tf.zeros([10, 10]))
```

Ideally though you should use the <a href="../../api_docs/python/tf/distribute.md"><code>tf.distribute</code></a> API, as that allows you to
write your code once and have it work under many different distributed setups.

## Using variables

To use the value of a <a href="../../api_docs/python/tf/Variable.md"><code>tf.Variable</code></a> in a TensorFlow graph, simply treat it like
a normal <a href="../../api_docs/python/tf/Tensor.md"><code>tf.Tensor</code></a>:

``` python
v = tf.Variable(0.0)
w = v + 1  # w is a tf.Tensor which is computed based on the value of v.
           # Any time a variable is used in an expression it gets automatically
           # converted to a tf.Tensor representing its value.
```

To assign a value to a variable, use the methods `assign`, `assign_add`, and
friends in the <a href="../../api_docs/python/tf/Variable.md"><code>tf.Variable</code></a> class. For example, here is how you can call these
methods:

``` python
v = tf.Variable(0.0)
v.assign_add(1)
```

Most TensorFlow optimizers have specialized ops that efficiently update the
values of variables according to some gradient descent-like algorithm. See
<a href="../../api_docs/python/tf/keras/optimizers/Optimizer.md"><code>tf.keras.optimizers.Optimizer</code></a> for an explanation of how to use optimizers.

You can also explicitly read the current value of a variable, using
`read_value`:

```python
v = tf.Variable(0.0)
v.assign_add(1)
v.read_value()  # 1.0
```

When the last reference to a <a href="../../api_docs/python/tf/Variable.md"><code>tf.Variable</code></a> goes out of scope its memory is
freed.

### Keeping track of variables

A Variable in TensorFlow is a Python object. As you build your layers, models,
optimizers, and other related tools, you will likely want to get a list of all
variables in a (say) model.

While you can keep track of variables ad-hoc in your own Python code we
recommend you use <a href="../../api_docs/python/tf/Module.md"><code>tf.Module</code></a> as a base class for your classes which own
variables. Instances of <a href="../../api_docs/python/tf/Module.md"><code>tf.Module</code></a> have a `variables` and a
`trainable_variables` methods which return all (trainable) variables reachable
from that model, potentially navigating through other modules.

```python
class MyModuleOne(tf.Module):
  def __init__(self):
    self.v0 = tf.Variable(1.0)
    self.vs = [tf.Variable(x) for x in range(10)]
    
class MyOtherModule(tf.Module):
  def __init__(self):
    self.m = MyModuleOne()
    self.v = tf.Variable(10.0)
    
m = MyOtherModule()
len(m.variables)  # 12; 11 from m.m and another from m.v

```

Note that you're implementing a layer, `tf.keras.Layer` might be a better base
class, as implementing its interface will let your layer integrate fully into
Keras, allowing you to use `model.fit` and other well-integrated APIs. The
variable tracking of `tf.keras.Layer` is identical to that of <a href="../../api_docs/python/tf/Module.md"><code>tf.Module</code></a>.





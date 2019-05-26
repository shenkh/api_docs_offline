<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.GradientTape" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__enter__"/>
<meta itemprop="property" content="__exit__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="gradient"/>
<meta itemprop="property" content="reset"/>
<meta itemprop="property" content="stop_recording"/>
<meta itemprop="property" content="watch"/>
<meta itemprop="property" content="watched_variables"/>
</div>

# tf.GradientTape

## Class `GradientTape`



### Aliases:

* Class `tf.GradientTape`
* Class `tf.contrib.eager.GradientTape`



Defined in [`tensorflow/python/eager/backprop.py`](https://www.tensorflow.org/code/tensorflow/python/eager/backprop.py).

Record operations for automatic differentiation.

Operations are recorded if they are executed within this context manager and
at least one of their inputs is being "watched".

Trainable variables (created by <a href="../tf/Variable.md"><code>tf.Variable</code></a> or <a href="../tf/get_variable.md"><code>tf.get_variable</code></a>,
trainable=True is default in both cases) are automatically watched. Tensors
can be manually watched by invoking the `watch` method on this context
manager.

For example, consider the function `y = x * x`. The gradient at `x = 3.0` can
be computed as:

```python
x = tf.constant(3.0)
with tf.GradientTape() as g:
  g.watch(x)
  y = x * x
dy_dx = g.gradient(y, x) # Will compute to 6.0
```

GradientTapes can be nested to compute higher-order derivatives. For example,

```python
x = tf.constant(3.0)
with tf.GradientTape() as g:
  with tf.GradientTape() as gg:
    gg.watch(x)
    y = x * x
  dy_dx = gg.gradient(y, x)     # Will compute to 6.0
d2y_dx2 = g.gradient(dy_dx, x)  # Will compute to 2.0
```

By default, the resources held by a GradientTape are released as soon as
GradientTape.gradient() method is called. To compute multiple gradients over
the same computation, create a persistent gradient tape. This allows multiple
calls to the gradient() method as resources are released when the tape object
is garbage collected. For example:

```python
x = tf.constant(3.0)
with tf.GradientTape(persistent=True) as g:
  g.watch(x)
  y = x * x
  z = y * y
dz_dx = g.gradient(z, x)  # 108.0 (4*x^3 at x = 3)
dy_dx = g.gradient(y, x)  # 6.0
del g  # Drop the reference to the tape
```

Note that only tensors with real or complex dtypes are differentiable.

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(persistent=False)
```

Creates a new GradientTape.

#### Args:

* <b>`persistent`</b>: Boolean controlling whether a persistent gradient tape
    is created. False by default, which means at most one call can
    be made to the gradient() method on this object.



## Methods

<h3 id="__enter__"><code>__enter__</code></h3>

``` python
__enter__()
```

Enters a context inside which operations are recorded on this tape.

<h3 id="__exit__"><code>__exit__</code></h3>

``` python
__exit__(
    typ,
    value,
    traceback
)
```

Exits the recording context, no further operations are traced.

<h3 id="gradient"><code>gradient</code></h3>

``` python
gradient(
    target,
    sources,
    output_gradients=None
)
```

Computes the gradient using operations recorded in context of this tape.

#### Args:

* <b>`target`</b>: Tensor (or list of tensors) to be differentiated.
* <b>`sources`</b>: a list or nested structure of Tensors or Variables. `target`
    will be differentiated against elements in `sources`.
* <b>`output_gradients`</b>: a list of gradients, one for each element of
    target. Defaults to None.


#### Returns:

a list or nested structure of Tensors (or IndexedSlices, or None),
one for each element in `sources`. Returned structure is the same as
the structure of `sources`.


#### Raises:

* <b>`RuntimeError`</b>: if called inside the context of the tape, or if called more
   than once on a non-persistent tape.

<h3 id="reset"><code>reset</code></h3>

``` python
reset()
```

Clears all information stored in this tape.

Equivalent to exiting and reentering the tape context manager with a new
tape. For example, the two following code blocks are equivalent:
```
with tf.GradientTape() as t:
  loss = loss_fn()
with tf.GradientTape() as t:
  loss += other_loss_fn()
t.gradient(loss, ...)  # Only differentiates other_loss_fn, not loss_fn


# The following is equivalent to the above
with tf.GradientTape() as t:
  loss = loss_fn()
  t.reset()
  loss += other_loss_fn()
t.gradient(loss, ...)  # Only differentiates other_loss_fn, not loss_fn
```

This is useful if you don't want to exit the context manager for the tape,
or can't because the desired reset point is inside a control flow construct:

```
with tf.GradientTape() as t:
  loss = ...
  if loss > k:
    t.reset()
```

<h3 id="stop_recording"><code>stop_recording</code></h3>

``` python
stop_recording()
```

Temporarily stops recording operations on this tape.

Operations executed while this context manager is active will not be
recorded on the tape. This is useful for reducing the memory used by tracing
all computations.

For example:

```
  with tf.GradientTape(persistent=True) as t:
    loss = compute_loss(model)
    with t.stop_recording():
      # The gradient computation below is not traced, saving memory.
      grads = t.gradient(loss, model.variables)
```

#### Yields:

None

#### Raises:

* <b>`RuntimeError`</b>: if the tape is not currently recording.

<h3 id="watch"><code>watch</code></h3>

``` python
watch(tensor)
```

Ensures that `tensor` is being traced by this tape.

#### Args:

* <b>`tensor`</b>: a Tensor or list of Tensors.

<h3 id="watched_variables"><code>watched_variables</code></h3>

``` python
watched_variables()
```

Returns variables watched by this tape in order of construction.




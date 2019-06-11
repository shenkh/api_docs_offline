<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.vectorized_map" />
<meta itemprop="path" content="Stable" />
</div>

# tf.vectorized_map

Parallel map on the list of tensors unpacked from `elems` on dimension 0.

### Aliases:

* `tf.compat.v1.vectorized_map`
* `tf.compat.v2.vectorized_map`
* `tf.vectorized_map`

``` python
tf.vectorized_map(
    fn,
    elems
)
```



Defined in [`python/ops/parallel_for/control_flow_ops.py`](/code/stable/tensorflow/python/ops/parallel_for/control_flow_ops.py).

<!-- Placeholder for "Used in" -->


This method works similar to tf.map_fn but is optimized to run much faster,
but possibly with a much larger memory footprint. The speedups are obtained by
vectorization (see https://arxiv.org/pdf/1903.04243.pdf). The idea behind
vectorization is to semantically launch all the invocations of `fn` in
parallel and fuse corresponding operations across all these invocations. This
fusion is done statically at graph generation time and the generated code is
often similar in performance to a manually fused version.


For example, let's look at a method that calculates the outer product of a
matrix.

```python
def outer_product(a):
  return tf.tensordot(a, a, 0)

# outer_product was designed to not support batching.
c = outer_product(tf.ones((2, 3)))
# The shape is consistent
assert c.shape == (2, 3, 2, 3)
```

Now suppose we want an efficient batched version of outer_product. We can
simply write:

```python
batch_size = 100
a = tf.ones((batch_size, 32, 32))
c = tf.vectorized_map(outer_product, a)
assert c.shape == (batch_size, 32, 32, 32, 32)
 ```

Because <a href="../tf/vectorized_map.md"><code>tf.vectorized_map</code></a> fully parallelizes the batch, this method will
generally be significantly faster than using <a href="../tf/map_fn.md"><code>tf.map_fn</code></a>, especially in eager
mode.

This is an experimental feature and currently has a lot of limitations:
  - There should be no data dependency between the different semantic
    invocations of `fn`, i.e. it should be safe to map the elements of the
    inputs in any order.
  - Stateful kernels may mostly not be supported since these often imply a
    data dependency. We do support a limited set of such stateful kernels
    though (like RandomFoo, Variable operations like reads, etc).
  - `fn` has limited support for control flow operations. <a href="../tf/cond.md"><code>tf.cond</code></a> in
    particular is not supported.
  - `fn` should return nested structure of Tensors or Operations. However
    if an Operation is returned, it should have zero outputs.
  - The shape and dtype of `fn` outputs should not depend on the input
    to `fn`.

#### Args:


* <b>`fn`</b>: The callable to be performed. It accepts one argument, which will have
  the same (possibly nested) structure as `elems`, and returns a possibly
  nested structure of Tensors and Operations, which may be different than
  the structure of `elems`.
* <b>`elems`</b>: A tensor or (possibly nested) sequence of tensors, each of which will
  be unpacked along their first dimension. The nested sequence of the
  resulting slices will be mapped over by `fn`.


#### Returns:

A tensor or (possibly nested) sequence of tensors. Each tensor packs the
results of applying fn to tensors unpacked from elems along the first
dimension, from first to last.

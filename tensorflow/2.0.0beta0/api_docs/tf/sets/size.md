<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.sets.size" />
<meta itemprop="path" content="Stable" />
</div>

# tf.sets.size

Compute number of unique elements along last dimension of `a`.

### Aliases:

* `tf.compat.v1.sets.set_size`
* `tf.compat.v1.sets.size`
* `tf.compat.v2.sets.size`
* `tf.sets.size`

``` python
tf.sets.size(
    a,
    validate_indices=True
)
```



Defined in [`python/ops/sets_impl.py`](/code/stable/tensorflow/python/ops/sets_impl.py).

<!-- Placeholder for "Used in" -->


#### Args:


* <b>`a`</b>: `SparseTensor`, with indices sorted in row-major order.
* <b>`validate_indices`</b>: Whether to validate the order and range of sparse indices
   in `a`.


#### Returns:

`int32` `Tensor` of set sizes. For `a` ranked `n`, this is a `Tensor` with
rank `n-1`, and the same 1st `n-1` dimensions as `a`. Each value is the
number of unique elements in the corresponding `[0...n-1]` dimension of `a`.



#### Raises:


* <b>`TypeError`</b>: If `a` is an invalid types.
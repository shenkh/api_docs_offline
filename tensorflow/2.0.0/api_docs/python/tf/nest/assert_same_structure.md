<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.nest.assert_same_structure" />
<meta itemprop="path" content="Stable" />
</div>

# tf.nest.assert_same_structure

``` python
tf.nest.assert_same_structure(
    nest1,
    nest2,
    check_types=True,
    expand_composites=False
)
```



Defined in [`tensorflow/python/util/nest.py`](/code/stable/tensorflow/python/util/nest.py).

Asserts that two structures are nested in the same way.

Note that namedtuples with identical name and fields are always considered
to have the same shallow structure (even with `check_types=True`).
For instance, this code will print `True`:

```python
def nt(a, b):
  return collections.namedtuple('foo', 'a b')(a, b)
print(assert_same_structure(nt(0, 1), nt(2, 3)))
```

#### Args:

* <b>`nest1`</b>: an arbitrarily nested structure.
* <b>`nest2`</b>: an arbitrarily nested structure.
* <b>`check_types`</b>: if `True` (default) types of sequences are checked as well,
      including the keys of dictionaries. If set to `False`, for example a
      list and a tuple of objects will look the same if they have the same
      size. Note that namedtuples with identical name and fields are always
      considered to have the same shallow structure. Two types will also be
      considered the same if they are both list subtypes (which allows "list"
      and "_ListWrapper" from trackable dependency tracking to compare
      equal).
* <b>`expand_composites`</b>: If true, then composite tensors such as <a href="../../tf/sparse/SparseTensor.md"><code>tf.SparseTensor</code></a>
      and <a href="../../tf/RaggedTensor.md"><code>tf.RaggedTensor</code></a> are expanded into their component tensors.


#### Raises:

* <b>`ValueError`</b>: If the two structures do not have the same number of elements or
    if the two structures are not nested in the same way.
* <b>`TypeError`</b>: If the two structures differ in the type of sequence in any of
    their substructures. Only possible if `check_types` is `True`.
<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.Dimension" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="value"/>
<meta itemprop="property" content="__add__"/>
<meta itemprop="property" content="__div__"/>
<meta itemprop="property" content="__eq__"/>
<meta itemprop="property" content="__floordiv__"/>
<meta itemprop="property" content="__ge__"/>
<meta itemprop="property" content="__gt__"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="__le__"/>
<meta itemprop="property" content="__lt__"/>
<meta itemprop="property" content="__mod__"/>
<meta itemprop="property" content="__mul__"/>
<meta itemprop="property" content="__ne__"/>
<meta itemprop="property" content="__radd__"/>
<meta itemprop="property" content="__rdiv__"/>
<meta itemprop="property" content="__rfloordiv__"/>
<meta itemprop="property" content="__rmod__"/>
<meta itemprop="property" content="__rmul__"/>
<meta itemprop="property" content="__rsub__"/>
<meta itemprop="property" content="__rtruediv__"/>
<meta itemprop="property" content="__sub__"/>
<meta itemprop="property" content="__truediv__"/>
<meta itemprop="property" content="assert_is_compatible_with"/>
<meta itemprop="property" content="is_compatible_with"/>
<meta itemprop="property" content="merge_with"/>
</div>

# tf.compat.v1.Dimension

## Class `Dimension`

Represents the value of one dimension in a TensorShape.





Defined in [`python/framework/tensor_shape.py`](/code/stable/tensorflow/python/framework/tensor_shape.py).

<!-- Placeholder for "Used in" -->


<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(value)
```

Creates a new Dimension with the given value.




## Properties

<h3 id="value"><code>value</code></h3>

The value of this dimension, or None if it is unknown.




## Methods

<h3 id="__add__"><code>__add__</code></h3>

``` python
__add__(other)
```

Returns the sum of `self` and `other`.

Dimensions are summed as follows:

```python
tf.compat.v1.Dimension(m)    + tf.compat.v1.Dimension(n)     ==
tf.compat.v1.Dimension(m + n)
tf.compat.v1.Dimension(m)    + tf.compat.v1.Dimension(None)  # equiv. to
tf.compat.v1.Dimension(None)
tf.compat.v1.Dimension(None) + tf.compat.v1.Dimension(n)     # equiv. to
tf.compat.v1.Dimension(None)
tf.compat.v1.Dimension(None) + tf.compat.v1.Dimension(None)  # equiv. to
tf.compat.v1.Dimension(None)
```

#### Args:


* <b>`other`</b>: Another Dimension, or a value accepted by `as_dimension`.


#### Returns:

A Dimension whose value is the sum of `self` and `other`.


<h3 id="__div__"><code>__div__</code></h3>

``` python
__div__(other)
```

DEPRECATED: Use `__floordiv__` via `x // y` instead.

This function exists only for backwards compatibility purposes; new code
should use `__floordiv__` via the syntax `x // y`.  Using `x // y`
communicates clearly that the result rounds down, and is forward compatible
to Python 3.

#### Args:


* <b>`other`</b>: Another `Dimension`.


#### Returns:

A `Dimension` whose value is the integer quotient of `self` and `other`.


<h3 id="__eq__"><code>__eq__</code></h3>

``` python
__eq__(other)
```

Returns true if `other` has the same known value as this Dimension.


<h3 id="__floordiv__"><code>__floordiv__</code></h3>

``` python
__floordiv__(other)
```

Returns the quotient of `self` and `other` rounded down.

Dimensions are divided as follows:

```python
tf.compat.v1.Dimension(m)    // tf.compat.v1.Dimension(n)     ==
tf.compat.v1.Dimension(m // n)
tf.compat.v1.Dimension(m)    // tf.compat.v1.Dimension(None)  # equiv. to
tf.compat.v1.Dimension(None)
tf.compat.v1.Dimension(None) // tf.compat.v1.Dimension(n)     # equiv. to
tf.compat.v1.Dimension(None)
tf.compat.v1.Dimension(None) // tf.compat.v1.Dimension(None)  # equiv. to
tf.compat.v1.Dimension(None)
```

#### Args:


* <b>`other`</b>: Another Dimension, or a value accepted by `as_dimension`.


#### Returns:

A `Dimension` whose value is the integer quotient of `self` and `other`.


<h3 id="__ge__"><code>__ge__</code></h3>

``` python
__ge__(other)
```

Returns True if `self` is known to be greater than or equal to `other`.

Dimensions are compared as follows:

```python
(tf.compat.v1.Dimension(m)    >= tf.compat.v1.Dimension(n))    == (m >= n)
(tf.compat.v1.Dimension(m)    >= tf.compat.v1.Dimension(None)) == None
(tf.compat.v1.Dimension(None) >= tf.compat.v1.Dimension(n))    == None
(tf.compat.v1.Dimension(None) >= tf.compat.v1.Dimension(None)) == None
```

#### Args:


* <b>`other`</b>: Another Dimension.


#### Returns:

The value of `self.value >= other.value` if both are known, otherwise
None.


<h3 id="__gt__"><code>__gt__</code></h3>

``` python
__gt__(other)
```

Returns True if `self` is known to be greater than `other`.

Dimensions are compared as follows:

```python
(tf.compat.v1.Dimension(m)    > tf.compat.v1.Dimension(n))    == (m > n)
(tf.compat.v1.Dimension(m)    > tf.compat.v1.Dimension(None)) == None
(tf.compat.v1.Dimension(None) > tf.compat.v1.Dimension(n))    == None
(tf.compat.v1.Dimension(None) > tf.compat.v1.Dimension(None)) == None
```

#### Args:


* <b>`other`</b>: Another Dimension.


#### Returns:

The value of `self.value > other.value` if both are known, otherwise
None.


<h3 id="__le__"><code>__le__</code></h3>

``` python
__le__(other)
```

Returns True if `self` is known to be less than or equal to `other`.

Dimensions are compared as follows:

```python
(tf.compat.v1.Dimension(m)    <= tf.compat.v1.Dimension(n))    == (m <= n)
(tf.compat.v1.Dimension(m)    <= tf.compat.v1.Dimension(None)) == None
(tf.compat.v1.Dimension(None) <= tf.compat.v1.Dimension(n))    == None
(tf.compat.v1.Dimension(None) <= tf.compat.v1.Dimension(None)) == None
```

#### Args:


* <b>`other`</b>: Another Dimension.


#### Returns:

The value of `self.value <= other.value` if both are known, otherwise
None.


<h3 id="__lt__"><code>__lt__</code></h3>

``` python
__lt__(other)
```

Returns True if `self` is known to be less than `other`.

Dimensions are compared as follows:

```python
(tf.compat.v1.Dimension(m)    < tf.compat.v1.Dimension(n))    == (m < n)
(tf.compat.v1.Dimension(m)    < tf.compat.v1.Dimension(None)) == None
(tf.compat.v1.Dimension(None) < tf.compat.v1.Dimension(n))    == None
(tf.compat.v1.Dimension(None) < tf.compat.v1.Dimension(None)) == None
```

#### Args:


* <b>`other`</b>: Another Dimension.


#### Returns:

The value of `self.value < other.value` if both are known, otherwise
None.


<h3 id="__mod__"><code>__mod__</code></h3>

``` python
__mod__(other)
```

Returns `self` modulo `other`.

Dimension moduli are computed as follows:

```python
tf.compat.v1.Dimension(m)    % tf.compat.v1.Dimension(n)     ==
tf.compat.v1.Dimension(m % n)
tf.compat.v1.Dimension(m)    % tf.compat.v1.Dimension(None)  # equiv. to
tf.compat.v1.Dimension(None)
tf.compat.v1.Dimension(None) % tf.compat.v1.Dimension(n)     # equiv. to
tf.compat.v1.Dimension(None)
tf.compat.v1.Dimension(None) % tf.compat.v1.Dimension(None)  # equiv. to
tf.compat.v1.Dimension(None)
```

#### Args:


* <b>`other`</b>: Another Dimension, or a value accepted by `as_dimension`.


#### Returns:

A Dimension whose value is `self` modulo `other`.


<h3 id="__mul__"><code>__mul__</code></h3>

``` python
__mul__(other)
```

Returns the product of `self` and `other`.

Dimensions are summed as follows:

```python
tf.compat.v1.Dimension(m)    * tf.compat.v1.Dimension(n)     ==
tf.compat.v1.Dimension(m * n)
tf.compat.v1.Dimension(m)    * tf.compat.v1.Dimension(None)  # equiv. to
tf.compat.v1.Dimension(None)
tf.compat.v1.Dimension(None) * tf.compat.v1.Dimension(n)     # equiv. to
tf.compat.v1.Dimension(None)
tf.compat.v1.Dimension(None) * tf.compat.v1.Dimension(None)  # equiv. to
tf.compat.v1.Dimension(None)
```

#### Args:


* <b>`other`</b>: Another Dimension, or a value accepted by `as_dimension`.


#### Returns:

A Dimension whose value is the product of `self` and `other`.


<h3 id="__ne__"><code>__ne__</code></h3>

``` python
__ne__(other)
```

Returns true if `other` has a different known value from `self`.


<h3 id="__radd__"><code>__radd__</code></h3>

``` python
__radd__(other)
```

Returns the sum of `other` and `self`.


#### Args:


* <b>`other`</b>: Another Dimension, or a value accepted by `as_dimension`.


#### Returns:

A Dimension whose value is the sum of `self` and `other`.


<h3 id="__rdiv__"><code>__rdiv__</code></h3>

``` python
__rdiv__(other)
```

Use `__floordiv__` via `x // y` instead.

This function exists only to have a better error message. Instead of:
`TypeError: unsupported operand type(s) for /: 'int' and 'Dimension'`,
this function will explicitly call for usage of `//` instead.

#### Args:


* <b>`other`</b>: Another `Dimension`.


#### Raises:

TypeError.


<h3 id="__rfloordiv__"><code>__rfloordiv__</code></h3>

``` python
__rfloordiv__(other)
```

Returns the quotient of `other` and `self` rounded down.


#### Args:


* <b>`other`</b>: Another Dimension, or a value accepted by `as_dimension`.


#### Returns:

A `Dimension` whose value is the integer quotient of `self` and `other`.


<h3 id="__rmod__"><code>__rmod__</code></h3>

``` python
__rmod__(other)
```

Returns `other` modulo `self`.


#### Args:


* <b>`other`</b>: Another Dimension, or a value accepted by `as_dimension`.


#### Returns:

A Dimension whose value is `other` modulo `self`.


<h3 id="__rmul__"><code>__rmul__</code></h3>

``` python
__rmul__(other)
```

Returns the product of `self` and `other`.


#### Args:


* <b>`other`</b>: Another Dimension, or a value accepted by `as_dimension`.


#### Returns:

A Dimension whose value is the product of `self` and `other`.


<h3 id="__rsub__"><code>__rsub__</code></h3>

``` python
__rsub__(other)
```

Returns the subtraction of `self` from `other`.


#### Args:


* <b>`other`</b>: Another Dimension, or a value accepted by `as_dimension`.


#### Returns:

A Dimension whose value is the subtraction of `self` from `other`.


<h3 id="__rtruediv__"><code>__rtruediv__</code></h3>

``` python
__rtruediv__(other)
```

Use `__floordiv__` via `x // y` instead.

This function exists only to have a better error message. Instead of:
`TypeError: unsupported operand type(s) for /: 'int' and 'Dimension'`,
this function will explicitly call for usage of `//` instead.

#### Args:


* <b>`other`</b>: Another `Dimension`.


#### Raises:

TypeError.


<h3 id="__sub__"><code>__sub__</code></h3>

``` python
__sub__(other)
```

Returns the subtraction of `other` from `self`.

Dimensions are subtracted as follows:

```python
tf.compat.v1.Dimension(m)    - tf.compat.v1.Dimension(n)     ==
tf.compat.v1.Dimension(m - n)
tf.compat.v1.Dimension(m)    - tf.compat.v1.Dimension(None)  # equiv. to
tf.compat.v1.Dimension(None)
tf.compat.v1.Dimension(None) - tf.compat.v1.Dimension(n)     # equiv. to
tf.compat.v1.Dimension(None)
tf.compat.v1.Dimension(None) - tf.compat.v1.Dimension(None)  # equiv. to
tf.compat.v1.Dimension(None)
```

#### Args:


* <b>`other`</b>: Another Dimension, or a value accepted by `as_dimension`.


#### Returns:

A Dimension whose value is the subtraction of `other` from `self`.


<h3 id="__truediv__"><code>__truediv__</code></h3>

``` python
__truediv__(other)
```

Use `__floordiv__` via `x // y` instead.

This function exists only to have a better error message. Instead of:
`TypeError: unsupported operand type(s) for /: 'Dimension' and 'int'`,
this function will explicitly call for usage of `//` instead.

#### Args:


* <b>`other`</b>: Another `Dimension`.


#### Raises:

TypeError.


<h3 id="assert_is_compatible_with"><code>assert_is_compatible_with</code></h3>

``` python
assert_is_compatible_with(other)
```

Raises an exception if `other` is not compatible with this Dimension.


#### Args:


* <b>`other`</b>: Another Dimension.


#### Raises:


* <b>`ValueError`</b>: If `self` and `other` are not compatible (see
  is_compatible_with).

<h3 id="is_compatible_with"><code>is_compatible_with</code></h3>

``` python
is_compatible_with(other)
```

Returns true if `other` is compatible with this Dimension.

Two known Dimensions are compatible if they have the same value.
An unknown Dimension is compatible with all other Dimensions.

#### Args:


* <b>`other`</b>: Another Dimension.


#### Returns:

True if this Dimension and `other` are compatible.


<h3 id="merge_with"><code>merge_with</code></h3>

``` python
merge_with(other)
```

Returns a Dimension that combines the information in `self` and `other`.

Dimensions are combined as follows:

```python
tf.compat.v1.Dimension(n)   .merge_with(tf.compat.v1.Dimension(n))     ==
tf.compat.v1.Dimension(n)
tf.compat.v1.Dimension(n)   .merge_with(tf.compat.v1.Dimension(None))  ==
tf.compat.v1.Dimension(n)
tf.compat.v1.Dimension(None).merge_with(tf.compat.v1.Dimension(n))     ==
tf.compat.v1.Dimension(n)
# equivalent to tf.compat.v1.Dimension(None)
tf.compat.v1.Dimension(None).merge_with(tf.compat.v1.Dimension(None))

# raises ValueError for n != m
tf.compat.v1.Dimension(n)   .merge_with(tf.compat.v1.Dimension(m))
```

#### Args:


* <b>`other`</b>: Another Dimension.


#### Returns:

A Dimension containing the combined information of `self` and
`other`.



#### Raises:


* <b>`ValueError`</b>: If `self` and `other` are not compatible (see
  is_compatible_with).




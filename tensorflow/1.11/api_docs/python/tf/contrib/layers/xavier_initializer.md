<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.layers.xavier_initializer" />
<meta itemprop="path" content="Stable" />
</div>

# tf.contrib.layers.xavier_initializer

### Aliases:

* `tf.contrib.layers.xavier_initializer`
* `tf.contrib.layers.xavier_initializer_conv2d`

``` python
tf.contrib.layers.xavier_initializer(
    uniform=True,
    seed=None,
    dtype=tf.float32
)
```



Defined in [`tensorflow/contrib/layers/python/layers/initializers.py`](https://www.tensorflow.org/code/tensorflow/contrib/layers/python/layers/initializers.py).

Returns an initializer performing "Xavier" initialization for weights.

This function implements the weight initialization from:

Xavier Glorot and Yoshua Bengio (2010):
         [Understanding the difficulty of training deep feedforward neural
         networks. International conference on artificial intelligence and
         statistics.](
         http://www.jmlr.org/proceedings/papers/v9/glorot10a/glorot10a.pdf)

This initializer is designed to keep the scale of the gradients roughly the
same in all layers. In uniform distribution this ends up being the range:
`x = sqrt(6. / (in + out)); [-x, x]` and for normal distribution a standard
deviation of `sqrt(2. / (in + out))` is used.

#### Args:

* <b>`uniform`</b>: Whether to use uniform or normal distributed random initialization.
* <b>`seed`</b>: A Python integer. Used to create random seeds. See
        <a href="../../../tf/set_random_seed.md"><code>tf.set_random_seed</code></a> for behavior.
* <b>`dtype`</b>: The data type. Only floating point types are supported.


#### Returns:

An initializer for a weight matrix.
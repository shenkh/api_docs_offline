<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.gan.CycleGANModel" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="model_x2y"/>
<meta itemprop="property" content="model_y2x"/>
<meta itemprop="property" content="reconstructed_x"/>
<meta itemprop="property" content="reconstructed_y"/>
<meta itemprop="property" content="__new__"/>
</div>

# tf.contrib.gan.CycleGANModel

## Class `CycleGANModel`





Defined in [`tensorflow/contrib/gan/python/namedtuples.py`](https://www.tensorflow.org/code/tensorflow/contrib/gan/python/namedtuples.py).

An CycleGANModel contains all the pieces needed for CycleGAN training.

The model `model_x2y` generator F maps data set X to Y, while the model
`model_y2x` generator G maps data set Y to X.

See https://arxiv.org/abs/1703.10593 for more details.

#### Args:

* <b>`model_x2y`</b>: A `GANModel` namedtuple whose generator maps data set X to Y.
* <b>`model_y2x`</b>: A `GANModel` namedtuple whose generator maps data set Y to X.
* <b>`reconstructed_x`</b>: A `Tensor` of reconstructed data X which is G(F(X)).
* <b>`reconstructed_y`</b>: A `Tensor` of reconstructed data Y which is F(G(Y)).

<h2 id="__new__"><code>__new__</code></h2>

``` python
__new__(
    _cls,
    model_x2y,
    model_y2x,
    reconstructed_x,
    reconstructed_y
)
```

Create new instance of CycleGANModel(model_x2y, model_y2x, reconstructed_x, reconstructed_y)



## Properties

<h3 id="model_x2y"><code>model_x2y</code></h3>

Alias for field number 0

<h3 id="model_y2x"><code>model_y2x</code></h3>

Alias for field number 1

<h3 id="reconstructed_x"><code>reconstructed_x</code></h3>

Alias for field number 2

<h3 id="reconstructed_y"><code>reconstructed_y</code></h3>

Alias for field number 3




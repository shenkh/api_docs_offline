<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.gan.eval.add_cyclegan_image_summaries" />
</div>

# tf.contrib.gan.eval.add_cyclegan_image_summaries

### Aliases:

* `tf.contrib.gan.eval.add_cyclegan_image_summaries`
* `tf.contrib.gan.eval.summaries.add_cyclegan_image_summaries`

``` python
tf.contrib.gan.eval.add_cyclegan_image_summaries(cyclegan_model)
```



Defined in [`tensorflow/contrib/gan/python/eval/python/summaries_impl.py`](https://www.tensorflow.org/code/tensorflow/contrib/gan/python/eval/python/summaries_impl.py).

Adds image summaries for CycleGAN.

There are two summaries, one for each generator. The first image is the
generator input, the second is the generator output, and the third is G(F(x)).

#### Args:

* <b>`cyclegan_model`</b>: A CycleGANModel tuple.


#### Raises:

* <b>`ValueError`</b>: If `cyclegan_model` isn't a CycleGANModel.
* <b>`ValueError`</b>: If generated data, generator inputs, and reconstructions aren't
    images.
* <b>`ValueError`</b>: If the generator input, generated data, and reconstructions
    aren't all the same size.
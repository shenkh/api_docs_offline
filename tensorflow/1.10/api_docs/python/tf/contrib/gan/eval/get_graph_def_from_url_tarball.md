<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.gan.eval.get_graph_def_from_url_tarball" />
</div>

# tf.contrib.gan.eval.get_graph_def_from_url_tarball

### Aliases:

* `tf.contrib.gan.eval.classifier_metrics.get_graph_def_from_url_tarball`
* `tf.contrib.gan.eval.get_graph_def_from_url_tarball`

``` python
tf.contrib.gan.eval.get_graph_def_from_url_tarball(
    url,
    filename,
    tar_filename=None
)
```



Defined in [`tensorflow/contrib/gan/python/eval/python/classifier_metrics_impl.py`](https://www.tensorflow.org/code/tensorflow/contrib/gan/python/eval/python/classifier_metrics_impl.py).

Get a GraphDef proto from a tarball on the web.

#### Args:

* <b>`url`</b>: Web address of tarball
* <b>`filename`</b>: Filename of graph definition within tarball
* <b>`tar_filename`</b>: Temporary download filename (None = always download)


#### Returns:

A GraphDef loaded from a file in the downloaded tarball.
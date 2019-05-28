<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.bigtable.BigtableClient" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="table"/>
</div>

# tf.contrib.bigtable.BigtableClient

## Class `BigtableClient`



### Aliases:

* Class `tf.contrib.bigtable.BigtableClient`
* Class `tf.contrib.cloud.BigtableClient`



Defined in [`tensorflow/contrib/bigtable/python/ops/bigtable_api.py`](https://www.tensorflow.org/code/tensorflow/contrib/bigtable/python/ops/bigtable_api.py).

BigtableClient is the entrypoint for interacting with Cloud Bigtable in TF.

BigtableClient encapsulates a connection to Cloud Bigtable, and exposes the
`table` method to open a Bigtable Table.

## Methods

<h3 id="__init__"><code>__init__</code></h3>

``` python
__init__(
    project_id,
    instance_id,
    connection_pool_size=None,
    max_receive_message_size=None
)
```

Creates a BigtableClient that can be used to open connections to tables.

#### Args:

* <b>`project_id`</b>: A string representing the GCP project id to connect to.
* <b>`instance_id`</b>: A string representing the Bigtable instance to connect to.
* <b>`connection_pool_size`</b>: (Optional.) A number representing the number of
    concurrent connections to the Cloud Bigtable service to make.
* <b>`max_receive_message_size`</b>: (Optional.) The maximum bytes received in a
    single gRPC response.


#### Raises:

* <b>`ValueError`</b>: if the arguments are invalid (e.g. wrong type, or out of
    expected ranges (e.g. negative).)

<h3 id="table"><code>table</code></h3>

``` python
table(
    name,
    snapshot=None
)
```

Opens a table and returns a `BigtableTable` object.

#### Args:

* <b>`name`</b>: A <a href="../../../tf/string.md"><code>tf.string</code></a> <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a> name of the table to open.
* <b>`snapshot`</b>: Either a <a href="../../../tf/string.md"><code>tf.string</code></a> <a href="../../../tf/Tensor.md"><code>tf.Tensor</code></a> snapshot id, or `True` to
    request the creation of a snapshot. (Note: currently unimplemented.)


#### Returns:

A `BigtableTable` python object representing the operations available on
the table.




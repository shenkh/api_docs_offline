<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.tpu.keras_to_tpu_model" />
</div>

# tf.contrib.tpu.keras_to_tpu_model

``` python
tf.contrib.tpu.keras_to_tpu_model(
    *args,
    **kwargs
)
```



Defined in [`tensorflow/contrib/framework/python/framework/experimental.py`](https://www.tensorflow.org/code/tensorflow/contrib/framework/python/framework/experimental.py).

Copy `model` along with weights to the TPU.  Returns a TPU model. (experimental)

THIS FUNCTION IS EXPERIMENTAL. It may change or be removed at any time, and without warning.

Usage:
```
a = Input(shape=(32,))
b = Dense(32)(a)
model = Model(inputs=a, outputs=b)

# If `num_cores_per_host` is greater than one, batch parallelism will be used
# to run on multiple TPU cores.
strategy = keras_support.TPUDistributionStrategy(num_cores_per_host=8)
model = keras_support.tpu_model(model, strategy)
model.compile(
    optimizer=tf.train.GradientDescentOptimizer(learning_rate=1.0),
    ...)
model.shutdown()
```

#### Args:

* <b>`model`</b>: A `KerasTPUModel`.
* <b>`tpu_name_or_address`</b>: A string that is either the name of the Cloud TPU,
    the grpc address of the Cloud TPU, or (Googlers only) the BNS name of the
    Cloud TPU. If tpu_name_or_address is None, the TPUClusterResolver will
    examine the environment to determine a potential Cloud TPU to use.
* <b>`strategy`</b>: `TPUDistributionStrategy`.  The strategy to use for replicating
            model across multiple TPU cores.


#### Returns:

A new `KerasTPUModel` instance.
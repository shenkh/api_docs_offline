<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.learning_phase" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.learning_phase

``` python
tf.keras.backend.learning_phase()
```



Defined in [`tensorflow/python/keras/backend.py`](/code/stable/tensorflow/python/keras/backend.py).

Returns the learning phase flag.

The learning phase flag is a bool tensor (0 = test, 1 = train)
to be passed as input to any Keras function
that uses a different behavior at train time and test time.

#### Returns:

Learning phase (scalar integer tensor or Python integer).
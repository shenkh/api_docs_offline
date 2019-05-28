<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.eager.run" />
</div>

# tf.contrib.eager.run

``` python
tf.contrib.eager.run(
    main=None,
    argv=None
)
```



Defined in [`tensorflow/python/framework/ops.py`](https://www.tensorflow.org/code/tensorflow/python/framework/ops.py).

Runs the program with an optional main function and argv list.

The program will run with eager execution enabled.

Example:
```python
import tensorflow as tf
# Import subject to future changes:
from tensorflow.contrib.eager.python import tfe

def main(_):
  u = tf.constant(6.0)
  v = tf.constant(7.0)
  print(u * v)

if __name__ == "__main__":
  tfe.run()
```

#### Args:

* <b>`main`</b>: the main function to run.
* <b>`argv`</b>: the arguments to pass to it.
# Regression Examples

This unit provides the following short examples demonstrating how
to implement regression in Estimators:

<table>
  <tr> <th>Example</th> <th>Demonstrates How To...</th></tr>

  <tr>
    <td><a href="https://www.tensorflow.org/code/tensorflow/examples/get_started/regression/linear_regression_categorical.py">linear_regression_categorical.py</a></td>
    <td>Use the <a href="../../api_docs/python/tf/estimator/LinearRegressor.md"><code>tf.estimator.LinearRegressor</code></a> Estimator to train a
        regression model on categorical data.</td>
  </tr>

  <tr>
    <td><a href="https://www.tensorflow.org/code/tensorflow/examples/get_started/regression/dnn_regression.py">dnn_regression.py</a></td>
    <td>Use the <a href="../../api_docs/python/tf/estimator/DNNRegressor.md"><code>tf.estimator.DNNRegressor</code></a> Estimator to train a
        regression model on discrete data with a deep neural network.</td>
  </tr>

  <tr>
    <td><a href="https://www.tensorflow.org/code/tensorflow/examples/get_started/regression/custom_regression.py">custom_regression.py</a></td>
    <td>Use <a href="../../api_docs/python/tf/estimator/Estimator.md"><code>tf.estimator.Estimator</code></a> to train a customized dnn
        regression model.</td>
  </tr>

</table>

The preceding examples rely on the following data set utility:

<table>
  <tr> <th>Utility</th> <th>Description</th></tr>

  <tr>
    <td><a href="https://www.tensorflow.org/code/tensorflow/examples/get_started/regression/imports85.py">imports85.py</a></td>
    <td>This program provides utility functions that load the
        <tt>imports85</tt> data set into formats that other TensorFlow
        programs (for example, <tt>linear_regression.py</tt> and
        <tt>dnn_regression.py</tt>) can use.</td>
  </tr>


</table>


<!--
<h2 id="Linear_regression_concepts">Linear regression concepts</h2>

If you are new to machine learning and want to learn about regression,
watch the following video:

(todo:jbgordon) Video introduction goes here.
-->

<!--
[When MLCC becomes available externally, add links to the relevant MLCC units.]
-->


<a name="running"></a>
<h2 id="Running_the_examples">Running the examples</h2>

You must [install TensorFlow](../../install/) prior to running these examples.
Depending on the way you've installed TensorFlow, you might also
need to activate your TensorFlow environment.  Then, do the following:

1. Clone the TensorFlow repository from github.
2. `cd` to the top of the downloaded tree.
3. Check out the branch for you current tensorflow version: `git checkout rX.X`
4. `cd tensorflow/examples/get_started/regression`.

You can now run any of the example TensorFlow programs in the
`tensorflow/examples/get_started/regression` directory as you
would run any Python program:

```bsh
python linear_regressor.py
```

During training, all three programs output the following information:

* The name of the checkpoint directory, which is important for TensorBoard.
* The training loss after every 100 iterations, which helps you
  determine whether the model is converging.

For example, here's some possible output for the `linear_regressor.py`
program:

``` None
INFO:tensorflow:Saving checkpoints for 1 into /tmp/tmpAObiz9/model.ckpt.
INFO:tensorflow:loss = 161.308, step = 1
INFO:tensorflow:global_step/sec: 1557.24
INFO:tensorflow:loss = 15.7937, step = 101 (0.065 sec)
INFO:tensorflow:global_step/sec: 1529.17
INFO:tensorflow:loss = 12.1988, step = 201 (0.065 sec)
INFO:tensorflow:global_step/sec: 1663.86
...
INFO:tensorflow:loss = 6.99378, step = 901 (0.058 sec)
INFO:tensorflow:Saving checkpoints for 1000 into /tmp/tmpAObiz9/model.ckpt.
INFO:tensorflow:Loss for final step: 5.12413.
```


<a name="basic"></a>
<h2 id="linear_regressor_py">linear_regressor.py</h2>

`linear_regressor.py` trains a model that predicts the price of a car from
two numerical features.

<table>
  <tr>
    <td>Estimator</td>
    <td><tt>LinearRegressor</tt>, which is a pre-made Estimator for linear
        regression.</td>
  </tr>

  <tr>
    <td>Features</td>
    <td>Numerical: <tt>body-style</tt> and <tt>make</tt>.</td>
  </tr>

  <tr>
    <td>Label</td>
    <td>Numerical: <tt>price</tt>
  </tr>

  <tr>
    <td>Algorithm</td>
    <td>Linear regression.</td>
  </tr>
</table>

After training the model, the program concludes by outputting predicted
car prices for two car models.



<a name="categorical"></a>
<h2 id="linear_regression_categorical_py">linear_regression_categorical.py</h2>

This program illustrates ways to represent categorical features. It
also demonstrates how to train a linear model based on a mix of
categorical and numerical features.

<table>
  <tr>
    <td>Estimator</td>
    <td><tt>LinearRegressor</tt>, which is a pre-made Estimator for linear
        regression. </td>
  </tr>

  <tr>
    <td>Features</td>
    <td>Categorical: <tt>curb-weight</tt> and <tt>highway-mpg</tt>.<br/>
        Numerical: <tt>body-style</tt> and <tt>make</tt>.</td>
  </tr>

  <tr>
    <td>Label</td>
    <td>Numerical: <tt>price</tt>.</td>
  </tr>

  <tr>
    <td>Algorithm</td>
    <td>Linear regression.</td>
  </tr>
</table>


<a name="dnn"></a>
<h2 id="dnn_regression_py">dnn_regression.py</h2>

Like `linear_regression_categorical.py`, the `dnn_regression.py` example
trains a model that predicts the price of a car from two features.
Unlike `linear_regression_categorical.py`, the `dnn_regression.py` example uses
a deep neural network to train the model.  Both examples rely on the same
features; `dnn_regression.py` demonstrates how to treat categorical features
in a deep neural network.

<table>
  <tr>
    <td>Estimator</td>
    <td><tt>DNNRegressor</tt>, which is a pre-made Estimator for
        regression that relies on a deep neural network.  The
        `hidden_units` parameter defines the topography of the network.</td>
  </tr>

  <tr>
    <td>Features</td>
    <td>Categorical: <tt>curb-weight</tt> and <tt>highway-mpg</tt>.<br/>
        Numerical: <tt>body-style</tt> and <tt>make</tt>.</td>
  </tr>

  <tr>
    <td>Label</td>
    <td>Numerical: <tt>price</tt>.</td>
  </tr>

  <tr>
    <td>Algorithm</td>
    <td>Regression through a deep neural network.</td>
  </tr>
</table>

After printing loss values, the program outputs the Mean Square Error
on a test set.


<a name="dnn"></a>
<h2 id="custom_regression_py">custom_regression.py</h2>

The `custom_regression.py` example also trains a model that predicts the price
of a car based on mixed real-valued and categorical input features, described by
feature_columns. Unlike `linear_regression_categorical.py`, and
`dnn_regression.py` this example does not use a pre-made estimator, but defines
a custom model using the base <a href="../../api_docs/python/tf/estimator/Estimator.md"><code>tf.estimator.Estimator</code></a> class. The
custom model is quite similar to the model defined by `dnn_regression.py`.

The custom model is defined by the `model_fn` argument to the constructor. The
customization is made more reusable through `params` dictionary, which is later
passed through to the `model_fn` when the `model_fn` is called.

The `model_fn` returns an
<a href="../../api_docs/python/tf/estimator/EstimatorSpec.md"><code>tf.estimator.EstimatorSpec</code></a> which is a simple structure
indicating to the `Estimator` which operations should be run to accomplish
various tasks.

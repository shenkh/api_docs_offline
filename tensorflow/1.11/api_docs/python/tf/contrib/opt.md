<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.opt" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.contrib.opt



Defined in [`tensorflow/contrib/opt/__init__.py`](https://www.tensorflow.org/code/tensorflow/contrib/opt/__init__.py).

A module containing optimization routines.

## Classes

[`class AdaMaxOptimizer`](../../tf/contrib/opt/AdaMaxOptimizer.md): Optimizer that implements the AdaMax algorithm.

[`class AdamWOptimizer`](../../tf/contrib/opt/AdamWOptimizer.md): Optimizer that implements the Adam algorithm with weight decay.

[`class AddSignOptimizer`](../../tf/contrib/opt/AddSignOptimizer.md): Optimizer that implements the AddSign update.

[`class DecoupledWeightDecayExtension`](../../tf/contrib/opt/DecoupledWeightDecayExtension.md): This class allows to extend optimizers with decoupled weight decay.

[`class DropStaleGradientOptimizer`](../../tf/contrib/opt/DropStaleGradientOptimizer.md): Wrapper optimizer that checks and drops stale gradient.

[`class ElasticAverageCustomGetter`](../../tf/contrib/opt/ElasticAverageCustomGetter.md): Custom_getter class is used to do:

[`class ElasticAverageOptimizer`](../../tf/contrib/opt/ElasticAverageOptimizer.md): Wrapper optimizer that implements the Elastic Average SGD algorithm.

[`class ExternalOptimizerInterface`](../../tf/contrib/opt/ExternalOptimizerInterface.md): Base class for interfaces with external optimization algorithms.

[`class GGTOptimizer`](../../tf/contrib/opt/GGTOptimizer.md): Optimizer that implements the GGT algorithm.

[`class LARSOptimizer`](../../tf/contrib/opt/LARSOptimizer.md): Layer-wise Adaptive Rate Scaling for large batch training.

[`class LazyAdamOptimizer`](../../tf/contrib/opt/LazyAdamOptimizer.md): Variant of the Adam optimizer that handles sparse updates more efficiently.

[`class ModelAverageCustomGetter`](../../tf/contrib/opt/ModelAverageCustomGetter.md): Custom_getter class is used to do.

[`class ModelAverageOptimizer`](../../tf/contrib/opt/ModelAverageOptimizer.md): Wrapper optimizer that implements the Model Average algorithm.

[`class MomentumWOptimizer`](../../tf/contrib/opt/MomentumWOptimizer.md): Optimizer that implements the Momentum algorithm with weight_decay.

[`class MovingAverageOptimizer`](../../tf/contrib/opt/MovingAverageOptimizer.md): Optimizer that computes a moving average of the variables.

[`class MultitaskOptimizerWrapper`](../../tf/contrib/opt/MultitaskOptimizerWrapper.md): Optimizer wrapper making all-zero gradients harmless.

[`class NadamOptimizer`](../../tf/contrib/opt/NadamOptimizer.md): Optimizer that implements the Nadam algorithm.

[`class PowerSignOptimizer`](../../tf/contrib/opt/PowerSignOptimizer.md): Optimizer that implements the PowerSign update.

[`class RegAdagradOptimizer`](../../tf/contrib/opt/RegAdagradOptimizer.md): RegAdagrad: Adagrad with updates that optionally skip updating the slots.

[`class ScipyOptimizerInterface`](../../tf/contrib/opt/ScipyOptimizerInterface.md): Wrapper allowing `scipy.optimize.minimize` to operate a <a href="../../tf/Session.md"><code>tf.Session</code></a>.

[`class ShampooOptimizer`](../../tf/contrib/opt/ShampooOptimizer.md): The Shampoo Optimizer

[`class VariableClippingOptimizer`](../../tf/contrib/opt/VariableClippingOptimizer.md): Wrapper optimizer that clips the norm of specified variables after update.

## Functions

[`clip_gradients_by_global_norm(...)`](../../tf/contrib/opt/clip_gradients_by_global_norm.md): Clips gradients of a multitask loss by their global norm.

[`extend_with_decoupled_weight_decay(...)`](../../tf/contrib/opt/extend_with_decoupled_weight_decay.md): Factory function returning an optimizer class with decoupled weight decay.


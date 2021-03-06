<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.contrib.gan" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.contrib.gan



Defined in [`tensorflow/contrib/gan/__init__.py`](/code/stable/tensorflow/contrib/gan/__init__.py).

TFGAN is a lightweight library for training and evaluating GANs.

In addition to providing the infrastructure for easily training and evaluating
GANS, this library contains modules for a TFGAN-backed Estimator,
evaluation metrics, features (such as virtual batch normalization), and losses.
Please see README.md for details and usage.

## Modules

[`estimator`](../../tf/contrib/gan/estimator.md) module: TFGAN estimator module.

[`eval`](../../tf/contrib/gan/eval.md) module: TFGAN evaluation module.

[`features`](../../tf/contrib/gan/features.md) module: TFGAN features module.

[`losses`](../../tf/contrib/gan/losses.md) module: TFGAN losses and penalties.

## Classes

[`class ACGANModel`](../../tf/contrib/gan/ACGANModel.md): An ACGANModel contains all the pieces needed for ACGAN training.

[`class CycleGANLoss`](../../tf/contrib/gan/CycleGANLoss.md): CycleGANLoss contains the losses for `CycleGANModel`.

[`class CycleGANModel`](../../tf/contrib/gan/CycleGANModel.md): An CycleGANModel contains all the pieces needed for CycleGAN training.

[`class GANLoss`](../../tf/contrib/gan/GANLoss.md): GANLoss contains the generator and discriminator losses.

[`class GANModel`](../../tf/contrib/gan/GANModel.md): A GANModel contains all the pieces needed for GAN training.

[`class GANTrainOps`](../../tf/contrib/gan/GANTrainOps.md): GANTrainOps contains the training ops.

[`class GANTrainSteps`](../../tf/contrib/gan/GANTrainSteps.md): Contains configuration for the GAN Training.

[`class InfoGANModel`](../../tf/contrib/gan/InfoGANModel.md): An InfoGANModel contains all the pieces needed for InfoGAN training.

[`class RunTrainOpsHook`](../../tf/contrib/gan/RunTrainOpsHook.md): A hook to run train ops a fixed number of times.

[`class StarGANModel`](../../tf/contrib/gan/StarGANModel.md): A StarGANModel contains all the pieces needed for StarGAN training.

## Functions

[`acgan_model(...)`](../../tf/contrib/gan/acgan_model.md): Returns an ACGANModel contains all the pieces needed for ACGAN training.

[`cyclegan_loss(...)`](../../tf/contrib/gan/cyclegan_loss.md): Returns the losses for a `CycleGANModel`.

[`cyclegan_model(...)`](../../tf/contrib/gan/cyclegan_model.md): Returns a CycleGAN model outputs and variables.

[`gan_loss(...)`](../../tf/contrib/gan/gan_loss.md): Returns losses necessary to train generator and discriminator.

[`gan_model(...)`](../../tf/contrib/gan/gan_model.md): Returns GAN model outputs and variables.

[`gan_train(...)`](../../tf/contrib/gan/gan_train.md): A wrapper around `contrib.training.train` that uses GAN hooks.

[`gan_train_ops(...)`](../../tf/contrib/gan/gan_train_ops.md): Returns GAN train ops.

[`get_joint_train_hooks(...)`](../../tf/contrib/gan/get_joint_train_hooks.md): Returns a hooks function for sequential GAN training.

[`get_sequential_train_hooks(...)`](../../tf/contrib/gan/get_sequential_train_hooks.md): Returns a hooks function for sequential GAN training.

[`get_sequential_train_steps(...)`](../../tf/contrib/gan/get_sequential_train_steps.md): Returns a thin wrapper around slim.learning.train_step, for GANs.

[`infogan_model(...)`](../../tf/contrib/gan/infogan_model.md): Returns an InfoGAN model outputs and variables.

[`stargan_loss(...)`](../../tf/contrib/gan/stargan_loss.md): StarGAN Loss.

[`stargan_model(...)`](../../tf/contrib/gan/stargan_model.md): Returns a StarGAN model outputs and variables.


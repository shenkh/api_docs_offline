<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.distribute.cluster_resolver" />
<meta itemprop="path" content="Stable" />
</div>

# Module: tf.compat.v1.distribute.cluster_resolver

Library Imports for Cluster Resolvers.

<!-- Placeholder for "Used in" -->


## Classes

[`class ClusterResolver`](../../../../tf/distribute/cluster_resolver/ClusterResolver.md): Abstract class for all implementations of ClusterResolvers.

[`class GCEClusterResolver`](../../../../tf/distribute/cluster_resolver/GCEClusterResolver.md): Cluster Resolver for Google Compute Engine.

[`class KubernetesClusterResolver`](../../../../tf/distribute/cluster_resolver/KubernetesClusterResolver.md): Cluster Resolver for Kubernetes.

[`class SimpleClusterResolver`](../../../../tf/distribute/cluster_resolver/SimpleClusterResolver.md): Simple implementation of ClusterResolver that accepts a ClusterSpec.

[`class SlurmClusterResolver`](../../../../tf/distribute/cluster_resolver/SlurmClusterResolver.md): Cluster Resolver for system with Slurm workload manager.

[`class TFConfigClusterResolver`](../../../../tf/distribute/cluster_resolver/TFConfigClusterResolver.md): Implementation of a ClusterResolver which reads the TF_CONFIG EnvVar.

[`class TPUClusterResolver`](../../../../tf/distribute/cluster_resolver/TPUClusterResolver.md): Cluster Resolver for Google Cloud TPUs.

[`class UnionResolver`](../../../../tf/distribute/cluster_resolver/UnionResolver.md): Performs a union on underlying ClusterResolvers.


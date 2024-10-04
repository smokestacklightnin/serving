::: {#classtensorflow_1_1serving_1_1ResourceUnsafeLoader}
:::

[\[classtensorflow\_1\_1serving\_1\_1ResourceUnsafeLoader\]]{#classtensorflow_1_1serving_1_1ResourceUnsafeLoader
label="classtensorflow_1_1serving_1_1ResourceUnsafeLoader"}

\#include $<$loader.h$>$

Inheritance diagram for tensorflow::serving::ResourceUnsafeLoader:

![image](classtensorflow_1_1serving_1_1ResourceUnsafeLoader__inherit__graph.pdf){width="215pt"}

Collaboration diagram for tensorflow::serving::ResourceUnsafeLoader:

![image](classtensorflow_1_1serving_1_1ResourceUnsafeLoader__coll__graph.pdf){width="215pt"}

Status
[EstimateResources](#classtensorflow_1_1serving_1_1ResourceUnsafeLoader_a1a0c1398af9af54032ba16a79a9ecac4)
(ResourceAllocation $\ast$estimate) const final

A [Loader](#classtensorflow_1_1serving_1_1Loader) that is oblivious to
resources. Its
[EstimateResources()](#classtensorflow_1_1serving_1_1ResourceUnsafeLoader_a1a0c1398af9af54032ba16a79a9ecac4)
method returns 0, thus effectively disabling resource-based safety
checks in the serving system.

Loaders that are experimental, or run in environments that do not need
the resource safety checks, can subclass
[ResourceUnsafeLoader](#classtensorflow_1_1serving_1_1ResourceUnsafeLoader)
instead of [Loader](#classtensorflow_1_1serving_1_1Loader).

[\[classtensorflow\_1\_1serving\_1\_1ResourceUnsafeLoader\_a1a0c1398af9af54032ba16a79a9ecac4\]]{#classtensorflow_1_1serving_1_1ResourceUnsafeLoader_a1a0c1398af9af54032ba16a79a9ecac4
label="classtensorflow_1_1serving_1_1ResourceUnsafeLoader_a1a0c1398af9af54032ba16a79a9ecac4"}

Status tensorflow::serving::ResourceUnsafeLoader::EstimateResources (

estimate

) const, ,

Estimates the resources a servable will use.

IMPORTANT: This methods implementation must obey following requirements,
which enable the serving system to reason correctly about which
servables can be loaded safely:

The estimate must represent an upper bound on the actual value.

Prior to load, the estimate may include resources that are not bound to
any specific device instance, e.g. RAM on one of the two GPUs.

While loaded, for any devices with multiple instances (e.g. two GPUs),
the estimate must specify the instance to which each resource is bound.

The estimate must be monotonically non-increasing, i.e. it cannot
increase over time. Reasons to have it potentially decrease over time

Returns an estimate of the resources the servable will consume once
loaded. If the servable has already been loaded, returns an estimate of
the actual resource usage.

Implements
[tensorflow::serving::Loader](#classtensorflow_1_1serving_1_1Loader_ab59db26b242a2224889bc7c5c6edae40).

The documentation for this class was generated from the following file:

tensorflow\_serving/core/loader.h

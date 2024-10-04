::: {#classtensorflow_1_1serving_1_1ResourcePreservingPolicy}
:::

[\[classtensorflow\_1\_1serving\_1\_1ResourcePreservingPolicy\]]{#classtensorflow_1_1serving_1_1ResourcePreservingPolicy
label="classtensorflow_1_1serving_1_1ResourcePreservingPolicy"}

Inheritance diagram for tensorflow::serving::ResourcePreservingPolicy:

![image](classtensorflow_1_1serving_1_1ResourcePreservingPolicy__inherit__graph.pdf){width="229pt"}

Collaboration diagram for tensorflow::serving::ResourcePreservingPolicy:

![image](classtensorflow_1_1serving_1_1ResourcePreservingPolicy__coll__graph.pdf){width="229pt"}

absl::optional$<$
[ServableAction](#structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction)
$>$
[GetNextAction](#classtensorflow_1_1serving_1_1ResourcePreservingPolicy_ab1fa4fa3d4a8dc165bb86f5377436532)
(const std::vector$<$
[AspiredServableStateSnapshot](#structtensorflow_1_1serving_1_1AspiredServableStateSnapshot)
$>$ &all\_versions) const override

[\[classtensorflow\_1\_1serving\_1\_1ResourcePreservingPolicy\_ab1fa4fa3d4a8dc165bb86f5377436532\]]{#classtensorflow_1_1serving_1_1ResourcePreservingPolicy_ab1fa4fa3d4a8dc165bb86f5377436532
label="classtensorflow_1_1serving_1_1ResourcePreservingPolicy_ab1fa4fa3d4a8dc165bb86f5377436532"}

absl::optional$<$
[AspiredVersionPolicy::ServableAction](#structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction)
$>$ tensorflow::serving::ResourcePreservingPolicy::GetNextAction (

all\_versions

) const,

Takes in a vector of state snapshots of all versions of a servable
stream and returns an action to be performed for a particular servable
version, depending only on the states of all the versions.

If no action is to be performed, we dont return an action, meaning that
the servable stream is up to date.

Implements
[tensorflow::serving::AspiredVersionPolicy](#classtensorflow_1_1serving_1_1AspiredVersionPolicy_a86135f0f3225cd2999033da63e013214).

The documentation for this class was generated from the following files:

tensorflow\_serving/core/resource\_preserving\_policy.h

tensorflow\_serving/core/resource\_preserving\_policy.cc

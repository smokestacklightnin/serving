::: {#classtensorflow_1_1serving_1_1AvailabilityPreservingPolicy}
:::

[\[classtensorflow\_1\_1serving\_1\_1AvailabilityPreservingPolicy\]]{#classtensorflow_1_1serving_1_1AvailabilityPreservingPolicy
label="classtensorflow_1_1serving_1_1AvailabilityPreservingPolicy"}

Inheritance diagram for
tensorflow::serving::AvailabilityPreservingPolicy:

![image](classtensorflow_1_1serving_1_1AvailabilityPreservingPolicy__inherit__graph.pdf){width="238pt"}

Collaboration diagram for
tensorflow::serving::AvailabilityPreservingPolicy:

![image](classtensorflow_1_1serving_1_1AvailabilityPreservingPolicy__coll__graph.pdf){width="238pt"}

absl::optional$<$
[ServableAction](#structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction)
$>$
[GetNextAction](#classtensorflow_1_1serving_1_1AvailabilityPreservingPolicy_a3e7f155e7dd0bb9fadacfdfe4cad5d4c)
(const std::vector$<$
[AspiredServableStateSnapshot](#structtensorflow_1_1serving_1_1AspiredServableStateSnapshot)
$>$ &all\_versions) const override

[\[classtensorflow\_1\_1serving\_1\_1AvailabilityPreservingPolicy\_a3e7f155e7dd0bb9fadacfdfe4cad5d4c\]]{#classtensorflow_1_1serving_1_1AvailabilityPreservingPolicy_a3e7f155e7dd0bb9fadacfdfe4cad5d4c
label="classtensorflow_1_1serving_1_1AvailabilityPreservingPolicy_a3e7f155e7dd0bb9fadacfdfe4cad5d4c"}

absl::optional$<$
[AspiredVersionPolicy::ServableAction](#structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction)
$>$ tensorflow::serving::AvailabilityPreservingPolicy::GetNextAction (

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

tensorflow\_serving/core/availability\_preserving\_policy.h

tensorflow\_serving/core/availability\_preserving\_policy.cc

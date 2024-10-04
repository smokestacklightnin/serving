::: {#classtensorflow_1_1serving_1_1AspiredVersionPolicy}
:::

[\[classtensorflow\_1\_1serving\_1\_1AspiredVersionPolicy\]]{#classtensorflow_1_1serving_1_1AspiredVersionPolicy
label="classtensorflow_1_1serving_1_1AspiredVersionPolicy"}

\#include $<$aspired\_version\_policy.h$>$

Inheritance diagram for tensorflow::serving::AspiredVersionPolicy:

![image](classtensorflow_1_1serving_1_1AspiredVersionPolicy__inherit__graph.pdf){width="350pt"}

struct
[ServableAction](#structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction)

*Action and the id of the servable associated with it.*

enum class
[Action](#classtensorflow_1_1serving_1_1AspiredVersionPolicy_a5681f3f1c6c14f088084b29438e6fa85)
: int {
[kLoad](#classtensorflow_1_1serving_1_1AspiredVersionPolicy_a5681f3f1c6c14f088084b29438e6fa85ae40d6c82a1a5f5a163aca43efa5e444a)
,
[kUnload](#classtensorflow_1_1serving_1_1AspiredVersionPolicy_a5681f3f1c6c14f088084b29438e6fa85a2941108d29908fe92ae8627b1d2ec0a1)
}

*The different actions that could be recommended by a policy.*

virtual absl::optional$<$
[ServableAction](#structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction)
$>$
[GetNextAction](#classtensorflow_1_1serving_1_1AspiredVersionPolicy_a86135f0f3225cd2999033da63e013214)
(const std::vector$<$
[AspiredServableStateSnapshot](#structtensorflow_1_1serving_1_1AspiredServableStateSnapshot)
$>$ &all\_versions) const =0

static absl::optional$<$
[ServableId](#structtensorflow_1_1serving_1_1ServableId) $>$
[GetHighestAspiredNewServableId](#classtensorflow_1_1serving_1_1AspiredVersionPolicy_a71bde7aea4c6116cede2714758688857)
(const std::vector$<$
[AspiredServableStateSnapshot](#structtensorflow_1_1serving_1_1AspiredServableStateSnapshot)
$>$ &all\_versions)

[\[classtensorflow\_1\_1serving\_1\_1AspiredVersionPolicy\_a2ad82a88769861ba90f16c53008216f1\]]{#classtensorflow_1_1serving_1_1AspiredVersionPolicy_a2ad82a88769861ba90f16c53008216f1
label="classtensorflow_1_1serving_1_1AspiredVersionPolicy_a2ad82a88769861ba90f16c53008216f1"}
class **AspiredVersionPolicyTest**

An interface for the policy to be applied for transitioning servable
versions in a servable stream.

Policies should be entirely stateless and idempotent. Asking the same
policy multiple times for the next action, for an identical vector of
AspiredServableStateSnapshots, should return the same result.

If additional state is required to implement a Policy, such state shall
be shared via AspiredServableStateSnapshots. Depending on the kind of
state, the most likely candidates for originating or tracking state are
Sources or the Harness and
[Manager](#classtensorflow_1_1serving_1_1Manager).

[\[classtensorflow\_1\_1serving\_1\_1AspiredVersionPolicy\_a5681f3f1c6c14f088084b29438e6fa85\]]{#classtensorflow_1_1serving_1_1AspiredVersionPolicy_a5681f3f1c6c14f088084b29438e6fa85
label="classtensorflow_1_1serving_1_1AspiredVersionPolicy_a5681f3f1c6c14f088084b29438e6fa85"}
enum
[tensorflow::serving::AspiredVersionPolicy::Action](#classtensorflow_1_1serving_1_1AspiredVersionPolicy_a5681f3f1c6c14f088084b29438e6fa85)
: int

The different actions that could be recommended by a policy.

Enumerator
\[0pt\]\[0pt\][\[classtensorflow\_1\_1serving\_1\_1AspiredVersionPolicy\_a5681f3f1c6c14f088084b29438e6fa85ae40d6c82a1a5f5a163aca43efa5e444a\]]{#classtensorflow_1_1serving_1_1AspiredVersionPolicy_a5681f3f1c6c14f088084b29438e6fa85ae40d6c82a1a5f5a163aca43efa5e444a
label="classtensorflow_1_1serving_1_1AspiredVersionPolicy_a5681f3f1c6c14f088084b29438e6fa85ae40d6c82a1a5f5a163aca43efa5e444a"}
kLoad&Call load on the servable.\

\[0pt\]\[0pt\][\[classtensorflow\_1\_1serving\_1\_1AspiredVersionPolicy\_a5681f3f1c6c14f088084b29438e6fa85a2941108d29908fe92ae8627b1d2ec0a1\]]{#classtensorflow_1_1serving_1_1AspiredVersionPolicy_a5681f3f1c6c14f088084b29438e6fa85a2941108d29908fe92ae8627b1d2ec0a1
label="classtensorflow_1_1serving_1_1AspiredVersionPolicy_a5681f3f1c6c14f088084b29438e6fa85a2941108d29908fe92ae8627b1d2ec0a1"}
kUnload&Call unload on the servable.\

[\[classtensorflow\_1\_1serving\_1\_1AspiredVersionPolicy\_a71bde7aea4c6116cede2714758688857\]]{#classtensorflow_1_1serving_1_1AspiredVersionPolicy_a71bde7aea4c6116cede2714758688857
label="classtensorflow_1_1serving_1_1AspiredVersionPolicy_a71bde7aea4c6116cede2714758688857"}

absl::optional$<$
[ServableId](#structtensorflow_1_1serving_1_1ServableId) $>$
tensorflow::serving::AspiredVersionPolicy::GetHighestAspiredNewServableId
(

all\_versions

),

Returns the aspired
[ServableId](#structtensorflow_1_1serving_1_1ServableId) with the
highest version that matches kNew state, if any exists.
[\[classtensorflow\_1\_1serving\_1\_1AspiredVersionPolicy\_a86135f0f3225cd2999033da63e013214\]]{#classtensorflow_1_1serving_1_1AspiredVersionPolicy_a86135f0f3225cd2999033da63e013214
label="classtensorflow_1_1serving_1_1AspiredVersionPolicy_a86135f0f3225cd2999033da63e013214"}

virtual
absl::optional$<$[ServableAction](#structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction)$>$
tensorflow::serving::AspiredVersionPolicy::GetNextAction (

all\_versions

) const

Takes in a vector of state snapshots of all versions of a servable
stream and returns an action to be performed for a particular servable
version, depending only on the states of all the versions.

If no action is to be performed, we dont return an action, meaning that
the servable stream is up to date.

Implemented in
[tensorflow::serving::ResourcePreservingPolicy](#classtensorflow_1_1serving_1_1ResourcePreservingPolicy_ab1fa4fa3d4a8dc165bb86f5377436532),
and
[tensorflow::serving::AvailabilityPreservingPolicy](#classtensorflow_1_1serving_1_1AvailabilityPreservingPolicy_a3e7f155e7dd0bb9fadacfdfe4cad5d4c).

The documentation for this class was generated from the following files:

tensorflow\_serving/core/aspired\_version\_policy.h

tensorflow\_serving/core/aspired\_version\_policy.cc

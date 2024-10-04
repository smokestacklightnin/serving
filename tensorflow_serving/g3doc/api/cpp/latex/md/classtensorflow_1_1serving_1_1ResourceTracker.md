::: {#classtensorflow_1_1serving_1_1ResourceTracker}
:::

[\[classtensorflow\_1\_1serving\_1\_1ResourceTracker\]]{#classtensorflow_1_1serving_1_1ResourceTracker
label="classtensorflow_1_1serving_1_1ResourceTracker"}

[\[classtensorflow\_1\_1serving\_1\_1ResourceTracker\_a0a6ca7665095f104fb32431edc30dbbd\]]{#classtensorflow_1_1serving_1_1ResourceTracker_a0a6ca7665095f104fb32431edc30dbbd
label="classtensorflow_1_1serving_1_1ResourceTracker_a0a6ca7665095f104fb32431edc30dbbd"}
Status **ReserveResources** (const
[Loader](#classtensorflow_1_1serving_1_1Loader) &servable, bool
$\ast$success)

[\[classtensorflow\_1\_1serving\_1\_1ResourceTracker\_ae18c086a1e00b5f75e6cdd0fc196b68c\]]{#classtensorflow_1_1serving_1_1ResourceTracker_ae18c086a1e00b5f75e6cdd0fc196b68c
label="classtensorflow_1_1serving_1_1ResourceTracker_ae18c086a1e00b5f75e6cdd0fc196b68c"}
Status **RecomputeUsedResources** (const std::vector$<$ const
[Loader](#classtensorflow_1_1serving_1_1Loader) $\ast$ $>$ &servables)

[\[classtensorflow\_1\_1serving\_1\_1ResourceTracker\_a0bee6aba9b805879cad91a8216b27d2c\]]{#classtensorflow_1_1serving_1_1ResourceTracker_a0bee6aba9b805879cad91a8216b27d2c
label="classtensorflow_1_1serving_1_1ResourceTracker_a0bee6aba9b805879cad91a8216b27d2c"}
const ResourceAllocation & **total\_resources** () const

[\[classtensorflow\_1\_1serving\_1\_1ResourceTracker\_a3642b816f004bc0a21110a7b99bb60f8\]]{#classtensorflow_1_1serving_1_1ResourceTracker_a3642b816f004bc0a21110a7b99bb60f8
label="classtensorflow_1_1serving_1_1ResourceTracker_a3642b816f004bc0a21110a7b99bb60f8"}
const ResourceAllocation & **used\_resources** () const

[\[classtensorflow\_1\_1serving\_1\_1ResourceTracker\_a1f5dda2912636b45701e2a6159e6a263\]]{#classtensorflow_1_1serving_1_1ResourceTracker_a1f5dda2912636b45701e2a6159e6a263
label="classtensorflow_1_1serving_1_1ResourceTracker_a1f5dda2912636b45701e2a6159e6a263"}
static Status **Create** (const ResourceAllocation &total\_resources,
std::unique\_ptr$<$
[ResourceUtil](#classtensorflow_1_1serving_1_1ResourceUtil) $>$ util,
std::unique\_ptr$<$
[ResourceTracker](#classtensorflow_1_1serving_1_1ResourceTracker) $>$
$\ast$tracker)

The documentation for this class was generated from the following files:

tensorflow\_serving/resources/resource\_tracker.h

tensorflow\_serving/resources/resource\_tracker.cc

::: {#classtensorflow_1_1serving_1_1ResourceUtil}
:::

[\[classtensorflow\_1\_1serving\_1\_1ResourceUtil\]]{#classtensorflow_1_1serving_1_1ResourceUtil
label="classtensorflow_1_1serving_1_1ResourceUtil"}

struct
[Options](#structtensorflow_1_1serving_1_1ResourceUtil_1_1Options)

[\[classtensorflow\_1\_1serving\_1\_1ResourceUtil\_ae0589b74ea835e5ff5776cc0fead5268\]]{#classtensorflow_1_1serving_1_1ResourceUtil_ae0589b74ea835e5ff5776cc0fead5268
label="classtensorflow_1_1serving_1_1ResourceUtil_ae0589b74ea835e5ff5776cc0fead5268"}
**ResourceUtil** (const
[Options](#structtensorflow_1_1serving_1_1ResourceUtil_1_1Options)
&options)

[\[classtensorflow\_1\_1serving\_1\_1ResourceUtil\_a566add5959eae03a8c9e1734eb2552c8\]]{#classtensorflow_1_1serving_1_1ResourceUtil_a566add5959eae03a8c9e1734eb2552c8
label="classtensorflow_1_1serving_1_1ResourceUtil_a566add5959eae03a8c9e1734eb2552c8"}
virtual Status **VerifyValidity** (const ResourceAllocation &allocation)
const

[\[classtensorflow\_1\_1serving\_1\_1ResourceUtil\_a67c0aaeeb91f42f665b009dd8719c6e0\]]{#classtensorflow_1_1serving_1_1ResourceUtil_a67c0aaeeb91f42f665b009dd8719c6e0
label="classtensorflow_1_1serving_1_1ResourceUtil_a67c0aaeeb91f42f665b009dd8719c6e0"}
Status **VerifyOverrideDeviceValidity** (const ResourceAllocation
&base\_allocation, const ResourceAllocation &override\_allocation) const

[\[classtensorflow\_1\_1serving\_1\_1ResourceUtil\_acc2d572b859ed3de06a5003e4f67e91f\]]{#classtensorflow_1_1serving_1_1ResourceUtil_acc2d572b859ed3de06a5003e4f67e91f
label="classtensorflow_1_1serving_1_1ResourceUtil_acc2d572b859ed3de06a5003e4f67e91f"}
Status **VerifyResourceValidity** (const Resource &resource) const

[\[classtensorflow\_1\_1serving\_1\_1ResourceUtil\_a37da83c9dc7dff8754885294a620c1d2\]]{#classtensorflow_1_1serving_1_1ResourceUtil_a37da83c9dc7dff8754885294a620c1d2
label="classtensorflow_1_1serving_1_1ResourceUtil_a37da83c9dc7dff8754885294a620c1d2"}
virtual ResourceAllocation **Normalize** (const ResourceAllocation
&allocation) const

[\[classtensorflow\_1\_1serving\_1\_1ResourceUtil\_a61cbfa0f197edaaa39f4f05a85138547\]]{#classtensorflow_1_1serving_1_1ResourceUtil_a61cbfa0f197edaaa39f4f05a85138547
label="classtensorflow_1_1serving_1_1ResourceUtil_a61cbfa0f197edaaa39f4f05a85138547"}
virtual bool **IsNormalized** (const ResourceAllocation &allocation)
const

[\[classtensorflow\_1\_1serving\_1\_1ResourceUtil\_ad393b9582bb60a37953fc189a15191fd\]]{#classtensorflow_1_1serving_1_1ResourceUtil_ad393b9582bb60a37953fc189a15191fd
label="classtensorflow_1_1serving_1_1ResourceUtil_ad393b9582bb60a37953fc189a15191fd"}
bool **IsBound** (const ResourceAllocation &allocation) const

[\[classtensorflow\_1\_1serving\_1\_1ResourceUtil\_a3074d1bc7b8f04122ffc3a9e40f21002\]]{#classtensorflow_1_1serving_1_1ResourceUtil_a3074d1bc7b8f04122ffc3a9e40f21002
label="classtensorflow_1_1serving_1_1ResourceUtil_a3074d1bc7b8f04122ffc3a9e40f21002"}
Resource **CreateBoundResource** (const string &device, const string
&kind, uint32 device\_instance=0) const

[\[classtensorflow\_1\_1serving\_1\_1ResourceUtil\_aff846f7afa95b25085993a14e97add19\]]{#classtensorflow_1_1serving_1_1ResourceUtil_aff846f7afa95b25085993a14e97add19
label="classtensorflow_1_1serving_1_1ResourceUtil_aff846f7afa95b25085993a14e97add19"}
uint64\_t **GetQuantity** (const Resource &resource, const
ResourceAllocation &allocation) const

[\[classtensorflow\_1\_1serving\_1\_1ResourceUtil\_aa8618572cf960877eec6a34e0878ac1d\]]{#classtensorflow_1_1serving_1_1ResourceUtil_aa8618572cf960877eec6a34e0878ac1d
label="classtensorflow_1_1serving_1_1ResourceUtil_aa8618572cf960877eec6a34e0878ac1d"}
void **SetQuantity** (const Resource &resource, uint64\_t quantity,
ResourceAllocation $\ast$allocation) const

[\[classtensorflow\_1\_1serving\_1\_1ResourceUtil\_a001ce0d279c99684b83b7d1c3c7e3929\]]{#classtensorflow_1_1serving_1_1ResourceUtil_a001ce0d279c99684b83b7d1c3c7e3929
label="classtensorflow_1_1serving_1_1ResourceUtil_a001ce0d279c99684b83b7d1c3c7e3929"}
void **Add** (const ResourceAllocation &to\_add, ResourceAllocation
$\ast$base) const

[\[classtensorflow\_1\_1serving\_1\_1ResourceUtil\_aef61e95284d5e4563403da00db67dfce\]]{#classtensorflow_1_1serving_1_1ResourceUtil_aef61e95284d5e4563403da00db67dfce
label="classtensorflow_1_1serving_1_1ResourceUtil_aef61e95284d5e4563403da00db67dfce"}
bool **Subtract** (const ResourceAllocation &to\_subtract,
ResourceAllocation $\ast$base) const

[\[classtensorflow\_1\_1serving\_1\_1ResourceUtil\_af761d3325f0d947e342a89f8de57e1e2\]]{#classtensorflow_1_1serving_1_1ResourceUtil_af761d3325f0d947e342a89f8de57e1e2
label="classtensorflow_1_1serving_1_1ResourceUtil_af761d3325f0d947e342a89f8de57e1e2"}
void **Multiply** (uint64\_t multiplier, ResourceAllocation $\ast$base)
const

[\[classtensorflow\_1\_1serving\_1\_1ResourceUtil\_ae058853919a775bd21ed28e399335ddb\]]{#classtensorflow_1_1serving_1_1ResourceUtil_ae058853919a775bd21ed28e399335ddb
label="classtensorflow_1_1serving_1_1ResourceUtil_ae058853919a775bd21ed28e399335ddb"}
bool **Equal** (const ResourceAllocation &lhs, const ResourceAllocation
&rhs) const

[\[classtensorflow\_1\_1serving\_1\_1ResourceUtil\_a5331d0a0381ea010fe06a63ecb727e78\]]{#classtensorflow_1_1serving_1_1ResourceUtil_a5331d0a0381ea010fe06a63ecb727e78
label="classtensorflow_1_1serving_1_1ResourceUtil_a5331d0a0381ea010fe06a63ecb727e78"}
bool **ResourcesEqual** (const Resource &lhs, const Resource &rhs) const

[\[classtensorflow\_1\_1serving\_1\_1ResourceUtil\_abbf51b184f12105e8c77c829030a4e0f\]]{#classtensorflow_1_1serving_1_1ResourceUtil_abbf51b184f12105e8c77c829030a4e0f
label="classtensorflow_1_1serving_1_1ResourceUtil_abbf51b184f12105e8c77c829030a4e0f"}
bool **LessThanOrEqual** (const ResourceAllocation &lhs, const
ResourceAllocation &rhs) const

[\[classtensorflow\_1\_1serving\_1\_1ResourceUtil\_a217cc95e2010df33bc78d8025ca24d7c\]]{#classtensorflow_1_1serving_1_1ResourceUtil_a217cc95e2010df33bc78d8025ca24d7c
label="classtensorflow_1_1serving_1_1ResourceUtil_a217cc95e2010df33bc78d8025ca24d7c"}
ResourceAllocation **Overbind** (const ResourceAllocation &allocation)
const

[\[classtensorflow\_1\_1serving\_1\_1ResourceUtil\_a19546fac5bdb1f09150ad8b3deac7a23\]]{#classtensorflow_1_1serving_1_1ResourceUtil_a19546fac5bdb1f09150ad8b3deac7a23
label="classtensorflow_1_1serving_1_1ResourceUtil_a19546fac5bdb1f09150ad8b3deac7a23"}
ResourceAllocation **Max** (const ResourceAllocation &lhs, const
ResourceAllocation &rhs) const

[\[classtensorflow\_1\_1serving\_1\_1ResourceUtil\_ad0c6e2e911364ee8beb1141a3c1660f5\]]{#classtensorflow_1_1serving_1_1ResourceUtil_ad0c6e2e911364ee8beb1141a3c1660f5
label="classtensorflow_1_1serving_1_1ResourceUtil_ad0c6e2e911364ee8beb1141a3c1660f5"}
ResourceAllocation **Min** (const ResourceAllocation &lhs, const
ResourceAllocation &rhs) const

[\[classtensorflow\_1\_1serving\_1\_1ResourceUtil\_a1349deb7fb558e697d9f2f8bc41b2a0a\]]{#classtensorflow_1_1serving_1_1ResourceUtil_a1349deb7fb558e697d9f2f8bc41b2a0a
label="classtensorflow_1_1serving_1_1ResourceUtil_a1349deb7fb558e697d9f2f8bc41b2a0a"}
ResourceAllocation **NormalizeResourceAllocation** (const
ResourceAllocation &allocation) const

The documentation for this class was generated from the following files:

tensorflow\_serving/resources/resource\_util.h

tensorflow\_serving/resources/resource\_util.cc

::: {#structtensorflow_1_1serving_1_1ServableRequest}
:::

[\[structtensorflow\_1\_1serving\_1\_1ServableRequest\]]{#structtensorflow_1_1serving_1_1ServableRequest
label="structtensorflow_1_1serving_1_1ServableRequest"}

\#include $<$manager.h$>$

[\[structtensorflow\_1\_1serving\_1\_1ServableRequest\_abccd7156407220fca288f3d32ca1cc77\]]{#structtensorflow_1_1serving_1_1ServableRequest_abccd7156407220fca288f3d32ca1cc77
label="structtensorflow_1_1serving_1_1ServableRequest_abccd7156407220fca288f3d32ca1cc77"}
enum class **AutoVersionPolicy** { **kEarliest** , **kLatest** }

[\[structtensorflow\_1\_1serving\_1\_1ServableRequest\_ac7238b5fd50bb5ec39c9e514321c9637\]]{#structtensorflow_1_1serving_1_1ServableRequest_ac7238b5fd50bb5ec39c9e514321c9637
label="structtensorflow_1_1serving_1_1ServableRequest_ac7238b5fd50bb5ec39c9e514321c9637"}
string **DebugString** () const

[\[structtensorflow\_1\_1serving\_1\_1ServableRequest\_a85dfdb32ede1a952d9ae8f3b23887338\]]{#structtensorflow_1_1serving_1_1ServableRequest_a85dfdb32ede1a952d9ae8f3b23887338
label="structtensorflow_1_1serving_1_1ServableRequest_a85dfdb32ede1a952d9ae8f3b23887338"}
**ServableRequest** (const string &name\_in, const absl::optional$<$
int64\_t $>$ &version\_in)

[\[structtensorflow\_1\_1serving\_1\_1ServableRequest\_aabeada0a1a93091a5dbb18dbc1118099\]]{#structtensorflow_1_1serving_1_1ServableRequest_aabeada0a1a93091a5dbb18dbc1118099
label="structtensorflow_1_1serving_1_1ServableRequest_aabeada0a1a93091a5dbb18dbc1118099"}
static
[ServableRequest](#structtensorflow_1_1serving_1_1ServableRequest)
**Specific** (const string &name, const int64\_t version)

[\[structtensorflow\_1\_1serving\_1\_1ServableRequest\_ab292a8eef10db15daa637e67e677e14d\]]{#structtensorflow_1_1serving_1_1ServableRequest_ab292a8eef10db15daa637e67e677e14d
label="structtensorflow_1_1serving_1_1ServableRequest_ab292a8eef10db15daa637e67e677e14d"}
static
[ServableRequest](#structtensorflow_1_1serving_1_1ServableRequest)
**Earliest** (const string &name)

[\[structtensorflow\_1\_1serving\_1\_1ServableRequest\_ade36fe1b25c730da03c046dcb80f4b6a\]]{#structtensorflow_1_1serving_1_1ServableRequest_ade36fe1b25c730da03c046dcb80f4b6a
label="structtensorflow_1_1serving_1_1ServableRequest_ade36fe1b25c730da03c046dcb80f4b6a"}
static
[ServableRequest](#structtensorflow_1_1serving_1_1ServableRequest)
**Latest** (const string &name)

[\[structtensorflow\_1\_1serving\_1\_1ServableRequest\_ab4de96122f9bb0e927b503e615c71d88\]]{#structtensorflow_1_1serving_1_1ServableRequest_ab4de96122f9bb0e927b503e615c71d88
label="structtensorflow_1_1serving_1_1ServableRequest_ab4de96122f9bb0e927b503e615c71d88"}
static
[ServableRequest](#structtensorflow_1_1serving_1_1ServableRequest)
**FromId** (const
[ServableId](#structtensorflow_1_1serving_1_1ServableId) &id)

[\[structtensorflow\_1\_1serving\_1\_1ServableRequest\_a1814fb28eba7976ccabaad34447d4f11\]]{#structtensorflow_1_1serving_1_1ServableRequest_a1814fb28eba7976ccabaad34447d4f11
label="structtensorflow_1_1serving_1_1ServableRequest_a1814fb28eba7976ccabaad34447d4f11"}
string **name**

[\[structtensorflow\_1\_1serving\_1\_1ServableRequest\_a5cc5cec940313d38a961304031387a7a\]]{#structtensorflow_1_1serving_1_1ServableRequest_a5cc5cec940313d38a961304031387a7a
label="structtensorflow_1_1serving_1_1ServableRequest_a5cc5cec940313d38a961304031387a7a"}
absl::optional$<$ int64\_t $>$ **version**

[\[structtensorflow\_1\_1serving\_1\_1ServableRequest\_ab7598011328fe3ed55c2544580d548bb\]]{#structtensorflow_1_1serving_1_1ServableRequest_ab7598011328fe3ed55c2544580d548bb
label="structtensorflow_1_1serving_1_1ServableRequest_ab7598011328fe3ed55c2544580d548bb"}
AutoVersionPolicy **auto\_version\_policy** = AutoVersionPolicy::kLatest

A query for a specific loaded servable object. The request can either
specify a specific version number, or simply opt to use the earliest or
latest loaded version.

The documentation for this struct was generated from the following file:

tensorflow\_serving/core/manager.h

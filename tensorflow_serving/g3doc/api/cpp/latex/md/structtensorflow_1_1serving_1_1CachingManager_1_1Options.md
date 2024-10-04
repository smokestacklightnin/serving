::: {#structtensorflow_1_1serving_1_1CachingManager_1_1Options}
:::

[\[structtensorflow\_1\_1serving\_1\_1CachingManager\_1\_1Options\]]{#structtensorflow_1_1serving_1_1CachingManager_1_1Options
label="structtensorflow_1_1serving_1_1CachingManager_1_1Options"}

\#include $<$caching\_manager.h$>$

Collaboration diagram for tensorflow::serving::CachingManager::Options:

![image](structtensorflow_1_1serving_1_1CachingManager_1_1Options__coll__graph.pdf){width="312pt"}

[\[structtensorflow\_1\_1serving\_1\_1CachingManager\_1\_1Options\_a3ca8429f5139e1128f1d2aa37b33456d\]]{#structtensorflow_1_1serving_1_1CachingManager_1_1Options_a3ca8429f5139e1128f1d2aa37b33456d
label="structtensorflow_1_1serving_1_1CachingManager_1_1Options_a3ca8429f5139e1128f1d2aa37b33456d"}
std::unique\_ptr$<$
[ResourceTracker](#classtensorflow_1_1serving_1_1ResourceTracker) $>$
**resource\_tracker**

[\[structtensorflow\_1\_1serving\_1\_1CachingManager\_1\_1Options\_a8cc4930d77b36886a170d2797cabb97b\]]{#structtensorflow_1_1serving_1_1CachingManager_1_1Options_a8cc4930d77b36886a170d2797cabb97b
label="structtensorflow_1_1serving_1_1CachingManager_1_1Options_a8cc4930d77b36886a170d2797cabb97b"}
uint32 **num\_load\_threads** = 0

[\[structtensorflow\_1\_1serving\_1\_1CachingManager\_1\_1Options\_a39159b23af4768d50c82bc8dcc63bca7\]]{#structtensorflow_1_1serving_1_1CachingManager_1_1Options_a39159b23af4768d50c82bc8dcc63bca7
label="structtensorflow_1_1serving_1_1CachingManager_1_1Options_a39159b23af4768d50c82bc8dcc63bca7"}
uint32 **num\_unload\_threads** = 0

[\[structtensorflow\_1\_1serving\_1\_1CachingManager\_1\_1Options\_ae663b718a0c91b496c71e126a951417e\]]{#structtensorflow_1_1serving_1_1CachingManager_1_1Options_ae663b718a0c91b496c71e126a951417e
label="structtensorflow_1_1serving_1_1CachingManager_1_1Options_ae663b718a0c91b496c71e126a951417e"}
[EventBus](#classtensorflow_1_1serving_1_1EventBus)$<$
[ServableState](#structtensorflow_1_1serving_1_1ServableState) $>$
$\ast$ **servable\_event\_bus** = nullptr

[\[structtensorflow\_1\_1serving\_1\_1CachingManager\_1\_1Options\_aad885f7103a34e84ab69a5e35f13ceb3\]]{#structtensorflow_1_1serving_1_1CachingManager_1_1Options_aad885f7103a34e84ab69a5e35f13ceb3
label="structtensorflow_1_1serving_1_1CachingManager_1_1Options_aad885f7103a34e84ab69a5e35f13ceb3"}
uint32 **max\_num\_load\_retries** = 5

[\[structtensorflow\_1\_1serving\_1\_1CachingManager\_1\_1Options\_ae4357586a6206653e4c48898e15d89f7\]]{#structtensorflow_1_1serving_1_1CachingManager_1_1Options_ae4357586a6206653e4c48898e15d89f7
label="structtensorflow_1_1serving_1_1CachingManager_1_1Options_ae4357586a6206653e4c48898e15d89f7"}
int64\_t **load\_retry\_interval\_micros** = 1LL $\ast$ 60 $\ast$ 1000
$\ast$ 1000

[\[structtensorflow\_1\_1serving\_1\_1CachingManager\_1\_1Options\_a37422eae96e8e0f107c970adeef43e75\]]{#structtensorflow_1_1serving_1_1CachingManager_1_1Options_a37422eae96e8e0f107c970adeef43e75
label="structtensorflow_1_1serving_1_1CachingManager_1_1Options_a37422eae96e8e0f107c970adeef43e75"}
Env $\ast$ **env** = Env::Default()

Config options and pluggable objects that will be used by the
[CachingManager](#classtensorflow_1_1serving_1_1CachingManager).

The documentation for this struct was generated from the following file:

tensorflow\_serving/core/caching\_manager.h

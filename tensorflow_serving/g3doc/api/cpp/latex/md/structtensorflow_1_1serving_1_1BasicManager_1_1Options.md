::: {#structtensorflow_1_1serving_1_1BasicManager_1_1Options}
:::

[\[structtensorflow\_1\_1serving\_1\_1BasicManager\_1\_1Options\]]{#structtensorflow_1_1serving_1_1BasicManager_1_1Options
label="structtensorflow_1_1serving_1_1BasicManager_1_1Options"}

\#include $<$basic\_manager.h$>$

Collaboration diagram for tensorflow::serving::BasicManager::Options:

![image](structtensorflow_1_1serving_1_1BasicManager_1_1Options__coll__graph.pdf){width="306pt"}

[\[structtensorflow\_1\_1serving\_1\_1BasicManager\_1\_1Options\_ac9d1a81dee98cc7620de7def2f3fc5ec\]]{#structtensorflow_1_1serving_1_1BasicManager_1_1Options_ac9d1a81dee98cc7620de7def2f3fc5ec
label="structtensorflow_1_1serving_1_1BasicManager_1_1Options_ac9d1a81dee98cc7620de7def2f3fc5ec"}
std::unique\_ptr$<$
[ResourceTracker](#classtensorflow_1_1serving_1_1ResourceTracker) $>$
**resource\_tracker**

[\[structtensorflow\_1\_1serving\_1\_1BasicManager\_1\_1Options\_ac070dcf4f3e622849a8352331bf3e8a0\]]{#structtensorflow_1_1serving_1_1BasicManager_1_1Options_ac070dcf4f3e622849a8352331bf3e8a0
label="structtensorflow_1_1serving_1_1BasicManager_1_1Options_ac070dcf4f3e622849a8352331bf3e8a0"}
uint32 **num\_load\_threads** = 0

[\[structtensorflow\_1\_1serving\_1\_1BasicManager\_1\_1Options\_a273fb5aec53cf0112c4518ef7dbf0ec7\]]{#structtensorflow_1_1serving_1_1BasicManager_1_1Options_a273fb5aec53cf0112c4518ef7dbf0ec7
label="structtensorflow_1_1serving_1_1BasicManager_1_1Options_a273fb5aec53cf0112c4518ef7dbf0ec7"}
uint32 **num\_unload\_threads** = 0

[\[structtensorflow\_1\_1serving\_1\_1BasicManager\_1\_1Options\_acecf73db4c465ee6f2b09f1ea30ebd17\]]{#structtensorflow_1_1serving_1_1BasicManager_1_1Options_acecf73db4c465ee6f2b09f1ea30ebd17
label="structtensorflow_1_1serving_1_1BasicManager_1_1Options_acecf73db4c465ee6f2b09f1ea30ebd17"}
std::function$<$ bool(absl::Status)$>$ **should\_retry\_model\_load**

[\[structtensorflow\_1\_1serving\_1\_1BasicManager\_1\_1Options\_af01298b82549a3c5d186c364456e6778\]]{#structtensorflow_1_1serving_1_1BasicManager_1_1Options_af01298b82549a3c5d186c364456e6778
label="structtensorflow_1_1serving_1_1BasicManager_1_1Options_af01298b82549a3c5d186c364456e6778"}
[EventBus](#classtensorflow_1_1serving_1_1EventBus)$<$
[ServableState](#structtensorflow_1_1serving_1_1ServableState) $>$
$\ast$ **servable\_event\_bus** = nullptr

[\[structtensorflow\_1\_1serving\_1\_1BasicManager\_1\_1Options\_a4777c52b37e1f1f344a788cbf17e286d\]]{#structtensorflow_1_1serving_1_1BasicManager_1_1Options_a4777c52b37e1f1f344a788cbf17e286d
label="structtensorflow_1_1serving_1_1BasicManager_1_1Options_a4777c52b37e1f1f344a788cbf17e286d"}
uint32 **max\_num\_load\_retries** = 5

[\[structtensorflow\_1\_1serving\_1\_1BasicManager\_1\_1Options\_a135c912432f053b1914b584cb5f788c6\]]{#structtensorflow_1_1serving_1_1BasicManager_1_1Options_a135c912432f053b1914b584cb5f788c6
label="structtensorflow_1_1serving_1_1BasicManager_1_1Options_a135c912432f053b1914b584cb5f788c6"}
int64\_t **load\_retry\_interval\_micros** = 1LL $\ast$ 60 $\ast$ 1000
$\ast$ 1000

[\[structtensorflow\_1\_1serving\_1\_1BasicManager\_1\_1Options\_a4dc84a151ab56ec00b8fab09afb3fd23\]]{#structtensorflow_1_1serving_1_1BasicManager_1_1Options_a4dc84a151ab56ec00b8fab09afb3fd23
label="structtensorflow_1_1serving_1_1BasicManager_1_1Options_a4dc84a151ab56ec00b8fab09afb3fd23"}
bool **flush\_filesystem\_caches** = false

[\[structtensorflow\_1\_1serving\_1\_1BasicManager\_1\_1Options\_a2c3dceb7d8960577039ed6b60f56021c\]]{#structtensorflow_1_1serving_1_1BasicManager_1_1Options_a2c3dceb7d8960577039ed6b60f56021c
label="structtensorflow_1_1serving_1_1BasicManager_1_1Options_a2c3dceb7d8960577039ed6b60f56021c"}
Env $\ast$ **env** = Env::Default()

[\[structtensorflow\_1\_1serving\_1\_1BasicManager\_1\_1Options\_a94643fc592451b32d60c86dc63c4a992\]]{#structtensorflow_1_1serving_1_1BasicManager_1_1Options_a94643fc592451b32d60c86dc63c4a992
label="structtensorflow_1_1serving_1_1BasicManager_1_1Options_a94643fc592451b32d60c86dc63c4a992"}
PreLoadHook **pre\_load\_hook**

Config options and pluggable objects that will be used by the
[BasicManager](#classtensorflow_1_1serving_1_1BasicManager).

The documentation for this struct was generated from the following file:

tensorflow\_serving/core/basic\_manager.h

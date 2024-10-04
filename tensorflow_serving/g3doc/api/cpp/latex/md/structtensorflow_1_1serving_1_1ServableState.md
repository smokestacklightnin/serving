::: {#structtensorflow_1_1serving_1_1ServableState}
:::

[\[structtensorflow\_1\_1serving\_1\_1ServableState\]]{#structtensorflow_1_1serving_1_1ServableState
label="structtensorflow_1_1serving_1_1ServableState"}

Collaboration diagram for tensorflow::serving::ServableState:

![image](structtensorflow_1_1serving_1_1ServableState__coll__graph.pdf){width="254pt"}

[\[structtensorflow\_1\_1serving\_1\_1ServableState\_a1e5ed6bcc3fadea5e88989fe36ed5542\]]{#structtensorflow_1_1serving_1_1ServableState_a1e5ed6bcc3fadea5e88989fe36ed5542
label="structtensorflow_1_1serving_1_1ServableState_a1e5ed6bcc3fadea5e88989fe36ed5542"}
enum class **ManagerState** : int { **kStart** , **kLoading** ,
**kAvailable** , **kUnloading** , **kEnd** }

[\[structtensorflow\_1\_1serving\_1\_1ServableState\_a125c2a9c2009491f12ad80df017ed3f0\]]{#structtensorflow_1_1serving_1_1ServableState_a125c2a9c2009491f12ad80df017ed3f0
label="structtensorflow_1_1serving_1_1ServableState_a125c2a9c2009491f12ad80df017ed3f0"}
string **DebugString** () const

[\[structtensorflow\_1\_1serving\_1\_1ServableState\_a6968fadb4ef8a823128ad54ba1471396\]]{#structtensorflow_1_1serving_1_1ServableState_a6968fadb4ef8a823128ad54ba1471396
label="structtensorflow_1_1serving_1_1ServableState_a6968fadb4ef8a823128ad54ba1471396"}
static string **ManagerStateString** (ManagerState state)

[\[structtensorflow\_1\_1serving\_1\_1ServableState\_a8fddd5065a2ea189a7b4e333a0cda3df\]]{#structtensorflow_1_1serving_1_1ServableState_a8fddd5065a2ea189a7b4e333a0cda3df
label="structtensorflow_1_1serving_1_1ServableState_a8fddd5065a2ea189a7b4e333a0cda3df"}
[ServableId](#structtensorflow_1_1serving_1_1ServableId) **id**

[\[structtensorflow\_1\_1serving\_1\_1ServableState\_a32cc38aae55327182b206b3a04cd4a5d\]]{#structtensorflow_1_1serving_1_1ServableState_a32cc38aae55327182b206b3a04cd4a5d
label="structtensorflow_1_1serving_1_1ServableState_a32cc38aae55327182b206b3a04cd4a5d"}
ManagerState **manager\_state**

[\[structtensorflow\_1\_1serving\_1\_1ServableState\_ae648258ad900a9ed4dd9190ba1595192\]]{#structtensorflow_1_1serving_1_1ServableState_ae648258ad900a9ed4dd9190ba1595192
label="structtensorflow_1_1serving_1_1ServableState_ae648258ad900a9ed4dd9190ba1595192"}
Status **health**

The documentation for this struct was generated from the following file:

tensorflow\_serving/core/servable\_state.h

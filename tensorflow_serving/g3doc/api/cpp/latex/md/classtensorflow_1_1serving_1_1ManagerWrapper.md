::: {#classtensorflow_1_1serving_1_1ManagerWrapper}
:::

[\[classtensorflow\_1\_1serving\_1\_1ManagerWrapper\]]{#classtensorflow_1_1serving_1_1ManagerWrapper
label="classtensorflow_1_1serving_1_1ManagerWrapper"}

Inheritance diagram for tensorflow::serving::ManagerWrapper:

![image](classtensorflow_1_1serving_1_1ManagerWrapper__inherit__graph.pdf){width="189pt"}

Collaboration diagram for tensorflow::serving::ManagerWrapper:

![image](classtensorflow_1_1serving_1_1ManagerWrapper__coll__graph.pdf){width="189pt"}

[\[classtensorflow\_1\_1serving\_1\_1ManagerWrapper\_a0b5d2e29eb8c2b48a256496de1cf4fee\]]{#classtensorflow_1_1serving_1_1ManagerWrapper_a0b5d2e29eb8c2b48a256496de1cf4fee
label="classtensorflow_1_1serving_1_1ManagerWrapper_a0b5d2e29eb8c2b48a256496de1cf4fee"}
**ManagerWrapper**
([UniquePtrWithDeps](#classtensorflow_1_1serving_1_1UniquePtrWithDeps)$<$
[Manager](#classtensorflow_1_1serving_1_1Manager) $>$ wrapped)

std::vector$<$ [ServableId](#structtensorflow_1_1serving_1_1ServableId)
$>$
[ListAvailableServableIds](#classtensorflow_1_1serving_1_1ManagerWrapper_a76a6e899de4dfca374b71c4ef415b3d0)
() const override

[\[classtensorflow\_1\_1serving\_1\_1ManagerWrapper\_a76a6e899de4dfca374b71c4ef415b3d0\]]{#classtensorflow_1_1serving_1_1ManagerWrapper_a76a6e899de4dfca374b71c4ef415b3d0
label="classtensorflow_1_1serving_1_1ManagerWrapper_a76a6e899de4dfca374b71c4ef415b3d0"}

std::vector$<$ [ServableId](#structtensorflow_1_1serving_1_1ServableId)
$>$ tensorflow::serving::ManagerWrapper::ListAvailableServableIds (

) const,

Gets a list of all available servable ids, i.e. each of these can be
retrieved using GetServableHandle.

Implements
[tensorflow::serving::Manager](#classtensorflow_1_1serving_1_1Manager_a10694eb8c3e845e4738788092057b7ef).

The documentation for this class was generated from the following files:

tensorflow\_serving/core/manager\_wrapper.h

tensorflow\_serving/core/manager\_wrapper.cc

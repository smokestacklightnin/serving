::: {#classtensorflow_1_1serving_1_1Manager}
:::

[\[classtensorflow\_1\_1serving\_1\_1Manager\]]{#classtensorflow_1_1serving_1_1Manager
label="classtensorflow_1_1serving_1_1Manager"}

\#include $<$manager.h$>$

Inheritance diagram for tensorflow::serving::Manager:

![image](classtensorflow_1_1serving_1_1Manager__inherit__graph.pdf){width="350pt"}

virtual std::vector$<$
[ServableId](#structtensorflow_1_1serving_1_1ServableId) $>$
[ListAvailableServableIds](#classtensorflow_1_1serving_1_1Manager_a10694eb8c3e845e4738788092057b7ef)
() const =0

template$<$typename T $>$ \
std::map$<$ [ServableId](#structtensorflow_1_1serving_1_1ServableId),
[ServableHandle](#classtensorflow_1_1serving_1_1ServableHandle)$<$ T $>$
$>$
[GetAvailableServableHandles](#classtensorflow_1_1serving_1_1Manager_a8ad1c3155120737e5a41776ceeff6aaa)
() const

template$<$typename T $>$ \
Status
[GetServableHandle](#classtensorflow_1_1serving_1_1Manager_aca70babd38f4b416cf27bbf40f8bb093)
(const
[ServableRequest](#structtensorflow_1_1serving_1_1ServableRequest)
&request,
[ServableHandle](#classtensorflow_1_1serving_1_1ServableHandle)$<$ T $>$
$\ast$const handle)

[\[classtensorflow\_1\_1serving\_1\_1Manager\_a5022aa931fef5755238dd5fb8f78ad6c\]]{#classtensorflow_1_1serving_1_1Manager_a5022aa931fef5755238dd5fb8f78ad6c
label="classtensorflow_1_1serving_1_1Manager_a5022aa931fef5755238dd5fb8f78ad6c"}
class **ManagerWrapper**

[Manager](#classtensorflow_1_1serving_1_1Manager) is responsible for
loading, unloading, lookup and lifetime management of all
[Servable](#classtensorflow_1_1serving_1_1Servable) objects via their
Loaders.

[\[classtensorflow\_1\_1serving\_1\_1Manager\_a8ad1c3155120737e5a41776ceeff6aaa\]]{#classtensorflow_1_1serving_1_1Manager_a8ad1c3155120737e5a41776ceeff6aaa
label="classtensorflow_1_1serving_1_1Manager_a8ad1c3155120737e5a41776ceeff6aaa"}
template$<$typename T $>$\
std::map$<$ [ServableId](#structtensorflow_1_1serving_1_1ServableId),
[ServableHandle](#classtensorflow_1_1serving_1_1ServableHandle)$<$ T $>$
$>$ tensorflow::serving::Manager::GetAvailableServableHandles

Returns a map of all the currently available servables of a particular
type T. The map is from the servables id to its corresponding handle.

IMPORTANT: The caller should not hold onto the handles for a long time,
because holding them will delay servable loading and unloading.
[\[classtensorflow\_1\_1serving\_1\_1Manager\_aca70babd38f4b416cf27bbf40f8bb093\]]{#classtensorflow_1_1serving_1_1Manager_aca70babd38f4b416cf27bbf40f8bb093
label="classtensorflow_1_1serving_1_1Manager_aca70babd38f4b416cf27bbf40f8bb093"}

template$<$typename T $>$\
Status tensorflow::serving::Manager::GetServableHandle (

request,

handle

)

Returns a
[ServableHandle](#classtensorflow_1_1serving_1_1ServableHandle) given a
[ServableRequest](#structtensorflow_1_1serving_1_1ServableRequest).
Returns error if no such
[Servable](#classtensorflow_1_1serving_1_1Servable) is available -- e.g.
not yet loaded, has been quiesced/unloaded, etc. Callers may assume that
an OK status indicates a non-null handle.

IMPORTANT: The caller should not hold onto the handles for a long time,
because holding them will delay servable loading and unloading.
[\[classtensorflow\_1\_1serving\_1\_1Manager\_a10694eb8c3e845e4738788092057b7ef\]]{#classtensorflow_1_1serving_1_1Manager_a10694eb8c3e845e4738788092057b7ef
label="classtensorflow_1_1serving_1_1Manager_a10694eb8c3e845e4738788092057b7ef"}

virtual
std::vector$<$[ServableId](#structtensorflow_1_1serving_1_1ServableId)$>$
tensorflow::serving::Manager::ListAvailableServableIds (

) const

Gets a list of all available servable ids, i.e. each of these can be
retrieved using GetServableHandle.

Implemented in
[tensorflow::serving::ServerCore](#classtensorflow_1_1serving_1_1ServerCore_ac88da0268e401fa99bcd074e692ee709),
[tensorflow::serving::ManagerWrapper](#classtensorflow_1_1serving_1_1ManagerWrapper_a76a6e899de4dfca374b71c4ef415b3d0),
[tensorflow::serving::CachingManager](#classtensorflow_1_1serving_1_1CachingManager_af7ec61e19bcd1ac85a4c97c32e977ffe),
[tensorflow::serving::BasicManager](#classtensorflow_1_1serving_1_1BasicManager_a3c004d32952596c1f5759b1cfcc3c639),
and
[tensorflow::serving::AspiredVersionsManager](#classtensorflow_1_1serving_1_1AspiredVersionsManager_a058a76ee71c52d4a6319f14cd9b2ad69).

The documentation for this class was generated from the following file:

tensorflow\_serving/core/manager.h

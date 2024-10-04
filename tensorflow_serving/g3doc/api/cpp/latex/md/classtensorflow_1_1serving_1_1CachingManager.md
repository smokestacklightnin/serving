::: {#classtensorflow_1_1serving_1_1CachingManager}
:::

[\[classtensorflow\_1\_1serving\_1\_1CachingManager\]]{#classtensorflow_1_1serving_1_1CachingManager
label="classtensorflow_1_1serving_1_1CachingManager"}

\#include $<$caching\_manager.h$>$

Inheritance diagram for tensorflow::serving::CachingManager:

![image](classtensorflow_1_1serving_1_1CachingManager__inherit__graph.pdf){width="189pt"}

Collaboration diagram for tensorflow::serving::CachingManager:

![image](classtensorflow_1_1serving_1_1CachingManager__coll__graph.pdf){width="189pt"}

class
[LoaderFactory](#classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory)

struct
[Options](#structtensorflow_1_1serving_1_1CachingManager_1_1Options)

[\[classtensorflow\_1\_1serving\_1\_1CachingManager\_a7b93b1674e052aa564dccf5315a7be8d\]]{#classtensorflow_1_1serving_1_1CachingManager_a7b93b1674e052aa564dccf5315a7be8d
label="classtensorflow_1_1serving_1_1CachingManager_a7b93b1674e052aa564dccf5315a7be8d"}
std::map$<$ [ServableId](#structtensorflow_1_1serving_1_1ServableId),
std::unique\_ptr$<$
[UntypedServableHandle](#classtensorflow_1_1serving_1_1UntypedServableHandle)
$>$ $>$ **GetAvailableUntypedServableHandles** () const override

std::vector$<$ [ServableId](#structtensorflow_1_1serving_1_1ServableId)
$>$
[ListAvailableServableIds](#classtensorflow_1_1serving_1_1CachingManager_af7ec61e19bcd1ac85a4c97c32e977ffe)
() const override

[\[classtensorflow\_1\_1serving\_1\_1CachingManager\_ac530ae46b94f69e00ac75280a8cced2f\]]{#classtensorflow_1_1serving_1_1CachingManager_ac530ae46b94f69e00ac75280a8cced2f
label="classtensorflow_1_1serving_1_1CachingManager_ac530ae46b94f69e00ac75280a8cced2f"}
static Status **Create**
([Options](#structtensorflow_1_1serving_1_1CachingManager_1_1Options)
options, std::unique\_ptr$<$
[LoaderFactory](#classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory)
$>$ loader\_factory, std::unique\_ptr$<$
[CachingManager](#classtensorflow_1_1serving_1_1CachingManager) $>$
$\ast$caching\_manager)

[\[classtensorflow\_1\_1serving\_1\_1CachingManager\_ac7f55e952795d71fecc78543972ddb0c\]]{#classtensorflow_1_1serving_1_1CachingManager_ac7f55e952795d71fecc78543972ddb0c
label="classtensorflow_1_1serving_1_1CachingManager_ac7f55e952795d71fecc78543972ddb0c"}
class **test\_util::CachingManagerTestAccess**

A manager that manages and loads servables on-demand. Upon receiving the
request for a servable name and optional version, the manager checks if
it already has the requested servable loaded. If not, it initiates the
load operation and then serves the request.

The manager blocks on the load operation and returns the handle when the
servable has been loaded, or upon error.

[\[classtensorflow\_1\_1serving\_1\_1CachingManager\_af7ec61e19bcd1ac85a4c97c32e977ffe\]]{#classtensorflow_1_1serving_1_1CachingManager_af7ec61e19bcd1ac85a4c97c32e977ffe
label="classtensorflow_1_1serving_1_1CachingManager_af7ec61e19bcd1ac85a4c97c32e977ffe"}

std::vector$<$ [ServableId](#structtensorflow_1_1serving_1_1ServableId)
$>$ tensorflow::serving::CachingManager::ListAvailableServableIds (

) const,

Gets a list of all available servable ids, i.e. each of these can be
retrieved using GetServableHandle.

Implements
[tensorflow::serving::Manager](#classtensorflow_1_1serving_1_1Manager_a10694eb8c3e845e4738788092057b7ef).

The documentation for this class was generated from the following files:

tensorflow\_serving/core/caching\_manager.h

tensorflow\_serving/core/caching\_manager.cc

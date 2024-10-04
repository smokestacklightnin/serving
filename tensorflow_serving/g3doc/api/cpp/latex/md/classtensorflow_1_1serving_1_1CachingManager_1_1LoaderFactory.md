::: {#classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory}
:::

[\[classtensorflow\_1\_1serving\_1\_1CachingManager\_1\_1LoaderFactory\]]{#classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory
label="classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory"}

\#include $<$caching\_manager.h$>$

Inheritance diagram for
tensorflow::serving::CachingManager::LoaderFactory:

![image](classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory__inherit__graph.pdf){width="259pt"}

virtual [ServableData](#classtensorflow_1_1serving_1_1ServableData)$<$
std::unique\_ptr$<$ [Loader](#classtensorflow_1_1serving_1_1Loader) $>$
$>$
[CreateLoader](#classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory_ab95a61ff7c67b25e96594631207045a2)
(const [ServableId](#structtensorflow_1_1serving_1_1ServableId)
&servable\_id)=0

virtual int64\_t
[GetServableVersion](#classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory_ae3b86ce052eeee59a53ef0ab58080729)
(const string &servable\_name, ServableRequest::AutoVersionPolicy
policy) const =0

An abstraction for a loader-factory to map from a servable request to
the corresponding loader.

[\[classtensorflow\_1\_1serving\_1\_1CachingManager\_1\_1LoaderFactory\_ab95a61ff7c67b25e96594631207045a2\]]{#classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory_ab95a61ff7c67b25e96594631207045a2
label="classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory_ab95a61ff7c67b25e96594631207045a2"}

virtual
[ServableData](#classtensorflow_1_1serving_1_1ServableData)$<$std::unique\_ptr$<$[Loader](#classtensorflow_1_1serving_1_1Loader)$>$
$>$ tensorflow::serving::CachingManager::LoaderFactory::CreateLoader (

servable\_id

)

Creates servable data consisting of the loader corresponding to the
servable-id. Any errors can be reported by embedding them in the
returned [ServableData](#classtensorflow_1_1serving_1_1ServableData)
item.

Implemented in
[tensorflow::serving::PathPrefixLoaderFactory](#classtensorflow_1_1serving_1_1PathPrefixLoaderFactory_a9e0ecef7ee02c156984a710904b663a2).

[\[classtensorflow\_1\_1serving\_1\_1CachingManager\_1\_1LoaderFactory\_ae3b86ce052eeee59a53ef0ab58080729\]]{#classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory_ae3b86ce052eeee59a53ef0ab58080729
label="classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory_ae3b86ce052eeee59a53ef0ab58080729"}

virtual int64\_t
tensorflow::serving::CachingManager::LoaderFactory::GetServableVersion (

servable\_name,

policy

) const

Returns a version corresponding to the servable name, for the given
policy.

Implemented in
[tensorflow::serving::PathPrefixLoaderFactory](#classtensorflow_1_1serving_1_1PathPrefixLoaderFactory_a77c005c15269b9996b55e1703658f8cc).

The documentation for this class was generated from the following file:

tensorflow\_serving/core/caching\_manager.h

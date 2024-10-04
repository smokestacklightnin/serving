::: {#classtensorflow_1_1serving_1_1PathPrefixLoaderFactory}
:::

[\[classtensorflow\_1\_1serving\_1\_1PathPrefixLoaderFactory\]]{#classtensorflow_1_1serving_1_1PathPrefixLoaderFactory
label="classtensorflow_1_1serving_1_1PathPrefixLoaderFactory"}

\#include $<$caching\_manager.h$>$

Inheritance diagram for tensorflow::serving::PathPrefixLoaderFactory:

![image](classtensorflow_1_1serving_1_1PathPrefixLoaderFactory__inherit__graph.pdf){width="259pt"}

Collaboration diagram for tensorflow::serving::PathPrefixLoaderFactory:

![image](classtensorflow_1_1serving_1_1PathPrefixLoaderFactory__coll__graph.pdf){width="259pt"}

[\[classtensorflow\_1\_1serving\_1\_1PathPrefixLoaderFactory\_ab3ed02c5720671062c9e068b48f076b5\]]{#classtensorflow_1_1serving_1_1PathPrefixLoaderFactory_ab3ed02c5720671062c9e068b48f076b5
label="classtensorflow_1_1serving_1_1PathPrefixLoaderFactory_ab3ed02c5720671062c9e068b48f076b5"}
**PathPrefixLoaderFactory** (const string &path\_prefix,
std::unique\_ptr$<$
[StoragePathSourceAdapter](#classtensorflow_1_1serving_1_1SourceAdapter)
$>$ adapter)

[ServableData](#classtensorflow_1_1serving_1_1ServableData)$<$
std::unique\_ptr$<$ [Loader](#classtensorflow_1_1serving_1_1Loader) $>$
$>$
[CreateLoader](#classtensorflow_1_1serving_1_1PathPrefixLoaderFactory_a9e0ecef7ee02c156984a710904b663a2)
(const [ServableId](#structtensorflow_1_1serving_1_1ServableId) &id)
override

int64\_t
[GetServableVersion](#classtensorflow_1_1serving_1_1PathPrefixLoaderFactory_a77c005c15269b9996b55e1703658f8cc)
(const string &servable\_name, ServableRequest::AutoVersionPolicy
policy) const override

A simple LoaderFactory that looks for a servable at a path formed by
concatenating a fixed path prefix with the servables name. It assumes
that a given servable only has one version, namely version 0.

[\[classtensorflow\_1\_1serving\_1\_1PathPrefixLoaderFactory\_a9e0ecef7ee02c156984a710904b663a2\]]{#classtensorflow_1_1serving_1_1PathPrefixLoaderFactory_a9e0ecef7ee02c156984a710904b663a2
label="classtensorflow_1_1serving_1_1PathPrefixLoaderFactory_a9e0ecef7ee02c156984a710904b663a2"}

[ServableData](#classtensorflow_1_1serving_1_1ServableData)$<$
std::unique\_ptr$<$ [Loader](#classtensorflow_1_1serving_1_1Loader) $>$
$>$ tensorflow::serving::PathPrefixLoaderFactory::CreateLoader (

servable\_id

),

Creates servable data consisting of the loader corresponding to the
servable-id. Any errors can be reported by embedding them in the
returned [ServableData](#classtensorflow_1_1serving_1_1ServableData)
item.

Implements
[tensorflow::serving::CachingManager::LoaderFactory](#classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory_ab95a61ff7c67b25e96594631207045a2).

[\[classtensorflow\_1\_1serving\_1\_1PathPrefixLoaderFactory\_a77c005c15269b9996b55e1703658f8cc\]]{#classtensorflow_1_1serving_1_1PathPrefixLoaderFactory_a77c005c15269b9996b55e1703658f8cc
label="classtensorflow_1_1serving_1_1PathPrefixLoaderFactory_a77c005c15269b9996b55e1703658f8cc"}

int64\_t
tensorflow::serving::PathPrefixLoaderFactory::GetServableVersion (

servable\_name,

policy

) const,

Returns a version corresponding to the servable name, for the given
policy.

Implements
[tensorflow::serving::CachingManager::LoaderFactory](#classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory_ae3b86ce052eeee59a53ef0ab58080729).

The documentation for this class was generated from the following files:

tensorflow\_serving/core/caching\_manager.h

tensorflow\_serving/core/caching\_manager.cc

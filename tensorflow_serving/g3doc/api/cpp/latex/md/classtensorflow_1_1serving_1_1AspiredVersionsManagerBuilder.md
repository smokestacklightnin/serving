::: {#classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder}
:::

[\[classtensorflow\_1\_1serving\_1\_1AspiredVersionsManagerBuilder\]]{#classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder
label="classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder"}

\#include $<$aspired\_versions\_manager\_builder.h$>$

[\[classtensorflow\_1\_1serving\_1\_1AspiredVersionsManagerBuilder\_af921abbdbda20510e5aed5a0d28d9edb\]]{#classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder_af921abbdbda20510e5aed5a0d28d9edb
label="classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder_af921abbdbda20510e5aed5a0d28d9edb"}
using **Options** =
[AspiredVersionsManager::Options](#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options)

template$<$typename S $>$ \
void
[AddSource](#classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder_abd6f745193c54f7887119ed886dda0ed)
(std::unique\_ptr$<$ S $>$ source)

template$<$typename S , typename SA , typename\... Args$>$ \
void
[AddSourceChain](#classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder_a4b8c4eda9ac206ecc69b7464b6e42a44)
(std::unique\_ptr$<$ S $>$ source, std::unique\_ptr$<$ SA $>$
first\_source\_adapter, std::unique\_ptr$<$ Args $>$\...
remaining\_source\_adapters)

[\[classtensorflow\_1\_1serving\_1\_1AspiredVersionsManagerBuilder\_a9a95dc4a19029c2bc28fdc6caa274656\]]{#classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder_a9a95dc4a19029c2bc28fdc6caa274656
label="classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder_a9a95dc4a19029c2bc28fdc6caa274656"}
std::unique\_ptr$<$ [Manager](#classtensorflow_1_1serving_1_1Manager)
$>$
[Build](#classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder_a9a95dc4a19029c2bc28fdc6caa274656)
()

*Builds the
[AspiredVersionsManager](#classtensorflow_1_1serving_1_1AspiredVersionsManager)
and returns it as the [Manager](#classtensorflow_1_1serving_1_1Manager)
interface.*

[\[classtensorflow\_1\_1serving\_1\_1AspiredVersionsManagerBuilder\_a2a6aa53dab22f2d35af4a9022b84c5ea\]]{#classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder_a2a6aa53dab22f2d35af4a9022b84c5ea
label="classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder_a2a6aa53dab22f2d35af4a9022b84c5ea"}
static Status **Create**
([Options](#structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options)
options, std::unique\_ptr$<$
[AspiredVersionsManagerBuilder](#classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder)
$>$ $\ast$builder)

Builds an
[AspiredVersionsManager](#classtensorflow_1_1serving_1_1AspiredVersionsManager)
with options and sources connected to it. It takes over the ownership of
the sources and the returned manager handles the destruction of itself
and its dependencies. Both single sources and source/source-adapter
chains are accepted, i.e. you can use sources that directly supply
loaders
([Source](#classtensorflow_1_1serving_1_1Source)&lt;std::unique\_ptr&lt;[Loader](#classtensorflow_1_1serving_1_1Loader)$>$$>$)
or composites that consist of
[Source](#classtensorflow_1_1serving_1_1Source)&lt;S$>$ + some chain of
[SourceAdapter](#classtensorflow_1_1serving_1_1SourceAdapter)&lt;S,
\...$>$, \...,
[SourceAdapter](#classtensorflow_1_1serving_1_1SourceAdapter)&lt;\...,
std::unique\_ptr&lt;[Loader](#classtensorflow_1_1serving_1_1Loader)$>$$>$.
The builder connects the chain for you.

Usage:

NOTE: A builder can only be used to build a single
[AspiredVersionsManager](#classtensorflow_1_1serving_1_1AspiredVersionsManager).

This class is not thread-safe.

[\[classtensorflow\_1\_1serving\_1\_1AspiredVersionsManagerBuilder\_abd6f745193c54f7887119ed886dda0ed\]]{#classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder_abd6f745193c54f7887119ed886dda0ed
label="classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder_abd6f745193c54f7887119ed886dda0ed"}

template$<$typename S $>$\
void tensorflow::serving::AspiredVersionsManagerBuilder::AddSource (

source

)

Connects the source to the
[AspiredVersionsManager](#classtensorflow_1_1serving_1_1AspiredVersionsManager)
being built and takes over its ownership.

REQUIRES: Template type S be convertible to
[Source](#classtensorflow_1_1serving_1_1Source)&lt;std::unique\_ptr&lt;[Loader](#classtensorflow_1_1serving_1_1Loader)$>$$>$.
[\[classtensorflow\_1\_1serving\_1\_1AspiredVersionsManagerBuilder\_a4b8c4eda9ac206ecc69b7464b6e42a44\]]{#classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder_a4b8c4eda9ac206ecc69b7464b6e42a44
label="classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder_a4b8c4eda9ac206ecc69b7464b6e42a44"}

template$<$typename S , typename SA , typename\... Args$>$\
void tensorflow::serving::AspiredVersionsManagerBuilder::AddSourceChain
(

source,

first\_source\_adapter,

remaining\_source\_adapters

)

Connects a chain comprising a source and a chain of source adapters,
s.t. the final adapter in the chain emits Loaders for the manager. The
final adapter is connected to the manager. We take ownership of the
whole chain.

REQUIRES: At least one source adapter.

Usage: builder-$>$AddSourceChain( std::move(source),
std::move(source\_adapter1), std::move(source\_adapter2));

The documentation for this class was generated from the following files:

tensorflow\_serving/core/aspired\_versions\_manager\_builder.h

tensorflow\_serving/core/aspired\_versions\_manager\_builder.cc

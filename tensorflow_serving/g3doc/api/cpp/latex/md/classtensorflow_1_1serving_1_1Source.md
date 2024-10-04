::: {#classtensorflow_1_1serving_1_1Source}
:::

[\[classtensorflow\_1\_1serving\_1\_1Source\]]{#classtensorflow_1_1serving_1_1Source
label="classtensorflow_1_1serving_1_1Source"}

\#include $<$source.h$>$

Inheritance diagram for tensorflow::serving::Source$<$ T $>$:

![image](classtensorflow_1_1serving_1_1Source__inherit__graph.pdf){width="217pt"}

using
[AspiredVersionsCallback](#classtensorflow_1_1serving_1_1Source_aeb281087e1478b0ff4a74e3f60496c6f)
= std::function$<$ void(const StringPiece servable\_name, std::vector$<$
[ServableData](#classtensorflow_1_1serving_1_1ServableData)$<$ T $>$ $>$
versions)$>$

[\[classtensorflow\_1\_1serving\_1\_1Source\_a70d7f3b3ab429deb777d4672c0cec447\]]{#classtensorflow_1_1serving_1_1Source_a70d7f3b3ab429deb777d4672c0cec447
label="classtensorflow_1_1serving_1_1Source_a70d7f3b3ab429deb777d4672c0cec447"}
virtual void
[SetAspiredVersionsCallback](#classtensorflow_1_1serving_1_1Source_a70d7f3b3ab429deb777d4672c0cec447)
([AspiredVersionsCallback](#classtensorflow_1_1serving_1_1Source_aeb281087e1478b0ff4a74e3f60496c6f)
callback)=0

*Supplies an AspiredVersionsCallback to use. Can be called at most
once.*

### template$<$typename T$>$ class tensorflow::serving::Source$<$ T $>$ {#templatetypename-t-class-tensorflowservingsource-t .unnumbered}

An abstraction for a module that sources servables to load, or, more
precisely, handles to data that can be used to load those servables.
Examples of such data handles are:

a file-system path to a serialized vocabulary map

a handle to an incoming RPC that specifies a machine-learned model to
load

a [Loader](#classtensorflow_1_1serving_1_1Loader) (see
[loader.h](#loader_8h_source)) The data handles are generally assumed to
be small.

A [Source](#classtensorflow_1_1serving_1_1Source) monitors some external
resource (e.g. file system, RPC calls) to find out about new servables
and/or new versions of servables and/or the need to unload servable
versions. It uses the provided callback to instruct a
[Target](#classtensorflow_1_1serving_1_1Target) module (e.g.
[AspiredVersionsManager](#classtensorflow_1_1serving_1_1AspiredVersionsManager))
which version(s) of a given servable to load. Furthermore, depending on
the semantics of the [Target](#classtensorflow_1_1serving_1_1Target)
module, the [Source](#classtensorflow_1_1serving_1_1Source) implicitly
instructs it which ones to unload by omitting those servables.

A common case is that a [Source](#classtensorflow_1_1serving_1_1Source)
emits versions for exactly one servable. An even simpler case is that a
servable has a single, static version for the lifetime of the server.

Sources can house state that is shared among multiple emitted servables,
e.g.

A shared thread pool or other resource that multiple servables use.

A shared read-only data structure that multiple servables use, to avoid
the time and space overhead of replicating the data structure in each
servable instance. Shared state whose initialization time and size is
negligible (e.g. thread pools) can be created eagerly by the source,
which then embeds a pointer to it in each emitted
[ServableData](#classtensorflow_1_1serving_1_1ServableData) item.
Creation of expensive or large shared state should be deferred to the
first applicable
[Loader::Load()](#classtensorflow_1_1serving_1_1Loader_a7dadc89ccbf488aae0102368261cc692)
call, i.e. governed by the manager. Symmetrically, the
[Loader::Unload()](#classtensorflow_1_1serving_1_1Loader_addca8f4264380e5e635bbe1197f5347f)
call to the final servable using the expensive/large shared state should
tear it down.

[\[classtensorflow\_1\_1serving\_1\_1Source\_aeb281087e1478b0ff4a74e3f60496c6f\]]{#classtensorflow_1_1serving_1_1Source_aeb281087e1478b0ff4a74e3f60496c6f
label="classtensorflow_1_1serving_1_1Source_aeb281087e1478b0ff4a74e3f60496c6f"}
template$<$typename T $>$\
using
[tensorflow::serving::Source](#classtensorflow_1_1serving_1_1Source)$<$
T
$>$::[AspiredVersionsCallback](#classtensorflow_1_1serving_1_1Source_aeb281087e1478b0ff4a74e3f60496c6f)
= std::function$<$void( const StringPiece servable\_name,
std::vector$<$[ServableData](#classtensorflow_1_1serving_1_1ServableData)$<$T$>$
$>$ versions)$>$

A callback for a [Source](#classtensorflow_1_1serving_1_1Source) to
supply version(s) of a servable to a
[Target](#classtensorflow_1_1serving_1_1Target), to be loaded.

A single invocation of the callback pertains to a single servable stream
(given by servable\_name). All versions supplied in a call must be for
the servable identified in servable\_name. Invocations on different
servable streams are orthogonal to one another.

Multiple invocations may supply servable-data objects with identical ids
(i.e. same servable name and version). Such servable-data objects are
treated as semantically equivalent. The recipient will ultimately retain
one and discard the rest.

If a servable version V is supplied in a first invocation, and
subsequently omitted from a second invocation, the implication of
omitting V depends on the semantics of the
[Target](#classtensorflow_1_1serving_1_1Target) of the callback. Certain
Targets will interpret Vs omission as an implicit instruction to unload
V. Each [Target](#classtensorflow_1_1serving_1_1Target) must document
its semantics in this regard.

The documentation for this class was generated from the following file:

tensorflow\_serving/core/source.h

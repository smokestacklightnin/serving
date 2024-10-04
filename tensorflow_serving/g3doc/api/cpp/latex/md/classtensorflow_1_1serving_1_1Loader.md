::: {#classtensorflow_1_1serving_1_1Loader}
:::

[\[classtensorflow\_1\_1serving\_1\_1Loader\]]{#classtensorflow_1_1serving_1_1Loader
label="classtensorflow_1_1serving_1_1Loader"}

\#include $<$loader.h$>$

Inheritance diagram for tensorflow::serving::Loader:

![image](classtensorflow_1_1serving_1_1Loader__inherit__graph.pdf){width="350pt"}

struct [Metadata](#structtensorflow_1_1serving_1_1Loader_1_1Metadata)

*The metadata consists of the
[ServableId](#structtensorflow_1_1serving_1_1ServableId).*

virtual
[$\sim$Loader](#classtensorflow_1_1serving_1_1Loader_ab12e7e4d5f33ade6dd73d7a30873c032)
()=default

virtual Status
[EstimateResources](#classtensorflow_1_1serving_1_1Loader_ab59db26b242a2224889bc7c5c6edae40)
(ResourceAllocation $\ast$estimate) const =0

virtual Status
[Load](#classtensorflow_1_1serving_1_1Loader_a7dadc89ccbf488aae0102368261cc692)
()

virtual Status
[LoadWithMetadata](#classtensorflow_1_1serving_1_1Loader_a7aebd433e4a782265d847e507f3bc824)
(const [Metadata](#structtensorflow_1_1serving_1_1Loader_1_1Metadata)
&metadata)

virtual void
[Unload](#classtensorflow_1_1serving_1_1Loader_addca8f4264380e5e635bbe1197f5347f)
()=0

virtual [AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr)
[servable](#classtensorflow_1_1serving_1_1Loader_a640d67dc6ca9926595d29fdfe63868c1)
()=0

A standardized abstraction for an object that manages the lifecycle of a
servable, including loading and unloading it. Servables are arbitrary
objects that serve algorithms or data that often, though not
necessarily, use a machine-learned model.

A [Loader](#classtensorflow_1_1serving_1_1Loader) for a servable object
represents one instance of a stream of servable versions, all sharing a
common name (e.g. '̈my\_servable'̈) and increasing version numbers,
typically representing updated model parameters learned from fresh
training data.

A [Loader](#classtensorflow_1_1serving_1_1Loader) should start in an
unloaded state, meaning that no work has been done to prepare to perform
operations. A typical instance that has not yet been loaded contains
merely a pointer to a location from which its data can be loaded (e.g. a
file-system path or network location). Construction and destruction of
instances should be fairly cheap. Expensive initialization operations
should be done in
[Load()](#classtensorflow_1_1serving_1_1Loader_a7dadc89ccbf488aae0102368261cc692).

Subclasses may optionally store a pointer to the
[Source](#classtensorflow_1_1serving_1_1Source) that originated it, for
accessing state shared across multiple servable objects in a given
servable stream.

Implementations need to ensure that the methods they expose are
thread-safe, or carefully document and/or coordinate their thread-safety
properties with their clients to ensure correctness. Servables do not
need to worry about concurrent execution of
[Load()](#classtensorflow_1_1serving_1_1Loader_a7dadc89ccbf488aae0102368261cc692)/Unload()
as the caller will ensure that does not happen.

[\[classtensorflow\_1\_1serving\_1\_1Loader\_ab12e7e4d5f33ade6dd73d7a30873c032\]]{#classtensorflow_1_1serving_1_1Loader_ab12e7e4d5f33ade6dd73d7a30873c032
label="classtensorflow_1_1serving_1_1Loader_ab12e7e4d5f33ade6dd73d7a30873c032"}

virtual tensorflow::serving::Loader::$\sim$Loader (

),

The destructor will never be called on a
[Loader](#classtensorflow_1_1serving_1_1Loader) whose servable is
currently loaded, i.e. between (successful) calls to
[Load()](#classtensorflow_1_1serving_1_1Loader_a7dadc89ccbf488aae0102368261cc692)
and
[Unload()](#classtensorflow_1_1serving_1_1Loader_addca8f4264380e5e635bbe1197f5347f).

[\[classtensorflow\_1\_1serving\_1\_1Loader\_ab59db26b242a2224889bc7c5c6edae40\]]{#classtensorflow_1_1serving_1_1Loader_ab59db26b242a2224889bc7c5c6edae40
label="classtensorflow_1_1serving_1_1Loader_ab59db26b242a2224889bc7c5c6edae40"}

virtual Status tensorflow::serving::Loader::EstimateResources (

estimate

) const

Estimates the resources a servable will use.

IMPORTANT: This methods implementation must obey following requirements,
which enable the serving system to reason correctly about which
servables can be loaded safely:

The estimate must represent an upper bound on the actual value.

Prior to load, the estimate may include resources that are not bound to
any specific device instance, e.g. RAM on one of the two GPUs.

While loaded, for any devices with multiple instances (e.g. two GPUs),
the estimate must specify the instance to which each resource is bound.

The estimate must be monotonically non-increasing, i.e. it cannot
increase over time. Reasons to have it potentially decrease over time

Returns an estimate of the resources the servable will consume once
loaded. If the servable has already been loaded, returns an estimate of
the actual resource usage.

Implemented in
[tensorflow::serving::SimpleLoader$<$ ServableType $>$](#classtensorflow_1_1serving_1_1SimpleLoader_a05ede6c604d05037f59fe13472b48935),
and
[tensorflow::serving::ResourceUnsafeLoader](#classtensorflow_1_1serving_1_1ResourceUnsafeLoader_a1a0c1398af9af54032ba16a79a9ecac4).

[\[classtensorflow\_1\_1serving\_1\_1Loader\_a7dadc89ccbf488aae0102368261cc692\]]{#classtensorflow_1_1serving_1_1Loader_a7dadc89ccbf488aae0102368261cc692
label="classtensorflow_1_1serving_1_1Loader_a7dadc89ccbf488aae0102368261cc692"}

virtual Status tensorflow::serving::Loader::Load (

),

Fetches any data that needs to be loaded before using the servable
returned by
[servable()](#classtensorflow_1_1serving_1_1Loader_a640d67dc6ca9926595d29fdfe63868c1).
May use no more resources than the estimate reported by
[EstimateResources()](#classtensorflow_1_1serving_1_1Loader_ab59db26b242a2224889bc7c5c6edae40).

If implementing
[Load()](#classtensorflow_1_1serving_1_1Loader_a7dadc89ccbf488aae0102368261cc692),
you dont have to override
[LoadWithMetadata()](#classtensorflow_1_1serving_1_1Loader_a7aebd433e4a782265d847e507f3bc824).

Reimplemented in
[tensorflow::serving::test\_util::FakeLoader](#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_a2edb74f10db51d582ee689d3d81cacb7),
and
[tensorflow::serving::SimpleLoader$<$ ServableType $>$](#classtensorflow_1_1serving_1_1SimpleLoader_ada69d680b17f2e054faef889f135cb74).

[\[classtensorflow\_1\_1serving\_1\_1Loader\_a7aebd433e4a782265d847e507f3bc824\]]{#classtensorflow_1_1serving_1_1Loader_a7aebd433e4a782265d847e507f3bc824
label="classtensorflow_1_1serving_1_1Loader_a7aebd433e4a782265d847e507f3bc824"}

virtual Status tensorflow::serving::Loader::LoadWithMetadata (

metadata

),

Similar to the above method, but takes
[Metadata](#structtensorflow_1_1serving_1_1Loader_1_1Metadata) as a
param, which may be used by the loader implementation appropriately.

If youre overriding
[LoadWithMetadata()](#classtensorflow_1_1serving_1_1Loader_a7aebd433e4a782265d847e507f3bc824),
because you can use the metadata appropriately, you can skip overriding
[Load()](#classtensorflow_1_1serving_1_1Loader_a7dadc89ccbf488aae0102368261cc692).

Reimplemented in
[tensorflow::serving::SimpleLoader$<$ ServableType $>$](#classtensorflow_1_1serving_1_1SimpleLoader_a4c9a2f88fd1cab8a68ffa69bb9900e24).

[\[classtensorflow\_1\_1serving\_1\_1Loader\_a640d67dc6ca9926595d29fdfe63868c1\]]{#classtensorflow_1_1serving_1_1Loader_a640d67dc6ca9926595d29fdfe63868c1
label="classtensorflow_1_1serving_1_1Loader_a640d67dc6ca9926595d29fdfe63868c1"}

virtual [AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr)
tensorflow::serving::Loader::servable (

)

Returns an opaque interface to the underlying servable object. The
caller should know the precise type of the interface in order to make
actual use of it. For example:

CustomLoader implementation:

Serving user request:

ServableHandle&lt;CustomServable\> handle = \... CustomServable\*
servable = handle.get(); servable-\>\...

If
[servable()](#classtensorflow_1_1serving_1_1Loader_a640d67dc6ca9926595d29fdfe63868c1)
is called after successful
[Load()](#classtensorflow_1_1serving_1_1Loader_a7dadc89ccbf488aae0102368261cc692)
and before
[Unload()](#classtensorflow_1_1serving_1_1Loader_addca8f4264380e5e635bbe1197f5347f),
it returns a valid, non-null
[AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr) object. If called before
a successful
[Load()](#classtensorflow_1_1serving_1_1Loader_a7dadc89ccbf488aae0102368261cc692)
call or after
[Unload()](#classtensorflow_1_1serving_1_1Loader_addca8f4264380e5e635bbe1197f5347f),
it returns null [AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr).

Implemented in
[tensorflow::serving::test\_util::FakeLoader](#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_afd3838612c119a086d1b17ce7cdfb9ed),
and
[tensorflow::serving::SimpleLoader$<$ ServableType $>$](#classtensorflow_1_1serving_1_1SimpleLoader_a914a9107be7cfeb587998934be9d9fee).

[\[classtensorflow\_1\_1serving\_1\_1Loader\_addca8f4264380e5e635bbe1197f5347f\]]{#classtensorflow_1_1serving_1_1Loader_addca8f4264380e5e635bbe1197f5347f
label="classtensorflow_1_1serving_1_1Loader_addca8f4264380e5e635bbe1197f5347f"}

virtual void tensorflow::serving::Loader::Unload (

)

Frees any resources allocated during
[Load()](#classtensorflow_1_1serving_1_1Loader_a7dadc89ccbf488aae0102368261cc692)
(except perhaps for resources shared across servables that are still
needed for other active ones). The loader does not need to return to the
'̈new'̈ state (i.e.
[Load()](#classtensorflow_1_1serving_1_1Loader_a7dadc89ccbf488aae0102368261cc692)
cannot be called after
[Unload()](#classtensorflow_1_1serving_1_1Loader_addca8f4264380e5e635bbe1197f5347f)).

Implemented in
[tensorflow::serving::test\_util::FakeLoader](#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_a336ea084823272d433d19be25769fc70),
and
[tensorflow::serving::SimpleLoader$<$ ServableType $>$](#classtensorflow_1_1serving_1_1SimpleLoader_ae24b904b3155f039fadd88b1c23e2f82).

The documentation for this class was generated from the following file:

tensorflow\_serving/core/loader.h

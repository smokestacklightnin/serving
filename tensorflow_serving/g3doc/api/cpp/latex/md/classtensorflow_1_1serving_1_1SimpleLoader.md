::: {#classtensorflow_1_1serving_1_1SimpleLoader}
:::

[\[classtensorflow\_1\_1serving\_1\_1SimpleLoader\]]{#classtensorflow_1_1serving_1_1SimpleLoader
label="classtensorflow_1_1serving_1_1SimpleLoader"}

Inheritance diagram for tensorflow::serving::SimpleLoader$<$
ServableType $>$:

![image](classtensorflow_1_1serving_1_1SimpleLoader__inherit__graph.pdf){width="257pt"}

Collaboration diagram for tensorflow::serving::SimpleLoader$<$
ServableType $>$:

![image](classtensorflow_1_1serving_1_1SimpleLoader__coll__graph.pdf){width="257pt"}

[\[classtensorflow\_1\_1serving\_1\_1SimpleLoader\_a41233d05569814753928a67a414281a9\]]{#classtensorflow_1_1serving_1_1SimpleLoader_a41233d05569814753928a67a414281a9
label="classtensorflow_1_1serving_1_1SimpleLoader_a41233d05569814753928a67a414281a9"}
using **Creator** = std::function$<$ Status(std::unique\_ptr$<$
ServableType $>$ $\ast$)$>$

[\[classtensorflow\_1\_1serving\_1\_1SimpleLoader\_a4623eb7f1ee9169db1d9f23e0f377922\]]{#classtensorflow_1_1serving_1_1SimpleLoader_a4623eb7f1ee9169db1d9f23e0f377922
label="classtensorflow_1_1serving_1_1SimpleLoader_a4623eb7f1ee9169db1d9f23e0f377922"}
using **CreatorWithMetadata** = std::function$<$ Status(const
[Metadata](#structtensorflow_1_1serving_1_1Loader_1_1Metadata) &,
std::unique\_ptr$<$ ServableType $>$ $\ast$)$>$

[\[classtensorflow\_1\_1serving\_1\_1SimpleLoader\_ab25158ab5062f7e125d5771ebef4c571\]]{#classtensorflow_1_1serving_1_1SimpleLoader_ab25158ab5062f7e125d5771ebef4c571
label="classtensorflow_1_1serving_1_1SimpleLoader_ab25158ab5062f7e125d5771ebef4c571"}
using **CreatorVariant** = absl::variant$<$ Creator, CreatorWithMetadata
$>$

[\[classtensorflow\_1\_1serving\_1\_1SimpleLoader\_ad56b75f604ff95b4740573209efd3fd5\]]{#classtensorflow_1_1serving_1_1SimpleLoader_ad56b75f604ff95b4740573209efd3fd5
label="classtensorflow_1_1serving_1_1SimpleLoader_ad56b75f604ff95b4740573209efd3fd5"}
using **ResourceEstimator** = std::function$<$ Status(ResourceAllocation
$\ast$)$>$

[\[classtensorflow\_1\_1serving\_1\_1SimpleLoader\_ab128232d2103f28712aca27d74a4d255\]]{#classtensorflow_1_1serving_1_1SimpleLoader_ab128232d2103f28712aca27d74a4d255
label="classtensorflow_1_1serving_1_1SimpleLoader_ab128232d2103f28712aca27d74a4d255"}
**SimpleLoader** (Creator creator, ResourceEstimator
resource\_estimator)

[\[classtensorflow\_1\_1serving\_1\_1SimpleLoader\_a9125d0e74cf2f7cd41ddaae3902713cb\]]{#classtensorflow_1_1serving_1_1SimpleLoader_a9125d0e74cf2f7cd41ddaae3902713cb
label="classtensorflow_1_1serving_1_1SimpleLoader_a9125d0e74cf2f7cd41ddaae3902713cb"}
**SimpleLoader** (CreatorWithMetadata creator\_with\_metadata,
ResourceEstimator resource\_estimator)

[\[classtensorflow\_1\_1serving\_1\_1SimpleLoader\_a14d1a5400554740aceae0d60840e1832\]]{#classtensorflow_1_1serving_1_1SimpleLoader_a14d1a5400554740aceae0d60840e1832
label="classtensorflow_1_1serving_1_1SimpleLoader_a14d1a5400554740aceae0d60840e1832"}
**SimpleLoader** (Creator creator, ResourceEstimator
resource\_estimator, ResourceEstimator post\_load\_resource\_estimator)

[\[classtensorflow\_1\_1serving\_1\_1SimpleLoader\_afd1e11ebf64eed6be7e63d32df4c8a77\]]{#classtensorflow_1_1serving_1_1SimpleLoader_afd1e11ebf64eed6be7e63d32df4c8a77
label="classtensorflow_1_1serving_1_1SimpleLoader_afd1e11ebf64eed6be7e63d32df4c8a77"}
**SimpleLoader** (CreatorWithMetadata creator\_with\_metadata,
ResourceEstimator resource\_estimator, ResourceEstimator
post\_load\_resource\_estimator)

[\[classtensorflow\_1\_1serving\_1\_1SimpleLoader\_a761d945b99d3cab3e8ec1b4e385f5ca2\]]{#classtensorflow_1_1serving_1_1SimpleLoader_a761d945b99d3cab3e8ec1b4e385f5ca2
label="classtensorflow_1_1serving_1_1SimpleLoader_a761d945b99d3cab3e8ec1b4e385f5ca2"}
**SimpleLoader** (CreatorVariant creator\_variant, ResourceEstimator
resource\_estimator, absl::optional$<$ ResourceEstimator $>$
post\_load\_resource\_estimator)

Status
[EstimateResources](#classtensorflow_1_1serving_1_1SimpleLoader_a05ede6c604d05037f59fe13472b48935)
(ResourceAllocation $\ast$estimate) const override

Status
[Load](#classtensorflow_1_1serving_1_1SimpleLoader_ada69d680b17f2e054faef889f135cb74)
() override

Status
[LoadWithMetadata](#classtensorflow_1_1serving_1_1SimpleLoader_a4c9a2f88fd1cab8a68ffa69bb9900e24)
(const [Metadata](#structtensorflow_1_1serving_1_1Loader_1_1Metadata)
&metadata) override

void
[Unload](#classtensorflow_1_1serving_1_1SimpleLoader_ae24b904b3155f039fadd88b1c23e2f82)
() override

[AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr)
[servable](#classtensorflow_1_1serving_1_1SimpleLoader_a914a9107be7cfeb587998934be9d9fee)
() override

[\[classtensorflow\_1\_1serving\_1\_1SimpleLoader\_a9df494e930b1c23df38685a10d7c9614\]]{#classtensorflow_1_1serving_1_1SimpleLoader_a9df494e930b1c23df38685a10d7c9614
label="classtensorflow_1_1serving_1_1SimpleLoader_a9df494e930b1c23df38685a10d7c9614"}
static ResourceEstimator **EstimateNoResources** ()

[\[classtensorflow\_1\_1serving\_1\_1SimpleLoader\_a05ede6c604d05037f59fe13472b48935\]]{#classtensorflow_1_1serving_1_1SimpleLoader_a05ede6c604d05037f59fe13472b48935
label="classtensorflow_1_1serving_1_1SimpleLoader_a05ede6c604d05037f59fe13472b48935"}

template$<$typename ServableType $>$\
Status
[tensorflow::serving::SimpleLoader](#classtensorflow_1_1serving_1_1SimpleLoader)$<$
ServableType $>$::EstimateResources (

estimate

) const,

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

Implements
[tensorflow::serving::Loader](#classtensorflow_1_1serving_1_1Loader_ab59db26b242a2224889bc7c5c6edae40).

[\[classtensorflow\_1\_1serving\_1\_1SimpleLoader\_ada69d680b17f2e054faef889f135cb74\]]{#classtensorflow_1_1serving_1_1SimpleLoader_ada69d680b17f2e054faef889f135cb74
label="classtensorflow_1_1serving_1_1SimpleLoader_ada69d680b17f2e054faef889f135cb74"}
template$<$typename ServableType $>$\
Status
[tensorflow::serving::SimpleLoader](#classtensorflow_1_1serving_1_1SimpleLoader)$<$
ServableType $>$::Load,

Fetches any data that needs to be loaded before using the servable
returned by
[servable()](#classtensorflow_1_1serving_1_1SimpleLoader_a914a9107be7cfeb587998934be9d9fee).
May use no more resources than the estimate reported by
[EstimateResources()](#classtensorflow_1_1serving_1_1SimpleLoader_a05ede6c604d05037f59fe13472b48935).

If implementing
[Load()](#classtensorflow_1_1serving_1_1SimpleLoader_ada69d680b17f2e054faef889f135cb74),
you dont have to override
[LoadWithMetadata()](#classtensorflow_1_1serving_1_1SimpleLoader_a4c9a2f88fd1cab8a68ffa69bb9900e24).

Reimplemented from
[tensorflow::serving::Loader](#classtensorflow_1_1serving_1_1Loader_a7dadc89ccbf488aae0102368261cc692).

[\[classtensorflow\_1\_1serving\_1\_1SimpleLoader\_a4c9a2f88fd1cab8a68ffa69bb9900e24\]]{#classtensorflow_1_1serving_1_1SimpleLoader_a4c9a2f88fd1cab8a68ffa69bb9900e24
label="classtensorflow_1_1serving_1_1SimpleLoader_a4c9a2f88fd1cab8a68ffa69bb9900e24"}

template$<$typename ServableType $>$\
Status
[tensorflow::serving::SimpleLoader](#classtensorflow_1_1serving_1_1SimpleLoader)$<$
ServableType $>$::LoadWithMetadata (

metadata

),

Similar to the above method, but takes Metadata as a param, which may be
used by the loader implementation appropriately.

If youre overriding
[LoadWithMetadata()](#classtensorflow_1_1serving_1_1SimpleLoader_a4c9a2f88fd1cab8a68ffa69bb9900e24),
because you can use the metadata appropriately, you can skip overriding
[Load()](#classtensorflow_1_1serving_1_1SimpleLoader_ada69d680b17f2e054faef889f135cb74).

Reimplemented from
[tensorflow::serving::Loader](#classtensorflow_1_1serving_1_1Loader_a7aebd433e4a782265d847e507f3bc824).

[\[classtensorflow\_1\_1serving\_1\_1SimpleLoader\_a914a9107be7cfeb587998934be9d9fee\]]{#classtensorflow_1_1serving_1_1SimpleLoader_a914a9107be7cfeb587998934be9d9fee
label="classtensorflow_1_1serving_1_1SimpleLoader_a914a9107be7cfeb587998934be9d9fee"}

template$<$typename ServableType $>$\
[AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr)
[tensorflow::serving::SimpleLoader](#classtensorflow_1_1serving_1_1SimpleLoader)$<$
ServableType $>$::servable (

), ,

Returns an opaque interface to the underlying servable object. The
caller should know the precise type of the interface in order to make
actual use of it. For example:

CustomLoader implementation:

Serving user request:

ServableHandle&lt;CustomServable\> handle = \... CustomServable\*
servable = handle.get(); servable-\>\...

If
[servable()](#classtensorflow_1_1serving_1_1SimpleLoader_a914a9107be7cfeb587998934be9d9fee)
is called after successful
[Load()](#classtensorflow_1_1serving_1_1SimpleLoader_ada69d680b17f2e054faef889f135cb74)
and before
[Unload()](#classtensorflow_1_1serving_1_1SimpleLoader_ae24b904b3155f039fadd88b1c23e2f82),
it returns a valid, non-null
[AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr) object. If called before
a successful
[Load()](#classtensorflow_1_1serving_1_1SimpleLoader_ada69d680b17f2e054faef889f135cb74)
call or after
[Unload()](#classtensorflow_1_1serving_1_1SimpleLoader_ae24b904b3155f039fadd88b1c23e2f82),
it returns null [AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr).

Implements
[tensorflow::serving::Loader](#classtensorflow_1_1serving_1_1Loader_a640d67dc6ca9926595d29fdfe63868c1).

[\[classtensorflow\_1\_1serving\_1\_1SimpleLoader\_ae24b904b3155f039fadd88b1c23e2f82\]]{#classtensorflow_1_1serving_1_1SimpleLoader_ae24b904b3155f039fadd88b1c23e2f82
label="classtensorflow_1_1serving_1_1SimpleLoader_ae24b904b3155f039fadd88b1c23e2f82"}

template$<$typename ServableType $>$\
void
[tensorflow::serving::SimpleLoader](#classtensorflow_1_1serving_1_1SimpleLoader)$<$
ServableType $>$::Unload (

),

Frees any resources allocated during
[Load()](#classtensorflow_1_1serving_1_1SimpleLoader_ada69d680b17f2e054faef889f135cb74)
(except perhaps for resources shared across servables that are still
needed for other active ones). The loader does not need to return to the
'̈new'̈ state (i.e.
[Load()](#classtensorflow_1_1serving_1_1SimpleLoader_ada69d680b17f2e054faef889f135cb74)
cannot be called after
[Unload()](#classtensorflow_1_1serving_1_1SimpleLoader_ae24b904b3155f039fadd88b1c23e2f82)).

Implements
[tensorflow::serving::Loader](#classtensorflow_1_1serving_1_1Loader_addca8f4264380e5e635bbe1197f5347f).

The documentation for this class was generated from the following file:

tensorflow\_serving/core/simple\_loader.h

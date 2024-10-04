::: {#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader}
:::

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1FakeLoader\]]{#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader
label="classtensorflow_1_1serving_1_1test__util_1_1FakeLoader"}

Inheritance diagram for tensorflow::serving::test\_util::FakeLoader:

![image](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader__inherit__graph.pdf){width="215pt"}

Collaboration diagram for tensorflow::serving::test\_util::FakeLoader:

![image](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader__coll__graph.pdf){width="215pt"}

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1FakeLoader\_a7dca957e589fd4eaaf57fcf05aab62ae\]]{#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_a7dca957e589fd4eaaf57fcf05aab62ae
label="classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_a7dca957e589fd4eaaf57fcf05aab62ae"}
**FakeLoader** (int64\_t
[servable](#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_afd3838612c119a086d1b17ce7cdfb9ed),
const Status load\_status=Status())

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1FakeLoader\_ace387f4f5d2b37245bbb5864c548dd0c\]]{#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_ace387f4f5d2b37245bbb5864c548dd0c
label="classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_ace387f4f5d2b37245bbb5864c548dd0c"}
Status **load\_status** ()

Status
[Load](#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_a2edb74f10db51d582ee689d3d81cacb7)
() override

void
[Unload](#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_a336ea084823272d433d19be25769fc70)
() override

[AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr)
[servable](#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_afd3838612c119a086d1b17ce7cdfb9ed)
() override

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1FakeLoader\_a961505cccbe5ead1572b3ba8a69eb097\]]{#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_a961505cccbe5ead1572b3ba8a69eb097
label="classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_a961505cccbe5ead1572b3ba8a69eb097"}
static int **num\_fake\_loaders** ()

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1FakeLoader\_a27d8493fe0f418b27cdd9949db26ede2\]]{#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_a27d8493fe0f418b27cdd9949db26ede2
label="classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_a27d8493fe0f418b27cdd9949db26ede2"}
static bool **was\_deleted\_in\_this\_thread** ()

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1FakeLoader\_a2edb74f10db51d582ee689d3d81cacb7\]]{#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_a2edb74f10db51d582ee689d3d81cacb7
label="classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_a2edb74f10db51d582ee689d3d81cacb7"}

Status tensorflow::serving::test\_util::FakeLoader::Load (

),

Fetches any data that needs to be loaded before using the servable
returned by
[servable()](#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_afd3838612c119a086d1b17ce7cdfb9ed).
May use no more resources than the estimate reported by
[EstimateResources()](#classtensorflow_1_1serving_1_1ResourceUnsafeLoader_a1a0c1398af9af54032ba16a79a9ecac4).

If implementing
[Load()](#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_a2edb74f10db51d582ee689d3d81cacb7),
you dont have to override
[LoadWithMetadata()](#classtensorflow_1_1serving_1_1Loader_a7aebd433e4a782265d847e507f3bc824).

Reimplemented from
[tensorflow::serving::Loader](#classtensorflow_1_1serving_1_1Loader_a7dadc89ccbf488aae0102368261cc692).

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1FakeLoader\_afd3838612c119a086d1b17ce7cdfb9ed\]]{#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_afd3838612c119a086d1b17ce7cdfb9ed
label="classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_afd3838612c119a086d1b17ce7cdfb9ed"}

[AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr)
tensorflow::serving::test\_util::FakeLoader::servable (

),

Returns an opaque interface to the underlying servable object. The
caller should know the precise type of the interface in order to make
actual use of it. For example:

CustomLoader implementation:

Serving user request:

ServableHandle&lt;CustomServable\> handle = \... CustomServable\*
servable = handle.get(); servable-\>\...

If
[servable()](#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_afd3838612c119a086d1b17ce7cdfb9ed)
is called after successful
[Load()](#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_a2edb74f10db51d582ee689d3d81cacb7)
and before
[Unload()](#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_a336ea084823272d433d19be25769fc70),
it returns a valid, non-null
[AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr) object. If called before
a successful
[Load()](#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_a2edb74f10db51d582ee689d3d81cacb7)
call or after
[Unload()](#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_a336ea084823272d433d19be25769fc70),
it returns null [AnyPtr](#classtensorflow_1_1serving_1_1AnyPtr).

Implements
[tensorflow::serving::Loader](#classtensorflow_1_1serving_1_1Loader_a640d67dc6ca9926595d29fdfe63868c1).

[\[classtensorflow\_1\_1serving\_1\_1test\_\_util\_1\_1FakeLoader\_a336ea084823272d433d19be25769fc70\]]{#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_a336ea084823272d433d19be25769fc70
label="classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_a336ea084823272d433d19be25769fc70"}

void tensorflow::serving::test\_util::FakeLoader::Unload (

),

Frees any resources allocated during
[Load()](#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_a2edb74f10db51d582ee689d3d81cacb7)
(except perhaps for resources shared across servables that are still
needed for other active ones). The loader does not need to return to the
'̈new'̈ state (i.e.
[Load()](#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_a2edb74f10db51d582ee689d3d81cacb7)
cannot be called after
[Unload()](#classtensorflow_1_1serving_1_1test__util_1_1FakeLoader_a336ea084823272d433d19be25769fc70)).

Implements
[tensorflow::serving::Loader](#classtensorflow_1_1serving_1_1Loader_addca8f4264380e5e635bbe1197f5347f).

The documentation for this class was generated from the following files:

tensorflow\_serving/core/test\_util/fake\_loader.h

tensorflow\_serving/core/test\_util/fake\_loader.cc

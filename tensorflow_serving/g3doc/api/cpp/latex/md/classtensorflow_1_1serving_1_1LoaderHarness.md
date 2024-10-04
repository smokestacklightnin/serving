::: {#classtensorflow_1_1serving_1_1LoaderHarness}
:::

[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\]]{#classtensorflow_1_1serving_1_1LoaderHarness
label="classtensorflow_1_1serving_1_1LoaderHarness"}

\#include $<$loader\_harness.h$>$

struct
[Options](#structtensorflow_1_1serving_1_1LoaderHarness_1_1Options)

*[Options](#structtensorflow_1_1serving_1_1LoaderHarness_1_1Options) to
configure a
[LoaderHarness](#classtensorflow_1_1serving_1_1LoaderHarness).*

enum class
[State](#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8)
{
[kNew](#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8aaf1adf7ec3673b4f5765cfbc5d43b7dc)
,
[kLoadRequested](#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8a20bc321c13f15e2546c39d9e0f296dd3)
,
[kLoadApproved](#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8a80697002f1c98b1828669ae672654ff5)
,
[kLoading](#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8aa2c94488cf2076543584c6a3f78556d1)
,
[kReady](#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8a25d5606fe07425ea73f245c48612c039)
,
[kUnloadRequested](#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8a723f4d66c7dcb881700bf57200e52e7d)
,
[kQuiescing](#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8ab872a4b4ff718537f0aee3d06c9f914f)
,
[kQuiesced](#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8aa468d1e1bd9ad8243b7c9d31ac711ed6)
,
[kUnloading](#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8ae4e34ef3f2680339459b2a77aa84fdb8)
,
[kDisabled](#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8a7b04d8795f5fd03c761ce70dab985fee)
,
[kError](#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8ae3587c730cc1aa530fa4ddc9c4204e97)
}

[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a2ed475c3b4a7ede4c00a4e2e34b66cdf\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a2ed475c3b4a7ede4c00a4e2e34b66cdf
label="classtensorflow_1_1serving_1_1LoaderHarness_a2ed475c3b4a7ede4c00a4e2e34b66cdf"}
**LoaderHarness** (const
[ServableId](#structtensorflow_1_1serving_1_1ServableId)
&[id](#classtensorflow_1_1serving_1_1LoaderHarness_ac6581aa3aa10002465c0ffab0b83ab95),
std::unique\_ptr$<$ [Loader](#classtensorflow_1_1serving_1_1Loader) $>$
[loader](#classtensorflow_1_1serving_1_1LoaderHarness_ae0be696227d934efdfc91bd13de4e48a),
const
[Options](#structtensorflow_1_1serving_1_1LoaderHarness_1_1Options)
&options=[Options](#structtensorflow_1_1serving_1_1LoaderHarness_1_1Options)())

template$<$typename T $>$ \
[LoaderHarness](#classtensorflow_1_1serving_1_1LoaderHarness_a7f7ab209922600ef1d95e6be35dec8fd)
(const [ServableId](#structtensorflow_1_1serving_1_1ServableId)
&[id](#classtensorflow_1_1serving_1_1LoaderHarness_ac6581aa3aa10002465c0ffab0b83ab95),
std::unique\_ptr$<$ [Loader](#classtensorflow_1_1serving_1_1Loader) $>$
[loader](#classtensorflow_1_1serving_1_1LoaderHarness_ae0be696227d934efdfc91bd13de4e48a),
std::unique\_ptr$<$ T $>$
[additional\_state](#classtensorflow_1_1serving_1_1LoaderHarness_a2a5bfd26e4b27de0e59a9dea68315a84),
const
[Options](#structtensorflow_1_1serving_1_1LoaderHarness_1_1Options)
&options=[Options](#structtensorflow_1_1serving_1_1LoaderHarness_1_1Options)())

[$\sim$LoaderHarness](#classtensorflow_1_1serving_1_1LoaderHarness_a60facd158c858dbdcaaae74a18a4edd9)
()

[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_ac6581aa3aa10002465c0ffab0b83ab95\]]{#classtensorflow_1_1serving_1_1LoaderHarness_ac6581aa3aa10002465c0ffab0b83ab95
label="classtensorflow_1_1serving_1_1LoaderHarness_ac6581aa3aa10002465c0ffab0b83ab95"}
[ServableId](#structtensorflow_1_1serving_1_1ServableId)
[id](#classtensorflow_1_1serving_1_1LoaderHarness_ac6581aa3aa10002465c0ffab0b83ab95)
() const

*Returns the identifier of underlying
[Servable](#classtensorflow_1_1serving_1_1Servable).*

[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a5ba7d4fb6a28bbfeb94d42cfa81bd95f\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a5ba7d4fb6a28bbfeb94d42cfa81bd95f
label="classtensorflow_1_1serving_1_1LoaderHarness_a5ba7d4fb6a28bbfeb94d42cfa81bd95f"}
[State](#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8)
[state](#classtensorflow_1_1serving_1_1LoaderHarness_a5ba7d4fb6a28bbfeb94d42cfa81bd95f)
() const TF\_LOCKS\_EXCLUDED(mu\_)

*Returns the current state of underlying
[Servable](#classtensorflow_1_1serving_1_1Servable).*

[Loader](#classtensorflow_1_1serving_1_1Loader) $\ast$
[loader](#classtensorflow_1_1serving_1_1LoaderHarness_ae0be696227d934efdfc91bd13de4e48a)
() const

[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_af4ed9d7690c7bd8907cc35f8f0343fd5\]]{#classtensorflow_1_1serving_1_1LoaderHarness_af4ed9d7690c7bd8907cc35f8f0343fd5
label="classtensorflow_1_1serving_1_1LoaderHarness_af4ed9d7690c7bd8907cc35f8f0343fd5"}
template$<$typename T = std::nullptr\_t$>$ \
[ServableStateSnapshot](#structtensorflow_1_1serving_1_1ServableStateSnapshot)$<$
T $>$
[loader\_state\_snapshot](#classtensorflow_1_1serving_1_1LoaderHarness_af4ed9d7690c7bd8907cc35f8f0343fd5)
() const TF\_LOCKS\_EXCLUDED(mu\_)

*Returns the current overall state snapshot of the underlying
[Servable](#classtensorflow_1_1serving_1_1Servable).*

Status
[LoadRequested](#classtensorflow_1_1serving_1_1LoaderHarness_af38723eb75813331dad2f0d910466f57)
() TF\_LOCKS\_EXCLUDED(mu\_)

Status
[LoadApproved](#classtensorflow_1_1serving_1_1LoaderHarness_aab4e0158cc9fccd7539df5a9fa312e8c)
() TF\_LOCKS\_EXCLUDED(mu\_)

Status
[Load](#classtensorflow_1_1serving_1_1LoaderHarness_af7e5a0ecbec71342dcb2aa9764d0604e)
() TF\_LOCKS\_EXCLUDED(mu\_)

Status
[UnloadRequested](#classtensorflow_1_1serving_1_1LoaderHarness_a6451e73c25ba30b0c78a560deba29e03)
() TF\_LOCKS\_EXCLUDED(mu\_)

void
[set\_should\_retry](#classtensorflow_1_1serving_1_1LoaderHarness_a001ec617f6fd186d27cc911f9a952f00)
(std::function$<$ bool(absl::Status)$>$
[should\_retry](#classtensorflow_1_1serving_1_1LoaderHarness_ae344a05f0ae81c0f589daaa737223435))
TF\_LOCKS\_EXCLUDED(mu\_)

[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_ae344a05f0ae81c0f589daaa737223435\]]{#classtensorflow_1_1serving_1_1LoaderHarness_ae344a05f0ae81c0f589daaa737223435
label="classtensorflow_1_1serving_1_1LoaderHarness_ae344a05f0ae81c0f589daaa737223435"}
bool
[should\_retry](#classtensorflow_1_1serving_1_1LoaderHarness_ae344a05f0ae81c0f589daaa737223435)
(absl::Status
[status](#classtensorflow_1_1serving_1_1LoaderHarness_afb34eca424243aacbf71f466d4ec99ef))
TF\_LOCKS\_EXCLUDED(mu\_)

*Returns true if the servable should be retried.*

Status
[Unload](#classtensorflow_1_1serving_1_1LoaderHarness_a5c131cef32324cd2ec6b22fc4dd92942)
() TF\_LOCKS\_EXCLUDED(mu\_)

Status
[StartQuiescing](#classtensorflow_1_1serving_1_1LoaderHarness_a811f9dbe7ab8fb5df0c35916ec57aad8)
() TF\_LOCKS\_EXCLUDED(mu\_)

Status
[DoneQuiescing](#classtensorflow_1_1serving_1_1LoaderHarness_a11b81e561e55c5b21907f8fc2eafe6e9)
() TF\_LOCKS\_EXCLUDED(mu\_)

[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a9833ae8f23545a9975901d8a3508d30a\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a9833ae8f23545a9975901d8a3508d30a
label="classtensorflow_1_1serving_1_1LoaderHarness_a9833ae8f23545a9975901d8a3508d30a"}
void
[Error](#classtensorflow_1_1serving_1_1LoaderHarness_a9833ae8f23545a9975901d8a3508d30a)
(const Status
&[status](#classtensorflow_1_1serving_1_1LoaderHarness_afb34eca424243aacbf71f466d4ec99ef))
TF\_LOCKS\_EXCLUDED(mu\_)

*Transitions the state to kError and invokes options\_.error\_callback.*

Status
[status](#classtensorflow_1_1serving_1_1LoaderHarness_afb34eca424243aacbf71f466d4ec99ef)
() const TF\_LOCKS\_EXCLUDED(mu\_)

template$<$typename T $>$ \
T $\ast$
[additional\_state](#classtensorflow_1_1serving_1_1LoaderHarness_a2a5bfd26e4b27de0e59a9dea68315a84)
()

[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a9c74459525e232eb6a03f4a7a0b9cfb2\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a9c74459525e232eb6a03f4a7a0b9cfb2
label="classtensorflow_1_1serving_1_1LoaderHarness_a9c74459525e232eb6a03f4a7a0b9cfb2"}
template$<$$>$
[ServableStateSnapshot](#structtensorflow_1_1serving_1_1ServableStateSnapshot)$<$
std::nullptr\_t $>$ **loader\_state\_snapshot** () const

[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a890bb1c1568cae9d58cfe9f750c6c499\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a890bb1c1568cae9d58cfe9f750c6c499
label="classtensorflow_1_1serving_1_1LoaderHarness_a890bb1c1568cae9d58cfe9f750c6c499"}
static string **StateDebugString**
([State](#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8)
[state](#classtensorflow_1_1serving_1_1LoaderHarness_a5ba7d4fb6a28bbfeb94d42cfa81bd95f))

[LoaderHarness](#classtensorflow_1_1serving_1_1LoaderHarness) is a
widget the [Manager](#classtensorflow_1_1serving_1_1Manager) uses to
hold on to and talk to a [Loader](#classtensorflow_1_1serving_1_1Loader)
while it owns it. It tracks the overall state of a
[Servable](#classtensorflow_1_1serving_1_1Servable) such that
[Manager](#classtensorflow_1_1serving_1_1Manager) can determine which
state transitions to make at what times.

A manager implementation can also add some additional state with each
harness. For example, a manager could put ACL or lifecycle metadata
here. The ownership is maintained by the harness.

This class is thread-safe.

[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a9552eba3f9f1ca631c218befd9e686f8\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8
label="classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8"}
enum
[tensorflow::serving::LoaderHarness::State](#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8)

State of the underlying servable, from the perspective of the
[LoaderHarness](#classtensorflow_1_1serving_1_1LoaderHarness) and for
the purpose of communication between it and a
[Manager](#classtensorflow_1_1serving_1_1Manager). Not equivalent to the
semantic servable states in
[servable\_state.h](#servable__state_8h_source).

Valid transitions:
kNew\--$>$kLoading\--$>$kReady\--$>$kQuiescing\--$>$kQuiesced\--$>$kUnloading\--$>$kDisabled
as well as: any\_state\--$>$kError.

Enumerator
\[0pt\]\[0pt\][\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a9552eba3f9f1ca631c218befd9e686f8aaf1adf7ec3673b4f5765cfbc5d43b7dc\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8aaf1adf7ec3673b4f5765cfbc5d43b7dc
label="classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8aaf1adf7ec3673b4f5765cfbc5d43b7dc"}
kNew&Initial state.\

\[0pt\]\[0pt\][\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a9552eba3f9f1ca631c218befd9e686f8a20bc321c13f15e2546c39d9e0f296dd3\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8a20bc321c13f15e2546c39d9e0f296dd3
label="classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8a20bc321c13f15e2546c39d9e0f296dd3"}
kLoadRequested&The manager has been requested to load this servable.\

\[0pt\]\[0pt\][\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a9552eba3f9f1ca631c218befd9e686f8a80697002f1c98b1828669ae672654ff5\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8a80697002f1c98b1828669ae672654ff5
label="classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8a80697002f1c98b1828669ae672654ff5"}
kLoadApproved&The servable has been approved for loading, e.g. resources
have been set aside for it.\

\[0pt\]\[0pt\][\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a9552eba3f9f1ca631c218befd9e686f8aa2c94488cf2076543584c6a3f78556d1\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8aa2c94488cf2076543584c6a3f78556d1
label="classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8aa2c94488cf2076543584c6a3f78556d1"}
kLoading&loader\_-$>$[Load()](#classtensorflow_1_1serving_1_1LoaderHarness_af7e5a0ecbec71342dcb2aa9764d0604e)
has been called.\

\[0pt\]\[0pt\][\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a9552eba3f9f1ca631c218befd9e686f8a25d5606fe07425ea73f245c48612c039\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8a25d5606fe07425ea73f245c48612c039
label="classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8a25d5606fe07425ea73f245c48612c039"}
kReady&loader\_-$>$[Load()](#classtensorflow_1_1serving_1_1LoaderHarness_af7e5a0ecbec71342dcb2aa9764d0604e)
has succeeded.\

\[0pt\]\[0pt\][\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a9552eba3f9f1ca631c218befd9e686f8a723f4d66c7dcb881700bf57200e52e7d\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8a723f4d66c7dcb881700bf57200e52e7d
label="classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8a723f4d66c7dcb881700bf57200e52e7d"}
kUnloadRequested&The manager has been requested to unload this
servable.\

\[0pt\]\[0pt\][\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a9552eba3f9f1ca631c218befd9e686f8ab872a4b4ff718537f0aee3d06c9f914f\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8ab872a4b4ff718537f0aee3d06c9f914f
label="classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8ab872a4b4ff718537f0aee3d06c9f914f"}
kQuiescing&The servable is going to be made unavailable for serving.\

\[0pt\]\[0pt\][\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a9552eba3f9f1ca631c218befd9e686f8aa468d1e1bd9ad8243b7c9d31ac711ed6\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8aa468d1e1bd9ad8243b7c9d31ac711ed6
label="classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8aa468d1e1bd9ad8243b7c9d31ac711ed6"}
kQuiesced&The servable has been made unavailable for serving.\

\[0pt\]\[0pt\][\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a9552eba3f9f1ca631c218befd9e686f8ae4e34ef3f2680339459b2a77aa84fdb8\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8ae4e34ef3f2680339459b2a77aa84fdb8
label="classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8ae4e34ef3f2680339459b2a77aa84fdb8"}
kUnloading&loader\_-$>$[Unload()](#classtensorflow_1_1serving_1_1LoaderHarness_a5c131cef32324cd2ec6b22fc4dd92942)
has been called.\

\[0pt\]\[0pt\][\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a9552eba3f9f1ca631c218befd9e686f8a7b04d8795f5fd03c761ce70dab985fee\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8a7b04d8795f5fd03c761ce70dab985fee
label="classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8a7b04d8795f5fd03c761ce70dab985fee"}
kDisabled&loader\_-$>$[Unload()](#classtensorflow_1_1serving_1_1LoaderHarness_a5c131cef32324cd2ec6b22fc4dd92942)
has finished.\

\[0pt\]\[0pt\][\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a9552eba3f9f1ca631c218befd9e686f8ae3587c730cc1aa530fa4ddc9c4204e97\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8ae3587c730cc1aa530fa4ddc9c4204e97
label="classtensorflow_1_1serving_1_1LoaderHarness_a9552eba3f9f1ca631c218befd9e686f8ae3587c730cc1aa530fa4ddc9c4204e97"}
kError&An error has occurred, either during
loader\_-$>$[Load()](#classtensorflow_1_1serving_1_1LoaderHarness_af7e5a0ecbec71342dcb2aa9764d0604e)
or outside of the harness (and was reported to the harness via a call to
[Error()](#classtensorflow_1_1serving_1_1LoaderHarness_a9833ae8f23545a9975901d8a3508d30a)).\

[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a7f7ab209922600ef1d95e6be35dec8fd\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a7f7ab209922600ef1d95e6be35dec8fd
label="classtensorflow_1_1serving_1_1LoaderHarness_a7f7ab209922600ef1d95e6be35dec8fd"}

template$<$typename T $>$\
tensorflow::serving::LoaderHarness::LoaderHarness (

id,

loader,

additional\_state,

options =
[Options](#structtensorflow_1_1serving_1_1LoaderHarness_1_1Options)()

)

Constructor to create a harness with additional state, which a manager
needs.
[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a60facd158c858dbdcaaae74a18a4edd9\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a60facd158c858dbdcaaae74a18a4edd9
label="classtensorflow_1_1serving_1_1LoaderHarness_a60facd158c858dbdcaaae74a18a4edd9"}

tensorflow::serving::LoaderHarness::$\sim$LoaderHarness (

)

Legal to destruct iff current state is one of kNew, kDisabled or kError.
Check-fails if violated.

[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a2a5bfd26e4b27de0e59a9dea68315a84\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a2a5bfd26e4b27de0e59a9dea68315a84
label="classtensorflow_1_1serving_1_1LoaderHarness_a2a5bfd26e4b27de0e59a9dea68315a84"}

template$<$typename T $>$\
T$\ast$ tensorflow::serving::LoaderHarness::additional\_state (

)

Gets the additional state. Returns nullptr if the type mismatches or if
it wasnt set.
[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a11b81e561e55c5b21907f8fc2eafe6e9\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a11b81e561e55c5b21907f8fc2eafe6e9
label="classtensorflow_1_1serving_1_1LoaderHarness_a11b81e561e55c5b21907f8fc2eafe6e9"}

Status tensorflow::serving::LoaderHarness::DoneQuiescing (

)

Transitions the state to kQuiesced, which means that there are no more
live handles to this servable available in the frontend. At this point,
we can unload this object.

REQUIRES: State is kQuiescing when called. Otherwise DCHECK-fails,
transitions to state kError and invokes options\_.error\_callback.
[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_af7e5a0ecbec71342dcb2aa9764d0604e\]]{#classtensorflow_1_1serving_1_1LoaderHarness_af7e5a0ecbec71342dcb2aa9764d0604e
label="classtensorflow_1_1serving_1_1LoaderHarness_af7e5a0ecbec71342dcb2aa9764d0604e"}

Status tensorflow::serving::LoaderHarness::Load (

)

Transitions to kLoading, delegates to Servable::Load(), then transitions
either to kReady if
[Load()](#classtensorflow_1_1serving_1_1LoaderHarness_af7e5a0ecbec71342dcb2aa9764d0604e)
succeeds, or to kError (and invokes options\_. error\_callback) if
[Load()](#classtensorflow_1_1serving_1_1LoaderHarness_af7e5a0ecbec71342dcb2aa9764d0604e)
fails. This call may take a long time.

We retry the Servable::Load() according to the options set during
construction of this class. We stop retrying and give up if 1. we have
reached max\_num\_load\_retries or, 2. if cancel\_load() is set to true.

REQUIRES: State is kLoadApproved when called. Otherwise DCHECK-fails,
transitions to state kError and invokes options\_.error\_callback.
[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_aab4e0158cc9fccd7539df5a9fa312e8c\]]{#classtensorflow_1_1serving_1_1LoaderHarness_aab4e0158cc9fccd7539df5a9fa312e8c
label="classtensorflow_1_1serving_1_1LoaderHarness_aab4e0158cc9fccd7539df5a9fa312e8c"}

Status tensorflow::serving::LoaderHarness::LoadApproved (

)

Transitions to kLoadApproved.

REQUIRES: State is kLoadRequested when called. Otherwise DCHECK-fails,
transitions to state kError and invokes options\_.error\_callback.
[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_ae0be696227d934efdfc91bd13de4e48a\]]{#classtensorflow_1_1serving_1_1LoaderHarness_ae0be696227d934efdfc91bd13de4e48a
label="classtensorflow_1_1serving_1_1LoaderHarness_ae0be696227d934efdfc91bd13de4e48a"}

[Loader](#classtensorflow_1_1serving_1_1Loader)$\ast$
tensorflow::serving::LoaderHarness::loader (

) const

Returns a pointer to the wrapped loader. Ownership remains with this
class.
[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_af38723eb75813331dad2f0d910466f57\]]{#classtensorflow_1_1serving_1_1LoaderHarness_af38723eb75813331dad2f0d910466f57
label="classtensorflow_1_1serving_1_1LoaderHarness_af38723eb75813331dad2f0d910466f57"}

Status tensorflow::serving::LoaderHarness::LoadRequested (

)

Transitions the state of the harness to kLoadRequested iff its current
state is kNew. The test-and-change is done transactionally, so this
method can be used to ensure that at most one
[Load()](#classtensorflow_1_1serving_1_1LoaderHarness_af7e5a0ecbec71342dcb2aa9764d0604e)
request can proceed.
[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a001ec617f6fd186d27cc911f9a952f00\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a001ec617f6fd186d27cc911f9a952f00
label="classtensorflow_1_1serving_1_1LoaderHarness_a001ec617f6fd186d27cc911f9a952f00"}

void tensorflow::serving::LoaderHarness::set\_should\_retry (

should\_retry

)

Sets the retry behavior for the servable using a function which accepts
the status of the last load attempt and returns a boolean. If the
boolean is false, we cancel the next retry. This is best-effort, and
does not preempt a
[Load()](#classtensorflow_1_1serving_1_1LoaderHarness_af7e5a0ecbec71342dcb2aa9764d0604e)
which is already happening, only subsequent calls.

If the retries are cancelled, the servable goes into a state dependent
on the last
[Load()](#classtensorflow_1_1serving_1_1LoaderHarness_af7e5a0ecbec71342dcb2aa9764d0604e)
called on it. If the last
[Load()](#classtensorflow_1_1serving_1_1LoaderHarness_af7e5a0ecbec71342dcb2aa9764d0604e)
was successful, it will be in state kReady, else in kError.
[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a811f9dbe7ab8fb5df0c35916ec57aad8\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a811f9dbe7ab8fb5df0c35916ec57aad8
label="classtensorflow_1_1serving_1_1LoaderHarness_a811f9dbe7ab8fb5df0c35916ec57aad8"}

Status tensorflow::serving::LoaderHarness::StartQuiescing (

)

Transitions the state to kQuiescing, which means that we would like to
not give out any more handles to this servable.

REQUIRES: State is kUnloadRequested when called. Otherwise DCHECK-fails,
transitions to state kError and invokes options\_.error\_callback.
[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_afb34eca424243aacbf71f466d4ec99ef\]]{#classtensorflow_1_1serving_1_1LoaderHarness_afb34eca424243aacbf71f466d4ec99ef
label="classtensorflow_1_1serving_1_1LoaderHarness_afb34eca424243aacbf71f466d4ec99ef"}

Status tensorflow::serving::LoaderHarness::status (

) const

Whether anything has gone wrong with this servable. If state is kError,
this will be non-OK. If not OK, the error could be something that
occurred in a [Source](#classtensorflow_1_1serving_1_1Source) or
[SourceAdapter](#classtensorflow_1_1serving_1_1SourceAdapter), in the
[Loader](#classtensorflow_1_1serving_1_1Loader), in the
[Manager](#classtensorflow_1_1serving_1_1Manager), or elsewhere. All
errors pertaining to the servable are reported here, regardless of
origin.
[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a5c131cef32324cd2ec6b22fc4dd92942\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a5c131cef32324cd2ec6b22fc4dd92942
label="classtensorflow_1_1serving_1_1LoaderHarness_a5c131cef32324cd2ec6b22fc4dd92942"}

Status tensorflow::serving::LoaderHarness::Unload (

)

Transitions to kUnloading, delegates to Servable::Unload(), then
transitions to kDisabled when
[Unload()](#classtensorflow_1_1serving_1_1LoaderHarness_a5c131cef32324cd2ec6b22fc4dd92942)
is done.

REQUIRES: State is kQuiesced when called. Otherwise DCHECK-fails,
transitions to state kError and invokes options\_.error\_callback.
[\[classtensorflow\_1\_1serving\_1\_1LoaderHarness\_a6451e73c25ba30b0c78a560deba29e03\]]{#classtensorflow_1_1serving_1_1LoaderHarness_a6451e73c25ba30b0c78a560deba29e03
label="classtensorflow_1_1serving_1_1LoaderHarness_a6451e73c25ba30b0c78a560deba29e03"}

Status tensorflow::serving::LoaderHarness::UnloadRequested (

)

Transitions the state of the harness to kUnloadRequested iff its current
state is kReady. The test-and-change is done transactionally, so this
method can be used to ensure that at most one
[Load()](#classtensorflow_1_1serving_1_1LoaderHarness_af7e5a0ecbec71342dcb2aa9764d0604e)
request can proceed.

The documentation for this class was generated from the following files:

tensorflow\_serving/core/loader\_harness.h

tensorflow\_serving/core/loader\_harness.cc

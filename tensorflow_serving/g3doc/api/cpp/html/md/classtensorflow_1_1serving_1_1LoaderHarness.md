::: {#top}
::: {#titlearea}
+-----------------------------------------------------------------------+
| ::: {#projectname}                                                    |
| My Project                                                            |
| :::                                                                   |
+-----------------------------------------------------------------------+
:::

::: {#main-nav}
:::

::: {#MSearchSelectWindow onmouseover="return searchBox.OnSearchSelectShow()" onmouseout="return searchBox.OnSearchSelectHide()" onkeydown="return searchBox.OnSearchSelectKey(event)"}
:::

::: {#MSearchResultsWindow}
:::

::: {#nav-path .navpath}
-   **tensorflow**
-   **serving**
-   [LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Classes](#nested-classes) \| [Public Types](#pub-types) \| [Public
Member Functions](#pub-methods) \| [Static Public Member
Functions](#pub-static-methods) \| [List of all
members](classtensorflow_1_1serving_1_1LoaderHarness-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::LoaderHarness Class
Reference[[final]{.mlabel}]{.mlabels}
:::
:::
:::

::: {.contents}
`#include <loader_harness.h>`

[]{#nested-classes} Classes {#classes .groupheader}
---------------------------
:::

struct  

[Options](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html){.el}

 

[Options](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html "Options to configure a LoaderHarness."){.el}
to configure a
[LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}.
[More\...](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html#details)\

 

[]{#pub-types} Public Types {#public-types .groupheader}
---------------------------

enum class  

[State](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8){.el}
{\
  [kNew](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8aaf1adf7ec3673b4f5765cfbc5d43b7dc){.el}
,
[kLoadRequested](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8a20bc321c13f15e2546c39d9e0f296dd3){.el}
,
[kLoadApproved](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8a80697002f1c98b1828669ae672654ff5){.el}
,
[kLoading](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8aa2c94488cf2076543584c6a3f78556d1){.el}
,\
  [kReady](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8a25d5606fe07425ea73f245c48612c039){.el}
,
[kUnloadRequested](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8a723f4d66c7dcb881700bf57200e52e7d){.el}
,
[kQuiescing](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8ab872a4b4ff718537f0aee3d06c9f914f){.el}
,
[kQuiesced](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8aa468d1e1bd9ad8243b7c9d31ac711ed6){.el}
,\
  [kUnloading](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8ae4e34ef3f2680339459b2a77aa84fdb8){.el}
,
[kDisabled](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8a7b04d8795f5fd03c761ce70dab985fee){.el}
,
[kError](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8ae3587c730cc1aa530fa4ddc9c4204e97){.el}\
}

 

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------

[]{#a2ed475c3b4a7ede4c00a4e2e34b66cdf}  

**LoaderHarness** (const
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el}
&[id](classtensorflow_1_1serving_1_1LoaderHarness.html#ac6581aa3aa10002465c0ffab0b83ab95){.el},
std::unique\_ptr\<
[Loader](classtensorflow_1_1serving_1_1Loader.html){.el} \>
[loader](classtensorflow_1_1serving_1_1LoaderHarness.html#ae0be696227d934efdfc91bd13de4e48a){.el},
const
[Options](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html){.el}
&options=[Options](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html){.el}())

 

template\<typename T \>

 

[LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html#a7f7ab209922600ef1d95e6be35dec8fd){.el}
(const [ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el}
&[id](classtensorflow_1_1serving_1_1LoaderHarness.html#ac6581aa3aa10002465c0ffab0b83ab95){.el},
std::unique\_ptr\<
[Loader](classtensorflow_1_1serving_1_1Loader.html){.el} \>
[loader](classtensorflow_1_1serving_1_1LoaderHarness.html#ae0be696227d934efdfc91bd13de4e48a){.el},
std::unique\_ptr\< T \>
[additional\_state](classtensorflow_1_1serving_1_1LoaderHarness.html#a2a5bfd26e4b27de0e59a9dea68315a84){.el},
const
[Options](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html){.el}
&options=[Options](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html){.el}())

 

 

[\~LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html#a60facd158c858dbdcaaae74a18a4edd9){.el}
()

 

[]{#ac6581aa3aa10002465c0ffab0b83ab95}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el} 

[id](classtensorflow_1_1serving_1_1LoaderHarness.html#ac6581aa3aa10002465c0ffab0b83ab95){.el}
() const

 

Returns the identifier of underlying
[Servable](classtensorflow_1_1serving_1_1Servable.html){.el}.\

 

[]{#a5ba7d4fb6a28bbfeb94d42cfa81bd95f}
[State](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8){.el} 

[state](classtensorflow_1_1serving_1_1LoaderHarness.html#a5ba7d4fb6a28bbfeb94d42cfa81bd95f){.el}
() const TF\_LOCKS\_EXCLUDED(mu\_)

 

Returns the current state of underlying
[Servable](classtensorflow_1_1serving_1_1Servable.html){.el}.\

 

[Loader](classtensorflow_1_1serving_1_1Loader.html){.el} \* 

[loader](classtensorflow_1_1serving_1_1LoaderHarness.html#ae0be696227d934efdfc91bd13de4e48a){.el}
() const

 

[]{#af4ed9d7690c7bd8907cc35f8f0343fd5} template\<typename T =
std::nullptr\_t\>

[ServableStateSnapshot](structtensorflow_1_1serving_1_1ServableStateSnapshot.html){.el}\<
T \> 

[loader\_state\_snapshot](classtensorflow_1_1serving_1_1LoaderHarness.html#af4ed9d7690c7bd8907cc35f8f0343fd5){.el}
() const TF\_LOCKS\_EXCLUDED(mu\_)

 

Returns the current overall state snapshot of the underlying
[Servable](classtensorflow_1_1serving_1_1Servable.html){.el}.\

 

Status 

[LoadRequested](classtensorflow_1_1serving_1_1LoaderHarness.html#af38723eb75813331dad2f0d910466f57){.el}
() TF\_LOCKS\_EXCLUDED(mu\_)

 

Status 

[LoadApproved](classtensorflow_1_1serving_1_1LoaderHarness.html#aab4e0158cc9fccd7539df5a9fa312e8c){.el}
() TF\_LOCKS\_EXCLUDED(mu\_)

 

Status 

[Load](classtensorflow_1_1serving_1_1LoaderHarness.html#af7e5a0ecbec71342dcb2aa9764d0604e){.el}
() TF\_LOCKS\_EXCLUDED(mu\_)

 

Status 

[UnloadRequested](classtensorflow_1_1serving_1_1LoaderHarness.html#a6451e73c25ba30b0c78a560deba29e03){.el}
() TF\_LOCKS\_EXCLUDED(mu\_)

 

void 

[set\_should\_retry](classtensorflow_1_1serving_1_1LoaderHarness.html#a001ec617f6fd186d27cc911f9a952f00){.el}
(std::function\< bool(absl::Status)\>
[should\_retry](classtensorflow_1_1serving_1_1LoaderHarness.html#ae344a05f0ae81c0f589daaa737223435){.el})
TF\_LOCKS\_EXCLUDED(mu\_)

 

[]{#ae344a05f0ae81c0f589daaa737223435} bool 

[should\_retry](classtensorflow_1_1serving_1_1LoaderHarness.html#ae344a05f0ae81c0f589daaa737223435){.el}
(absl::Status
[status](classtensorflow_1_1serving_1_1LoaderHarness.html#afb34eca424243aacbf71f466d4ec99ef){.el})
TF\_LOCKS\_EXCLUDED(mu\_)

 

Returns true if the servable should be retried.\

 

Status 

[Unload](classtensorflow_1_1serving_1_1LoaderHarness.html#a5c131cef32324cd2ec6b22fc4dd92942){.el}
() TF\_LOCKS\_EXCLUDED(mu\_)

 

Status 

[StartQuiescing](classtensorflow_1_1serving_1_1LoaderHarness.html#a811f9dbe7ab8fb5df0c35916ec57aad8){.el}
() TF\_LOCKS\_EXCLUDED(mu\_)

 

Status 

[DoneQuiescing](classtensorflow_1_1serving_1_1LoaderHarness.html#a11b81e561e55c5b21907f8fc2eafe6e9){.el}
() TF\_LOCKS\_EXCLUDED(mu\_)

 

[]{#a9833ae8f23545a9975901d8a3508d30a} void 

[Error](classtensorflow_1_1serving_1_1LoaderHarness.html#a9833ae8f23545a9975901d8a3508d30a){.el}
(const Status
&[status](classtensorflow_1_1serving_1_1LoaderHarness.html#afb34eca424243aacbf71f466d4ec99ef){.el})
TF\_LOCKS\_EXCLUDED(mu\_)

 

Transitions the state to kError and invokes
\'options\_.error\_callback\'.\

 

Status 

[status](classtensorflow_1_1serving_1_1LoaderHarness.html#afb34eca424243aacbf71f466d4ec99ef){.el}
() const TF\_LOCKS\_EXCLUDED(mu\_)

 

template\<typename T \>

T \* 

[additional\_state](classtensorflow_1_1serving_1_1LoaderHarness.html#a2a5bfd26e4b27de0e59a9dea68315a84){.el}
()

 

[]{#a9c74459525e232eb6a03f4a7a0b9cfb2} template\<\>

[ServableStateSnapshot](structtensorflow_1_1serving_1_1ServableStateSnapshot.html){.el}\<
std::nullptr\_t \> 

**loader\_state\_snapshot** () const

 

[]{#pub-static-methods} Static Public Member Functions {#static-public-member-functions .groupheader}
------------------------------------------------------

[]{#a890bb1c1568cae9d58cfe9f750c6c499} static string 

**StateDebugString**
([State](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8){.el}
[state](classtensorflow_1_1serving_1_1LoaderHarness.html#a5ba7d4fb6a28bbfeb94d42cfa81bd95f){.el})

 

[]{#details}

Detailed Description {#detailed-description .groupheader}
--------------------

::: {.textblock}
[LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}
is a widget the
[Manager](classtensorflow_1_1serving_1_1Manager.html){.el} uses to hold
on to and talk to a
[Loader](classtensorflow_1_1serving_1_1Loader.html){.el} while it owns
it. It tracks the overall state of a
[Servable](classtensorflow_1_1serving_1_1Servable.html){.el} such that
[Manager](classtensorflow_1_1serving_1_1Manager.html){.el} can determine
which state transitions to make at what times.

A manager implementation can also add some additional state with each
harness. For example, a manager could put ACL or lifecycle metadata
here. The ownership is maintained by the harness.

This class is thread-safe.
:::

Member Enumeration Documentation {#member-enumeration-documentation .groupheader}
--------------------------------

[]{#a9552eba3f9f1ca631c218befd9e686f8}

[[◆ ](#a9552eba3f9f1ca631c218befd9e686f8)]{.permalink}State {#state .memtitle}
-----------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   -------                         | [[strong]{.mlabel}]{.mlabels}     |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
|   enum                            |                                   |
| [tensorflow::serving::LoaderHarne |                                   |
| ss::State](classtensorflow_1_1ser |                                   |
| ving_1_1LoaderHarness.html#a9552e |                                   |
| ba3f9f1ca631c218befd9e686f8){.el} |                                   |
|   -------                         |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
State of the underlying servable, from the perspective of the
[LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.el}
and for the purpose of communication between it and a
[Manager](classtensorflow_1_1serving_1_1Manager.html){.el}. Not
equivalent to the semantic servable states in
[servable\_state.h](servable__state_8h_source.html){.el}.

Valid transitions:
kNew\--\>kLoading\--\>kReady\--\>kQuiescing\--\>kQuiesced\--\>kUnloading\--\>kDisabled
as well as: any\_state\--\>kError.

Enumerator
:::
:::

[]{#a9552eba3f9f1ca631c218befd9e686f8aaf1adf7ec3673b4f5765cfbc5d43b7dc}kNew 

Initial state.

[]{#a9552eba3f9f1ca631c218befd9e686f8a20bc321c13f15e2546c39d9e0f296dd3}kLoadRequested 

The manager has been requested to load this servable.

[]{#a9552eba3f9f1ca631c218befd9e686f8a80697002f1c98b1828669ae672654ff5}kLoadApproved 

The servable has been approved for loading, e.g. resources have been set
aside for it.

[]{#a9552eba3f9f1ca631c218befd9e686f8aa2c94488cf2076543584c6a3f78556d1}kLoading 

\'loader\_-\>[Load()](classtensorflow_1_1serving_1_1LoaderHarness.html#af7e5a0ecbec71342dcb2aa9764d0604e){.el}\'
has been called.

[]{#a9552eba3f9f1ca631c218befd9e686f8a25d5606fe07425ea73f245c48612c039}kReady 

\'loader\_-\>[Load()](classtensorflow_1_1serving_1_1LoaderHarness.html#af7e5a0ecbec71342dcb2aa9764d0604e){.el}\'
has succeeded.

[]{#a9552eba3f9f1ca631c218befd9e686f8a723f4d66c7dcb881700bf57200e52e7d}kUnloadRequested 

The manager has been requested to unload this servable.

[]{#a9552eba3f9f1ca631c218befd9e686f8ab872a4b4ff718537f0aee3d06c9f914f}kQuiescing 

The servable is going to be made unavailable for serving.

[]{#a9552eba3f9f1ca631c218befd9e686f8aa468d1e1bd9ad8243b7c9d31ac711ed6}kQuiesced 

The servable has been made unavailable for serving.

[]{#a9552eba3f9f1ca631c218befd9e686f8ae4e34ef3f2680339459b2a77aa84fdb8}kUnloading 

\'loader\_-\>[Unload()](classtensorflow_1_1serving_1_1LoaderHarness.html#a5c131cef32324cd2ec6b22fc4dd92942){.el}\'
has been called.

[]{#a9552eba3f9f1ca631c218befd9e686f8a7b04d8795f5fd03c761ce70dab985fee}kDisabled 

\'loader\_-\>[Unload()](classtensorflow_1_1serving_1_1LoaderHarness.html#a5c131cef32324cd2ec6b22fc4dd92942){.el}\'
has finished.

[]{#a9552eba3f9f1ca631c218befd9e686f8ae3587c730cc1aa530fa4ddc9c4204e97}kError 

An error has occurred, either during
\'loader\_-\>[Load()](classtensorflow_1_1serving_1_1LoaderHarness.html#af7e5a0ecbec71342dcb2aa9764d0604e){.el}\'
or outside of the harness (and was reported to the harness via a call to
[Error()](classtensorflow_1_1serving_1_1LoaderHarness.html#a9833ae8f23545a9975901d8a3508d30a "Transitions the state to kError and invokes 'options_.error_callback'."){.el}).

Constructor & Destructor Documentation {#constructor-destructor-documentation .groupheader}
--------------------------------------

[]{#a7f7ab209922600ef1d95e6be35dec8fd}

[[◆ ](#a7f7ab209922600ef1d95e6be35dec8fd)]{.permalink}LoaderHarness() {#loaderharness .memtitle}
---------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
::: {.memtemplate}
template\<typename T \>
:::

+-----------------------------------+-----------------------------------+
|   -----                           | [[inline]{.mlabel}]{.mlabels}     |
| --------------------------------- |                                   |
| ------------- --- --------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------ -------------------------- |                                   |
|   tensorflow::servi               |                                   |
| ng::LoaderHarness::LoaderHarness  |                                   |
|   (   const [ServableId](structte |                                   |
| nsorflow_1_1serving_1_1ServableId |                                   |
| .html){.el} &               *id*, |                                   |
|                                   |                                   |
|                                   |                                   |
|   std::unique\_ptr\< [Loader](cla |                                   |
| sstensorflow_1_1serving_1_1Loader |                                   |
| .html){.el} \>          *loader*, |                                   |
|                                   |                                   |
|                                   |                                   |
|                         std::uniq |                                   |
| ue\_ptr\< T \>                    |                                   |
|                                   |                                   |
|              *additional\_state*, |                                   |
|                                   |                                   |
|                                   |                                   |
|                     const [Option |                                   |
| s](structtensorflow_1_1serving_1_ |                                   |
| 1LoaderHarness_1_1Options.html){. |                                   |
| el} &    *options* = `Options()`  |                                   |
|                                   |                                   |
|                                   |                                   |
|        )                          |                                   |
|                                   |                                   |
|                                   |                                   |
|   -----                           |                                   |
| --------------------------------- |                                   |
| ------------- --- --------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------ -------------------------- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Constructor to create a harness with additional state, which a manager
needs.
:::
:::

[]{#a60facd158c858dbdcaaae74a18a4edd9}

[[◆ ](#a60facd158c858dbdcaaae74a18a4edd9)]{.permalink}\~LoaderHarness() {#loaderharness-1 .memtitle}
-----------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ----------------------------------------------------- --- -- --- --
  tensorflow::serving::LoaderHarness::\~LoaderHarness   (      )   
  ----------------------------------------------------- --- -- --- --
:::

::: {.memdoc}
Legal to destruct iff current state is one of kNew, kDisabled or kError.
Check-fails if violated.
:::
:::

Member Function Documentation {#member-function-documentation .groupheader}
-----------------------------

[]{#a2a5bfd26e4b27de0e59a9dea68315a84}

[[◆ ](#a2a5bfd26e4b27de0e59a9dea68315a84)]{.permalink}additional\_state() {#additional_state .memtitle}
-------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
::: {.memtemplate}
template\<typename T \>
:::

+-----------------------------------+-----------------------------------+
|   -------                         | [[inline]{.mlabel}]{.mlabels}     |
| --------------------------------- |                                   |
| ------------------- --- -- --- -- |                                   |
|   T\* t                           |                                   |
| ensorflow::serving::LoaderHarness |                                   |
| ::additional\_state   (      )    |                                   |
|   -------                         |                                   |
| --------------------------------- |                                   |
| ------------------- --- -- --- -- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Gets the additional state. Returns nullptr if the type mismatches or if
it wasn\'t set.
:::
:::

[]{#a11b81e561e55c5b21907f8fc2eafe6e9}

[[◆ ](#a11b81e561e55c5b21907f8fc2eafe6e9)]{.permalink}DoneQuiescing() {#donequiescing .memtitle}
---------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ---------------------------------------------------------- --- -- --- --
  Status tensorflow::serving::LoaderHarness::DoneQuiescing   (      )   
  ---------------------------------------------------------- --- -- --- --
:::

::: {.memdoc}
Transitions the state to kQuiesced, which means that there are no more
live handles to this servable available in the frontend. At this point,
we can unload this object.

REQUIRES: State is kQuiescing when called. Otherwise DCHECK-fails,
transitions to state kError and invokes \'options\_.error\_callback\'.
:::
:::

[]{#af7e5a0ecbec71342dcb2aa9764d0604e}

[[◆ ](#af7e5a0ecbec71342dcb2aa9764d0604e)]{.permalink}Load() {#load .memtitle}
------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ------------------------------------------------- --- -- --- --
  Status tensorflow::serving::LoaderHarness::Load   (      )   
  ------------------------------------------------- --- -- --- --
:::

::: {.memdoc}
Transitions to kLoading, delegates to Servable::Load(), then transitions
either to kReady if
[Load()](classtensorflow_1_1serving_1_1LoaderHarness.html#af7e5a0ecbec71342dcb2aa9764d0604e){.el}
succeeds, or to kError (and invokes \'options\_. error\_callback\') if
[Load()](classtensorflow_1_1serving_1_1LoaderHarness.html#af7e5a0ecbec71342dcb2aa9764d0604e){.el}
fails. This call may take a long time.

We retry the Servable::Load() according to the options set during
construction of this class. We stop retrying and give up if 1. we have
reached max\_num\_load\_retries or, 2. if cancel\_load() is set to true.

REQUIRES: State is kLoadApproved when called. Otherwise DCHECK-fails,
transitions to state kError and invokes \'options\_.error\_callback\'.
:::
:::

[]{#aab4e0158cc9fccd7539df5a9fa312e8c}

[[◆ ](#aab4e0158cc9fccd7539df5a9fa312e8c)]{.permalink}LoadApproved() {#loadapproved .memtitle}
--------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  --------------------------------------------------------- --- -- --- --
  Status tensorflow::serving::LoaderHarness::LoadApproved   (      )   
  --------------------------------------------------------- --- -- --- --
:::

::: {.memdoc}
Transitions to kLoadApproved.

REQUIRES: State is kLoadRequested when called. Otherwise DCHECK-fails,
transitions to state kError and invokes \'options\_.error\_callback\'.
:::
:::

[]{#ae0be696227d934efdfc91bd13de4e48a}

[[◆ ](#ae0be696227d934efdfc91bd13de4e48a)]{.permalink}loader() {#loader .memtitle}
--------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   -----------------------         | [[inline]{.mlabel}]{.mlabels}     |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| -------------- --- -- --- ------- |                                   |
|   [Loader](classtensorf           |                                   |
| low_1_1serving_1_1Loader.html){.e |                                   |
| l}\* tensorflow::serving::LoaderH |                                   |
| arness::loader   (      )   const |                                   |
|   -----------------------         |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| -------------- --- -- --- ------- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Returns a pointer to the wrapped loader. Ownership remains with this
class.
:::
:::

[]{#af38723eb75813331dad2f0d910466f57}

[[◆ ](#af38723eb75813331dad2f0d910466f57)]{.permalink}LoadRequested() {#loadrequested .memtitle}
---------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ---------------------------------------------------------- --- -- --- --
  Status tensorflow::serving::LoaderHarness::LoadRequested   (      )   
  ---------------------------------------------------------- --- -- --- --
:::

::: {.memdoc}
Transitions the state of the harness to kLoadRequested iff its current
state is kNew. The test-and-change is done transactionally, so this
method can be used to ensure that at most one
[Load()](classtensorflow_1_1serving_1_1LoaderHarness.html#af7e5a0ecbec71342dcb2aa9764d0604e){.el}
request can proceed.
:::
:::

[]{#a001ec617f6fd186d27cc911f9a952f00}

[[◆ ](#a001ec617f6fd186d27cc911f9a952f00)]{.permalink}set\_should\_retry() {#set_should_retry .memtitle}
--------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ------------------------------------------------------------- --- --------------------------------------- ----------------- --- --
  void tensorflow::serving::LoaderHarness::set\_should\_retry   (   std::function\< bool(absl::Status)\>    *should\_retry*   )   
  ------------------------------------------------------------- --- --------------------------------------- ----------------- --- --
:::

::: {.memdoc}
Sets the retry behavior for the servable using a function which accepts
the status of the last load attempt and returns a boolean. If the
boolean is false, we cancel the next retry. This is best-effort, and
does not preempt a
[Load()](classtensorflow_1_1serving_1_1LoaderHarness.html#af7e5a0ecbec71342dcb2aa9764d0604e){.el}
which is already happening, only subsequent calls.

If the retries are cancelled, the servable goes into a state dependent
on the last
[Load()](classtensorflow_1_1serving_1_1LoaderHarness.html#af7e5a0ecbec71342dcb2aa9764d0604e){.el}
called on it. If the last
[Load()](classtensorflow_1_1serving_1_1LoaderHarness.html#af7e5a0ecbec71342dcb2aa9764d0604e){.el}
was successful, it will be in state kReady, else in kError.
:::
:::

[]{#a811f9dbe7ab8fb5df0c35916ec57aad8}

[[◆ ](#a811f9dbe7ab8fb5df0c35916ec57aad8)]{.permalink}StartQuiescing() {#startquiescing .memtitle}
----------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ----------------------------------------------------------- --- -- --- --
  Status tensorflow::serving::LoaderHarness::StartQuiescing   (      )   
  ----------------------------------------------------------- --- -- --- --
:::

::: {.memdoc}
Transitions the state to kQuiescing, which means that we would like to
not give out any more handles to this servable.

REQUIRES: State is kUnloadRequested when called. Otherwise DCHECK-fails,
transitions to state kError and invokes \'options\_.error\_callback\'.
:::
:::

[]{#afb34eca424243aacbf71f466d4ec99ef}

[[◆ ](#afb34eca424243aacbf71f466d4ec99ef)]{.permalink}status() {#status .memtitle}
--------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  --------------------------------------------------- --- -- --- -------
  Status tensorflow::serving::LoaderHarness::status   (      )   const
  --------------------------------------------------- --- -- --- -------
:::

::: {.memdoc}
Whether anything has gone wrong with this servable. If state is kError,
this will be non-OK. If not OK, the error could be something that
occurred in a [Source](classtensorflow_1_1serving_1_1Source.html){.el}
or
[SourceAdapter](classtensorflow_1_1serving_1_1SourceAdapter.html){.el},
in the [Loader](classtensorflow_1_1serving_1_1Loader.html){.el}, in the
[Manager](classtensorflow_1_1serving_1_1Manager.html){.el}, or
elsewhere. All errors pertaining to the servable are reported here,
regardless of origin.
:::
:::

[]{#a5c131cef32324cd2ec6b22fc4dd92942}

[[◆ ](#a5c131cef32324cd2ec6b22fc4dd92942)]{.permalink}Unload() {#unload .memtitle}
--------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  --------------------------------------------------- --- -- --- --
  Status tensorflow::serving::LoaderHarness::Unload   (      )   
  --------------------------------------------------- --- -- --- --
:::

::: {.memdoc}
Transitions to kUnloading, delegates to Servable::Unload(), then
transitions to kDisabled when
[Unload()](classtensorflow_1_1serving_1_1LoaderHarness.html#a5c131cef32324cd2ec6b22fc4dd92942){.el}
is done.

REQUIRES: State is kQuiesced when called. Otherwise DCHECK-fails,
transitions to state kError and invokes \'options\_.error\_callback\'.
:::
:::

[]{#a6451e73c25ba30b0c78a560deba29e03}

[[◆ ](#a6451e73c25ba30b0c78a560deba29e03)]{.permalink}UnloadRequested() {#unloadrequested .memtitle}
-----------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
  ------------------------------------------------------------ --- -- --- --
  Status tensorflow::serving::LoaderHarness::UnloadRequested   (      )   
  ------------------------------------------------------------ --- -- --- --
:::

::: {.memdoc}
Transitions the state of the harness to kUnloadRequested iff its current
state is kReady. The test-and-change is done transactionally, so this
method can be used to ensure that at most one
[Load()](classtensorflow_1_1serving_1_1LoaderHarness.html#af7e5a0ecbec71342dcb2aa9764d0604e){.el}
request can proceed.
:::
:::

------------------------------------------------------------------------

The documentation for this class was generated from the following files:

-   tensorflow\_serving/core/[loader\_harness.h](loader__harness_8h_source.html){.el}
-   tensorflow\_serving/core/loader\_harness.cc

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

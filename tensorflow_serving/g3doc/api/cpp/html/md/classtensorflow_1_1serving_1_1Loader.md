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
-   [Loader](classtensorflow_1_1serving_1_1Loader.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Classes](#nested-classes) \| [Public Member Functions](#pub-methods) \|
[List of all members](classtensorflow_1_1serving_1_1Loader-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::Loader Class
Reference[[abstract]{.mlabel}]{.mlabels}
:::
:::
:::

::: {.contents}
`#include <loader.h>`

::: {.dynheader}
Inheritance diagram for tensorflow::serving::Loader:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1Loader__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#nested-classes} Classes {#classes .groupheader}
---------------------------
:::

struct  

[Metadata](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html){.el}

 

The metadata consists of the
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el}.
[More\...](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html#details)\

 

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------

virtual 

[\~Loader](classtensorflow_1_1serving_1_1Loader.html#ab12e7e4d5f33ade6dd73d7a30873c032){.el}
()=default

 

virtual Status 

[EstimateResources](classtensorflow_1_1serving_1_1Loader.html#ab59db26b242a2224889bc7c5c6edae40){.el}
(ResourceAllocation \*estimate) const =0

 

virtual Status 

[Load](classtensorflow_1_1serving_1_1Loader.html#a7dadc89ccbf488aae0102368261cc692){.el}
()

 

virtual Status 

[LoadWithMetadata](classtensorflow_1_1serving_1_1Loader.html#a7aebd433e4a782265d847e507f3bc824){.el}
(const
[Metadata](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html){.el}
&metadata)

 

virtual void 

[Unload](classtensorflow_1_1serving_1_1Loader.html#addca8f4264380e5e635bbe1197f5347f){.el}
()=0

 

virtual [AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html){.el} 

[servable](classtensorflow_1_1serving_1_1Loader.html#a640d67dc6ca9926595d29fdfe63868c1){.el}
()=0

 

[]{#details}

Detailed Description {#detailed-description .groupheader}
--------------------

::: {.textblock}
A standardized abstraction for an object that manages the lifecycle of a
servable, including loading and unloading it. Servables are arbitrary
objects that serve algorithms or data that often, though not
necessarily, use a machine-learned model.

A [Loader](classtensorflow_1_1serving_1_1Loader.html){.el} for a
servable object represents one instance of a stream of servable
versions, all sharing a common name (e.g. \"my\_servable\") and
increasing version numbers, typically representing updated model
parameters learned from fresh training data.

A [Loader](classtensorflow_1_1serving_1_1Loader.html){.el} should start
in an unloaded state, meaning that no work has been done to prepare to
perform operations. A typical instance that has not yet been loaded
contains merely a pointer to a location from which its data can be
loaded (e.g. a file-system path or network location). Construction and
destruction of instances should be fairly cheap. Expensive
initialization operations should be done in
[Load()](classtensorflow_1_1serving_1_1Loader.html#a7dadc89ccbf488aae0102368261cc692){.el}.

Subclasses may optionally store a pointer to the
[Source](classtensorflow_1_1serving_1_1Source.html){.el} that originated
it, for accessing state shared across multiple servable objects in a
given servable stream.

Implementations need to ensure that the methods they expose are
thread-safe, or carefully document and/or coordinate their thread-safety
properties with their clients to ensure correctness. Servables do not
need to worry about concurrent execution of
[Load()](classtensorflow_1_1serving_1_1Loader.html#a7dadc89ccbf488aae0102368261cc692){.el}/Unload()
as the caller will ensure that does not happen.
:::

Constructor & Destructor Documentation {#constructor-destructor-documentation .groupheader}
--------------------------------------

[]{#ab12e7e4d5f33ade6dd73d7a30873c032}

[[◆ ](#ab12e7e4d5f33ade6dd73d7a30873c032)]{.permalink}\~Loader() {#loader .memtitle}
----------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   ----------------------------    | [[virtual]{.mla                   |
| ------------------- --- -- --- -- | bel}[default]{.mlabel}]{.mlabels} |
|   virtual tensorflow::servin      |                                   |
| g::Loader::\~Loader   (      )    |                                   |
|   ----------------------------    |                                   |
| ------------------- --- -- --- -- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
The destructor will never be called on a
[Loader](classtensorflow_1_1serving_1_1Loader.html){.el} whose servable
is currently loaded, i.e. between (successful) calls to
[Load()](classtensorflow_1_1serving_1_1Loader.html#a7dadc89ccbf488aae0102368261cc692){.el}
and
[Unload()](classtensorflow_1_1serving_1_1Loader.html#addca8f4264380e5e635bbe1197f5347f){.el}.
:::
:::

Member Function Documentation {#member-function-documentation .groupheader}
-----------------------------

[]{#ab59db26b242a2224889bc7c5c6edae40}

[[◆ ](#ab59db26b242a2224889bc7c5c6edae40)]{.permalink}EstimateResources() {#estimateresources .memtitle}
-------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   ------------------              | [[pure                            |
| --------------------------------- | virtual]{.mlabel}]{.mlabels}      |
| ------------ --- ---------------- |                                   |
| -------- ------------ --- ------- |                                   |
|   virtual Status t                |                                   |
| ensorflow::serving::Loader::Estim |                                   |
| ateResources   (   ResourceAlloca |                                   |
| tion \*    *estimate*   )   const |                                   |
|   ------------------              |                                   |
| --------------------------------- |                                   |
| ------------ --- ---------------- |                                   |
| -------- ------------ --- ------- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Estimates the resources a servable will use.

IMPORTANT: This method\'s implementation must obey following
requirements, which enable the serving system to reason correctly about
which servables can be loaded safely:

1.  The estimate must represent an upper bound on the actual value.
2.  Prior to load, the estimate may include resources that are not bound
    to any specific device instance, e.g. RAM on one of the two GPUs.
3.  While loaded, for any devices with multiple instances (e.g. two
    GPUs), the estimate must specify the instance to which each resource
    is bound.
4.  The estimate must be monotonically non-increasing, i.e. it cannot
    increase over time. Reasons to have it potentially decrease over
    time

    Returns
    :   an estimate of the resources the servable will consume once
        loaded. If the servable has already been loaded, returns an
        estimate of the actual resource usage.

Implemented in [tensorflow::serving::SimpleLoader\< ServableType
\>](classtensorflow_1_1serving_1_1SimpleLoader.html#a05ede6c604d05037f59fe13472b48935){.el},
and
[tensorflow::serving::ResourceUnsafeLoader](classtensorflow_1_1serving_1_1ResourceUnsafeLoader.html#a1a0c1398af9af54032ba16a79a9ecac4){.el}.
:::
:::

[]{#a7dadc89ccbf488aae0102368261cc692}

[[◆ ](#a7dadc89ccbf488aae0102368261cc692)]{.permalink}Load() {#load .memtitle}
------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   ------------------------------- | [[inline]{.mla                    |
| ------------------- --- -- --- -- | bel}[virtual]{.mlabel}]{.mlabels} |
|   virtual Status tensorflow::se   |                                   |
| rving::Loader::Load   (      )    |                                   |
|   ------------------------------- |                                   |
| ------------------- --- -- --- -- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Fetches any data that needs to be loaded before using the servable
returned by
[servable()](classtensorflow_1_1serving_1_1Loader.html#a640d67dc6ca9926595d29fdfe63868c1){.el}.
May use no more resources than the estimate reported by
[EstimateResources()](classtensorflow_1_1serving_1_1Loader.html#ab59db26b242a2224889bc7c5c6edae40){.el}.

If implementing
[Load()](classtensorflow_1_1serving_1_1Loader.html#a7dadc89ccbf488aae0102368261cc692){.el},
you don\'t have to override
[LoadWithMetadata()](classtensorflow_1_1serving_1_1Loader.html#a7aebd433e4a782265d847e507f3bc824){.el}.

Reimplemented in
[tensorflow::serving::test\_util::FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#a2edb74f10db51d582ee689d3d81cacb7){.el},
and [tensorflow::serving::SimpleLoader\< ServableType
\>](classtensorflow_1_1serving_1_1SimpleLoader.html#ada69d680b17f2e054faef889f135cb74){.el}.
:::
:::

[]{#a7aebd433e4a782265d847e507f3bc824}

[[◆ ](#a7aebd433e4a782265d847e507f3bc824)]{.permalink}LoadWithMetadata() {#loadwithmetadata .memtitle}
------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   ----                            | [[inline]{.mla                    |
| --------------------------------- | bel}[virtual]{.mlabel}]{.mlabels} |
| ------------------------- --- --- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------------- ------------ --- -- |                                   |
|   vi                              |                                   |
| rtual Status tensorflow::serving: |                                   |
| :Loader::LoadWithMetadata   (   c |                                   |
| onst [Metadata](structtensorflow_ |                                   |
| 1_1serving_1_1Loader_1_1Metadata. |                                   |
| html){.el} &    *metadata*   )    |                                   |
|   ----                            |                                   |
| --------------------------------- |                                   |
| ------------------------- --- --- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------------- ------------ --- -- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Similar to the above method, but takes
[Metadata](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html "The metadata consists of the ServableId."){.el}
as a param, which may be used by the loader implementation
appropriately.

If you\'re overriding
[LoadWithMetadata()](classtensorflow_1_1serving_1_1Loader.html#a7aebd433e4a782265d847e507f3bc824){.el},
because you can use the metadata appropriately, you can skip overriding
[Load()](classtensorflow_1_1serving_1_1Loader.html#a7dadc89ccbf488aae0102368261cc692){.el}.

Reimplemented in [tensorflow::serving::SimpleLoader\< ServableType
\>](classtensorflow_1_1serving_1_1SimpleLoader.html#a4c9a2f88fd1cab8a68ffa69bb9900e24){.el}.
:::
:::

[]{#a640d67dc6ca9926595d29fdfe63868c1}

[[◆ ](#a640d67dc6ca9926595d29fdfe63868c1)]{.permalink}servable() {#servable .memtitle}
----------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   -------------------             | [[pure                            |
| --------------------------------- | virtual]{.mlabel}]{.mlabels}      |
| --------------------------------- |                                   |
| ------------------- --- -- --- -- |                                   |
|   virtual [AnyPtr](               |                                   |
| classtensorflow_1_1serving_1_1Any |                                   |
| Ptr.html){.el} tensorflow::servin |                                   |
| g::Loader::servable   (      )    |                                   |
|   -------------------             |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------------------- --- -- --- -- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Returns an opaque interface to the underlying servable object. The
caller should know the precise type of the interface in order to make
actual use of it. For example:

CustomLoader implementation:

``` {.fragment}
class CustomLoader : public Loader {
 public:
  ...
  Status Load() override {
    servable_ = ...;
  }

  AnyPtr servable() override { return servable_; }

 private:
  CustomServable* servable_ = nullptr;
};
```

Serving user request:

``` {.fragment}
ServableHandle&lt;CustomServable> handle = ...
CustomServable* servable = handle.get();
servable->...
```

If
[servable()](classtensorflow_1_1serving_1_1Loader.html#a640d67dc6ca9926595d29fdfe63868c1){.el}
is called after successful
[Load()](classtensorflow_1_1serving_1_1Loader.html#a7dadc89ccbf488aae0102368261cc692){.el}
and before
[Unload()](classtensorflow_1_1serving_1_1Loader.html#addca8f4264380e5e635bbe1197f5347f){.el},
it returns a valid, non-null
[AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html){.el} object. If
called before a successful
[Load()](classtensorflow_1_1serving_1_1Loader.html#a7dadc89ccbf488aae0102368261cc692){.el}
call or after
[Unload()](classtensorflow_1_1serving_1_1Loader.html#addca8f4264380e5e635bbe1197f5347f){.el},
it returns null
[AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html){.el}.

Implemented in
[tensorflow::serving::test\_util::FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#afd3838612c119a086d1b17ce7cdfb9ed){.el},
and [tensorflow::serving::SimpleLoader\< ServableType
\>](classtensorflow_1_1serving_1_1SimpleLoader.html#a914a9107be7cfeb587998934be9d9fee){.el}.
:::
:::

[]{#addca8f4264380e5e635bbe1197f5347f}

[[◆ ](#addca8f4264380e5e635bbe1197f5347f)]{.permalink}Unload() {#unload .memtitle}
--------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   ------------------------------- | [[pure                            |
| ------------------- --- -- --- -- | virtual]{.mlabel}]{.mlabels}      |
|   virtual void tensorflow::serv   |                                   |
| ing::Loader::Unload   (      )    |                                   |
|   ------------------------------- |                                   |
| ------------------- --- -- --- -- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Frees any resources allocated during
[Load()](classtensorflow_1_1serving_1_1Loader.html#a7dadc89ccbf488aae0102368261cc692){.el}
(except perhaps for resources shared across servables that are still
needed for other active ones). The loader does not need to return to the
\"new\" state (i.e.
[Load()](classtensorflow_1_1serving_1_1Loader.html#a7dadc89ccbf488aae0102368261cc692){.el}
cannot be called after
[Unload()](classtensorflow_1_1serving_1_1Loader.html#addca8f4264380e5e635bbe1197f5347f){.el}).

Implemented in
[tensorflow::serving::test\_util::FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#a336ea084823272d433d19be25769fc70){.el},
and [tensorflow::serving::SimpleLoader\< ServableType
\>](classtensorflow_1_1serving_1_1SimpleLoader.html#ae24b904b3155f039fadd88b1c23e2f82){.el}.
:::
:::

------------------------------------------------------------------------

The documentation for this class was generated from the following file:

-   tensorflow\_serving/core/[loader.h](loader_8h_source.html){.el}

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

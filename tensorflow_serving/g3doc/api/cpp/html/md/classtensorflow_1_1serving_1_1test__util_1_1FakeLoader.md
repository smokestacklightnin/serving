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
-   **test\_util**
-   [FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Member Functions](#pub-methods) \| [Static Public Member
Functions](#pub-static-methods) \| [List of all
members](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::test\_util::FakeLoader Class Reference
:::
:::
:::

::: {.contents}
::: {.dynheader}
Inheritance diagram for tensorflow::serving::test\_util::FakeLoader:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

::: {.dynheader}
Collaboration diagram for tensorflow::serving::test\_util::FakeLoader:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------
:::

[]{#a7dca957e589fd4eaaf57fcf05aab62ae}  

**FakeLoader** (int64\_t
[servable](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#afd3838612c119a086d1b17ce7cdfb9ed){.el},
const Status load\_status=Status())

 

[]{#ace387f4f5d2b37245bbb5864c548dd0c} Status 

**load\_status** ()

 

Status 

[Load](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#a2edb74f10db51d582ee689d3d81cacb7){.el}
() override

 

void 

[Unload](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#a336ea084823272d433d19be25769fc70){.el}
() override

 

[AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html){.el} 

[servable](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#afd3838612c119a086d1b17ce7cdfb9ed){.el}
() override

 

![-](closed.png) Public Member Functions inherited from
[tensorflow::serving::ResourceUnsafeLoader](classtensorflow_1_1serving_1_1ResourceUnsafeLoader.html){.el}

Status 

[EstimateResources](classtensorflow_1_1serving_1_1ResourceUnsafeLoader.html#a1a0c1398af9af54032ba16a79a9ecac4){.el}
(ResourceAllocation \*estimate) const final

 

![-](closed.png) Public Member Functions inherited from
[tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html){.el}

virtual 

[\~Loader](classtensorflow_1_1serving_1_1Loader.html#ab12e7e4d5f33ade6dd73d7a30873c032){.el}
()=default

 

virtual Status 

[LoadWithMetadata](classtensorflow_1_1serving_1_1Loader.html#a7aebd433e4a782265d847e507f3bc824){.el}
(const
[Metadata](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html){.el}
&metadata)

 

[]{#pub-static-methods} Static Public Member Functions {#static-public-member-functions .groupheader}
------------------------------------------------------

[]{#a961505cccbe5ead1572b3ba8a69eb097} static int 

**num\_fake\_loaders** ()

 

[]{#a27d8493fe0f418b27cdd9949db26ede2} static bool 

**was\_deleted\_in\_this\_thread** ()

 

Member Function Documentation {#member-function-documentation .groupheader}
-----------------------------

[]{#a2edb74f10db51d582ee689d3d81cacb7}

[[◆ ](#a2edb74f10db51d582ee689d3d81cacb7)]{.permalink}Load() {#load .memtitle}
------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   ------                          | [[override]{.mla                  |
| --------------------------------- | bel}[virtual]{.mlabel}]{.mlabels} |
| ------------------- --- -- --- -- |                                   |
|   Stat                            |                                   |
| us tensorflow::serving::test\_uti |                                   |
| l::FakeLoader::Load   (      )    |                                   |
|   ------                          |                                   |
| --------------------------------- |                                   |
| ------------------- --- -- --- -- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Fetches any data that needs to be loaded before using the servable
returned by
[servable()](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#afd3838612c119a086d1b17ce7cdfb9ed){.el}.
May use no more resources than the estimate reported by
[EstimateResources()](classtensorflow_1_1serving_1_1ResourceUnsafeLoader.html#a1a0c1398af9af54032ba16a79a9ecac4){.el}.

If implementing
[Load()](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#a2edb74f10db51d582ee689d3d81cacb7){.el},
you don\'t have to override
[LoadWithMetadata()](classtensorflow_1_1serving_1_1Loader.html#a7aebd433e4a782265d847e507f3bc824){.el}.

Reimplemented from
[tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html#a7dadc89ccbf488aae0102368261cc692){.el}.
:::
:::

[]{#afd3838612c119a086d1b17ce7cdfb9ed}

[[◆ ](#afd3838612c119a086d1b17ce7cdfb9ed)]{.permalink}servable() {#servable .memtitle}
----------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   ---------------------------     | [[override]{.mla                  |
| --------------------------------- | bel}[virtual]{.mlabel}]{.mlabels} |
| --------------------------------- |                                   |
| ------------------- --- -- --- -- |                                   |
|   [AnyPtr](classtensorflow_       |                                   |
| 1_1serving_1_1AnyPtr.html){.el} t |                                   |
| ensorflow::serving::test\_util::F |                                   |
| akeLoader::servable   (      )    |                                   |
|   ---------------------------     |                                   |
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
[servable()](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#afd3838612c119a086d1b17ce7cdfb9ed){.el}
is called after successful
[Load()](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#a2edb74f10db51d582ee689d3d81cacb7){.el}
and before
[Unload()](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#a336ea084823272d433d19be25769fc70){.el},
it returns a valid, non-null
[AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html){.el} object. If
called before a successful
[Load()](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#a2edb74f10db51d582ee689d3d81cacb7){.el}
call or after
[Unload()](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#a336ea084823272d433d19be25769fc70){.el},
it returns null
[AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html){.el}.

Implements
[tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html#a640d67dc6ca9926595d29fdfe63868c1){.el}.
:::
:::

[]{#a336ea084823272d433d19be25769fc70}

[[◆ ](#a336ea084823272d433d19be25769fc70)]{.permalink}Unload() {#unload .memtitle}
--------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   ------                          | [[override]{.mla                  |
| --------------------------------- | bel}[virtual]{.mlabel}]{.mlabels} |
| ------------------- --- -- --- -- |                                   |
|   void                            |                                   |
|  tensorflow::serving::test\_util: |                                   |
| :FakeLoader::Unload   (      )    |                                   |
|   ------                          |                                   |
| --------------------------------- |                                   |
| ------------------- --- -- --- -- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Frees any resources allocated during
[Load()](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#a2edb74f10db51d582ee689d3d81cacb7){.el}
(except perhaps for resources shared across servables that are still
needed for other active ones). The loader does not need to return to the
\"new\" state (i.e.
[Load()](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#a2edb74f10db51d582ee689d3d81cacb7){.el}
cannot be called after
[Unload()](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#a336ea084823272d433d19be25769fc70){.el}).

Implements
[tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html#addca8f4264380e5e635bbe1197f5347f){.el}.
:::
:::

------------------------------------------------------------------------

The documentation for this class was generated from the following files:

-   tensorflow\_serving/core/test\_util/[fake\_loader.h](fake__loader_8h_source.html){.el}
-   tensorflow\_serving/core/test\_util/fake\_loader.cc

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

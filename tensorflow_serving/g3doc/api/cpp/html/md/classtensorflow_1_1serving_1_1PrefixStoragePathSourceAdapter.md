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
-   [PrefixStoragePathSourceAdapter](classtensorflow_1_1serving_1_1PrefixStoragePathSourceAdapter.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Member Functions](#pub-methods) \| [Protected Member
Functions](#pro-methods) \| [List of all
members](classtensorflow_1_1serving_1_1PrefixStoragePathSourceAdapter-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::PrefixStoragePathSourceAdapter Class
Reference[[final]{.mlabel}]{.mlabels}
:::
:::
:::

::: {.contents}
::: {.dynheader}
Inheritance diagram for
tensorflow::serving::PrefixStoragePathSourceAdapter:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1PrefixStoragePathSourceAdapter__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

::: {.dynheader}
Collaboration diagram for
tensorflow::serving::PrefixStoragePathSourceAdapter:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](classtensorflow_1_1serving_1_1PrefixStoragePathSourceAdapter__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------
:::

[]{#ab856dbc6a93c91f3a4fedd0c7465d7a5}  

**PrefixStoragePathSourceAdapter** (const std::string &prefix)

 

![-](closed.png) Public Member Functions inherited from
[tensorflow::serving::SourceAdapter\< InputType, OutputType
\>](classtensorflow_1_1serving_1_1SourceAdapter.html){.el}

void 

[SetAspiredVersions](classtensorflow_1_1serving_1_1SourceAdapter.html#a9775d0a39269efb319a0dbd94862f183){.el}
(const StringPiece servable\_name, std::vector\<
[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.el}\<
InputType \>\> versions) final

 

[]{#aa123a0dc11c1c45073e16bb40ae50285} void 

**SetAspiredVersionsCallback** (typename
[Source](classtensorflow_1_1serving_1_1Source.html){.el}\< OutputType
\>::[AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f){.el}
callback) final

 

[]{#acb3ad719a856c7bb0085df33438c4986}
[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.el}\<
OutputType \> 

[AdaptOneVersion](classtensorflow_1_1serving_1_1SourceAdapter.html#acb3ad719a856c7bb0085df33438c4986){.el}
([ServableData](classtensorflow_1_1serving_1_1ServableData.html){.el}\<
InputType \> input)

 

Adapts a single servable data item. (Implemented on top of
[Adapt()](classtensorflow_1_1serving_1_1SourceAdapter.html#a7c960f8493040fc8cb0766e4c2cebf60){.el}.)\

 

![-](closed.png) Public Member Functions inherited from
[tensorflow::serving::TargetBase\< InputType
\>](classtensorflow_1_1serving_1_1TargetBase.html){.el}

[]{#aaaea9fc579a9432a9ed298ab78eb871a}
[Source](classtensorflow_1_1serving_1_1Source.html){.el}\< InputType
\>::AspiredVersionsCallback 

**GetAspiredVersionsCallback** () final

 

![-](closed.png) Public Member Functions inherited from
[tensorflow::serving::Source\< OutputType
\>](classtensorflow_1_1serving_1_1Source.html){.el}

[]{#a70d7f3b3ab429deb777d4672c0cec447} virtual void 

[SetAspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#a70d7f3b3ab429deb777d4672c0cec447){.el}
([AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f){.el}
callback)=0

 

Supplies an AspiredVersionsCallback to use. Can be called at most once.\

 

[]{#pro-methods} Protected Member Functions {#protected-member-functions .groupheader}
-------------------------------------------

[]{#a8a1157904ea6950ef87b78dc09efe83c} Status 

**Convert** (const StoragePath &source, StoragePath \*destination) final

 

![-](closed.png) Protected Member Functions inherited from
[tensorflow::serving::TargetBase\< InputType
\>](classtensorflow_1_1serving_1_1TargetBase.html){.el}

[]{#a57f4597495993d85148f4fd8c5ee78af} void 

**Detach** ()

 

[]{#inherited} Additional Inherited Members {#additional-inherited-members .groupheader}
-------------------------------------------

![-](closed.png) Public Types inherited from
[tensorflow::serving::Source\< OutputType
\>](classtensorflow_1_1serving_1_1Source.html){.el}

using 

[AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f){.el}
= std::function\< void(const StringPiece servable\_name, std::vector\<
[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.el}\<
OutputType \> \> versions)\>

 

------------------------------------------------------------------------

The documentation for this class was generated from the following files:

-   tensorflow\_serving/core/[prefix\_storage\_path\_source\_adapter.h](prefix__storage__path__source__adapter_8h_source.html){.el}
-   tensorflow\_serving/core/prefix\_storage\_path\_source\_adapter.cc

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

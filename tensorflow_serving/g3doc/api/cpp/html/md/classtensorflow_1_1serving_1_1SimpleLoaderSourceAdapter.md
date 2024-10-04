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
-   [SimpleLoaderSourceAdapter](classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Types](#pub-types) \| [Static Public Member
Functions](#pub-static-methods) \| [Protected Member
Functions](#pro-methods) \| [List of all
members](classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::SimpleLoaderSourceAdapter\< DataType, ServableType
\> Class Template Reference[[abstract]{.mlabel}]{.mlabels}
:::
:::
:::

::: {.contents}
::: {.dynheader}
Inheritance diagram for tensorflow::serving::SimpleLoaderSourceAdapter\<
DataType, ServableType \>:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

::: {.dynheader}
Collaboration diagram for
tensorflow::serving::SimpleLoaderSourceAdapter\< DataType, ServableType
\>:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#pub-types} Public Types {#public-types .groupheader}
---------------------------
:::

[]{#a75b8da596c076be3427775b6e2ef8101} using 

**Creator** = std::function\< Status(const DataType &,
std::unique\_ptr\< ServableType \> \*)\>

 

[]{#a7f8d82dfe30cae9364d9566c7e53c415} using 

**ResourceEstimator** = std::function\< Status(const DataType &,
ResourceAllocation \*)\>

 

![-](closed.png) Public Types inherited from
[tensorflow::serving::Source\< OutputType
\>](classtensorflow_1_1serving_1_1Source.html){.el}

using 

[AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f){.el}
= std::function\< void(const StringPiece servable\_name, std::vector\<
[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.el}\<
OutputType \> \> versions)\>

 

[]{#pub-static-methods} Static Public Member Functions {#static-public-member-functions .groupheader}
------------------------------------------------------

[]{#a591696188c5ad7f4bce43bf903571f02} static ResourceEstimator 

**EstimateNoResources** ()

 

[]{#pro-methods} Protected Member Functions {#protected-member-functions .groupheader}
-------------------------------------------

[]{#a4f9c20c8b345288f9cddd7717ece9c30}  

**SimpleLoaderSourceAdapter** (Creator creator, ResourceEstimator
resource\_estimator)

 

[]{#a4fe28cadc8e8e794aaeeedd15ddef4ed} Status 

**Convert** (const DataType &data, std::unique\_ptr\<
[Loader](classtensorflow_1_1serving_1_1Loader.html){.el} \> \*loader)
final

 

![-](closed.png) Protected Member Functions inherited from
[tensorflow::serving::TargetBase\< InputType
\>](classtensorflow_1_1serving_1_1TargetBase.html){.el}

[]{#a57f4597495993d85148f4fd8c5ee78af} void 

**Detach** ()

 

[]{#inherited} Additional Inherited Members {#additional-inherited-members .groupheader}
-------------------------------------------

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

 

------------------------------------------------------------------------

The documentation for this class was generated from the following file:

-   tensorflow\_serving/core/[simple\_loader.h](simple__loader_8h_source.html){.el}

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

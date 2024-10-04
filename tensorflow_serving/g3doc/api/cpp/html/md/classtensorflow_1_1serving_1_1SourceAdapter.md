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
-   [SourceAdapter](classtensorflow_1_1serving_1_1SourceAdapter.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Member Functions](#pub-methods) \| [List of all
members](classtensorflow_1_1serving_1_1SourceAdapter-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::SourceAdapter\< InputType, OutputType \> Class
Template Reference[[abstract]{.mlabel}]{.mlabels}
:::
:::
:::

::: {.contents}
`#include <source_adapter.h>`

::: {.dynheader}
Inheritance diagram for tensorflow::serving::SourceAdapter\< InputType,
OutputType \>:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1SourceAdapter__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

::: {.dynheader}
Collaboration diagram for tensorflow::serving::SourceAdapter\<
InputType, OutputType \>:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](classtensorflow_1_1serving_1_1SourceAdapter__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------
:::

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

 

virtual std::vector\<
[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.el}\<
OutputType \> \> 

[Adapt](classtensorflow_1_1serving_1_1SourceAdapter.html#a7c960f8493040fc8cb0766e4c2cebf60){.el}
(const StringPiece servable\_name, std::vector\<
[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.el}\<
InputType \>\> versions)=0

 

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

 

![-](closed.png) Protected Member Functions inherited from
[tensorflow::serving::TargetBase\< InputType
\>](classtensorflow_1_1serving_1_1TargetBase.html){.el}

[]{#a57f4597495993d85148f4fd8c5ee78af} void 

**Detach** ()

 

[]{#details}

Detailed Description {#detailed-description .groupheader}
--------------------

::: {.textblock}
### template\<typename InputType, typename OutputType\> class tensorflow::serving::SourceAdapter\< InputType, OutputType \>

An abstraction for a module that receives aspired-version callbacks with
data of type InputType and converts them into calls with data of type
OutputType.

A common example uses InputType=StoragePath,
OutputType=unique\_ptr&lt;[Loader](classtensorflow_1_1serving_1_1Loader.html){.el}\>,
in which case the module \"converts\" each incoming storage path into a
loader capable of loading a (particular type of) servable based on the
path.

SourceAdapters are typically stateless. However, as with all Sources
they can house state that is shared among multiple emitted servables.
See the discussion in [source.h](source_8h_source.html){.el}.

Implementing subclasses supply an implementation of the
[Adapt()](classtensorflow_1_1serving_1_1SourceAdapter.html#a7c960f8493040fc8cb0766e4c2cebf60){.el}
virtual method, which converts a servable version list from InputType to
OutputType.

IMPORTANT: Every leaf derived class must call Detach() at the top of its
destructor. (See documentation on TargetBase::Detach() in
[target.h](target_8h_source.html){.el}.) Doing so ensures that no
[Adapt()](classtensorflow_1_1serving_1_1SourceAdapter.html#a7c960f8493040fc8cb0766e4c2cebf60){.el}
calls are in flight during destruction of member variables.
:::

Member Function Documentation {#member-function-documentation .groupheader}
-----------------------------

[]{#a7c960f8493040fc8cb0766e4c2cebf60}

[[◆ ](#a7c960f8493040fc8cb0766e4c2cebf60)]{.permalink}Adapt() {#adapt .memtitle}
-------------------------------------------------------------

::: {.memitem}
::: {.memproto}
::: {.memtemplate}
template\<typename InputType , typename OutputType \>
:::

+-----------------------------------+-----------------------------------+
|   ------------------------------- | [[pure                            |
| --------------------------------- | virtual]{.mlabel}]{.mlabels}      |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ----- --- ----------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------------- ------------------- |                                   |
|   virtual std::vector\<[Servabl   |                                   |
| eData](classtensorflow_1_1serving |                                   |
| _1_1ServableData.html){.el}\<Outp |                                   |
| utType\> \> [tensorflow::serving: |                                   |
| :SourceAdapter](classtensorflow_1 |                                   |
| _1serving_1_1SourceAdapter.html){ |                                   |
| .el}\< InputType, OutputType \>:: |                                   |
| Adapt   (   const StringPiece     |                                   |
|                                   |                                   |
|                                   |                                   |
|                 *servable\_name*, |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|                   std::vector\< [ |                                   |
| ServableData](classtensorflow_1_1 |                                   |
| serving_1_1ServableData.html){.el |                                   |
| }\< InputType \>\>    *versions*  |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|                          )        |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|   ------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ----- --- ----------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------------- ------------------- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Given an InputType-based aspired-versions request, produces a
corresponding OutputType-based request.
:::
:::

[]{#a9775d0a39269efb319a0dbd94862f183}

[[◆ ](#a9775d0a39269efb319a0dbd94862f183)]{.permalink}SetAspiredVersions() {#setaspiredversions .memtitle}
--------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
::: {.memtemplate}
template\<typename InputType , typename OutputType \>
:::

+-----------------------------------+-----------------------------------+
|   --------                        | [[final]{.mla                     |
| --------------------------------- | bel}[virtual]{.mlabel}]{.mlabels} |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ----- --- ----------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------------- ------------------- |                                   |
|   void [                          |                                   |
| tensorflow::serving::SourceAdapte |                                   |
| r](classtensorflow_1_1serving_1_1 |                                   |
| SourceAdapter.html){.el}\< InputT |                                   |
| ype, OutputType \>::SetAspiredVer |                                   |
| sions   (   const StringPiece     |                                   |
|                                   |                                   |
|                                   |                                   |
|                 *servable\_name*, |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|                   std::vector\< [ |                                   |
| ServableData](classtensorflow_1_1 |                                   |
| serving_1_1ServableData.html){.el |                                   |
| }\< InputType \>\>    *versions*  |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|                          )        |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|   --------                        |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ----- --- ----------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ------------- ------------------- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
This method is implemented in terms of
[Adapt()](classtensorflow_1_1serving_1_1SourceAdapter.html#a7c960f8493040fc8cb0766e4c2cebf60){.el},
which the implementing subclass must supply.

Implements [tensorflow::serving::TargetBase\< InputType
\>](classtensorflow_1_1serving_1_1TargetBase.html){.el}.
:::
:::

------------------------------------------------------------------------

The documentation for this class was generated from the following file:

-   tensorflow\_serving/core/[source\_adapter.h](source__adapter_8h_source.html){.el}

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

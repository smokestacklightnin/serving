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
-   [ResourceUnsafeLoader](classtensorflow_1_1serving_1_1ResourceUnsafeLoader.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Member Functions](#pub-methods) \| [List of all
members](classtensorflow_1_1serving_1_1ResourceUnsafeLoader-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::ResourceUnsafeLoader Class Reference
:::
:::
:::

::: {.contents}
`#include <loader.h>`

::: {.dynheader}
Inheritance diagram for tensorflow::serving::ResourceUnsafeLoader:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1ResourceUnsafeLoader__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

::: {.dynheader}
Collaboration diagram for tensorflow::serving::ResourceUnsafeLoader:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](classtensorflow_1_1serving_1_1ResourceUnsafeLoader__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------
:::

Status 

[EstimateResources](classtensorflow_1_1serving_1_1ResourceUnsafeLoader.html#a1a0c1398af9af54032ba16a79a9ecac4){.el}
(ResourceAllocation \*estimate) const final

 

![-](closed.png) Public Member Functions inherited from
[tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html){.el}

virtual 

[\~Loader](classtensorflow_1_1serving_1_1Loader.html#ab12e7e4d5f33ade6dd73d7a30873c032){.el}
()=default

 

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
A [Loader](classtensorflow_1_1serving_1_1Loader.html){.el} that is
oblivious to resources. Its
[EstimateResources()](classtensorflow_1_1serving_1_1ResourceUnsafeLoader.html#a1a0c1398af9af54032ba16a79a9ecac4){.el}
method returns 0, thus effectively disabling resource-based safety
checks in the serving system.

Loaders that are experimental, or run in environments that do not need
the resource safety checks, can subclass
[ResourceUnsafeLoader](classtensorflow_1_1serving_1_1ResourceUnsafeLoader.html){.el}
instead of [Loader](classtensorflow_1_1serving_1_1Loader.html){.el}.
:::

Member Function Documentation {#member-function-documentation .groupheader}
-----------------------------

[]{#a1a0c1398af9af54032ba16a79a9ecac4}

[[◆ ](#a1a0c1398af9af54032ba16a79a9ecac4)]{.permalink}EstimateResources() {#estimateresources .memtitle}
-------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   ------------------------        | [[inline]{.mlabel}[final]{.mla    |
| --------------------------------- | bel}[virtual]{.mlabel}]{.mlabels} |
| ------------ --- ---------------- |                                   |
| -------- ------------ --- ------- |                                   |
|   Status tensorflow::ser          |                                   |
| ving::ResourceUnsafeLoader::Estim |                                   |
| ateResources   (   ResourceAlloca |                                   |
| tion \*    *estimate*   )   const |                                   |
|   ------------------------        |                                   |
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

Implements
[tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html#ab59db26b242a2224889bc7c5c6edae40){.el}.
:::
:::

------------------------------------------------------------------------

The documentation for this class was generated from the following file:

-   tensorflow\_serving/core/[loader.h](loader_8h_source.html){.el}

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

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
-   [ResourcePreservingPolicy](classtensorflow_1_1serving_1_1ResourcePreservingPolicy.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Member Functions](#pub-methods) \| [List of all
members](classtensorflow_1_1serving_1_1ResourcePreservingPolicy-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::ResourcePreservingPolicy Class
Reference[[final]{.mlabel}]{.mlabels}
:::
:::
:::

::: {.contents}
::: {.dynheader}
Inheritance diagram for tensorflow::serving::ResourcePreservingPolicy:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1ResourcePreservingPolicy__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

::: {.dynheader}
Collaboration diagram for tensorflow::serving::ResourcePreservingPolicy:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](classtensorflow_1_1serving_1_1ResourcePreservingPolicy__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------
:::

absl::optional\<
[ServableAction](structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction.html){.el}
\> 

[GetNextAction](classtensorflow_1_1serving_1_1ResourcePreservingPolicy.html#ab1fa4fa3d4a8dc165bb86f5377436532){.el}
(const std::vector\<
[AspiredServableStateSnapshot](structtensorflow_1_1serving_1_1AspiredServableStateSnapshot.html){.el}
\> &all\_versions) const override

 

[]{#inherited} Additional Inherited Members {#additional-inherited-members .groupheader}
-------------------------------------------

![-](closed.png) Public Types inherited from
[tensorflow::serving::AspiredVersionPolicy](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html){.el}

enum class  

[Action](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a5681f3f1c6c14f088084b29438e6fa85){.el}
: int {
[kLoad](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a5681f3f1c6c14f088084b29438e6fa85ae40d6c82a1a5f5a163aca43efa5e444a){.el}
,
[kUnload](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a5681f3f1c6c14f088084b29438e6fa85a2941108d29908fe92ae8627b1d2ec0a1){.el}
}

 

The different actions that could be recommended by a policy.
[More\...](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a5681f3f1c6c14f088084b29438e6fa85)\

 

![-](closed.png) Static Protected Member Functions inherited from
[tensorflow::serving::AspiredVersionPolicy](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html){.el}

static absl::optional\<
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el} \> 

[GetHighestAspiredNewServableId](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a71bde7aea4c6116cede2714758688857){.el}
(const std::vector\<
[AspiredServableStateSnapshot](structtensorflow_1_1serving_1_1AspiredServableStateSnapshot.html){.el}
\> &all\_versions)

 

Member Function Documentation {#member-function-documentation .groupheader}
-----------------------------

[]{#ab1fa4fa3d4a8dc165bb86f5377436532}

[[◆ ](#ab1fa4fa3d4a8dc165bb86f5377436532)]{.permalink}GetNextAction() {#getnextaction .memtitle}
---------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   ---                             | [[override]{.mla                  |
| --------------------------------- | bel}[virtual]{.mlabel}]{.mlabels} |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| - --- --------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --- ----------------- --- ------- |                                   |
|   a                               |                                   |
| bsl::optional\< [AspiredVersionPo |                                   |
| licy::ServableAction](structtenso |                                   |
| rflow_1_1serving_1_1AspiredVersio |                                   |
| nPolicy_1_1ServableAction.html){. |                                   |
| el} \> tensorflow::serving::Resou |                                   |
| rcePreservingPolicy::GetNextActio |                                   |
| n   (   const std::vector\< [Aspi |                                   |
| redServableStateSnapshot](structt |                                   |
| ensorflow_1_1serving_1_1AspiredSe |                                   |
| rvableStateSnapshot.html){.el} \> |                                   |
|  &    *all\_versions*   )   const |                                   |
|   ---                             |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| - --- --------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --- ----------------- --- ------- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Takes in a vector of state snapshots of all versions of a servable
stream and returns an action to be performed for a particular servable
version, depending only on the states of all the versions.

If no action is to be performed, we don\'t return an action, meaning
that the servable stream is up to date.

Implements
[tensorflow::serving::AspiredVersionPolicy](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a86135f0f3225cd2999033da63e013214){.el}.
:::
:::

------------------------------------------------------------------------

The documentation for this class was generated from the following files:

-   tensorflow\_serving/core/[resource\_preserving\_policy.h](resource__preserving__policy_8h_source.html){.el}
-   tensorflow\_serving/core/resource\_preserving\_policy.cc

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

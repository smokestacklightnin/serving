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
-   [AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Classes](#nested-classes) \| [Public Types](#pub-types) \| [Public
Member Functions](#pub-methods) \| [Static Public Member
Functions](#pub-static-methods) \| [Friends](#friends) \| [List of all
members](classtensorflow_1_1serving_1_1AspiredVersionsManager-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::AspiredVersionsManager Class Reference
:::
:::
:::

::: {.contents}
`#include <aspired_versions_manager.h>`

::: {.dynheader}
Inheritance diagram for tensorflow::serving::AspiredVersionsManager:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1AspiredVersionsManager__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

::: {.dynheader}
Collaboration diagram for tensorflow::serving::AspiredVersionsManager:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](classtensorflow_1_1serving_1_1AspiredVersionsManager__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#nested-classes} Classes {#classes .groupheader}
---------------------------
:::

struct  

[Options](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html){.el}

 

[]{#pub-types} Public Types {#public-types .groupheader}
---------------------------

[]{#a005f473f7335996a1c58beb773dd4cbb} using 

**PreLoadHook** = BasicManager::PreLoadHook

 

[]{#aad4848a5ef2d47bfbe5bfd0075ce906a} using 

**CustomSortActionsFn** = std::function\< bool(const
[AspiredVersionPolicy::ServableAction](structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction.html){.el}
&, const
[AspiredVersionPolicy::ServableAction](structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction.html){.el}
&)\>

 

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------

std::vector\<
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el} \> 

[ListAvailableServableIds](classtensorflow_1_1serving_1_1AspiredVersionsManager.html#a058a76ee71c52d4a6319f14cd9b2ad69){.el}
() const override

 

[]{#a4fcdded2573a67abe77f238857e57f35}
[Source](classtensorflow_1_1serving_1_1Source.html){.el}\<
std::unique\_ptr\<
[Loader](classtensorflow_1_1serving_1_1Loader.html){.el} \>
\>::AspiredVersionsCallback 

[GetAspiredVersionsCallback](classtensorflow_1_1serving_1_1AspiredVersionsManager.html#a4fcdded2573a67abe77f238857e57f35){.el}
() override

 

Returns a callback to set the list of aspired versions for a particular
servable stream, using Loaders.\

 

![-](closed.png) Public Member Functions inherited from
[tensorflow::serving::Manager](classtensorflow_1_1serving_1_1Manager.html){.el}

template\<typename T \>

std::map\<
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el},
[ServableHandle](classtensorflow_1_1serving_1_1ServableHandle.html){.el}\<
T \> \> 

[GetAvailableServableHandles](classtensorflow_1_1serving_1_1Manager.html#a8ad1c3155120737e5a41776ceeff6aaa){.el}
() const

 

template\<typename T \>

Status 

[GetServableHandle](classtensorflow_1_1serving_1_1Manager.html#aca70babd38f4b416cf27bbf40f8bb093){.el}
(const
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.el}
&request,
[ServableHandle](classtensorflow_1_1serving_1_1ServableHandle.html){.el}\<
T \> \*const handle)

 

[]{#pub-static-methods} Static Public Member Functions {#static-public-member-functions .groupheader}
------------------------------------------------------

[]{#a77527bce2c78cc09f55ec7bce2f3a28a} static Status 

**Create**
([Options](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html){.el}
options, std::unique\_ptr\<
[AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}
\> \*manager)

 

[]{#friends} Friends {#friends .groupheader}
--------------------

[]{#a331176a8d12da02dcfc7a4b475d8d845} class 

**internal::AspiredVersionsManagerTargetImpl**

 

[]{#acc49d7142d1c0d62cd06180eb4a9d492} class 

**test\_util::AspiredVersionsManagerTestAccess**

 

[]{#aef1c2aea9a94c4a1b0b2d735f8585246} class 

**ServerCore**

 

[]{#acfcc9f5a29a54b98d9ff40d5af34ee0a} uint32 

**internal::GetManagerNumLoadThreads**
([AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}
\*manager)

 

[]{#aa91cf33196ca873f547c8f1a894722f6} std::function\< void(uint32)\> 

**internal::SetManagerNumLoadThreadsNotifier**
([AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.el}
\*manager)

 

[]{#details}

Detailed Description {#detailed-description .groupheader}
--------------------

::: {.textblock}
A manager that implements the
[Target](classtensorflow_1_1serving_1_1Target.html){.el}&lt;[Loader](classtensorflow_1_1serving_1_1Loader.html){.el}\>
API which uses aspired-versions callbacks to dictate which servable
versions to load. This manager also uses that API to infer which ones to
unload: If a given servable version is currently loaded, and is omitted
from an aspired-versions callback invocation pertaining to its servable
stream, this manager interprets that omission as an implicit instruction
to unload the version. See below for details.

(The implicit-unload semantics facilitates stateless
[Source](classtensorflow_1_1serving_1_1Source.html){.el}
implementations, whereby a given iteration of the
[Source](classtensorflow_1_1serving_1_1Source.html){.el}\'s logic simply
decides which versions of a servable ought to be loaded, without needing
to know what it has decided in the past.)

This manager makes transitions between versions of a servable stream
using a configured
[AspiredVersionPolicy](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html){.el}.
The manager prefers unloading before loading to free up resources in the
server when deciding among transitions suggested by the policy.
:::

Member Function Documentation {#member-function-documentation .groupheader}
-----------------------------

[]{#a058a76ee71c52d4a6319f14cd9b2ad69}

[[◆ ](#a058a76ee71c52d4a6319f14cd9b2ad69)]{.permalink}ListAvailableServableIds() {#listavailableservableids .memtitle}
--------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   --------                        | [[override]{.mla                  |
| --------------------------------- | bel}[virtual]{.mlabel}]{.mlabels} |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| -------------- --- -- --- ------- |                                   |
|   std::v                          |                                   |
| ector\< [ServableId](structtensor |                                   |
| flow_1_1serving_1_1ServableId.htm |                                   |
| l){.el} \> tensorflow::serving::A |                                   |
| spiredVersionsManager::ListAvaila |                                   |
| bleServableIds   (      )   const |                                   |
|   --------                        |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| -------------- --- -- --- ------- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Gets a list of all available servable ids, i.e. each of these can be
retrieved using GetServableHandle.

Implements
[tensorflow::serving::Manager](classtensorflow_1_1serving_1_1Manager.html#a10694eb8c3e845e4738788092057b7ef){.el}.
:::
:::

------------------------------------------------------------------------

The documentation for this class was generated from the following files:

-   tensorflow\_serving/core/[aspired\_versions\_manager.h](aspired__versions__manager_8h_source.html){.el}
-   tensorflow\_serving/core/aspired\_versions\_manager.cc

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

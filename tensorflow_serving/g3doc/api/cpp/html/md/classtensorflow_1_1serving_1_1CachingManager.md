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
-   [CachingManager](classtensorflow_1_1serving_1_1CachingManager.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Classes](#nested-classes) \| [Public Member Functions](#pub-methods) \|
[Static Public Member Functions](#pub-static-methods) \|
[Friends](#friends) \| [List of all
members](classtensorflow_1_1serving_1_1CachingManager-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::CachingManager Class Reference
:::
:::
:::

::: {.contents}
`#include <caching_manager.h>`

::: {.dynheader}
Inheritance diagram for tensorflow::serving::CachingManager:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1CachingManager__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

::: {.dynheader}
Collaboration diagram for tensorflow::serving::CachingManager:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](classtensorflow_1_1serving_1_1CachingManager__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#nested-classes} Classes {#classes .groupheader}
---------------------------
:::

class  

[LoaderFactory](classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory.html){.el}

 

struct  

[Options](structtensorflow_1_1serving_1_1CachingManager_1_1Options.html){.el}

 

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------

[]{#a7b93b1674e052aa564dccf5315a7be8d} std::map\<
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el},
std::unique\_ptr\<
[UntypedServableHandle](classtensorflow_1_1serving_1_1UntypedServableHandle.html){.el}
\> \> 

**GetAvailableUntypedServableHandles** () const override

 

std::vector\<
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el} \> 

[ListAvailableServableIds](classtensorflow_1_1serving_1_1CachingManager.html#af7ec61e19bcd1ac85a4c97c32e977ffe){.el}
() const override

 

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

[]{#ac530ae46b94f69e00ac75280a8cced2f} static Status 

**Create**
([Options](structtensorflow_1_1serving_1_1CachingManager_1_1Options.html){.el}
options, std::unique\_ptr\<
[LoaderFactory](classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory.html){.el}
\> loader\_factory, std::unique\_ptr\<
[CachingManager](classtensorflow_1_1serving_1_1CachingManager.html){.el}
\> \*caching\_manager)

 

[]{#friends} Friends {#friends .groupheader}
--------------------

[]{#ac7f55e952795d71fecc78543972ddb0c} class 

**test\_util::CachingManagerTestAccess**

 

[]{#details}

Detailed Description {#detailed-description .groupheader}
--------------------

::: {.textblock}
A manager that manages and loads servables on-demand. Upon receiving the
request for a servable name and optional version, the manager checks if
it already has the requested servable loaded. If not, it initiates the
load operation and then serves the request.

The manager blocks on the load operation and returns the handle when the
servable has been loaded, or upon error.
:::

Member Function Documentation {#member-function-documentation .groupheader}
-----------------------------

[]{#af7ec61e19bcd1ac85a4c97c32e977ffe}

[[◆ ](#af7ec61e19bcd1ac85a4c97c32e977ffe)]{.permalink}ListAvailableServableIds() {#listavailableservableids .memtitle}
--------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|                                   | [[override]{.mla                  |
| --------------------------------- | bel}[virtual]{.mlabel}]{.mlabels} |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| -------------- --- -- --- ------- |                                   |
|   std::vector\< [ServableId](stru |                                   |
| cttensorflow_1_1serving_1_1Servab |                                   |
| leId.html){.el} \> tensorflow::se |                                   |
| rving::CachingManager::ListAvaila |                                   |
| bleServableIds   (      )   const |                                   |
|                                   |                                   |
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

-   tensorflow\_serving/core/[caching\_manager.h](caching__manager_8h_source.html){.el}
-   tensorflow\_serving/core/caching\_manager.cc

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

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
-   [ManagerWrapper](classtensorflow_1_1serving_1_1ManagerWrapper.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Member Functions](#pub-methods) \| [List of all
members](classtensorflow_1_1serving_1_1ManagerWrapper-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::ManagerWrapper Class Reference
:::
:::
:::

::: {.contents}
::: {.dynheader}
Inheritance diagram for tensorflow::serving::ManagerWrapper:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1ManagerWrapper__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

::: {.dynheader}
Collaboration diagram for tensorflow::serving::ManagerWrapper:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](classtensorflow_1_1serving_1_1ManagerWrapper__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------
:::

[]{#a0b5d2e29eb8c2b48a256496de1cf4fee}  

**ManagerWrapper**
([UniquePtrWithDeps](classtensorflow_1_1serving_1_1UniquePtrWithDeps.html){.el}\<
[Manager](classtensorflow_1_1serving_1_1Manager.html){.el} \> wrapped)

 

std::vector\<
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el} \> 

[ListAvailableServableIds](classtensorflow_1_1serving_1_1ManagerWrapper.html#a76a6e899de4dfca374b71c4ef415b3d0){.el}
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

 

Member Function Documentation {#member-function-documentation .groupheader}
-----------------------------

[]{#a76a6e899de4dfca374b71c4ef415b3d0}

[[◆ ](#a76a6e899de4dfca374b71c4ef415b3d0)]{.permalink}ListAvailableServableIds() {#listavailableservableids .memtitle}
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
| rving::ManagerWrapper::ListAvaila |                                   |
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

-   tensorflow\_serving/core/[manager\_wrapper.h](manager__wrapper_8h_source.html){.el}
-   tensorflow\_serving/core/manager\_wrapper.cc

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

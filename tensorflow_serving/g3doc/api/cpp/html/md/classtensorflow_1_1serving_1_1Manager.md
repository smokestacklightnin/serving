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
-   [Manager](classtensorflow_1_1serving_1_1Manager.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Member Functions](#pub-methods) \| [Friends](#friends) \| [List
of all members](classtensorflow_1_1serving_1_1Manager-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::Manager Class
Reference[[abstract]{.mlabel}]{.mlabels}
:::
:::
:::

::: {.contents}
`#include <manager.h>`

::: {.dynheader}
Inheritance diagram for tensorflow::serving::Manager:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1Manager__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------
:::

virtual std::vector\<
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el} \> 

[ListAvailableServableIds](classtensorflow_1_1serving_1_1Manager.html#a10694eb8c3e845e4738788092057b7ef){.el}
() const =0

 

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

 

[]{#friends} Friends {#friends .groupheader}
--------------------

[]{#a5022aa931fef5755238dd5fb8f78ad6c} class 

**ManagerWrapper**

 

[]{#details}

Detailed Description {#detailed-description .groupheader}
--------------------

::: {.textblock}
[Manager](classtensorflow_1_1serving_1_1Manager.html){.el} is
responsible for loading, unloading, lookup and lifetime management of
all [Servable](classtensorflow_1_1serving_1_1Servable.html){.el} objects
via their Loaders.
:::

Member Function Documentation {#member-function-documentation .groupheader}
-----------------------------

[]{#a8ad1c3155120737e5a41776ceeff6aaa}

[[◆ ](#a8ad1c3155120737e5a41776ceeff6aaa)]{.permalink}GetAvailableServableHandles() {#getavailableservablehandles .memtitle}
-----------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
::: {.memtemplate}
template\<typename T \>
:::

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  std::map\< [ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el}, [ServableHandle](classtensorflow_1_1serving_1_1ServableHandle.html){.el}\< T \> \> tensorflow::serving::Manager::GetAvailableServableHandles
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
:::

::: {.memdoc}
Returns a map of all the currently available servables of a particular
type T. The map is from the servable\'s id to its corresponding handle.

IMPORTANT: The caller should not hold onto the handles for a long time,
because holding them will delay servable loading and unloading.
:::
:::

[]{#aca70babd38f4b416cf27bbf40f8bb093}

[[◆ ](#aca70babd38f4b416cf27bbf40f8bb093)]{.permalink}GetServableHandle() {#getservablehandle .memtitle}
-------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
::: {.memtemplate}
template\<typename T \>
:::

  -------------------------------------------------------- --- ------------------------------------------------------------------------------------------ ------------
  Status tensorflow::serving::Manager::GetServableHandle   (   const [ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.el} &        *request*,
                                                               [ServableHandle](classtensorflow_1_1serving_1_1ServableHandle.html){.el}\< T \> \*const    *handle* 
                                                           )                                                                                              
  -------------------------------------------------------- --- ------------------------------------------------------------------------------------------ ------------
:::

::: {.memdoc}
Returns a
[ServableHandle](classtensorflow_1_1serving_1_1ServableHandle.html){.el}
given a
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.el}.
Returns error if no such
[Servable](classtensorflow_1_1serving_1_1Servable.html){.el} is
available -- e.g. not yet loaded, has been quiesced/unloaded, etc.
Callers may assume that an OK status indicates a non-null handle.

IMPORTANT: The caller should not hold onto the handles for a long time,
because holding them will delay servable loading and unloading.
:::
:::

[]{#a10694eb8c3e845e4738788092057b7ef}

[[◆ ](#a10694eb8c3e845e4738788092057b7ef)]{.permalink}ListAvailableServableIds() {#listavailableservableids .memtitle}
--------------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|                                   | [[pure                            |
|  -------------------------------- | virtual]{.mlabel}]{.mlabels}      |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| -------------- --- -- --- ------- |                                   |
|   virtual std::vector\<[Servable  |                                   |
| Id](structtensorflow_1_1serving_1 |                                   |
| _1ServableId.html){.el}\> tensorf |                                   |
| low::serving::Manager::ListAvaila |                                   |
| bleServableIds   (      )   const |                                   |
|                                   |                                   |
|  -------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| -------------- --- -- --- ------- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Gets a list of all available servable ids, i.e. each of these can be
retrieved using GetServableHandle.

Implemented in
[tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html#ac88da0268e401fa99bcd074e692ee709){.el},
[tensorflow::serving::ManagerWrapper](classtensorflow_1_1serving_1_1ManagerWrapper.html#a76a6e899de4dfca374b71c4ef415b3d0){.el},
[tensorflow::serving::CachingManager](classtensorflow_1_1serving_1_1CachingManager.html#af7ec61e19bcd1ac85a4c97c32e977ffe){.el},
[tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html#a3c004d32952596c1f5759b1cfcc3c639){.el},
and
[tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html#a058a76ee71c52d4a6319f14cd9b2ad69){.el}.
:::
:::

------------------------------------------------------------------------

The documentation for this class was generated from the following file:

-   tensorflow\_serving/core/[manager.h](manager_8h_source.html){.el}

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

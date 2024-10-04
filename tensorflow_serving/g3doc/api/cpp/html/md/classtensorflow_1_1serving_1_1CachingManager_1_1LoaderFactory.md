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
-   [LoaderFactory](classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Member Functions](#pub-methods) \| [List of all
members](classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::CachingManager::LoaderFactory Class
Reference[[abstract]{.mlabel}]{.mlabels}
:::
:::
:::

::: {.contents}
`#include <caching_manager.h>`

::: {.dynheader}
Inheritance diagram for
tensorflow::serving::CachingManager::LoaderFactory:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------
:::

virtual
[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.el}\<
std::unique\_ptr\<
[Loader](classtensorflow_1_1serving_1_1Loader.html){.el} \> \> 

[CreateLoader](classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory.html#ab95a61ff7c67b25e96594631207045a2){.el}
(const [ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el}
&servable\_id)=0

 

virtual int64\_t 

[GetServableVersion](classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory.html#ae3b86ce052eeee59a53ef0ab58080729){.el}
(const string &servable\_name, ServableRequest::AutoVersionPolicy
policy) const =0

 

[]{#details}

Detailed Description {#detailed-description .groupheader}
--------------------

::: {.textblock}
An abstraction for a loader-factory to map from a servable request to
the corresponding loader.
:::

Member Function Documentation {#member-function-documentation .groupheader}
-----------------------------

[]{#ab95a61ff7c67b25e96594631207045a2}

[[◆ ](#ab95a61ff7c67b25e96594631207045a2)]{.permalink}CreateLoader() {#createloader .memtitle}
--------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|                                   | [[pure                            |
|  -------------------------------- | virtual]{.mlabel}]{.mlabels}      |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------- --- - |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------- ---------------- --- -- |                                   |
|   virtual [ServableData](classte  |                                   |
| nsorflow_1_1serving_1_1ServableDa |                                   |
| ta.html){.el}\<std::unique\_ptr\< |                                   |
| [Loader](classtensorflow_1_1servi |                                   |
| ng_1_1Loader.html){.el}\> \> tens |                                   |
| orflow::serving::CachingManager:: |                                   |
| LoaderFactory::CreateLoader   (   |                                   |
|  const [ServableId](structtensorf |                                   |
| low_1_1serving_1_1ServableId.html |                                   |
| ){.el} &    *servable\_id*   )    |                                   |
|                                   |                                   |
|  -------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------- --- - |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------- ---------------- --- -- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Creates servable data consisting of the loader corresponding to the
servable-id. Any errors can be reported by embedding them in the
returned
[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.el}
item.

Implemented in
[tensorflow::serving::PathPrefixLoaderFactory](classtensorflow_1_1serving_1_1PathPrefixLoaderFactory.html#a9e0ecef7ee02c156984a710904b663a2){.el}.
:::
:::

[]{#ae3b86ce052eeee59a53ef0ab58080729}

[[◆ ](#ae3b86ce052eeee59a53ef0ab58080729)]{.permalink}GetServableVersion() {#getservableversion .memtitle}
--------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   -------------------             | [[pure                            |
| --------------------------------- | virtual]{.mlabel}]{.mlabels}      |
| --------------------------------- |                                   |
| ---- --- ------------------------ |                                   |
| ------------- ------------------- |                                   |
|   virtual int64\_t                |                                   |
| tensorflow::serving::CachingManag |                                   |
| er::LoaderFactory::GetServableVer |                                   |
| sion   (   const string &         |                                   |
|                 *servable\_name*, |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|                    ServableReques |                                   |
| t::AutoVersionPolicy    *policy*  |                                   |
|                                   |                                   |
|                                   |                                   |
|                                   |                                   |
|                    )              |                                   |
|                             const |                                   |
|   -------------------             |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ---- --- ------------------------ |                                   |
| ------------- ------------------- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Returns a version corresponding to the servable name, for the given
policy.

Implemented in
[tensorflow::serving::PathPrefixLoaderFactory](classtensorflow_1_1serving_1_1PathPrefixLoaderFactory.html#a77c005c15269b9996b55e1703658f8cc){.el}.
:::
:::

------------------------------------------------------------------------

The documentation for this class was generated from the following file:

-   tensorflow\_serving/core/[caching\_manager.h](caching__manager_8h_source.html){.el}

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

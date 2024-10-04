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
-   [PathPrefixLoaderFactory](classtensorflow_1_1serving_1_1PathPrefixLoaderFactory.html){.el}
:::
:::

::: {.header}
::: {.summary}
[Public Member Functions](#pub-methods) \| [List of all
members](classtensorflow_1_1serving_1_1PathPrefixLoaderFactory-members.html)
:::

::: {.headertitle}
::: {.title}
tensorflow::serving::PathPrefixLoaderFactory Class Reference
:::
:::
:::

::: {.contents}
`#include <caching_manager.h>`

::: {.dynheader}
Inheritance diagram for tensorflow::serving::PathPrefixLoaderFactory:
:::

::: {.dyncontent}
::: {.center}
![Inheritance
graph](classtensorflow_1_1serving_1_1PathPrefixLoaderFactory__inherit__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

::: {.dynheader}
Collaboration diagram for tensorflow::serving::PathPrefixLoaderFactory:
:::

::: {.dyncontent}
::: {.center}
![Collaboration
graph](classtensorflow_1_1serving_1_1PathPrefixLoaderFactory__coll__graph.png)
:::

[\[[legend](graph_legend.html)\]]{.legend}
:::

[]{#pub-methods} Public Member Functions {#public-member-functions .groupheader}
----------------------------------------
:::

[]{#ab3ed02c5720671062c9e068b48f076b5}  

**PathPrefixLoaderFactory** (const string &path\_prefix,
std::unique\_ptr\<
[StoragePathSourceAdapter](classtensorflow_1_1serving_1_1SourceAdapter.html){.el}
\> adapter)

 

[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.el}\<
std::unique\_ptr\<
[Loader](classtensorflow_1_1serving_1_1Loader.html){.el} \> \> 

[CreateLoader](classtensorflow_1_1serving_1_1PathPrefixLoaderFactory.html#a9e0ecef7ee02c156984a710904b663a2){.el}
(const [ServableId](structtensorflow_1_1serving_1_1ServableId.html){.el}
&id) override

 

int64\_t 

[GetServableVersion](classtensorflow_1_1serving_1_1PathPrefixLoaderFactory.html#a77c005c15269b9996b55e1703658f8cc){.el}
(const string &servable\_name, ServableRequest::AutoVersionPolicy
policy) const override

 

[]{#details}

Detailed Description {#detailed-description .groupheader}
--------------------

::: {.textblock}
A simple LoaderFactory that looks for a servable at a path formed by
concatenating a fixed path prefix with the servable\'s name. It assumes
that a given servable only has one version, namely version 0.
:::

Member Function Documentation {#member-function-documentation .groupheader}
-----------------------------

[]{#a9e0ecef7ee02c156984a710904b663a2}

[[◆ ](#a9e0ecef7ee02c156984a710904b663a2)]{.permalink}CreateLoader() {#createloader .memtitle}
--------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   ---------------------           | [[override]{.mla                  |
| --------------------------------- | bel}[virtual]{.mlabel}]{.mlabels} |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------------------------- --- - |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| --------- ---------------- --- -- |                                   |
|   [ServableData](clas             |                                   |
| stensorflow_1_1serving_1_1Servabl |                                   |
| eData.html){.el}\< std::unique\_p |                                   |
| tr\< [Loader](classtensorflow_1_1 |                                   |
| serving_1_1Loader.html){.el} \> \ |                                   |
| > tensorflow::serving::PathPrefix |                                   |
| LoaderFactory::CreateLoader   (   |                                   |
|  const [ServableId](structtensorf |                                   |
| low_1_1serving_1_1ServableId.html |                                   |
| ){.el} &    *servable\_id*   )    |                                   |
|   ---------------------           |                                   |
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

Implements
[tensorflow::serving::CachingManager::LoaderFactory](classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory.html#ab95a61ff7c67b25e96594631207045a2){.el}.
:::
:::

[]{#a77c005c15269b9996b55e1703658f8cc}

[[◆ ](#a77c005c15269b9996b55e1703658f8cc)]{.permalink}GetServableVersion() {#getservableversion .memtitle}
--------------------------------------------------------------------------

::: {.memitem}
::: {.memproto}
+-----------------------------------+-----------------------------------+
|   -----                           | [[override]{.mla                  |
| --------------------------------- | bel}[virtual]{.mlabel}]{.mlabels} |
| --------------------------------- |                                   |
| ---- --- ------------------------ |                                   |
| ------------- ------------------- |                                   |
|   int                             |                                   |
| 64\_t tensorflow::serving::PathPr |                                   |
| efixLoaderFactory::GetServableVer |                                   |
| sion   (   const string &         |                                   |
|                 *servable\_name*, |                                   |
|                                   |                                   |
|                                   |                                   |
|                    ServableReques |                                   |
| t::AutoVersionPolicy    *policy*  |                                   |
|                                   |                                   |
|                                   |                                   |
|                    )              |                                   |
|                             const |                                   |
|   -----                           |                                   |
| --------------------------------- |                                   |
| --------------------------------- |                                   |
| ---- --- ------------------------ |                                   |
| ------------- ------------------- |                                   |
+-----------------------------------+-----------------------------------+
:::

::: {.memdoc}
Returns a version corresponding to the servable name, for the given
policy.

Implements
[tensorflow::serving::CachingManager::LoaderFactory](classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory.html#ae3b86ce052eeee59a53ef0ab58080729){.el}.
:::
:::

------------------------------------------------------------------------

The documentation for this class was generated from the following files:

-   tensorflow\_serving/core/[caching\_manager.h](caching__manager_8h_source.html){.el}
-   tensorflow\_serving/core/caching\_manager.cc

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

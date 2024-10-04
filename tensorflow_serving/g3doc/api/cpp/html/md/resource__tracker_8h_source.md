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
-   [tensorflow\_serving](dir_bbc8937306723ff096d79d77f4a73363.html){.el}
-   [resources](dir_707e45924ba4592177e9789700f2f284.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
resource\_tracker.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2016 Google Inc. All Rights
Reserved.]{.comment}
:::

::: {.line}
[]{#l00002}[ 2]{.lineno} []{.comment}
:::

::: {.line}
[]{#l00003}[ 3]{.lineno} [Licensed under the Apache License, Version 2.0
(the \"License\");]{.comment}
:::

::: {.line}
[]{#l00004}[ 4]{.lineno} [you may not use this file except in compliance
with the License.]{.comment}
:::

::: {.line}
[]{#l00005}[ 5]{.lineno} [You may obtain a copy of the License
at]{.comment}
:::

::: {.line}
[]{#l00006}[ 6]{.lineno} []{.comment}
:::

::: {.line}
[]{#l00007}[ 7]{.lineno} [
http://www.apache.org/licenses/LICENSE-2.0]{.comment}
:::

::: {.line}
[]{#l00008}[ 8]{.lineno} []{.comment}
:::

::: {.line}
[]{#l00009}[ 9]{.lineno} [Unless required by applicable law or agreed to
in writing, software]{.comment}
:::

::: {.line}
[]{#l00010}[ 10]{.lineno} [distributed under the License is distributed
on an \"AS IS\" BASIS,]{.comment}
:::

::: {.line}
[]{#l00011}[ 11]{.lineno} [WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND,
either express or implied.]{.comment}
:::

::: {.line}
[]{#l00012}[ 12]{.lineno} [See the License for the specific language
governing permissions and]{.comment}
:::

::: {.line}
[]{#l00013}[ 13]{.lineno} [limitations under the License.]{.comment}
:::

::: {.line}
[]{#l00014}[
14]{.lineno} [==============================================================================\*/]{.comment}
:::

::: {.line}
[]{#l00015}[ 15]{.lineno} 
:::

::: {.line}
[]{#l00016}[ 16]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_RESOURCES\_RESOURCE\_TRACKER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_RESOURCES\_RESOURCE\_TRACKER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} 
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow\_serving/core/loader.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow\_serving/resources/resource\_util.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} 
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} 
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [// A class that keeps track of the available
and spoken-for resources in a]{.comment}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [// serving system. It can decide whether
enough resources are available to load]{.comment}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [// a new servable.]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// This class is not thread-safe.]{.comment}
:::

::: {.line}
[]{#l00033}[
[33](classtensorflow_1_1serving_1_1ResourceTracker.html){.line}]{.lineno} [class
]{.keyword}[ResourceTracker](classtensorflow_1_1serving_1_1ResourceTracker.html){.code}
{
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  [static]{.keyword} Status
Create([const]{.keyword} ResourceAllocation& total\_resources,
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  std::unique\_ptr\<ResourceUtil\> util,
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  std::unique\_ptr\<ResourceTracker\>\*
tracker);
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
\~[ResourceTracker](classtensorflow_1_1serving_1_1ResourceTracker.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} 
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [// Determines whether enough resources are
available to load \'servable\', i.e.]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [// is it guaranteed to fit in the gap
between the used and total resources?]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [// If so, adds the servable\'s resource
allocation to the used resources and]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [// sets \'success\' to true. Otherwise,
leaves the used resources unchanged and]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [// sets \'success\' to false. Upon
encountering illegal data, e.g. if \'servable\']{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [// emits an invalid resource estimate,
returns an error status.]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  Status ReserveResources([const]{.keyword}
[Loader](classtensorflow_1_1serving_1_1Loader.html){.code}& servable,
[bool]{.keywordtype}\* success);
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [// Recomputes the used resources from
scratch, given every loader whose]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [// servable is either loaded or
transitioning to/from being loaded,]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [// specifically:]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [// \* servables approved for loading (their
resources are reserved),]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [// \* servables in the process of
loading,]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [// \* servables that are currently
loaded,]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [// \* servables in the process of
unloading.]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  Status
RecomputeUsedResources([const]{.keyword} std::vector\<const Loader\*\>&
servables);
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} 
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [const]{.keyword} ResourceAllocation&
total\_resources()[ const ]{.keyword}{ [return]{.keywordflow}
total\_resources\_; }
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [const]{.keyword} ResourceAllocation&
used\_resources()[ const ]{.keyword}{ [return]{.keywordflow}
used\_resources\_; }
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} 
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} 
[ResourceTracker](classtensorflow_1_1serving_1_1ResourceTracker.html){.code}([const]{.keyword}
ResourceAllocation& total\_resources,
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  std::unique\_ptr\<ResourceUtil\> util);
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} 
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  [// A ResourceUtil object to use for
operations and comparisons on allocations.]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [const]{.keyword}
std::unique\_ptr\<ResourceUtil\> util\_;
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} 
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [// The total resources the system has. Must
be bound. Kept normalized.]{.comment}
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [const]{.keyword} ResourceAllocation
total\_resources\_;
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [// The resources currently set aside for
servables that are loaded, or]{.comment}
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  [// transitioning to/from being loaded. May
be bound or unbound. Kept]{.comment}
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [// normalized.]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  [// Under normal conditions, less than or
equal to \'total\_resources\_\'.]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  ResourceAllocation used\_resources\_;
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} 
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([ResourceTracker](classtensorflow_1_1serving_1_1ResourceTracker.html){.code});
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} };
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} 
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} 
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_RESOURCES\_RESOURCE\_TRACKER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1Loader_html .ttc}
::: {.ttname}
[tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html)
:::

::: {.ttdef}
**Definition:** loader.h:56
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ResourceTracker_html .ttc}
::: {.ttname}
[tensorflow::serving::ResourceTracker](classtensorflow_1_1serving_1_1ResourceTracker.html)
:::

::: {.ttdef}
**Definition:** resource\_tracker.h:33
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

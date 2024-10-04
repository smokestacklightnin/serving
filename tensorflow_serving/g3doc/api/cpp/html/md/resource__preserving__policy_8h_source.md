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
-   [core](dir_517df0ab1daf8f221f60ae5135602a49.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
resource\_preserving\_policy.h
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
TENSORFLOW\_SERVING\_CORE\_RESOURCE\_PRESERVING\_POLICY\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_RESOURCE\_PRESERVING\_POLICY\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"absl/types/optional.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow\_serving/core/aspired\_version\_policy.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow\_serving/core/loader\_harness.h\"]{.preprocessor}
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
[]{#l00028}[ 28]{.lineno} [// ServablePolicy that eagerly unloads any
no-longer-aspired versions of a]{.comment}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [// servable stream and only after done
unloading, loads newly aspired versions]{.comment}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [// in the order of descending version
number.]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// This policy minimizes resource consumption
with the trade-off of temporary]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// servable unavailability while all old
versions unload followed by the new]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// versions loading.]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [// Servables with a single version consuming
the majority of their host\'s]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [// resources must use this policy to prevent
deadlock. Other typical use-cases]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [// will be for multi-servable environments
where clients can tolerate brief]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [// interruptions to a single servable\'s
availability on a replica.]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [// NB: This policy does not in any way solve
cross-replica availability.]{.comment}
:::

::: {.line}
[]{#l00042}[
[42](classtensorflow_1_1serving_1_1ResourcePreservingPolicy.html){.line}]{.lineno} [class
]{.keyword}[ResourcePreservingPolicy](classtensorflow_1_1serving_1_1ResourcePreservingPolicy.html){.code}
final : [public]{.keyword}
[AspiredVersionPolicy](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html){.code}
{
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  absl::optional\<ServableAction\>
[GetNextAction](classtensorflow_1_1serving_1_1ResourcePreservingPolicy.html#ab1fa4fa3d4a8dc165bb86f5377436532){.code}(
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [const]{.keyword}
std::vector\<AspiredServableStateSnapshot\>& all\_versions)
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [const override]{.keyword};
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} };
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} 
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_RESOURCE\_PRESERVING\_POLICY\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1AspiredVersionPolicy_html .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionPolicy](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html)
:::

::: {.ttdef}
**Definition:** aspired\_version\_policy.h:48
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ResourcePreservingPolicy_html .ttc}
::: {.ttname}
[tensorflow::serving::ResourcePreservingPolicy](classtensorflow_1_1serving_1_1ResourcePreservingPolicy.html)
:::

::: {.ttdef}
**Definition:** resource\_preserving\_policy.h:42
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ResourcePreservingPolicy_html_ab1fa4fa3d4a8dc165bb86f5377436532 .ttc}
::: {.ttname}
[tensorflow::serving::ResourcePreservingPolicy::GetNextAction](classtensorflow_1_1serving_1_1ResourcePreservingPolicy.html#ab1fa4fa3d4a8dc165bb86f5377436532)
:::

::: {.ttdeci}
absl::optional\< ServableAction \> GetNextAction(const std::vector\<
AspiredServableStateSnapshot \> &all\_versions) const override
:::

::: {.ttdef}
**Definition:** resource\_preserving\_policy.cc:25
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

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
availability\_preserving\_policy.h
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
TENSORFLOW\_SERVING\_CORE\_AVAILABILITY\_PRESERVING\_POLICY\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_AVAILABILITY\_PRESERVING\_POLICY\_H\_]{.preprocessor}
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
\"tensorflow\_serving/core/aspired\_version\_policy.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow\_serving/core/loader\_harness.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} 
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} 
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [// AspiredVersionPolicy that provides
servable availability with the trade-off]{.comment}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [// of temporary increased resource
consumption while newly-aspired versions load]{.comment}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [// followed by newly-un-aspired versions
unloading. At the same time, it tries]{.comment}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [// to minimize the resource usage caused by
loading more versions than needed to]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [// maintain availability.]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// Here is a detailed description of how this
policy works:]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// First, if there are any unaspired loaded
versions, we unload the smallest]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [// such version, \*unless\* that is the only
loaded version (to avoid compromising]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [// availability).]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [// Second, if there are no non-aspired
versions we are permitted to unload, we]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [// load the aspired new version with the
highest version number.]{.comment}
:::

::: {.line}
[]{#l00039}[
[39](classtensorflow_1_1serving_1_1AvailabilityPreservingPolicy.html){.line}]{.lineno} [class
]{.keyword}[AvailabilityPreservingPolicy](classtensorflow_1_1serving_1_1AvailabilityPreservingPolicy.html){.code}
final : [public]{.keyword}
[AspiredVersionPolicy](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html){.code}
{
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  absl::optional\<ServableAction\>
[GetNextAction](classtensorflow_1_1serving_1_1AvailabilityPreservingPolicy.html#a3e7f155e7dd0bb9fadacfdfe4cad5d4c){.code}(
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [const]{.keyword}
std::vector\<AspiredServableStateSnapshot\>& all\_versions)
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [const override]{.keyword};
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} };
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} 
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_AVAILABILITY\_PRESERVING\_POLICY\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1AspiredVersionPolicy_html .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionPolicy](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html)
:::

::: {.ttdef}
**Definition:** aspired\_version\_policy.h:48
:::
:::

::: {#aclasstensorflow_1_1serving_1_1AvailabilityPreservingPolicy_html .ttc}
::: {.ttname}
[tensorflow::serving::AvailabilityPreservingPolicy](classtensorflow_1_1serving_1_1AvailabilityPreservingPolicy.html)
:::

::: {.ttdef}
**Definition:** availability\_preserving\_policy.h:39
:::
:::

::: {#aclasstensorflow_1_1serving_1_1AvailabilityPreservingPolicy_html_a3e7f155e7dd0bb9fadacfdfe4cad5d4c .ttc}
::: {.ttname}
[tensorflow::serving::AvailabilityPreservingPolicy::GetNextAction](classtensorflow_1_1serving_1_1AvailabilityPreservingPolicy.html#a3e7f155e7dd0bb9fadacfdfe4cad5d4c)
:::

::: {.ttdeci}
absl::optional\< ServableAction \> GetNextAction(const std::vector\<
AspiredServableStateSnapshot \> &all\_versions) const override
:::

::: {.ttdef}
**Definition:** availability\_preserving\_policy.cc:48
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

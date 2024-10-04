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
-   [test\_util](dir_306b000a767a3d8d2b2841959aa6b5f0.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
availability\_test\_util.h
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
[]{#l00016}[ 16]{.lineno} [// Methods related to the availability of
servables, that are useful in writing]{.comment}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [// tests. (Not intended for production
use.)]{.comment}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_AVAILABILITY\_TEST\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_AVAILABILITY\_TEST\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} 
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_state\_monitor.h\"]{.preprocessor}
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
[]{#l00026}[ 26]{.lineno} [namespace ]{.keyword}test\_util {
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} 
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [// Waits until \'monitor\' shows that the
manager state of \'servable\' is one of]{.comment}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [// \'states\'.]{.comment}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [void]{.keywordtype}
WaitUntilServableManagerStateIsOneOf(
:::

::: {.line}
[]{#l00031}[ 31]{.lineno}  [const]{.keyword} ServableStateMonitor&
monitor, [const]{.keyword} ServableId& servable,
:::

::: {.line}
[]{#l00032}[ 32]{.lineno}  [const]{.keyword}
std::vector\<ServableState::ManagerState\>& states);
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} 
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// Waits until \'monitor\' shows that the
manager state servable ids is]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [// kAvailable.]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [void]{.keywordtype}
WaitUntilVersionsAvailable([const]{.keyword} ServableStateMonitor&
monitor,
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [const]{.keyword} [string]{.keywordtype}&
servable\_id\_name,
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  absl::Span\<const int64\_t\>
servable\_id\_versions);
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} 
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} } [// namespace test\_util]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} 
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_AVAILABILITY\_TEST\_UTIL\_H\_]{.comment}
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

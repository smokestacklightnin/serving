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
load\_servables\_fast.h
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
TENSORFLOW\_SERVING\_CORE\_LOAD\_SERVABLES\_FAST\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_LOAD\_SERVABLES\_FAST\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<functional\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} 
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow/core/platform/cpu\_info.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow\_serving/core/aspired\_versions\_manager.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/core/loader.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/core/manager.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_state\_monitor.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} 
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} 
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// Connects \'source\' to \'manager\', and
speeds up loading of the servables]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// matching \'initial\_servables\'. The
speeding up is accomplished by boosting the]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// number of threads used for loading until
the initial servables have been]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [// loaded, and then resetting it to the
manager\'s originally configured value.]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} Status ConnectSourceWithFastInitialLoad(
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  AspiredVersionsManager\* manager,
Source\<std::unique\_ptr\<Loader\>\>\* source,
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  ServableStateMonitor\*
servable\_state\_monitor,
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [const]{.keyword}
std::vector\<ServableRequest\>& initial\_servables,
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  uint32 num\_threads = 4 \*
port::NumSchedulableCPUs());
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} 
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [// Like ConnectSourceWithFastInitialLoad(),
but with multiple sources.]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} Status ConnectSourcesWithFastInitialLoad(
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  AspiredVersionsManager\* manager,
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
std::vector\<Source\<std::unique\_ptr\<Loader\>\>\*\> sources,
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  ServableStateMonitor\*
servable\_state\_monitor,
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [const]{.keyword}
std::vector\<ServableRequest\>& initial\_servables,
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  uint32 num\_threads = 4 \*
port::NumSchedulableCPUs());
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} [// Implementation detail. API readers may
skip.]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} []{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [namespace ]{.keyword}internal {
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} 
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} Status ConnectSourcesWithFastInitialLoad(
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  AspiredVersionsManager\* manager,
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} 
std::vector\<Source\<std::unique\_ptr\<Loader\>\>\*\> sources,
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [const]{.keyword} std::function\<Status()\>&
wait\_until\_loaded\_fn, uint32 num\_threads);
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} uint32
GetManagerNumLoadThreads(AspiredVersionsManager\* manager);
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} std::function\<void([const]{.keyword}
uint32)\> SetManagerNumLoadThreadsNotifier(
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  AspiredVersionsManager\* manager);
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} } [// namespace internal]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} 
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_LOAD\_SERVABLES\_FAST\_H\_]{.comment}
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

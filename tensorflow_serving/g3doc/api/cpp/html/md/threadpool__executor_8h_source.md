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
-   [util](dir_1303efdc8de326749a332c6a57186055.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
threadpool\_executor.h
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
TENSORFLOW\_SERVING\_UTIL\_THREADPOOL\_EXECUTOR\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_UTIL\_THREADPOOL\_EXECUTOR\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<functional\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow/core/lib/core/threadpool.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow/core/platform/env.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow\_serving/util/executor.h\"]{.preprocessor}
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
[]{#l00028}[ 28]{.lineno} [// An executor which uses a pool of threads
to execute the scheduled closures.]{.comment}
:::

::: {.line}
[]{#l00029}[
[29](classtensorflow_1_1serving_1_1ThreadPoolExecutor.html){.line}]{.lineno} [class
]{.keyword}[ThreadPoolExecutor](classtensorflow_1_1serving_1_1ThreadPoolExecutor.html){.code}
: [public]{.keyword}
[Executor](classtensorflow_1_1serving_1_1Executor.html){.code} {
:::

::: {.line}
[]{#l00030}[ 30]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00031}[ 31]{.lineno}  [// Constructs a threadpool that has
\'num\_threads\' threads with specified]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno}  [// \'thread\_pool\_name\'. Env is used to
start the thread.]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  [// REQUIRES: num\_threads \> 0.]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} 
[ThreadPoolExecutor](classtensorflow_1_1serving_1_1ThreadPoolExecutor.html){.code}(Env\*
env, [const]{.keyword} [string]{.keywordtype}& thread\_pool\_name,
[int]{.keywordtype} num\_threads);
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [// Waits until all scheduled work has
finished and then destroy the set of]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  [// threads.]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} 
\~[ThreadPoolExecutor](classtensorflow_1_1serving_1_1ThreadPoolExecutor.html){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [void]{.keywordtype}
[Schedule](classtensorflow_1_1serving_1_1ThreadPoolExecutor.html#a5d81e166c32207d3ce4c378927e0f131){.code}(std::function\<[void]{.keywordtype}()\>
fn) [override]{.keyword};
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  thread::ThreadPool thread\_pool\_;
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([ThreadPoolExecutor](classtensorflow_1_1serving_1_1ThreadPoolExecutor.html){.code});
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
TENSORFLOW\_SERVING\_UTIL\_THREADPOOL\_EXECUTOR\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1Executor_html .ttc}
::: {.ttname}
[tensorflow::serving::Executor](classtensorflow_1_1serving_1_1Executor.html)
:::

::: {.ttdef}
**Definition:** executor.h:27
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ThreadPoolExecutor_html .ttc}
::: {.ttname}
[tensorflow::serving::ThreadPoolExecutor](classtensorflow_1_1serving_1_1ThreadPoolExecutor.html)
:::

::: {.ttdef}
**Definition:** threadpool\_executor.h:29
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ThreadPoolExecutor_html_a5d81e166c32207d3ce4c378927e0f131 .ttc}
::: {.ttname}
[tensorflow::serving::ThreadPoolExecutor::Schedule](classtensorflow_1_1serving_1_1ThreadPoolExecutor.html#a5d81e166c32207d3ce4c378927e0f131)
:::

::: {.ttdeci}
void Schedule(std::function\< void()\> fn) override
:::

::: {.ttdef}
**Definition:** threadpool\_executor.cc:29
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

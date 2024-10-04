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
inline\_executor.h
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
TENSORFLOW\_SERVING\_UTIL\_INLINE\_EXECUTOR\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_UTIL\_INLINE\_EXECUTOR\_H\_]{.preprocessor}
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
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow\_serving/util/executor.h\"]{.preprocessor}
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
[]{#l00027}[ 27]{.lineno} [// An InlineExecutor is a trivial executor
that immediately executes the closure]{.comment}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [// given to it. It\'s useful as a fake, and
in cases where an executor is needed,]{.comment}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [// but multi-threadedness is not.]{.comment}
:::

::: {.line}
[]{#l00030}[
[30](classtensorflow_1_1serving_1_1InlineExecutor.html){.line}]{.lineno} [class
]{.keyword}[InlineExecutor](classtensorflow_1_1serving_1_1InlineExecutor.html){.code}
: [public]{.keyword}
[Executor](classtensorflow_1_1serving_1_1Executor.html){.code} {
:::

::: {.line}
[]{#l00031}[ 31]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} 
[InlineExecutor](classtensorflow_1_1serving_1_1InlineExecutor.html){.code}();
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} 
\~[InlineExecutor](classtensorflow_1_1serving_1_1InlineExecutor.html){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  [void]{.keywordtype}
[Schedule](classtensorflow_1_1serving_1_1InlineExecutor.html#a4787bb65866f0b4746d65103cc17761a){.code}(std::function\<[void]{.keywordtype}()\>
fn) [override]{.keyword};
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} };
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} 
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_UTIL\_INLINE\_EXECUTOR\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1Executor_html .ttc}
::: {.ttname}
[tensorflow::serving::Executor](classtensorflow_1_1serving_1_1Executor.html)
:::

::: {.ttdef}
**Definition:** executor.h:27
:::
:::

::: {#aclasstensorflow_1_1serving_1_1InlineExecutor_html .ttc}
::: {.ttname}
[tensorflow::serving::InlineExecutor](classtensorflow_1_1serving_1_1InlineExecutor.html)
:::

::: {.ttdef}
**Definition:** inline\_executor.h:30
:::
:::

::: {#aclasstensorflow_1_1serving_1_1InlineExecutor_html_a4787bb65866f0b4746d65103cc17761a .ttc}
::: {.ttname}
[tensorflow::serving::InlineExecutor::Schedule](classtensorflow_1_1serving_1_1InlineExecutor.html#a4787bb65866f0b4746d65103cc17761a)
:::

::: {.ttdeci}
void Schedule(std::function\< void()\> fn) override
:::

::: {.ttdef}
**Definition:** inline\_executor.cc:27
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

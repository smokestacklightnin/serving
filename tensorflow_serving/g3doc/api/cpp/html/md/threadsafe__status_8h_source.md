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
-   [batching](dir_02baa623061b1c8249c9d45b41261099.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
threadsafe\_status.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2020 Google Inc. All Rights
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
TENSORFLOW\_CORE\_KERNELS\_BATCHING\_UTIL\_THREADSAFE\_STATUS\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_CORE\_KERNELS\_BATCHING\_UTIL\_THREADSAFE\_STATUS\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include
\"tensorflow/core/platform/mutex.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include
\"tensorflow/core/platform/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow/core/platform/thread\_annotations.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} 
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [// TODO(b/161829688):]{.comment}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [// Possibly merge ThreadSafeStatus
implementation in TF and TF serving, when]{.comment}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [// TF exposes ThreadSafeStatus in its public
API (i.e., an release candidate).]{.comment}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [// Wrapper class to allow both lock-free
construction and concurrent updates on]{.comment}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [// a \'status\'.]{.comment}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [// Example Usage:]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// std::thread threads\[2\];]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// ThreadSafeStatus
thread\_safe\_status;]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// threads\[0\] = std::thread(\[&\]()
{]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [// status.Update(errors::Internal(\"internal
error\"));]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [// });]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [// threads\[1\] = std::thread(\[&\]()
{]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [//
status.Update(errors::InvalidArgument(\"invalid argument\"));]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [// });]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [// threads\[0\].Join();]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [// threads\[1\].Join();]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [// NOTE:]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [// When updated in a multi-threading setup,
only the first error is retained.]{.comment}
:::

::: {.line}
[]{#l00045}[
[45](classtensorflow_1_1serving_1_1ThreadSafeStatus.html){.line}]{.lineno} [class
]{.keyword}[ThreadSafeStatus](classtensorflow_1_1serving_1_1ThreadSafeStatus.html){.code}
{
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [const]{.keyword} Status& status()
[const]{.keyword}& TF\_LOCKS\_EXCLUDED(mutex\_);
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  Status status() &&
TF\_LOCKS\_EXCLUDED(mutex\_);
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [// Retains the first error status: replaces
the current status with]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [// \`new\_status\` if \`new\_status\` is not
OK and the previous status is OK.]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [void]{.keywordtype} Update([const]{.keyword}
Status& new\_status) TF\_LOCKS\_EXCLUDED(mutex\_);
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [void]{.keywordtype} Update(Status&&
new\_status) TF\_LOCKS\_EXCLUDED(mutex\_);
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} 
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [mutable]{.keyword} mutex mutex\_;
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  Status status\_ TF\_GUARDED\_BY(mutex\_);
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} };
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} 
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_CORE\_KERNELS\_BATCHING\_UTIL\_THREADSAFE\_STATUS\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1ThreadSafeStatus_html .ttc}
::: {.ttname}
[tensorflow::serving::ThreadSafeStatus](classtensorflow_1_1serving_1_1ThreadSafeStatus.html)
:::

::: {.ttdef}
**Definition:** threadsafe\_status.h:45
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

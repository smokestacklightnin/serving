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
incremental\_barrier.h
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
TENSORFLOW\_CORE\_KERNELS\_BATCHING\_UTIL\_INCREMENTAL\_BARRIER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_CORE\_KERNELS\_BATCHING\_UTIL\_INCREMENTAL\_BARRIER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<atomic\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<functional\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} 
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} 
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [class ]{.keyword}InternalIncrementalBarrier;
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} 
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [// BarrierClosure (see]{.comment}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [//
https://github.com/chromium/chromium/blob/master/base/barrier\_closure.h)]{.comment}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [// executes a callback after it has been
invoked \|num\_closures\| times.]{.comment}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [// Plus, \`BarrierClosure\` is a
continuation-passing style abstraction and self-]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [// deleting.]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} 
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// IncrementalBarrier is a convenience class
to be used in place of a barrier]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// closure, which is particularly helpful
(e.g. simplify code) because callers]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [// don\'t need to calculate the
\|num\_closures\| beforehand.]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [// Example Usage:]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [// void MakeCalls() {]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [// typedef std::function\<void()\>
Callback;]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [// typedef std::function\<void(Callback)\>
OtherCallback;]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [// Callback done\_callback = \...]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [// OtherCallback cb1 = \...]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [// OtherCallback cb2 = \...]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [// std::thread threads\[2\];]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [// {]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [// IncrementalBarrier
barrier(done\_callback);]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [// threads\[0\] =
std::thread(cb1(barrier.Inc());]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [// threads\[1\] =
std::thread(cb2(barrier.Inc());]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [// \... at this moment, \`barrier\` is
incremented twice, and then]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [// destructed\....]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [// threads\[0\].join();]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} [// threads\[1\].join();]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} [// \`done\_callback\` will be called when
both conditions are true:]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} [// 1) after \`barrier\` is
destructed.]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} [// 2) Each \`BarrierCallback\` returned by
\`Inc\` is called.]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} [// This class is thread-safe.]{.comment}
:::

::: {.line}
[]{#l00060}[
[60](classtensorflow_1_1serving_1_1IncrementalBarrier.html){.line}]{.lineno} [class
]{.keyword}[IncrementalBarrier](classtensorflow_1_1serving_1_1IncrementalBarrier.html){.code}
{
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [typedef]{.keyword} std::function\<void()\>
DoneCallback;
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [typedef]{.keyword} std::function\<void()\>
BarrierCallback;
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  [explicit]{.keyword}
[IncrementalBarrier](classtensorflow_1_1serving_1_1IncrementalBarrier.html){.code}(DoneCallback
callback);
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} 
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} 
\~[IncrementalBarrier](classtensorflow_1_1serving_1_1IncrementalBarrier.html){.code}();
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [// Returns a BarrierCallback (std::function)
that individual task call to]{.comment}
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [// signal its completeness.]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [// The returned BarrierCallback outlives
this \`IncrementalBarrier\` instance.]{.comment}
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  [// Furthermore, each task should eventually
call the returned function, or]{.comment}
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [// else done\_callback wouldn\'t be
called.]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  BarrierCallback Inc();
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} 
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [// self-deleting, thereby not owned by
\'IncrementalBarrier\'.]{.comment}
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} 
[InternalIncrementalBarrier](classtensorflow_1_1serving_1_1InternalIncrementalBarrier.html){.code}\*
internal\_barrier\_;
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
TENSORFLOW\_CORE\_KERNELS\_BATCHING\_UTIL\_INCREMENTAL\_BARRIER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1IncrementalBarrier_html .ttc}
::: {.ttname}
[tensorflow::serving::IncrementalBarrier](classtensorflow_1_1serving_1_1IncrementalBarrier.html)
:::

::: {.ttdef}
**Definition:** incremental\_barrier.h:60
:::
:::

::: {#aclasstensorflow_1_1serving_1_1InternalIncrementalBarrier_html .ttc}
::: {.ttname}
[tensorflow::serving::InternalIncrementalBarrier](classtensorflow_1_1serving_1_1InternalIncrementalBarrier.html)
:::

::: {.ttdef}
**Definition:** incremental\_barrier.cc:28
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

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
-   [net\_http](dir_3615685a5307a228eaa5ec677f0aeb77.html){.el}
-   [internal](dir_0b5bf4ec89be083080e2df7576ab401e.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
fixed\_thread\_pool.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2018 Google Inc. All Rights
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
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_INTERNAL\_FIXED\_THREAD\_POOL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_INTERNAL\_FIXED\_THREAD\_POOL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<cassert\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<functional\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<queue\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<thread\>]{.preprocessor} [//
NOLINT(build/c++11)]{.comment}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} 
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"absl/base/thread\_annotations.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"absl/synchronization/mutex.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} 
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [namespace ]{.keyword}net\_http {
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} 
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// A simple fixed-size ThreadPool
implementation for tests.]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// The initial version is copied
from]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [//
absl/synchronization/internal/thread\_pool.h]{.comment}
:::

::: {.line}
[]{#l00035}[
[35](classtensorflow_1_1serving_1_1net__http_1_1FixedThreadPool.html){.line}]{.lineno} [class
]{.keyword}[FixedThreadPool](classtensorflow_1_1serving_1_1net__http_1_1FixedThreadPool.html){.code}
{
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [explicit]{.keyword}
[FixedThreadPool](classtensorflow_1_1serving_1_1net__http_1_1FixedThreadPool.html){.code}([int]{.keywordtype}
num\_threads) {
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  [for]{.keywordflow} ([int]{.keywordtype} i =
0; i \< num\_threads; ++i) {
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} 
threads\_.push\_back(std::thread(&FixedThreadPool::WorkLoop,
[this]{.keyword}));
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  }
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  }
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} 
[FixedThreadPool](classtensorflow_1_1serving_1_1net__http_1_1FixedThreadPool.html){.code}([const]{.keyword}
[FixedThreadPool](classtensorflow_1_1serving_1_1net__http_1_1FixedThreadPool.html){.code}
&) = [delete]{.keyword};
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
[FixedThreadPool](classtensorflow_1_1serving_1_1net__http_1_1FixedThreadPool.html){.code}
&operator=([const]{.keyword}
[FixedThreadPool](classtensorflow_1_1serving_1_1net__http_1_1FixedThreadPool.html){.code}
&) = [delete]{.keyword};
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} 
\~[FixedThreadPool](classtensorflow_1_1serving_1_1net__http_1_1FixedThreadPool.html){.code}()
{
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  {
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  absl::MutexLock l(&mu\_);
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [for]{.keywordflow} ([int]{.keywordtype} i =
0; i \< threads\_.size(); ++i) {
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  queue\_.push([nullptr]{.keyword}); [//
Shutdown signal.]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  }
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  }
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [for]{.keywordflow} ([auto]{.keyword} &t :
threads\_) {
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  t.join();
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  }
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  }
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} 
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [// Schedule a function to be run on a
ThreadPool thread immediately.]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [void]{.keywordtype}
Schedule(std::function\<[void]{.keywordtype}()\> func) {
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  assert(func != [nullptr]{.keyword});
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  absl::MutexLock l(&mu\_);
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  queue\_.push(std::move(func));
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  }
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [bool]{.keywordtype} WorkAvailable()
[const]{.keyword} ABSL\_EXCLUSIVE\_LOCKS\_REQUIRED(mu\_) {
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [return]{.keywordflow} !queue\_.empty();
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  }
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [void]{.keywordtype} WorkLoop() {
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  [while]{.keywordflow} ([true]{.keyword}) {
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  std::function\<void()\> func;
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  {
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  absl::MutexLock l(&mu\_);
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  mu\_.Await(absl::Condition([this]{.keyword},
&FixedThreadPool::WorkAvailable));
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  func = std::move(queue\_.front());
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  queue\_.pop();
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  }
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  [if]{.keywordflow} (func ==
[nullptr]{.keyword}) { [// Shutdown signal.]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [break]{.keywordflow};
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  }
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  func();
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  }
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  }
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} 
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  absl::Mutex mu\_;
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  std::queue\<std::function\<void()\>\> queue\_
ABSL\_GUARDED\_BY(mu\_);
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  std::vector\<std::thread\> threads\_;
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} };
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} 
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} } [// namespace net\_http]{.comment}
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} 
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_INTERNAL\_FIXED\_THREAD\_POOL\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1net__http_1_1FixedThreadPool_html .ttc}
::: {.ttname}
[tensorflow::serving::net\_http::FixedThreadPool](classtensorflow_1_1serving_1_1net__http_1_1FixedThreadPool.html)
:::

::: {.ttdef}
**Definition:** fixed\_thread\_pool.h:35
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

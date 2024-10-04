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
-   [servables](dir_e240d895a087fc4ce46e8f4c52318018.html){.el}
-   [tensorflow](dir_143c99ffaf6c8b3b63b06c22e49d7998.html){.el}
-   [test\_util](dir_02e7f11df71bfe34e46d134dc12d183d.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
fake\_thread\_pool\_factory.h
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
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_TEST\_UTIL\_FAKE\_THREAD\_POOL\_FACTORY\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_TEST\_UTIL\_FAKE\_THREAD\_POOL\_FACTORY\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow/core/platform/threadpool.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/test\_util/fake\_thread\_pool\_factory.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/thread\_pool\_factory.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} 
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [namespace ]{.keyword}test\_util {
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} 
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [// A fake ThreadPoolFactory that returns the
given inter- and intra-op thread]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// pools.]{.comment}
:::

::: {.line}
[]{#l00033}[
[33](classtensorflow_1_1serving_1_1test__util_1_1FakeThreadPoolFactory.html){.line}]{.lineno} [class
]{.keyword}[FakeThreadPoolFactory](classtensorflow_1_1serving_1_1test__util_1_1FakeThreadPoolFactory.html){.code}
final : [public]{.keyword}
[ThreadPoolFactory](classtensorflow_1_1serving_1_1ThreadPoolFactory.html){.code}
{
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  [static]{.keyword} Status
Create([const]{.keyword} FakeThreadPoolFactoryConfig& config,
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  std::unique\_ptr\<ThreadPoolFactory\>\*
result);
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} 
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  [explicit]{.keyword}
[FakeThreadPoolFactory](classtensorflow_1_1serving_1_1test__util_1_1FakeThreadPoolFactory.html){.code}([const]{.keyword}
FakeThreadPoolFactoryConfig& config) {}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [virtual]{.keyword}
\~[FakeThreadPoolFactory](classtensorflow_1_1serving_1_1test__util_1_1FakeThreadPoolFactory.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [virtual]{.keyword}
[ScopedThreadPools](classtensorflow_1_1serving_1_1ScopedThreadPools.html){.code}
GetThreadPools() {
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [return]{.keywordflow}
[ScopedThreadPools](classtensorflow_1_1serving_1_1ScopedThreadPools.html){.code}(inter\_op\_thread\_pool\_,
intra\_op\_thread\_pool\_);
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  }
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [void]{.keywordtype} SetInterOpThreadPool(
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} 
std::shared\_ptr\<thread::ThreadPoolInterface\> thread\_pool) {
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  inter\_op\_thread\_pool\_ = thread\_pool;
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  }
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [void]{.keywordtype} SetIntraOpThreadPool(
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} 
std::shared\_ptr\<thread::ThreadPoolInterface\> thread\_pool) {
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  intra\_op\_thread\_pool\_ = thread\_pool;
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  }
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} 
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} 
std::shared\_ptr\<thread::ThreadPoolInterface\>
inter\_op\_thread\_pool\_;
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} 
std::shared\_ptr\<thread::ThreadPoolInterface\>
intra\_op\_thread\_pool\_;
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([FakeThreadPoolFactory](classtensorflow_1_1serving_1_1test__util_1_1FakeThreadPoolFactory.html){.code});
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} };
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} 
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} } [// namespace test\_util]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} 
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_TEST\_UTIL\_FAKE\_THREAD\_POOL\_FACTORY\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1ScopedThreadPools_html .ttc}
::: {.ttname}
[tensorflow::serving::ScopedThreadPools](classtensorflow_1_1serving_1_1ScopedThreadPools.html)
:::

::: {.ttdef}
**Definition:** thread\_pool\_factory.h:29
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ThreadPoolFactory_html .ttc}
::: {.ttname}
[tensorflow::serving::ThreadPoolFactory](classtensorflow_1_1serving_1_1ThreadPoolFactory.html)
:::

::: {.ttdef}
**Definition:** thread\_pool\_factory.h:48
:::
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1FakeThreadPoolFactory_html .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::FakeThreadPoolFactory](classtensorflow_1_1serving_1_1test__util_1_1FakeThreadPoolFactory.html)
:::

::: {.ttdef}
**Definition:** fake\_thread\_pool\_factory.h:33
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

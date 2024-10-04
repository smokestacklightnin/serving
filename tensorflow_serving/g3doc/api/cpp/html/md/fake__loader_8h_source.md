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
fake\_loader.h
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
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_FAKE\_LOADER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_FAKE\_LOADER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include
\"tensorflow/core/platform/mutex.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow/core/platform/thread\_annotations.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow\_serving/core/loader.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow\_serving/util/any\_ptr.h\"]{.preprocessor}
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
[]{#l00027}[ 27]{.lineno} [namespace ]{.keyword}test\_util {
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} 
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [// A fake loader to be used in
tests.]{.comment}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [// Useful for -]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// 1. Erroring out on load.]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// 2. Counting the total number of fake
loaders alive.]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// 3. Detecting if deletion of the loader
happened on a particular thread.]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [// This class is thread-safe.]{.comment}
:::

::: {.line}
[]{#l00037}[
[37](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html){.line}]{.lineno} [class
]{.keyword}[FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html){.code}
: [public]{.keyword}
[ResourceUnsafeLoader](classtensorflow_1_1serving_1_1ResourceUnsafeLoader.html){.code}
{
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [explicit]{.keyword}
[FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html){.code}(int64\_t
[servable](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#afd3838612c119a086d1b17ce7cdfb9ed){.code},
[const]{.keyword} Status load\_status = Status());
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} 
\~[FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [// The status returned during
load.]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  Status load\_status();
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  Status
[Load](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#a2edb74f10db51d582ee689d3d81cacb7){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [void]{.keywordtype}
[Unload](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#a336ea084823272d433d19be25769fc70){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} 
[AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html){.code}
[servable](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#afd3838612c119a086d1b17ce7cdfb9ed){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [static]{.keyword} [int]{.keywordtype}
num\_fake\_loaders();
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} 
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [// Returns true if a loader was deleted in
this thread.]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [static]{.keyword} [bool]{.keywordtype}
was\_deleted\_in\_this\_thread();
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} 
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [// Used to detect the thread in which
deletion of a loader occurs.]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [static]{.keyword} thread\_local
[bool]{.keywordtype} was\_deleted\_in\_this\_thread\_;
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [// Counts the number of FakeLoader objects
alive.]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [static]{.keyword} [int]{.keywordtype}
num\_fake\_loaders\_ TF\_GUARDED\_BY(num\_fake\_loaders\_mu\_);
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [static]{.keyword} mutex
num\_fake\_loaders\_mu\_;
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [// The servable returned from this
loader.]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [// Don\'t make const or you\'ll have to
change the handle type to \'const int64\'.]{.comment}
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  int64\_t servable\_;
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [// The status returned during
load.]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [const]{.keyword} Status load\_status\_;
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} };
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} 
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} } [// namespace test\_util]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} 
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_FAKE\_LOADER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1AnyPtr_html .ttc}
::: {.ttname}
[tensorflow::serving::AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html)
:::

::: {.ttdef}
**Definition:** any\_ptr.h:65
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ResourceUnsafeLoader_html .ttc}
::: {.ttname}
[tensorflow::serving::ResourceUnsafeLoader](classtensorflow_1_1serving_1_1ResourceUnsafeLoader.html)
:::

::: {.ttdef}
**Definition:** loader.h:155
:::
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1FakeLoader_html .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::FakeLoader](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html)
:::

::: {.ttdef}
**Definition:** fake\_loader.h:37
:::
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1FakeLoader_html_a2edb74f10db51d582ee689d3d81cacb7 .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::FakeLoader::Load](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#a2edb74f10db51d582ee689d3d81cacb7)
:::

::: {.ttdeci}
Status Load() override
:::

::: {.ttdef}
**Definition:** fake\_loader.cc:47
:::
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1FakeLoader_html_a336ea084823272d433d19be25769fc70 .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::FakeLoader::Unload](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#a336ea084823272d433d19be25769fc70)
:::

::: {.ttdeci}
void Unload() override
:::

::: {.ttdef}
**Definition:** fake\_loader.cc:49
:::
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1FakeLoader_html_afd3838612c119a086d1b17ce7cdfb9ed .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::FakeLoader::servable](classtensorflow_1_1serving_1_1test__util_1_1FakeLoader.html#afd3838612c119a086d1b17ce7cdfb9ed)
:::

::: {.ttdeci}
AnyPtr servable() override
:::

::: {.ttdef}
**Definition:** fake\_loader.cc:51
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

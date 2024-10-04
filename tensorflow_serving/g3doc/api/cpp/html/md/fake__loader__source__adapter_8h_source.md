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
fake\_loader\_source\_adapter.h
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
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_FAKE\_LOADER\_SOURCE\_ADAPTER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_FAKE\_LOADER\_SOURCE\_ADAPTER\_H\_]{.preprocessor}
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
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow/core/platform/types.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow\_serving/core/simple\_loader.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/core/storage\_path.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/core/test\_util/fake\_loader\_source\_adapter.pb.h\"]{.preprocessor}
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
[]{#l00030}[ 30]{.lineno} [namespace ]{.keyword}test\_util {
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} 
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// A fake loader source adapter that creates
loaders of servable-type string]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// from data of type StoragePath.]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [// If path = \"/a/simple/path\" and suffix =
\"foo\", the servable string becomes]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [// \"a/simple/path/foo\".]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [// To help with verifying the order of
destruction of these adapters in tests,]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [// the adapter may take a callback to be
invoked upon destruction. The]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [// suffix provided to the source-adapter is
passed to the string argument of the]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [// callback when it is invoked.]{.comment}
:::

::: {.line}
[]{#l00042}[
[42](classtensorflow_1_1serving_1_1test__util_1_1FakeLoaderSourceAdapter.html){.line}]{.lineno} [class
]{.keyword}[FakeLoaderSourceAdapter](classtensorflow_1_1serving_1_1test__util_1_1FakeLoaderSourceAdapter.html){.code}
final
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  : [public]{.keyword}
[SimpleLoaderSourceAdapter](classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter.html){.code}\<StoragePath,
string\> {
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
[FakeLoaderSourceAdapter](classtensorflow_1_1serving_1_1test__util_1_1FakeLoaderSourceAdapter.html){.code}(
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [const]{.keyword} [string]{.keywordtype}&
suffix = [\"\"]{.stringliteral},
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
std::function\<[void]{.keywordtype}([const]{.keyword}
[string]{.keywordtype}&)\> call\_on\_destruct = {});
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} 
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
\~[FakeLoaderSourceAdapter](classtensorflow_1_1serving_1_1test__util_1_1FakeLoaderSourceAdapter.html){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} 
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [const]{.keyword} [string]{.keywordtype}
suffix\_;
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  std::function\<void([const]{.keyword}
[string]{.keywordtype}&)\> call\_on\_destruct\_;
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([FakeLoaderSourceAdapter](classtensorflow_1_1serving_1_1test__util_1_1FakeLoaderSourceAdapter.html){.code});
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} };
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} 
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} } [// namespace test\_util]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_FAKE\_LOADER\_SOURCE\_ADAPTER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1SimpleLoaderSourceAdapter_html .ttc}
::: {.ttname}
[tensorflow::serving::SimpleLoaderSourceAdapter](classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter.html)
:::

::: {.ttdef}
**Definition:** simple\_loader.h:185
:::
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1FakeLoaderSourceAdapter_html .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::FakeLoaderSourceAdapter](classtensorflow_1_1serving_1_1test__util_1_1FakeLoaderSourceAdapter.html)
:::

::: {.ttdef}
**Definition:** fake\_loader\_source\_adapter.h:43
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

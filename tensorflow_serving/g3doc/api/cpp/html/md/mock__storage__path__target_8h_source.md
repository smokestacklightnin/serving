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
mock\_storage\_path\_target.h
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
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_MOCK\_STORAGE\_PATH\_TARGET\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_MOCK\_STORAGE\_PATH\_TARGET\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<gmock/gmock.h\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow\_serving/core/storage\_path.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow\_serving/core/target.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} 
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [namespace ]{.keyword}test\_util {
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} 
:::

::: {.line}
[]{#l00030}[
[30](classtensorflow_1_1serving_1_1test__util_1_1MockStoragePathTarget.html){.line}]{.lineno} [class
]{.keyword}[MockStoragePathTarget](classtensorflow_1_1serving_1_1test__util_1_1MockStoragePathTarget.html){.code}
: [public]{.keyword}
[TargetBase](classtensorflow_1_1serving_1_1TargetBase.html){.code}\<StoragePath\>
{
:::

::: {.line}
[]{#l00031}[ 31]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} 
\~[MockStoragePathTarget](classtensorflow_1_1serving_1_1test__util_1_1MockStoragePathTarget.html){.code}()[
override ]{.keyword}{ Detach(); }
:::

::: {.line}
[]{#l00033}[ 33]{.lineno}  MOCK\_METHOD([void]{.keywordtype},
SetAspiredVersions,
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  ([const]{.keyword} StringPiece,
std::vector\<[ServableData\<StoragePath\>](classtensorflow_1_1serving_1_1ServableData.html){.code}\>),
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  ([override]{.keyword}));
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} };
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} 
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} } [// namespace test\_util]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} 
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_MOCK\_STORAGE\_PATH\_TARGET\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1ServableData_html .ttc}
::: {.ttname}
[tensorflow::serving::ServableData](classtensorflow_1_1serving_1_1ServableData.html)
:::

::: {.ttdef}
**Definition:** servable\_data.h:32
:::
:::

::: {#aclasstensorflow_1_1serving_1_1TargetBase_html .ttc}
::: {.ttname}
[tensorflow::serving::TargetBase](classtensorflow_1_1serving_1_1TargetBase.html)
:::

::: {.ttdef}
**Definition:** target.h:61
:::
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1MockStoragePathTarget_html .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::MockStoragePathTarget](classtensorflow_1_1serving_1_1test__util_1_1MockStoragePathTarget.html)
:::

::: {.ttdef}
**Definition:** mock\_storage\_path\_target.h:30
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

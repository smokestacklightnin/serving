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
mock\_tfrt\_saved\_model.h
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
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_TEST\_UTIL\_MOCK\_TFRT\_SAVED\_MODEL]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_TEST\_UTIL\_MOCK\_TFRT\_SAVED\_MODEL]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<gmock/gmock.h\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include
\"tensorflow/core/tfrt/runtime/runtime.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow/core/tfrt/saved\_model/saved\_model.h\"]{.preprocessor}
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
[]{#l00025}[ 25]{.lineno} [namespace ]{.keyword}test\_util {
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} 
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [inline]{.keyword} tfrt\_stub::Runtime\*
GetTestTfrtRuntime() {
:::

::: {.line}
[]{#l00028}[ 28]{.lineno}  [static]{.keyword} [auto]{.keyword}\*
[const]{.keyword} runtime =
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} 
tfrt\_stub::Runtime::Create([/\*num\_inter\_op\_threads=\*/]{.comment}4).release();
:::

::: {.line}
[]{#l00030}[ 30]{.lineno}  [return]{.keywordflow} runtime;
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} }
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} 
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// A mock of tfrt::SavedModel.]{.comment}
:::

::: {.line}
[]{#l00034}[
[34](classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel.html){.line}]{.lineno} [class
]{.keyword}[MockSavedModel](classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel.html){.code}
: [public]{.keyword} tfrt::SavedModel {
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
[MockSavedModel](classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel.html){.code}()
: SavedModel(GetTestTfrtRuntime()) {}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} 
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  MOCK\_METHOD([const]{.keyword}
tensorflow::MetaGraphDef&, GetMetaGraphDef, (),
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  ([const]{.keyword}, [override]{.keyword}));
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} 
MOCK\_METHOD(absl::optional\<tfrt::FunctionMetadata\>,
GetFunctionMetadata,
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  (absl::string\_view func\_name),
([const]{.keyword}, [override]{.keyword}));
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} 
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  MOCK\_METHOD(::tensorflow::Status, Run,
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  ([const]{.keyword}
tfrt::SavedModel::RunOptions& run\_options,
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  absl::string\_view func\_name,
absl::Span\<const Tensor\> inputs,
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  std::vector\<Tensor\>\* outputs),
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  ([override]{.keyword}));
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  MOCK\_METHOD(std::vector\<std::string\>,
GetFunctionNames, (),
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  ([const]{.keyword}, [override]{.keyword}));
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} 
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  MOCK\_METHOD(::tensorflow::Status,
RunMultipleSignatures,
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  ([const]{.keyword}
tfrt::SavedModel::RunOptions& run\_options,
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  absl::Span\<const std::string\> names,
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  absl::Span\<[const]{.keyword}
std::vector\<tensorflow::Tensor\>\> multi\_inputs,
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} 
std::vector\<std::vector\<tensorflow::Tensor\>\>\* multi\_outputs),
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  ([override]{.keyword}));
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} 
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  MOCK\_METHOD(
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  ::tensorflow::Status, RunByTensorNames,
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  ([const]{.keyword}
tfrt::SavedModel::RunOptions& run\_options,
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  (absl::Span\<[const]{.keyword}
std::pair\<std::string, tensorflow::Tensor\>\> inputs),
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  absl::Span\<const std::string\>
output\_tensor\_names,
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  absl::Span\<const std::string\>
target\_node\_names,
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  std::vector\<tensorflow::Tensor\>\* outputs),
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  ([override]{.keyword}));
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} };
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} } [// namespace test\_util]{.comment}
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} 
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_TEST\_UTIL\_MOCK\_TFRT\_SAVED\_MODEL]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1MockSavedModel_html .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::MockSavedModel](classtensorflow_1_1serving_1_1test__util_1_1MockSavedModel.html)
:::

::: {.ttdef}
**Definition:** mock\_tfrt\_saved\_model.h:34
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

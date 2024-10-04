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
mock\_session.h
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
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_MOCK\_SESSION\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_MOCK\_SESSION\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<gmock/gmock.h\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include
\"tensorflow/core/platform/threadpool\_options.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow/core/public/session.h\"]{.preprocessor}
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
[]{#l00027}[ 27]{.lineno} [// A mock of tensorflow::Session.]{.comment}
:::

::: {.line}
[]{#l00028}[
[28](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.line}]{.lineno} [class
]{.keyword}[MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.code}
: [public]{.keyword} tensorflow::Session {
:::

::: {.line}
[]{#l00029}[ 29]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} 
[MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html){.code}()
: Session() {
:::

::: {.line}
[]{#l00031}[ 31]{.lineno}  ON\_CALL(\*[this]{.keyword},
Close()).WillByDefault(::testing::Return(Status()));
:::

::: {.line}
[]{#l00032}[ 32]{.lineno}  }
:::

::: {.line}
[]{#l00033}[ 33]{.lineno}  MOCK\_METHOD(::tensorflow::Status, Create,
([const]{.keyword} GraphDef& graph),
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  ([override]{.keyword}));
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  MOCK\_METHOD(::tensorflow::Status, Extend,
([const]{.keyword} GraphDef& graph),
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  ([override]{.keyword}));
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  MOCK\_METHOD(::tensorflow::Status, Run,
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  (([const]{.keyword}
std::vector\<std::pair\<string, Tensor\>\>& inputs),
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [const]{.keyword} std::vector\<string\>&
output\_names,
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [const]{.keyword} std::vector\<string\>&
target\_nodes,
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  std::vector\<Tensor\>\* outputs),
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  ([override]{.keyword}));
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  MOCK\_METHOD(::tensorflow::Status, Run,
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  ([const]{.keyword} RunOptions& run\_options,
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  ([const]{.keyword}
std::vector\<std::pair\<string, Tensor\>\>& inputs),
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [const]{.keyword} std::vector\<string\>&
output\_names,
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [const]{.keyword} std::vector\<string\>&
target\_nodes,
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  std::vector\<Tensor\>\* outputs,
RunMetadata\* run\_metadata),
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  ([override]{.keyword}));
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  MOCK\_METHOD(
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  ::tensorflow::Status, Run,
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  ([const]{.keyword} RunOptions& run\_options,
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  ([const]{.keyword}
std::vector\<std::pair\<string, Tensor\>\>& inputs),
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [const]{.keyword} std::vector\<string\>&
output\_names,
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [const]{.keyword} std::vector\<string\>&
target\_nodes, std::vector\<Tensor\>\* outputs,
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  RunMetadata\* run\_metadata,
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [const]{.keyword}
tensorflow::thread::ThreadPoolOptions& thread\_pool\_options),
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  ([override]{.keyword}));
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  MOCK\_METHOD(::tensorflow::Status, PRunSetup,
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  ([const]{.keyword} std::vector\<string\>&
input\_names,
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [const]{.keyword} std::vector\<string\>&
output\_names,
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [const]{.keyword} std::vector\<string\>&
target\_nodes, [string]{.keywordtype}\* handle),
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  ([override]{.keyword}));
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  MOCK\_METHOD(::tensorflow::Status, PRun,
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  ([const]{.keyword} [string]{.keywordtype}&
handle,
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  ([const]{.keyword}
std::vector\<std::pair\<string, Tensor\>\>& inputs),
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [const]{.keyword} std::vector\<string\>&
output\_names,
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  std::vector\<Tensor\>\* outputs),
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  ([override]{.keyword}));
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} 
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  MOCK\_METHOD(::tensorflow::Status,
ListDevices,
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} 
(std::vector\<::tensorflow::DeviceAttributes\> \* response),
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  ([override]{.keyword}));
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} 
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  MOCK\_METHOD(::tensorflow::Status, Close, (),
([override]{.keyword}));
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} };
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} 
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} } [// namespace test\_util]{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} 
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_MOCK\_SESSION\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1MockSession_html .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::MockSession](classtensorflow_1_1serving_1_1test__util_1_1MockSession.html)
:::

::: {.ttdef}
**Definition:** mock\_session.h:28
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

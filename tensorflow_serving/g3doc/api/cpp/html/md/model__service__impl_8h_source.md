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
-   [model\_servers](dir_5bce3ff2a459f05fa975e832b2676e62.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
model\_service\_impl.h
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
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_MODEL\_SERVICE\_IMPL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_MODEL\_SERVICE\_IMPL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<cstdint\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} 
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"grpcpp/server\_context.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"grpcpp/support/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"absl/container/flat\_hash\_map.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/apis/model\_management.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/apis/model\_service.grpc.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow\_serving/apis/model\_service.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow\_serving/model\_servers/server\_core.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} 
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} 
:::

::: {.line}
[]{#l00033}[
[33](classtensorflow_1_1serving_1_1ModelServiceImpl.html){.line}]{.lineno} [class
]{.keyword}[ModelServiceImpl](classtensorflow_1_1serving_1_1ModelServiceImpl.html){.code}
final : [public]{.keyword} ModelService::Service {
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  [explicit]{.keyword}
[ModelServiceImpl](classtensorflow_1_1serving_1_1ModelServiceImpl.html){.code}([ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.code}
\*core) : core\_(core) {}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  ::grpc::Status
GetModelStatus(::grpc::ServerContext \*context,
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  [const]{.keyword} GetModelStatusRequest
\*request,
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  GetModelStatusResponse \*response)
[override]{.keyword};
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  ::grpc::Status
HandleReloadConfigRequest(::grpc::ServerContext \*context,
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [const]{.keyword} ReloadConfigRequest
\*request,
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  ReloadConfigResponse \*response);
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} 
[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.code}
\*core\_;
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [// Obtains values for metrics provided in
request.]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  absl::flat\_hash\_map\<std::string,
int64\_t\> GetMetrics(
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [const]{.keyword} ReloadConfigRequest
\*request);
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [// Compares old\_metric\_values and
new\_metric\_values, storing the increases in]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [// response]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [void]{.keywordtype} RecordMetricsIncrease(
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [const]{.keyword}
absl::flat\_hash\_map\<std::string, int64\_t\> &old\_metric\_values,
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [const]{.keyword}
absl::flat\_hash\_map\<std::string, int64\_t\> &new\_metric\_values,
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  ReloadConfigResponse \*response);
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} };
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} 
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} 
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_MODEL\_SERVICE\_IMPL\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1ModelServiceImpl_html .ttc}
::: {.ttname}
[tensorflow::serving::ModelServiceImpl](classtensorflow_1_1serving_1_1ModelServiceImpl.html)
:::

::: {.ttdef}
**Definition:** model\_service\_impl.h:33
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServerCore_html .ttc}
::: {.ttname}
[tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html)
:::

::: {.ttdef}
**Definition:** server\_core.h:74
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

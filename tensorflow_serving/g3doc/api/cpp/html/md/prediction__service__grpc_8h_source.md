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
-   [experimental](dir_f3a7702a88a35f439eefb104a4dcf36a.html){.el}
-   [tensorflow](dir_bd7602075eb888604dc304949f6ac883.html){.el}
-   [ops](dir_b76c9497d88760821fddd9a3e2873138.html){.el}
-   [remote\_predict](dir_736b8517fd0d65079ceb0428758bba10.html){.el}
-   [kernels](dir_7024a4e6070c565eef9bd1cc6d151481.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
prediction\_service\_grpc.h
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
[]{#l00015}[ 15]{.lineno} [\#ifndef
THIRD\_PARTY\_TENSORFLOW\_SERVING\_EXPERIMENTAL\_TENSORFLOW\_OPS\_REMOTE\_PREDICT\_KERNELS\_PREDICTION\_SERVICE\_GRPC\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00016}[ 16]{.lineno} [\#define
THIRD\_PARTY\_TENSORFLOW\_SERVING\_EXPERIMENTAL\_TENSORFLOW\_OPS\_REMOTE\_PREDICT\_KERNELS\_PREDICTION\_SERVICE\_GRPC\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include
\"absl/status/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include
\"absl/time/time.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow/core/platform/statusor.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow\_serving/apis/prediction\_service.grpc.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} 
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} 
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [// gRPC based communication point with
PredictionService.]{.comment}
:::

::: {.line}
[]{#l00028}[
[28](classtensorflow_1_1serving_1_1PredictionServiceGrpc.html){.line}]{.lineno} [class
]{.keyword}[PredictionServiceGrpc](classtensorflow_1_1serving_1_1PredictionServiceGrpc.html){.code}
{
:::

::: {.line}
[]{#l00029}[ 29]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00030}[ 30]{.lineno}  [// Creates a new instance. Returns an error
if the creation fails.]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno}  [static]{.keyword} absl::Status
Create([const]{.keyword} std::string& target\_address,
:::

::: {.line}
[]{#l00032}[ 32]{.lineno}  std::unique\_ptr\<PredictionServiceGrpc\>\*
service) {
:::

::: {.line}
[]{#l00033}[ 33]{.lineno}  service-\>reset([new]{.keyword}
[PredictionServiceGrpc](classtensorflow_1_1serving_1_1PredictionServiceGrpc.html){.code}(target\_address));
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  return ::absl::OkStatus();
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  }
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  StatusOr\<::grpc::ClientContext\*\>
CreateRpc(absl::Duration max\_rpc\_deadline);
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [void]{.keywordtype}
Predict(::grpc::ClientContext\* rpc, PredictRequest\* request,
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  PredictResponse\* response,
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} 
std::function\<[void]{.keywordtype}(absl::Status status)\> callback);
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
[PredictionServiceGrpc](classtensorflow_1_1serving_1_1PredictionServiceGrpc.html){.code}([const]{.keyword}
std::string& target\_address);
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
std::unique\_ptr\<tensorflow::serving::PredictionService::Stub\> stub\_;
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} };
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} 
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} [\#endif ]{.preprocessor}[//
THIRD\_PARTY\_TENSORFLOW\_SERVING\_EXPERIMENTAL\_TENSORFLOW\_OPS\_REMOTE\_PREDICT\_KERNELS\_PREDICTION\_SERVICE\_GRPC\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1PredictionServiceGrpc_html .ttc}
::: {.ttname}
[tensorflow::serving::PredictionServiceGrpc](classtensorflow_1_1serving_1_1PredictionServiceGrpc.html)
:::

::: {.ttdef}
**Definition:** prediction\_service\_grpc.h:28
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

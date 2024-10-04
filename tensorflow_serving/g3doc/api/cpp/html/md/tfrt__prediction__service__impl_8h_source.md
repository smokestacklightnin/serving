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
tfrt\_prediction\_service\_impl.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2022 Google Inc. All Rights
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
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_TFRT\_PREDICTION\_SERVICE\_IMPL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_TFRT\_PREDICTION\_SERVICE\_IMPL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include
\"tensorflow\_serving/apis/prediction\_service.grpc.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include
\"tensorflow\_serving/model\_servers/prediction\_service\_util.h\"]{.preprocessor}
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
[]{#l00025}[
[25](classtensorflow_1_1serving_1_1TfrtPredictionServiceImpl.html){.line}]{.lineno} [class
]{.keyword}[TfrtPredictionServiceImpl](classtensorflow_1_1serving_1_1TfrtPredictionServiceImpl.html){.code}
final
:::

::: {.line}
[]{#l00026}[ 26]{.lineno}  : [public]{.keyword}
PredictionService::Service {
:::

::: {.line}
[]{#l00027}[ 27]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00028}[ 28]{.lineno}  [explicit]{.keyword}
[TfrtPredictionServiceImpl](classtensorflow_1_1serving_1_1TfrtPredictionServiceImpl.html){.code}([const]{.keyword}
[PredictionServiceOptions](structtensorflow_1_1serving_1_1PredictionServiceOptions.html){.code}&
options)
:::

::: {.line}
[]{#l00029}[ 29]{.lineno}  : core\_(options.server\_core),
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} 
enforce\_session\_run\_timeout\_(options.enforce\_session\_run\_timeout),
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} 
thread\_pool\_factory\_(options.thread\_pool\_factory) {}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} 
:::

::: {.line}
[]{#l00033}[ 33]{.lineno}  ::grpc::Status
Predict(::grpc::ServerContext\* context,
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  [const]{.keyword} PredictRequest\* request,
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  PredictResponse\* response)
[override]{.keyword};
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  ::grpc::Status
GetModelMetadata(::grpc::ServerContext\* context,
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  [const]{.keyword} GetModelMetadataRequest\*
request,
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  GetModelMetadataResponse\* response)
[override]{.keyword};
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  ::grpc::Status
Classify(::grpc::ServerContext\* context,
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [const]{.keyword} ClassificationRequest\*
request,
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  ClassificationResponse\* response)
[override]{.keyword};
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  ::grpc::Status
Regress(::grpc::ServerContext\* context,
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [const]{.keyword} RegressionRequest\*
request,
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  RegressionResponse\* response)
[override]{.keyword};
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} 
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  ::grpc::Status
MultiInference(::grpc::ServerContext\* context,
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [const]{.keyword} MultiInferenceRequest\*
request,
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  MultiInferenceResponse\* response)
[override]{.keyword};
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} 
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  absl::Time
GetRequestDeadline(::grpc::ServerContext\* context) [const]{.keyword};
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} 
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} 
[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.code}\*
core\_;
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [const]{.keyword} [bool]{.keywordtype}
enforce\_session\_run\_timeout\_;
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} 
[ThreadPoolFactory](classtensorflow_1_1serving_1_1ThreadPoolFactory.html){.code}\*
thread\_pool\_factory\_;
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} };
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
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
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_TFRT\_PREDICTION\_SERVICE\_IMPL\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1ServerCore_html .ttc}
::: {.ttname}
[tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html)
:::

::: {.ttdef}
**Definition:** server\_core.h:74
:::
:::

::: {#aclasstensorflow_1_1serving_1_1TfrtPredictionServiceImpl_html .ttc}
::: {.ttname}
[tensorflow::serving::TfrtPredictionServiceImpl](classtensorflow_1_1serving_1_1TfrtPredictionServiceImpl.html)
:::

::: {.ttdef}
**Definition:** tfrt\_prediction\_service\_impl.h:26
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

::: {#astructtensorflow_1_1serving_1_1PredictionServiceOptions_html .ttc}
::: {.ttname}
[tensorflow::serving::PredictionServiceOptions](structtensorflow_1_1serving_1_1PredictionServiceOptions.html)
:::

::: {.ttdef}
**Definition:** prediction\_service\_util.h:27
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

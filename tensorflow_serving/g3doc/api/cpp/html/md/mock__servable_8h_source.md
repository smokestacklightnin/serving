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
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
mock\_servable.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2023 Google Inc. All Rights
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
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_MOCK\_SERVABLE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_MOCK\_SERVABLE\_H\_]{.preprocessor}
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
[]{#l00021}[ 21]{.lineno} [\#include \<gmock/gmock.h\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"absl/functional/any\_invocable.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"absl/status/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"absl/status/statusor.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/apis/classification.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/apis/get\_model\_metadata.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow\_serving/apis/inference.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow\_serving/apis/predict.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow\_serving/apis/regression.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/servable.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} 
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} 
:::

::: {.line}
[]{#l00035}[
[35](classtensorflow_1_1serving_1_1MockPredictStreamedContext.html){.line}]{.lineno} [class
]{.keyword}[MockPredictStreamedContext](classtensorflow_1_1serving_1_1MockPredictStreamedContext.html){.code}
: [public]{.keyword}
[PredictStreamedContext](classtensorflow_1_1serving_1_1PredictStreamedContext.html){.code}
{
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  MOCK\_METHOD(absl::Status, ProcessRequest,
([const]{.keyword} PredictRequest& request),
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  ([final]{.keyword}));
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  MOCK\_METHOD(absl::Status, Close, (),
([final]{.keyword}));
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} };
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} 
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [// A mock of
tensorflow::serving::Servable.]{.comment}
:::

::: {.line}
[]{#l00043}[
[43](classtensorflow_1_1serving_1_1MockServable.html){.line}]{.lineno} [class
]{.keyword}[MockServable](classtensorflow_1_1serving_1_1MockServable.html){.code}
: [public]{.keyword}
[Servable](classtensorflow_1_1serving_1_1Servable.html){.code} {
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
[MockServable](classtensorflow_1_1serving_1_1MockServable.html){.code}()
:
[Servable](classtensorflow_1_1serving_1_1Servable.html){.code}([\"\"]{.stringliteral},
0) {}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} 
\~[MockServable](classtensorflow_1_1serving_1_1MockServable.html){.code}()
[override]{.keyword} = [default]{.keywordflow};
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  MOCK\_METHOD(absl::Status, Classify,
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  ([const]{.keyword}
[tensorflow::serving::Servable::RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code}&
run\_options,
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [const]{.keyword}
tensorflow::serving::ClassificationRequest& request,
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  tensorflow::serving::ClassificationResponse\*
response),
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  ([final]{.keyword}));
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  MOCK\_METHOD(absl::Status, Regress,
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  ([const]{.keyword}
[tensorflow::serving::Servable::RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code}&
run\_options,
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [const]{.keyword}
tensorflow::serving::RegressionRequest& request,
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  tensorflow::serving::RegressionResponse\*
response),
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  ([final]{.keyword}));
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  MOCK\_METHOD(absl::Status, Predict,
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  ([const]{.keyword}
[tensorflow::serving::Servable::RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code}&
run\_options,
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [const]{.keyword}
tensorflow::serving::PredictRequest& request,
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  tensorflow::serving::PredictResponse\*
response),
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  ([final]{.keyword}));
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} 
MOCK\_METHOD(absl::StatusOr\<std::unique\_ptr\<PredictStreamedContext\>\>,
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  PredictStreamed,
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  ([const]{.keyword}
[tensorflow::serving::Servable::RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code}&
run\_options,
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  absl::AnyInvocable\<
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
[void]{.keywordtype}(absl::StatusOr\<tensorflow::serving::PredictResponse\>)\>
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  response\_callback),
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  ([final]{.keyword}));
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  MOCK\_METHOD(absl::Status, MultiInference,
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  ([const]{.keyword}
[tensorflow::serving::Servable::RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html){.code}&
run\_options,
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [const]{.keyword}
tensorflow::serving::MultiInferenceRequest& request,
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  tensorflow::serving::MultiInferenceResponse\*
response),
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  ([final]{.keyword}));
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  MOCK\_METHOD(absl::Status, GetModelMetadata,
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  ([const]{.keyword}
tensorflow::serving::GetModelMetadataRequest& request,
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} 
tensorflow::serving::GetModelMetadataResponse\* response),
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  ([final]{.keyword}));
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  MOCK\_METHOD([bool]{.keywordtype},
SupportsPaging, (), ([const]{.keyword}, [final]{.keyword}));
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  MOCK\_METHOD(absl::Status, Suspend, (),
([final]{.keyword}));
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  MOCK\_METHOD(absl::Status, Resume, (),
([final]{.keyword}));
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} };
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} 
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} 
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_MOCK\_SERVABLE\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1MockPredictStreamedContext_html .ttc}
::: {.ttname}
[tensorflow::serving::MockPredictStreamedContext](classtensorflow_1_1serving_1_1MockPredictStreamedContext.html)
:::

::: {.ttdef}
**Definition:** mock\_servable.h:35
:::
:::

::: {#aclasstensorflow_1_1serving_1_1MockServable_html .ttc}
::: {.ttname}
[tensorflow::serving::MockServable](classtensorflow_1_1serving_1_1MockServable.html)
:::

::: {.ttdef}
**Definition:** mock\_servable.h:43
:::
:::

::: {#aclasstensorflow_1_1serving_1_1PredictStreamedContext_html .ttc}
::: {.ttname}
[tensorflow::serving::PredictStreamedContext](classtensorflow_1_1serving_1_1PredictStreamedContext.html)
:::

::: {.ttdef}
**Definition:** servable.h:47
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Servable_html .ttc}
::: {.ttname}
[tensorflow::serving::Servable](classtensorflow_1_1serving_1_1Servable.html)
:::

::: {.ttdef}
**Definition:** servable.h:80
:::
:::

::: {#astructtensorflow_1_1serving_1_1servables_1_1RunOptions_html .ttc}
::: {.ttname}
[tensorflow::serving::servables::RunOptions](structtensorflow_1_1serving_1_1servables_1_1RunOptions.html)
:::

::: {.ttdef}
**Definition:** run\_options.h:27
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

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
saved\_model\_warmup\_test\_util.h
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
THIRD\_PARTY\_TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_SAVED\_MODEL\_WARMUP\_TEST\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
THIRD\_PARTY\_TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_SAVED\_MODEL\_WARMUP\_TEST\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow/core/lib/io/path.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow/core/lib/io/record\_writer.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow/core/platform/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow/core/protobuf/meta\_graph.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/apis/classification.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/apis/inference.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow\_serving/apis/input.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow\_serving/apis/model.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow\_serving/apis/predict.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow\_serving/apis/prediction\_log.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include
\"tensorflow\_serving/apis/regression.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/session\_bundle\_config.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} 
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [void]{.keywordtype}
PopulateInferenceTask([const]{.keyword} [string]{.keywordtype}&
model\_name,
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  [const]{.keyword} [string]{.keywordtype}&
signature\_name,
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [const]{.keyword} [string]{.keywordtype}&
method\_name, InferenceTask\* task);
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [void]{.keywordtype}
PopulateMultiInferenceRequest(MultiInferenceRequest\* request);
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [void]{.keywordtype}
PopulatePredictRequest(PredictRequest\* request);
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [void]{.keywordtype}
PopulateClassificationRequest(ClassificationRequest\* request);
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} 
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [void]{.keywordtype}
PopulateRegressionRequest(RegressionRequest\* request);
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} 
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} Status PopulatePredictionLog(PredictionLog\*
prediction\_log,
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  PredictionLog::LogTypeCase log\_type,
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [int]{.keywordtype} num\_repeated\_values =
1);
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} 
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} Status WriteWarmupData([const]{.keyword}
[string]{.keywordtype}& fname,
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [const]{.keyword} std::vector\<string\>&
warmup\_records,
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [int]{.keywordtype} num\_warmup\_records);
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} 
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} Status WriteWarmupDataAsSerializedProtos(
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [const]{.keyword} [string]{.keywordtype}&
fname, [const]{.keyword} std::vector\<string\>& warmup\_records,
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [int]{.keywordtype} num\_warmup\_records);
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} Status AddMixedWarmupData(
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  std::vector\<string\>\* warmup\_records,
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [const]{.keyword}
std::vector\<PredictionLog::LogTypeCase\>& log\_types = {
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  PredictionLog::kRegressLog,
PredictionLog::kClassifyLog,
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  PredictionLog::kPredictLog,
PredictionLog::kMultiInferenceLog});
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} 
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} Status AddToWarmupData(std::vector\<string\>\*
warmup\_records,
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  PredictionLog::LogTypeCase log\_type,
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [int]{.keywordtype} num\_repeated\_values =
1);
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} 
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} [// Creates a test SignatureDef with the given
parameters]{.comment}
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} SignatureDef
CreateSignatureDef([const]{.keyword} [string]{.keywordtype}&
method\_name,
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [const]{.keyword} std::vector\<string\>&
input\_names,
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  [const]{.keyword} std::vector\<string\>&
output\_names);
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} 
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} [void]{.keywordtype}
AddSignatures(MetaGraphDef\* meta\_graph\_def);
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} 
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} 
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} [\#endif ]{.preprocessor}[//
THIRD\_PARTY\_TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_SAVED\_MODEL\_WARMUP\_TEST\_UTIL\_H\_]{.comment}
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

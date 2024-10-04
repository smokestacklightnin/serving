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
predict\_util.h
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
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_PREDICT\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_PREDICT\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include
\"absl/types/optional.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow/core/platform/threadpool\_options.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow/core/protobuf/config.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow/core/protobuf/meta\_graph.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow/core/public/session.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/apis/predict.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/predict\_response\_tensor\_serialization\_option.h\"]{.preprocessor}
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
[]{#l00030}[ 30]{.lineno} 
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [namespace ]{.keyword}internal {
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} 
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// Similar to RunPredict below, but allows
specification of a serialization]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// option for the TensorProtos in the
response.]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} Status RunPredict(
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  [const]{.keyword} RunOptions& run\_options,
[const]{.keyword} MetaGraphDef& meta\_graph\_def,
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [const]{.keyword} absl::optional\<int64\_t\>&
servable\_version,
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  [const]{.keyword}
PredictResponseTensorSerializationOption tensor\_serialization\_option,
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  Session\* session, [const]{.keyword}
PredictRequest& request, PredictResponse\* response,
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [const]{.keyword} thread::ThreadPoolOptions&
thread\_pool\_options =
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  thread::ThreadPoolOptions());
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [// Validate a SignatureDef to make sure it\'s
compatible with prediction, and]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [// if so, populate the input and output
tensor names.]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} Status PreProcessPrediction([const]{.keyword}
SignatureDef& signature,
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [const]{.keyword} PredictRequest& request,
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  std::vector\<std::pair\<string, Tensor\>\>\*
inputs,
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  std::vector\<string\>\*
output\_tensor\_names,
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  std::vector\<string\>\*
output\_tensor\_aliases);
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} 
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} [// Validate results and populate a
PredictResponse.]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [// Tensors are serialized as
specified.]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} Status PostProcessPredictionResult(
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [const]{.keyword} std::vector\<string\>&
output\_tensor\_aliases,
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [const]{.keyword} std::vector\<Tensor\>&
output\_tensors,
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [const]{.keyword}
internal::PredictResponseTensorSerializationOption option,
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  PredictResponse\* response);
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} 
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} } [// namespace internal]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} [// Implementation of Predict using the
SavedModel SignatureDef format.]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} [// IMPLEMENTATION NOTES: Calls the
internal::RunPredict function above by]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} [// specifying serialization option as
kAsProtoField for backward compatibility.]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} Status RunPredict([const]{.keyword}
RunOptions& run\_options,
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [const]{.keyword} MetaGraphDef&
meta\_graph\_def,
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [const]{.keyword} absl::optional\<int64\_t\>&
servable\_version,
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  Session\* session, [const]{.keyword}
PredictRequest& request,
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  PredictResponse\* response,
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [const]{.keyword} thread::ThreadPoolOptions&
thread\_pool\_options =
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  thread::ThreadPoolOptions());
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} 
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} 
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_PREDICT\_UTIL\_H\_]{.comment}
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

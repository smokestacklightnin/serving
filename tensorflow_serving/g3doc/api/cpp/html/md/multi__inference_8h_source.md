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
multi\_inference.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2017 Google Inc. All Rights
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
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_MULTI\_INFERENCE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_MULTI\_INFERENCE\_H\_]{.preprocessor}
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
\"tensorflow/core/protobuf/meta\_graph.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow/core/public/session.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow\_serving/apis/inference.pb.h\"]{.preprocessor}
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
[]{#l00028}[ 28]{.lineno} 
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [// TensorFlow implementation of the
MultiInference.]{.comment}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [// Only supports Models in the SavedModel
format.]{.comment}
:::

::: {.line}
[]{#l00031}[
[31](classtensorflow_1_1serving_1_1TensorFlowMultiInferenceRunner.html){.line}]{.lineno} [class
]{.keyword}[TensorFlowMultiInferenceRunner](classtensorflow_1_1serving_1_1TensorFlowMultiInferenceRunner.html){.code}
{
:::

::: {.line}
[]{#l00032}[ 32]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} 
[TensorFlowMultiInferenceRunner](classtensorflow_1_1serving_1_1TensorFlowMultiInferenceRunner.html){.code}(Session\*
session,
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  [const]{.keyword} MetaGraphDef\*
meta\_graph\_def)
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  :
[TensorFlowMultiInferenceRunner](classtensorflow_1_1serving_1_1TensorFlowMultiInferenceRunner.html){.code}(session,
meta\_graph\_def,
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  [/\*servable\_version=\*/]{.comment}{}) {}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} 
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
[TensorFlowMultiInferenceRunner](classtensorflow_1_1serving_1_1TensorFlowMultiInferenceRunner.html){.code}(
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  Session\* session, [const]{.keyword}
MetaGraphDef\* meta\_graph\_def,
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  absl::optional\<int64\_t\> servable\_version,
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [const]{.keyword} thread::ThreadPoolOptions&
thread\_pool\_options =
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  thread::ThreadPoolOptions())
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  : session\_(session),
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  meta\_graph\_def\_(meta\_graph\_def),
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  servable\_version\_(servable\_version),
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} 
thread\_pool\_options\_(thread\_pool\_options) {}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [// Run inference and return the inference
results in the same order as the]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [// InferenceTasks in the request.]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  Status Infer([const]{.keyword} RunOptions&
run\_options,
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [const]{.keyword} MultiInferenceRequest&
request,
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  MultiInferenceResponse\* response);
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} 
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [virtual]{.keyword}
\~[TensorFlowMultiInferenceRunner](classtensorflow_1_1serving_1_1TensorFlowMultiInferenceRunner.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} 
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  Session\* [const]{.keyword} session\_;
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [const]{.keyword} MetaGraphDef\*
[const]{.keyword} meta\_graph\_def\_;
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [// If available, servable\_version is used
to set the ModelSpec version in the]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [// InferenceResults of the
MultiInferenceResponse.]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [const]{.keyword} absl::optional\<int64\_t\>
servable\_version\_;
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [const]{.keyword}
tensorflow::thread::ThreadPoolOptions thread\_pool\_options\_;
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} };
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} [// Creates TensorFlowMultiInferenceRunner and
calls Infer on it.]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} Status RunMultiInference(
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [const]{.keyword} RunOptions& run\_options,
[const]{.keyword} MetaGraphDef& meta\_graph\_def,
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [const]{.keyword} absl::optional\<int64\_t\>&
servable\_version, Session\* session,
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [const]{.keyword} MultiInferenceRequest&
request, MultiInferenceResponse\* response,
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [const]{.keyword}
tensorflow::thread::ThreadPoolOptions& thread\_pool\_options =
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  tensorflow::thread::ThreadPoolOptions());
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
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_MULTI\_INFERENCE\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1TensorFlowMultiInferenceRunner_html .ttc}
::: {.ttname}
[tensorflow::serving::TensorFlowMultiInferenceRunner](classtensorflow_1_1serving_1_1TensorFlowMultiInferenceRunner.html)
:::

::: {.ttdef}
**Definition:** multi\_inference.h:31
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

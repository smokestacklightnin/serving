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
predict\_impl.h
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
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_PREDICT\_IMPL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_PREDICT\_IMPL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include
\"tensorflow/core/framework/tensor.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow/core/protobuf/config.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow\_serving/apis/predict.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow\_serving/model\_servers/server\_core.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/thread\_pool\_factory.h\"]{.preprocessor}
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
[]{#l00029}[ 29]{.lineno} [// Utility methods for implementation of
PredictionService::Predict.]{.comment}
:::

::: {.line}
[]{#l00030}[
[30](classtensorflow_1_1serving_1_1TensorflowPredictor.html){.line}]{.lineno} [class
]{.keyword}[TensorflowPredictor](classtensorflow_1_1serving_1_1TensorflowPredictor.html){.code}
{
:::

::: {.line}
[]{#l00031}[ 31]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} 
[TensorflowPredictor](classtensorflow_1_1serving_1_1TensorflowPredictor.html){.code}()
{}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} 
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  [explicit]{.keyword}
[TensorflowPredictor](classtensorflow_1_1serving_1_1TensorflowPredictor.html){.code}([ThreadPoolFactory](classtensorflow_1_1serving_1_1ThreadPoolFactory.html){.code}\*
thread\_pool\_factory)
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  :
thread\_pool\_factory\_(thread\_pool\_factory) {}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  Status Predict([const]{.keyword} RunOptions&
run\_options,
[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.code}\*
core,
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  [const]{.keyword} PredictRequest& request,
PredictResponse\* response);
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} 
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [// Like Predict(), but uses \'model\_spec\'
instead of the one embedded in]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [// \'request\'.]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  Status PredictWithModelSpec([const]{.keyword}
RunOptions& run\_options,
[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.code}\*
core,
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [const]{.keyword} ModelSpec& model\_spec,
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [const]{.keyword} PredictRequest& request,
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  PredictResponse\* response);
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} 
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} 
[ThreadPoolFactory](classtensorflow_1_1serving_1_1ThreadPoolFactory.html){.code}\*
thread\_pool\_factory\_ = [nullptr]{.keyword};
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} };
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} 
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} 
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_PREDICT\_IMPL\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1ServerCore_html .ttc}
::: {.ttname}
[tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html)
:::

::: {.ttdef}
**Definition:** server\_core.h:74
:::
:::

::: {#aclasstensorflow_1_1serving_1_1TensorflowPredictor_html .ttc}
::: {.ttname}
[tensorflow::serving::TensorflowPredictor](classtensorflow_1_1serving_1_1TensorflowPredictor.html)
:::

::: {.ttdef}
**Definition:** predict\_impl.h:30
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
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

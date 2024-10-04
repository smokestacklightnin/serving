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
device\_runner\_init\_stub.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2021 The TensorFlow Authors. All
Rights Reserved.]{.comment}
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
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_DEVICE\_RUNNER\_INIT\_STUB\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00016}[ 16]{.lineno} [\#define
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_DEVICE\_RUNNER\_INIT\_STUB\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} 
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include
\"tensorflow/core/tfrt/runtime/runtime.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [namespace ]{.keyword}tensorflow::serving {
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} 
:::

::: {.line}
[]{#l00023}[
[23](structtensorflow_1_1serving_1_1DeviceRunnerOptions.html){.line}]{.lineno} [struct
]{.keyword}[DeviceRunnerOptions](structtensorflow_1_1serving_1_1DeviceRunnerOptions.html){.code}
{
:::

::: {.line}
[]{#l00024}[ 24]{.lineno}  [bool]{.keywordtype} warmup\_all\_devices =
[true]{.keyword};
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} };
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} 
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [using]{.keyword}
InitializeDeviceRunnerAndTopologyFuncType =
:::

::: {.line}
[]{#l00028}[ 28]{.lineno}  Status (\*)(tfrt\_stub::Runtime&,
[int]{.keywordtype}\*, [int]{.keywordtype}\*, [const]{.keyword}
[DeviceRunnerOptions](structtensorflow_1_1serving_1_1DeviceRunnerOptions.html){.code}&);
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} 
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [// Initializes a \`TpuSystem\` instance, and
provide \`num\_local\_devices\` and]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [// \`cores\_per\_chip\` topology info. This
is a function pointer because some]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// binary contains code paths to call this
function even though it doesn\'t use]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// TPU, the function pointer allows us to
provide a dummy implementation so it]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// doesn\'t have to link TPU dependencies
that increases binary size.]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [extern]{.keyword}
InitializeDeviceRunnerAndTopologyFuncType
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  InitializeDeviceRunnerAndTopologyFunc;
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} 
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [// This enables default values for
\`InitializeDeviceRunnerAndTopology\`.]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} Status InitializeDeviceRunnerAndTopology(
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  tfrt\_stub::Runtime& runtime,
[int]{.keywordtype}\* num\_local\_devices = [nullptr]{.keyword},
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [int]{.keywordtype}\* cores\_per\_chip =
[nullptr]{.keyword}, [const]{.keyword}
[DeviceRunnerOptions](structtensorflow_1_1serving_1_1DeviceRunnerOptions.html){.code}&
options = {});
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} } [// namespace tensorflow::serving]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_DEVICE\_RUNNER\_INIT\_STUB\_H\_]{.comment}
:::

::: {#astructtensorflow_1_1serving_1_1DeviceRunnerOptions_html .ttc}
::: {.ttname}
[tensorflow::serving::DeviceRunnerOptions](structtensorflow_1_1serving_1_1DeviceRunnerOptions.html)
:::

::: {.ttdef}
**Definition:** device\_runner\_init\_stub.h:23
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

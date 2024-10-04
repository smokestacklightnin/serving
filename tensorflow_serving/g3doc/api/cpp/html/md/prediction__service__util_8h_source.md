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
prediction\_service\_util.h
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
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_PREDICTION\_SERVICE\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_PREDICTION\_SERVICE\_UTIL\_H\_]{.preprocessor}
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
\"tensorflow\_serving/model\_servers/server\_core.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/thread\_pool\_factory.h\"]{.preprocessor}
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
[]{#l00025}[ 25]{.lineno} 
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [// Options for configuring a
PredictionServiceBase object.]{.comment}
:::

::: {.line}
[]{#l00027}[
[27](structtensorflow_1_1serving_1_1PredictionServiceOptions.html){.line}]{.lineno} [struct
]{.keyword}[PredictionServiceOptions](structtensorflow_1_1serving_1_1PredictionServiceOptions.html){.code}
{
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} 
[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.code}\*
server\_core;
:::

::: {.line}
[]{#l00029}[ 29]{.lineno}  [bool]{.keywordtype}
enforce\_session\_run\_timeout;
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} 
[ThreadPoolFactory](classtensorflow_1_1serving_1_1ThreadPoolFactory.html){.code}\*
thread\_pool\_factory = [nullptr]{.keyword};
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} };
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} 
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// Convert the request deadline represented
in absolute time point into number]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// of milliseconds from now.]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [int]{.keywordtype}
DeadlineToTimeoutMillis([const]{.keyword} gpr\_timespec deadline);
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} 
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_PREDICTION\_SERVICE\_UTIL\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1ServerCore_html .ttc}
::: {.ttname}
[tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html)
:::

::: {.ttdef}
**Definition:** server\_core.h:74
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

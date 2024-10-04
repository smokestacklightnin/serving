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
get\_model\_status\_impl.h
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
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_GET\_MODEL\_STATUS\_IMPL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_GET\_MODEL\_STATUS\_IMPL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include
\"tensorflow\_serving/apis/get\_model\_status.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow\_serving/model\_servers/server\_core.h\"]{.preprocessor}
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
[]{#l00026}[ 26]{.lineno} [// Returns response with status information
for model. If the request]{.comment}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [// specifies a model version, information
about only that version will be]{.comment}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [// returned. If no version is specified,
information about all versions of the]{.comment}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [// model will be returned.]{.comment}
:::

::: {.line}
[]{#l00030}[
[30](classtensorflow_1_1serving_1_1GetModelStatusImpl.html){.line}]{.lineno} [class
]{.keyword}[GetModelStatusImpl](classtensorflow_1_1serving_1_1GetModelStatusImpl.html){.code}
{
:::

::: {.line}
[]{#l00031}[ 31]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00032}[ 32]{.lineno}  [static]{.keyword} Status
GetModelStatus([ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.code}\*
core,
:::

::: {.line}
[]{#l00033}[ 33]{.lineno}  [const]{.keyword} GetModelStatusRequest&
request,
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  GetModelStatusResponse\* response);
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} 
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  [// Like GetModelStatus(), but uses
\'model\_spec\' instead of the one embedded in]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [// \'request\'.]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  [static]{.keyword} Status
GetModelStatusWithModelSpec(
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} 
[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.code}\*
core, [const]{.keyword} ModelSpec& model\_spec,
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [const]{.keyword} GetModelStatusRequest&
request, GetModelStatusResponse\* response);
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} };
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_GET\_MODEL\_STATUS\_IMPL\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1GetModelStatusImpl_html .ttc}
::: {.ttname}
[tensorflow::serving::GetModelStatusImpl](classtensorflow_1_1serving_1_1GetModelStatusImpl.html)
:::

::: {.ttdef}
**Definition:** get\_model\_status\_impl.h:30
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

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
-   [apis](dir_d68ff6233532314831e00d5d4d9ff12e.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
regressor.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} 
:::

::: {.line}
[]{#l00002}[ 2]{.lineno} [/\* Copyright 2016 Google Inc. All Rights
Reserved.]{.comment}
:::

::: {.line}
[]{#l00003}[ 3]{.lineno} []{.comment}
:::

::: {.line}
[]{#l00004}[ 4]{.lineno} [Licensed under the Apache License, Version 2.0
(the \"License\");]{.comment}
:::

::: {.line}
[]{#l00005}[ 5]{.lineno} [you may not use this file except in compliance
with the License.]{.comment}
:::

::: {.line}
[]{#l00006}[ 6]{.lineno} [You may obtain a copy of the License
at]{.comment}
:::

::: {.line}
[]{#l00007}[ 7]{.lineno} []{.comment}
:::

::: {.line}
[]{#l00008}[ 8]{.lineno} [
http://www.apache.org/licenses/LICENSE-2.0]{.comment}
:::

::: {.line}
[]{#l00009}[ 9]{.lineno} []{.comment}
:::

::: {.line}
[]{#l00010}[ 10]{.lineno} [Unless required by applicable law or agreed
to in writing, software]{.comment}
:::

::: {.line}
[]{#l00011}[ 11]{.lineno} [distributed under the License is distributed
on an \"AS IS\" BASIS,]{.comment}
:::

::: {.line}
[]{#l00012}[ 12]{.lineno} [WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND,
either express or implied.]{.comment}
:::

::: {.line}
[]{#l00013}[ 13]{.lineno} [See the License for the specific language
governing permissions and]{.comment}
:::

::: {.line}
[]{#l00014}[ 14]{.lineno} [limitations under the License.]{.comment}
:::

::: {.line}
[]{#l00015}[
15]{.lineno} [==============================================================================\*/]{.comment}
:::

::: {.line}
[]{#l00016}[ 16]{.lineno} 
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_APIS\_REGRESSOR\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} [\#define
TENSORFLOW\_SERVING\_APIS\_REGRESSOR\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} 
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow\_serving/apis/regression.pb.h\"]{.preprocessor}
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
[]{#l00032}[
[32](classtensorflow_1_1serving_1_1RegressorInterface.html){.line}]{.lineno} [class
]{.keyword}[RegressorInterface](classtensorflow_1_1serving_1_1RegressorInterface.html){.code}
{
:::

::: {.line}
[]{#l00033}[ 33]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00041}[
[41](classtensorflow_1_1serving_1_1RegressorInterface.html#aef7f5c7d1d322f05a0821f20c0164203){.line}]{.lineno} 
[virtual]{.keyword} Status
[Regress](classtensorflow_1_1serving_1_1RegressorInterface.html#aef7f5c7d1d322f05a0821f20c0164203){.code}([const]{.keyword}
RegressionRequest& request,
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  RegressionResult\* result) = 0;
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} 
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [virtual]{.keyword}
\~[RegressorInterface](classtensorflow_1_1serving_1_1RegressorInterface.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} };
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} 
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_APIS\_REGRESSOR\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1RegressorInterface_html .ttc}
::: {.ttname}
[tensorflow::serving::RegressorInterface](classtensorflow_1_1serving_1_1RegressorInterface.html)
:::

::: {.ttdef}
**Definition:** regressor.h:32
:::
:::

::: {#aclasstensorflow_1_1serving_1_1RegressorInterface_html_aef7f5c7d1d322f05a0821f20c0164203 .ttc}
::: {.ttname}
[tensorflow::serving::RegressorInterface::Regress](classtensorflow_1_1serving_1_1RegressorInterface.html#aef7f5c7d1d322f05a0821f20c0164203)
:::

::: {.ttdeci}
virtual Status Regress(const RegressionRequest &request,
RegressionResult \*result)=0
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

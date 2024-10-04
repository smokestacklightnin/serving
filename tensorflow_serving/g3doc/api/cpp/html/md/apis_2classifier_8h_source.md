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
classifier.h
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
TENSORFLOW\_SERVING\_APIS\_CLASSIFIER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_APIS\_CLASSIFIER\_H\_]{.preprocessor}
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
\"tensorflow\_serving/apis/classification.pb.h\"]{.preprocessor}
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
[]{#l00031}[
[31](classtensorflow_1_1serving_1_1ClassifierInterface.html){.line}]{.lineno} [class
]{.keyword}[ClassifierInterface](classtensorflow_1_1serving_1_1ClassifierInterface.html){.code}
{
:::

::: {.line}
[]{#l00032}[ 32]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00040}[
[40](classtensorflow_1_1serving_1_1ClassifierInterface.html#a2823879e328bc9e6f99dd91942b203cb){.line}]{.lineno} 
[virtual]{.keyword} Status
[Classify](classtensorflow_1_1serving_1_1ClassifierInterface.html#a2823879e328bc9e6f99dd91942b203cb){.code}([const]{.keyword}
ClassificationRequest& request,
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  ClassificationResult\* result) = 0;
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [virtual]{.keyword}
\~[ClassifierInterface](classtensorflow_1_1serving_1_1ClassifierInterface.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} };
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} 
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_APIS\_CLASSIFIER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1ClassifierInterface_html .ttc}
::: {.ttname}
[tensorflow::serving::ClassifierInterface](classtensorflow_1_1serving_1_1ClassifierInterface.html)
:::

::: {.ttdef}
**Definition:** classifier.h:31
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ClassifierInterface_html_a2823879e328bc9e6f99dd91942b203cb .ttc}
::: {.ttname}
[tensorflow::serving::ClassifierInterface::Classify](classtensorflow_1_1serving_1_1ClassifierInterface.html#a2823879e328bc9e6f99dd91942b203cb)
:::

::: {.ttdeci}
virtual Status Classify(const ClassificationRequest &request,
ClassificationResult \*result)=0
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

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
run\_options\_base.h
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
[]{#l00002}[ 2]{.lineno} [Licensed under the Apache License, Version 2.0
(the \"License\");]{.comment}
:::

::: {.line}
[]{#l00003}[ 3]{.lineno} [you may not use this file except in compliance
with the License.]{.comment}
:::

::: {.line}
[]{#l00004}[ 4]{.lineno} [You may obtain a copy of the License
at]{.comment}
:::

::: {.line}
[]{#l00005}[ 5]{.lineno} [
http://www.apache.org/licenses/LICENSE-2.0]{.comment}
:::

::: {.line}
[]{#l00006}[ 6]{.lineno} [Unless required by applicable law or agreed to
in writing, software]{.comment}
:::

::: {.line}
[]{#l00007}[ 7]{.lineno} [distributed under the License is distributed
on an \"AS IS\" BASIS,]{.comment}
:::

::: {.line}
[]{#l00008}[ 8]{.lineno} [WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND,
either express or implied.]{.comment}
:::

::: {.line}
[]{#l00009}[ 9]{.lineno} [See the License for the specific language
governing permissions and]{.comment}
:::

::: {.line}
[]{#l00010}[ 10]{.lineno} [limitations under the License.]{.comment}
:::

::: {.line}
[]{#l00011}[
11]{.lineno} [==============================================================================\*/]{.comment}
:::

::: {.line}
[]{#l00012}[ 12]{.lineno} 
:::

::: {.line}
[]{#l00013}[ 13]{.lineno} [\#ifndef
THIRD\_PARTY\_TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_RUN\_OPTIONS\_BASE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00014}[ 14]{.lineno} [\#define
THIRD\_PARTY\_TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_RUN\_OPTIONS\_BASE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00015}[ 15]{.lineno} 
:::

::: {.line}
[]{#l00016}[ 16]{.lineno} [\#include \<stdint.h\>]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} 
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} [\#include
\"absl/time/time.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} 
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [namespace ]{.keyword}servables {
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} 
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [// RunOptionsBase group the configuration for
individual inference executions.]{.comment}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [// The per-request configuration (e.g.
deadline) can be passed here.]{.comment}
:::

::: {.line}
[]{#l00026}[
[26](structtensorflow_1_1serving_1_1servables_1_1RunOptionsBase.html){.line}]{.lineno} [struct
]{.keyword}[RunOptionsBase](structtensorflow_1_1serving_1_1servables_1_1RunOptionsBase.html){.code}
{
:::

::: {.line}
[]{#l00027}[ 27]{.lineno}  [// Priority of the request. Some thread pool
implementation will schedule]{.comment}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno}  [// ops based on the priority number. Larger
number means higher]{.comment}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno}  [// priority.]{.comment}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno}  int64\_t priority = 1;
:::

::: {.line}
[]{#l00031}[ 31]{.lineno}  [// The deadline for this request.]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno}  absl::Time deadline = absl::InfiniteFuture();
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} };
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} 
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} } [// namespace servables]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [\#endif ]{.preprocessor}[//
THIRD\_PARTY\_TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_OSS\_RUN\_OPTIONS\_BASE\_H\_]{.comment}
:::

::: {#astructtensorflow_1_1serving_1_1servables_1_1RunOptionsBase_html .ttc}
::: {.ttname}
[tensorflow::serving::servables::RunOptionsBase](structtensorflow_1_1serving_1_1servables_1_1RunOptionsBase.html)
:::

::: {.ttdef}
**Definition:** run\_options\_base.h:26
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

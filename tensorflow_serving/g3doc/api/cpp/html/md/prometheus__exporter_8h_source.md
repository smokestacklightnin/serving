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
-   [util](dir_1303efdc8de326749a332c6a57186055.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
prometheus\_exporter.h
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
TENSORFLOW\_SERVING\_UTIL\_PROMETHEUS\_EXPORTER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_UTIL\_PROMETHEUS\_EXPORTER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow/core/lib/monitoring/collected\_metrics.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow/core/lib/monitoring/collection\_registry.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} 
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} 
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [// Exports metrics in Prometheus monitoring
format.]{.comment}
:::

::: {.line}
[]{#l00029}[
[29](classtensorflow_1_1serving_1_1PrometheusExporter.html){.line}]{.lineno} [class
]{.keyword}[PrometheusExporter](classtensorflow_1_1serving_1_1PrometheusExporter.html){.code}
{
:::

::: {.line}
[]{#l00030}[ 30]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00031}[ 31]{.lineno}  [// Default path to expose the
metrics.]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype}\* [const]{.keyword} kPrometheusPath;
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} 
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} 
[PrometheusExporter](classtensorflow_1_1serving_1_1PrometheusExporter.html){.code}();
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} 
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  [// Generates text page in Prometheus
format:]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [//
https://prometheus.io/docs/instrumenting/exposition\_formats/\#text-format-example]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  [// If an error status returned, http\_page
is unchanged.]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  Status GeneratePage([string]{.keywordtype}\*
http\_page);
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [// The metrics registry.]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  monitoring::CollectionRegistry\*
collection\_registry\_;
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
TENSORFLOW\_SERVING\_UTIL\_PROMETHEUS\_EXPORTER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1PrometheusExporter_html .ttc}
::: {.ttname}
[tensorflow::serving::PrometheusExporter](classtensorflow_1_1serving_1_1PrometheusExporter.html)
:::

::: {.ttdef}
**Definition:** prometheus\_exporter.h:29
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

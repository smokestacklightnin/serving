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
simple\_servers.h
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
[]{#l00016}[ 16]{.lineno} [// Bootstrapping and configuration utilities
for creating simple servers of]{.comment}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [// TensorFlow models. Intended for basic
instantiation with default configs.]{.comment}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [// Note: All methods expect TensorFlow
SavedModel conforming to the format]{.comment}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [// specified at
third\_party/tensorflow/python/saved\_model/README.md.]{.comment}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_SIMPLE\_SERVERS\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#define
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_SIMPLE\_SERVERS\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} 
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} 
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow/cc/saved\_model/loader.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow/core/platform/types.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow\_serving/core/manager.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include
\"tensorflow\_serving/core/storage\_path.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [\#include
\"tensorflow\_serving/core/target.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} 
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [namespace ]{.keyword}simple\_servers {
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} 
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [// TODO(b/25969594): Add full test
coverage.]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} 
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [// Creates a Manager and associated Source
for a single TensorFlow model that]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [// automatically loads new versions over
time. All versions of the model will be]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [// loaded from new directories under the
specified base path. Uses default]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [// SessionOptions.]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [// The servables loaded and served from this
manager are of type]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [// tensorflow::SavedModelBundle.]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [// When new versions arrive the Manager will
unload the previous version before]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [// loading the new version. This is
preferable from a resource utilization]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [// perspective, but has reduced
availability.]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} Status CreateSingleTFModelManagerFromBasePath(
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [const]{.keyword} [string]{.keywordtype}&
base\_path, std::unique\_ptr\<Manager\>\* manager);
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} 
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} } [// namespace simple\_servers]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} 
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_SIMPLE\_SERVERS\_H\_]{.comment}
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

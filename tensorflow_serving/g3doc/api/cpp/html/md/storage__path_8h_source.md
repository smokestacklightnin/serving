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
-   [core](dir_517df0ab1daf8f221f60ae5135602a49.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
storage\_path.h
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
[]{#l00016}[ 16]{.lineno} [// Typedefs and registries pertaining to
storage system paths.]{.comment}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} 
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_CORE\_STORAGE\_PATH\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_STORAGE\_PATH\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<algorithm\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} 
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/platform/types.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_data.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_id.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} 
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} 
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// Strings that represent paths in some
storage system.]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [using]{.keyword} StoragePath = string;
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} 
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [inline]{.keyword} [bool]{.keywordtype}
operator==([const]{.keyword} ServableData\<StoragePath\>& a,
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [const]{.keyword}
ServableData\<StoragePath\>& b) {
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  [if]{.keywordflow} (a.id() != b.id()) {
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [return]{.keywordflow} [false]{.keyword};
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  }
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [if]{.keywordflow} (a.status().ok() !=
b.status().ok()) {
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [return]{.keywordflow} [false]{.keyword};
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  }
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [if]{.keywordflow} (a.status().ok()) {
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [return]{.keywordflow} a.DataOrDie() ==
b.DataOrDie();
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  } [else]{.keywordflow} {
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [return]{.keywordflow} a.status() ==
b.status();
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  }
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} }
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
TENSORFLOW\_SERVING\_CORE\_STORAGE\_PATH\_H\_]{.comment}
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

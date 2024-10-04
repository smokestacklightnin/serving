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
prefix\_storage\_path\_source\_adapter.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2019 Google Inc. All Rights
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
TENSORFLOW\_SERVING\_CORE\_PREFIX\_STORAGE\_PATH\_SOURCE\_ADAPTER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_PREFIX\_STORAGE\_PATH\_SOURCE\_ADAPTER\_H\_]{.preprocessor}
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
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow\_serving/core/source\_adapter.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow\_serving/core/storage\_path.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} 
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} 
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [// A SourceAdapter that adds a prefix to
StoragePath.]{.comment}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [// This can be useful for filesystems which
wrap other filesystems via namespace]{.comment}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [// prefixes, adding additional functionality
like buffering for example.]{.comment}
:::

::: {.line}
[]{#l00031}[
[31](classtensorflow_1_1serving_1_1PrefixStoragePathSourceAdapter.html){.line}]{.lineno} [class
]{.keyword}[PrefixStoragePathSourceAdapter](classtensorflow_1_1serving_1_1PrefixStoragePathSourceAdapter.html){.code}
final
:::

::: {.line}
[]{#l00032}[ 32]{.lineno}  : [public]{.keyword}
[UnarySourceAdapter](classtensorflow_1_1serving_1_1UnarySourceAdapter.html){.code}\<StoragePath,
StoragePath\> {
:::

::: {.line}
[]{#l00033}[ 33]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  [explicit]{.keyword}
[PrefixStoragePathSourceAdapter](classtensorflow_1_1serving_1_1PrefixStoragePathSourceAdapter.html){.code}([const]{.keyword}
std::string& prefix);
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} 
\~[PrefixStoragePathSourceAdapter](classtensorflow_1_1serving_1_1PrefixStoragePathSourceAdapter.html){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [protected]{.keyword}:
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  Status Convert([const]{.keyword} StoragePath&
source, StoragePath\* destination) [final]{.keyword};
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} 
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [const]{.keyword} std::string prefix\_;
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([PrefixStoragePathSourceAdapter](classtensorflow_1_1serving_1_1PrefixStoragePathSourceAdapter.html){.code});
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
TENSORFLOW\_SERVING\_CORE\_PREFIX\_STORAGE\_PATH\_SOURCE\_ADAPTER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1PrefixStoragePathSourceAdapter_html .ttc}
::: {.ttname}
[tensorflow::serving::PrefixStoragePathSourceAdapter](classtensorflow_1_1serving_1_1PrefixStoragePathSourceAdapter.html)
:::

::: {.ttdef}
**Definition:** prefix\_storage\_path\_source\_adapter.h:32
:::
:::

::: {#aclasstensorflow_1_1serving_1_1UnarySourceAdapter_html .ttc}
::: {.ttname}
[tensorflow::serving::UnarySourceAdapter](classtensorflow_1_1serving_1_1UnarySourceAdapter.html)
:::

::: {.ttdef}
**Definition:** source\_adapter.h:120
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

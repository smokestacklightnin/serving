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
-   [hashmap](dir_b1f399f606a53bbae6b01e75da3e9d2f.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
hashmap\_source\_adapter.h
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
TENSORFLOW\_SERVING\_SERVABLES\_HASHMAP\_HASHMAP\_SOURCE\_ADAPTER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SERVABLES\_HASHMAP\_HASHMAP\_SOURCE\_ADAPTER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<unordered\_map\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} 
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow\_serving/core/simple\_loader.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow\_serving/core/source\_adapter.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow\_serving/core/storage\_path.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/servables/hashmap/hashmap\_source\_adapter.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} 
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} 
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [// A SourceAdapter for string-string
hashmaps. It takes storage paths that give]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [// the locations of serialized hashmaps (in
the format indicated in the config)]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// and produces loaders for them.]{.comment}
:::

::: {.line}
[]{#l00033}[
[33](classtensorflow_1_1serving_1_1HashmapSourceAdapter.html){.line}]{.lineno} [class
]{.keyword}[HashmapSourceAdapter](classtensorflow_1_1serving_1_1HashmapSourceAdapter.html){.code}
final
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  : [public]{.keyword}
[SimpleLoaderSourceAdapter](classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter.html){.code}\<StoragePath,
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  std::unordered\_map\<string, string\>\> {
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [explicit]{.keyword}
[HashmapSourceAdapter](classtensorflow_1_1serving_1_1HashmapSourceAdapter.html){.code}([const]{.keyword}
HashmapSourceAdapterConfig& config);
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
\~[HashmapSourceAdapter](classtensorflow_1_1serving_1_1HashmapSourceAdapter.html){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} 
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([HashmapSourceAdapter](classtensorflow_1_1serving_1_1HashmapSourceAdapter.html){.code});
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} };
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} 
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} 
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SERVABLES\_HASHMAP\_HASHMAP\_SOURCE\_ADAPTER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1HashmapSourceAdapter_html .ttc}
::: {.ttname}
[tensorflow::serving::HashmapSourceAdapter](classtensorflow_1_1serving_1_1HashmapSourceAdapter.html)
:::

::: {.ttdef}
**Definition:** hashmap\_source\_adapter.h:35
:::
:::

::: {#aclasstensorflow_1_1serving_1_1SimpleLoaderSourceAdapter_html .ttc}
::: {.ttname}
[tensorflow::serving::SimpleLoaderSourceAdapter](classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter.html)
:::

::: {.ttdef}
**Definition:** simple\_loader.h:185
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

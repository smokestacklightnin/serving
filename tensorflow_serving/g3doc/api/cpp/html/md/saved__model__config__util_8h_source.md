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
saved\_model\_config\_util.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2023 Google Inc. All Rights
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
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_SAVED\_MODEL\_CONFIG\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_SAVED\_MODEL\_CONFIG\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"absl/status/statusor.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow/core/protobuf/rewriter\_config.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/saved\_model\_config.pb.h\"]{.preprocessor}
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
[]{#l00028}[ 28]{.lineno} [// Name of the additional asset file
containing a per model configuration proto.]{.comment}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [inline]{.keyword} constexpr
[char]{.keywordtype} kSavedModelConfigPath\[\] =
[\"saved\_model\_config.pb\"]{.stringliteral};
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} 
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [inline]{.keyword} constexpr
[char]{.keywordtype} kRemoteOpConfigRewriter\[\] =
[\"remote\_op\_config\_rewrite\"]{.stringliteral};
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [inline]{.keyword} constexpr
[char]{.keywordtype} kBatchOpRewriter\[\] =
[\"batch\_op\_rewriter\"]{.stringliteral};
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} 
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [inline]{.keyword} constexpr
[char]{.keywordtype} kRemoteOpRewriteConfigParamKey\[\] =
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} 
[\"remote\_op\_rewrite\_config\"]{.stringliteral};
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [inline]{.keyword} constexpr
[char]{.keywordtype} kBatchOpRewriteConfigParamKey\[\] =
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} 
[\"batch\_op\_rewrite\_config\"]{.stringliteral};
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [// Extracts a \`SavedModelConfig\` proto from
the optional asset file in the]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [// given directory. If the asset file does
not exist, it returns an empty]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [// proto.]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} absl::StatusOr\<SavedModelConfig\>
LoadSavedModelConfigOrDefault(
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [const]{.keyword} std::string& export\_dir);
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [// Updates \`rewrite\_options\` based on
optimizers options in \`session\_overrides\`.]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [void]{.keywordtype} UpdateRewriterConfig(
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [const]{.keyword}
tensorflow::serving::SessionOverrides& session\_overrides,
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  tensorflow::RewriterConfig\*
rewrite\_options);
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} 
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} [\#endif ]{.preprocessor}[//
\#define]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [//
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_SAVED\_MODEL\_CONFIG\_UTIL\_H\_]{.comment}
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

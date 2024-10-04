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
version.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2018 The TensorFlow Authors. All
Rights Reserved.]{.comment}
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
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_VERSION\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_VERSION\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [// TF Serving Model Server uses semantic
versioning for releases]{.comment}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [// - see http://semver.org/. For nightlies, a
git hash is used to track the]{.comment}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [// build via linkstamping]{.comment}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#define TF\_MODELSERVER\_STR\_HELPER(x)
\#x]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#define TF\_MODELSERVER\_STR(x)
TF\_MODELSERVER\_STR\_HELPER(x)]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} 
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#define TF\_MODELSERVER\_MAJOR\_VERSION
0]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#define TF\_MODELSERVER\_MINOR\_VERSION
0]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#define TF\_MODELSERVER\_PATCH\_VERSION
0]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [// TF\_MODELSERVER\_VERSION\_SUFFIX is
non-empty for pre-releases]{.comment}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [// (e.g. \"-alpha\", \"-alpha.1\", \"-beta\",
\"-rc\", \"-rc.1\")]{.comment}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#define TF\_MODELSERVER\_VERSION\_SUFFIX
\"\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} 
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [\#ifndef
TF\_MODELSERVER\_VERSION\_NO\_META]{.preprocessor}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// TF\_MODELSERVER\_BUILD\_TAG can be set to
be nightly for nightly builds]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [\#ifndef
TF\_MODELSERVER\_BUILD\_TAG]{.preprocessor}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [\#define TF\_MODELSERVER\_META\_TAG
\"+dev\"]{.preprocessor}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [\#else]{.preprocessor}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [\#define TF\_MODELSERVER\_META\_TAG
\"+\"]{.preprocessor} TF\_MODELSERVER\_STR(TF\_MODELSERVER\_BUILD\_TAG)
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [\#endif]{.preprocessor}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [\#define TF\_MODELSERVER\_META\_SCM\_HASH
\".sha.\"]{.preprocessor} BUILD\_SCM\_REVISION
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [\#else]{.preprocessor}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [\#define TF\_MODELSERVER\_META\_TAG
\"\"]{.preprocessor}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [\#define TF\_MODELSERVER\_META\_SCM\_HASH
\"\"]{.preprocessor}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [\#endif]{.preprocessor}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [// e.g. \"0.5.0+nightly.sha.a1b2c3d\" or
\"0.6.0-rc1\".]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [// clang-format off]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [\#define TF\_MODELSERVER\_VERSION\_STRING
\\]{.preprocessor}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [
(TF\_MODELSERVER\_STR(TF\_MODELSERVER\_MAJOR\_VERSION)
\".\"]{.preprocessor} TF\_MODELSERVER\_STR( \\
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  TF\_MODELSERVER\_MINOR\_VERSION) \".\"
TF\_MODELSERVER\_STR( \\
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  TF\_MODELSERVER\_PATCH\_VERSION)
TF\_MODELSERVER\_VERSION\_SUFFIX \\
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  TF\_MODELSERVER\_META\_TAG
TF\_MODELSERVER\_META\_SCM\_HASH)
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [// clang-format on]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} 
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [extern]{.keyword} [\"C\"]{.stringliteral} {
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} [const]{.keyword} [char]{.keywordtype}\*
TF\_Serving\_Version();
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} }
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} 
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_VERSION\_H\_]{.comment}
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

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
http\_rest\_api\_util.h
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
THIRD\_PARTY\_TENSORFLOW\_SERVING\_MODEL\_SERVERS\_HTTP\_REST\_API\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
THIRD\_PARTY\_TENSORFLOW\_SERVING\_MODEL\_SERVERS\_HTTP\_REST\_API\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} 
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"absl/strings/string\_view.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"absl/types/optional.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include \"re2/re2.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/apis/get\_model\_metadata.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow\_serving/apis/get\_model\_status.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow\_serving/apis/model.pb.h\"]{.preprocessor}
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
[]{#l00033}[ 33]{.lineno} [const]{.keyword} [char]{.keywordtype}\*
[const]{.keyword} kHTTPRestApiHandlerPathRegex =
[\"(?i)/v1/.\*\"]{.stringliteral};
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} 
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [void]{.keywordtype}
AddHeaders(std::vector\<std::pair\<string, string\>\>\* headers);
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [void]{.keywordtype}
AddCORSHeaders(std::vector\<std::pair\<string, string\>\>\* headers);
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} Status FillModelSpecWithNameVersionAndLabel(
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [const]{.keyword} absl::string\_view
model\_name,
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [const]{.keyword} absl::optional\<int64\_t\>&
model\_version,
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [const]{.keyword}
absl::optional\<absl::string\_view\> model\_version\_label,
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  ::tensorflow::serving::ModelSpec\*
model\_spec);
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [// Parse model information from the
request.]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} Status ParseModelInfo([const]{.keyword}
absl::string\_view http\_method,
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [const]{.keyword} absl::string\_view
request\_path, [string]{.keywordtype}\* model\_name,
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  absl::optional\<int64\_t\>\* model\_version,
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  absl::optional\<string\>\*
model\_version\_label,
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [string]{.keywordtype}\* method,
[string]{.keywordtype}\* model\_subresource,
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [bool]{.keywordtype}\* parse\_successful);
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} 
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} Status ToJsonString([const]{.keyword}
GetModelStatusResponse& response, [string]{.keywordtype}\* output);
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} 
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} Status ToJsonString([const]{.keyword}
GetModelMetadataResponse& response, [string]{.keywordtype}\* output);
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} 
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} 
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} [\#endif ]{.preprocessor}[//
THIRD\_PARTY\_TENSORFLOW\_SERVING\_MODEL\_SERVERS\_HTTP\_REST\_API\_UTIL\_H\_]{.comment}
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

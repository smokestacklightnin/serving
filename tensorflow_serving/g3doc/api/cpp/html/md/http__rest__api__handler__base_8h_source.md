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
http\_rest\_api\_handler\_base.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2022 Google Inc. All Rights
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
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_HTTP\_REST\_API\_HANDLER\_BASE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_HTTP\_REST\_API\_HANDLER\_BASE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<utility\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} 
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"absl/strings/string\_view.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
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
[]{#l00030}[ 30]{.lineno} [// Base class of HttpRestApiHandler classes
that handles HTTP/REST APIs of TF]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [// serving.]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// Currently supported APIs are as
follows:]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [// o Inference -
Classify/Regress/Predict]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [// POST
/v1/models/\<model\_name\>:(classify\|regress)]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [// POST
/v1/models/\<model\_name\>/versions/\<ver\>:(classify\|regress)]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [// o Model status]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [// GET /v1/models/\<model\_name\> (status of
all versions)]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [// GET
/v1/models/\<model\_name\>/versions/\<ver\> (status of specific
version)]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [// The API is documented here:]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [//
tensorflow\_serving/g3doc/api\_rest.md]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [// Users of this class should typically
create one instance of it at process]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [// startup, register paths defined by
kPathRegex with the in-process HTTP]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [// server, and when a request arrives,
forward the request to ProcessRequest()]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} [// method.]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} [// This class is thread safe.]{.comment}
:::

::: {.line}
[]{#l00054}[
[54](classtensorflow_1_1serving_1_1HttpRestApiHandlerBase.html){.line}]{.lineno} [class
]{.keyword}[HttpRestApiHandlerBase](classtensorflow_1_1serving_1_1HttpRestApiHandlerBase.html){.code}
{
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [virtual]{.keyword}
\~[HttpRestApiHandlerBase](classtensorflow_1_1serving_1_1HttpRestApiHandlerBase.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} 
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [// Process a HTTP request.]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [// In case of errors, the \`headers\` and
\`output\` are still relevant as they]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [// contain detailed error messages, that can
be relayed back to the client.]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [virtual]{.keyword} Status
ProcessRequest([const]{.keyword} absl::string\_view http\_method,
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [const]{.keyword} absl::string\_view
request\_path,
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  [const]{.keyword} absl::string\_view
request\_body,
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  std::vector\<std::pair\<string, string\>\>\*
headers,
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [string]{.keywordtype}\* model\_name,
[string]{.keywordtype}\* method,
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [string]{.keywordtype}\* output) = 0;
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} };
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} 
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_HTTP\_REST\_API\_HANDLER\_BASE\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1HttpRestApiHandlerBase_html .ttc}
::: {.ttname}
[tensorflow::serving::HttpRestApiHandlerBase](classtensorflow_1_1serving_1_1HttpRestApiHandlerBase.html)
:::

::: {.ttdef}
**Definition:** http\_rest\_api\_handler\_base.h:54
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

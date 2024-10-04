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
http\_rest\_api\_handler.h
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
[]{#l00015}[ 15]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_HTTP\_REST\_API\_HANDLER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00016}[ 16]{.lineno} [\#define
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_HTTP\_REST\_API\_HANDLER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} 
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<utility\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} 
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"absl/strings/string\_view.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"absl/types/optional.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include \"re2/re2.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow/core/protobuf/config.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow/core/protobuf/meta\_graph.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow\_serving/model\_servers/http\_rest\_api\_handler\_base.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} 
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} 
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [class ]{.keyword}SignatureDef;
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} 
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [class ]{.keyword}ServerCore;
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [class ]{.keyword}TensorflowPredictor;
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [class ]{.keyword}ModelSpec;
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [// HttpRestApiHandler handles HTTP/REST APIs
of TF serving.]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [// Currently supported APIs are as
follows:]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [// o Inference -
Classify/Regress/Predict]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [// POST
/v1/models/\<model\_name\>:(classify\|regress\|predict)]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [// POST
/v1/models/\<model\_name\>/versions/\<ver\>:(classify\|regress\|predict)]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [// o Model status]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [// GET /v1/models/\<model\_name\> (status of
all versions)]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} [// GET
/v1/models/\<model\_name\>/versions/\<ver\> (status of specific
version)]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} [// The API is documented here:]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} [//
tensorflow\_serving/g3doc/api\_rest.md]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} [// Users of this class should typically
create one instance of it at process]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} [// startup, register paths defined by
kPathRegex with the in-process HTTP]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} [// server, and when a request arrives,
forward the request to ProcessRequest()]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} [// method.]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} [// This class is thread safe.]{.comment}
:::

::: {.line}
[]{#l00064}[
[64](classtensorflow_1_1serving_1_1HttpRestApiHandler.html){.line}]{.lineno} [class
]{.keyword}[HttpRestApiHandler](classtensorflow_1_1serving_1_1HttpRestApiHandler.html){.code}
: [public]{.keyword}
[HttpRestApiHandlerBase](classtensorflow_1_1serving_1_1HttpRestApiHandlerBase.html){.code}
{
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [// Returns a regex that captures all API
paths handled by this handler.]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [// Typical use of this method is to register
request paths with underlying]{.comment}
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [// HTTP server, so incoming requests can be
forwarded to this handler.]{.comment}
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype}\* [const]{.keyword} kPathRegex;
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} 
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  [// API calls are configured to timeout after
\`timeout\_in\_ms\`.]{.comment}
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [// \`core\` is not owned and is expected to
outlive HttpRestApiHandler]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [// instance.]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} 
[HttpRestApiHandler](classtensorflow_1_1serving_1_1HttpRestApiHandler.html){.code}([int]{.keywordtype}
timeout\_in\_ms,
[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.code}\*
core);
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} 
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} 
\~[HttpRestApiHandler](classtensorflow_1_1serving_1_1HttpRestApiHandler.html){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} 
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [// Process a HTTP request.]{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [// In case of errors, the \`headers\` and
\`output\` are still relevant as they]{.comment}
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  [// contain detailed error messages, that can
be relayed back to the client.]{.comment}
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  Status ProcessRequest([const]{.keyword}
absl::string\_view http\_method,
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  [const]{.keyword} absl::string\_view
request\_path,
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [const]{.keyword} absl::string\_view
request\_body,
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  std::vector\<std::pair\<string, string\>\>\*
headers,
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  [string]{.keywordtype}\* model\_name,
[string]{.keywordtype}\* method,
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  [string]{.keywordtype}\* output)
[override]{.keyword};
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} 
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  Status ProcessClassifyRequest(
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  [const]{.keyword} absl::string\_view
model\_name,
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [const]{.keyword} absl::optional\<int64\_t\>&
model\_version,
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  [const]{.keyword}
absl::optional\<absl::string\_view\>& model\_version\_label,
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  [const]{.keyword} absl::string\_view
request\_body, [string]{.keywordtype}\* output);
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  Status ProcessRegressRequest(
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  [const]{.keyword} absl::string\_view
model\_name,
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  [const]{.keyword} absl::optional\<int64\_t\>&
model\_version,
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  [const]{.keyword}
absl::optional\<absl::string\_view\>& model\_version\_label,
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  [const]{.keyword} absl::string\_view
request\_body, [string]{.keywordtype}\* output);
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  Status ProcessPredictRequest(
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  [const]{.keyword} absl::string\_view
model\_name,
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [const]{.keyword}
absl::optional\<int64\_t\>& model\_version,
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  [const]{.keyword}
absl::optional\<absl::string\_view\>& model\_version\_label,
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  [const]{.keyword} absl::string\_view
request\_body, [string]{.keywordtype}\* output);
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  Status ProcessModelStatusRequest(
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  [const]{.keyword} absl::string\_view
model\_name,
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [const]{.keyword}
absl::optional\<int64\_t\>& model\_version,
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  [const]{.keyword}
absl::optional\<absl::string\_view\>& model\_version\_label,
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  [string]{.keywordtype}\* output);
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  Status ProcessModelMetadataRequest(
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  [const]{.keyword} absl::string\_view
model\_name,
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  [const]{.keyword}
absl::optional\<int64\_t\>& model\_version,
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  [const]{.keyword}
absl::optional\<absl::string\_view\>& model\_version\_label,
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [string]{.keywordtype}\* output);
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  Status GetInfoMap([const]{.keyword}
ModelSpec& model\_spec, [const]{.keyword} [string]{.keywordtype}&
signature\_name,
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  ::google::protobuf::Map\<string,
tensorflow::TensorInfo\>\* infomap);
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} 
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  RunOptions run\_options\_;
:::

::: {.line}
[]{#l00119}[ 119]{.lineno} 
[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.code}\*
core\_;
:::

::: {.line}
[]{#l00120}[ 120]{.lineno}  std::unique\_ptr\<TensorflowPredictor\>
predictor\_;
:::

::: {.line}
[]{#l00121}[ 121]{.lineno} };
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} 
:::

::: {.line}
[]{#l00123}[ 123]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00124}[ 124]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} 
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_HTTP\_REST\_API\_HANDLER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1HttpRestApiHandlerBase_html .ttc}
::: {.ttname}
[tensorflow::serving::HttpRestApiHandlerBase](classtensorflow_1_1serving_1_1HttpRestApiHandlerBase.html)
:::

::: {.ttdef}
**Definition:** http\_rest\_api\_handler\_base.h:54
:::
:::

::: {#aclasstensorflow_1_1serving_1_1HttpRestApiHandler_html .ttc}
::: {.ttname}
[tensorflow::serving::HttpRestApiHandler](classtensorflow_1_1serving_1_1HttpRestApiHandler.html)
:::

::: {.ttdef}
**Definition:** http\_rest\_api\_handler.h:64
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServerCore_html .ttc}
::: {.ttname}
[tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html)
:::

::: {.ttdef}
**Definition:** server\_core.h:74
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

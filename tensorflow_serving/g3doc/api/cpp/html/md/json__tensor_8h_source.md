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
json\_tensor.h
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
TENSORFLOW\_SERVING\_UTIL\_JSON\_TENSOR\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_UTIL\_JSON\_TENSOR\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<functional\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<string\>]{.preprocessor}
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
\"tensorflow/core/framework/tensor.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/protobuf/meta\_graph.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/apis/classification.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow\_serving/apis/predict.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow\_serving/apis/regression.pb.h\"]{.preprocessor}
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
[]{#l00033}[ 33]{.lineno} [// Format of input tensors in predict
request.]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// See comments for
FillPredictRequestFromJson() below for more details.]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [enum class]{.keyword}
JsonPredictRequestFormat {
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  kInvalid,
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  kRow,
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  kColumnar,
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} };
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [// Fills PredictRequest proto from a JSON
object.]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [// \`json\` string is parsed to create
TensorProtos based on the type map returned]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [// via \`get\_tensorinfo\_map\` and added to
\`PredictRequest.inputs\`. Both maps are]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [// keyed by the name/alias of the tensor as
it appears in the TensorFlow graph,]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [// and must contain at-least one entry. The
name to \<type\> (e.g. DT\_FLOAT etc.)]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [// mapping is typically part of the graph
metadata.]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [// Following fields of the request proto are
filled in:]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} [// \`model\_spec.signature\_name\`
(string)]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [// \`inputs\` (map string -\>
tensors)]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [// The JSON object is expected to be
formatted as follows:]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} [// {]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} [// \"signature\_name\": \<string\>]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} [// (\"instances\"\|\"inputs\"): \[
\<value\>\|\<(nested)list\>\|\<object\>, \... \]]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} [// The \"signature\_name\" is \*optional\*
(if not specified, default serving]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} [// signature is used). The \"instances\" or
\"inputs\" represents list of tensors]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} [// (read further on the formatting of these
tensors below). Any other keys in]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} [// the top-level JSON object are
ignored.]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} [// \"instances\" is used to format input
tensors in \"row\" format and \"inputs\"]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} [// is used to format them in \"columnar\"
format. The former is easy to read]{.comment}
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} [// but requires all inputs to have same 0-th
dimension whereas the latter]{.comment}
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} [// can represent input tensors with varying
sizes.]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} [// === Notes on formatting of \"instances\"
(row format) in the JSON ===]{.comment}
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} [// The \"instances\" represents a list of
tensors (all of same shape+type), and]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} [// this function builds a stack of these
tensors (represented as tensor). If the]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} [// list has tensors of rank-R, the output
tensor is of rank R+1.]{.comment}
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} [// The \"instances\" (key) maps to list of
tensors (value). Each element of the]{.comment}
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} [// list is of same type (and nesting, in case
listoflists).]{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} [// {]{.comment}
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} [// \"instances\": \[
\<value\>\|\<(nested)list\>\|\<object\>, \... \]]{.comment}
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} [// This formatting is similar to CMLE predict
API:]{.comment}
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} [//
https://cloud.google.com/ml-engine/docs/v1/predict-request]{.comment}
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} [// o When there is only one named input
(tensorinfo\_map has only one key),]{.comment}
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} [// the list items are expected to be scalars
(number/string) or lists of]{.comment}
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} [// these primitive types.]{.comment}
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} [// {]{.comment}
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} [// \"instances\": \[ \"foo\", \"bar\",
\"baz\" \]]{.comment}
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} [// {]{.comment}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} [// \"instances\": \[ \[\[1, 2\]\], \[\[3\],
\[4\]\] \]]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00099}[ 99]{.lineno} [// o For multiple named inputs
(tensorinfo\_map has \>1 keys), each item is]{.comment}
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} [// expected to be an object containing
key(name)/value(tensor) pairs, one]{.comment}
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} [// for each named input. Representing 2
instaces of a set of 3 named input]{.comment}
:::

::: {.line}
[]{#l00102}[ 102]{.lineno} [// tensors would look as follows:]{.comment}
:::

::: {.line}
[]{#l00103}[ 103]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00104}[ 104]{.lineno} [// {]{.comment}
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} [// \"instances\": \[]{.comment}
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} [// {]{.comment}
:::

::: {.line}
[]{#l00107}[ 107]{.lineno} [// \"tag\": \[\"foo\"\],]{.comment}
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} [// \"signal\": \[1, 2, 3, 4, 5\],]{.comment}
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} [// \"sensor\": \[\[1, 2\], \[3,
4\]\]]{.comment}
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} [// },]{.comment}
:::

::: {.line}
[]{#l00111}[ 111]{.lineno} [// {]{.comment}
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} [// \"tag\": \[\"bar\"\],]{.comment}
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} [// \"signal\": \[3, 4, 1, 2, 5\],]{.comment}
:::

::: {.line}
[]{#l00114}[ 114]{.lineno} [// \"sensor\": \[\[4, 5\], \[6,
8\]\]]{.comment}
:::

::: {.line}
[]{#l00115}[ 115]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00116}[ 116]{.lineno} [// \]]{.comment}
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00118}[ 118]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00119}[ 119]{.lineno} [// o Default encoding of strings is UTF-8.
To express binary data (like image]{.comment}
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} [// bytes) use a JSON object \'{ \"b64\":
\"\<base64-encoded-data\>\" }\' instead of]{.comment}
:::

::: {.line}
[]{#l00121}[ 121]{.lineno} [// a raw string. Following example shows
list of 2 binary strings:]{.comment}
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00123}[ 123]{.lineno} [// {]{.comment}
:::

::: {.line}
[]{#l00124}[ 124]{.lineno} [// \"instances\": \[ { \"b64\" :
\"aGVsbG8=\" }, { \"b64\": \"d29ybGQ=\" } \]]{.comment}
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00127}[ 127]{.lineno} [// === Notes on formatting of \"inputs\"
(columnar format) in the JSON ===]{.comment}
:::

::: {.line}
[]{#l00128}[ 128]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00129}[ 129]{.lineno} [// The value for \"inputs\" key is either a
single input tensor or a map]{.comment}
:::

::: {.line}
[]{#l00130}[ 130]{.lineno} [// of input name to tensor values. Each
input can have arbitrary shape]{.comment}
:::

::: {.line}
[]{#l00131}[ 131]{.lineno} [// and need not share the same 0-th
dimension as required by the row]{.comment}
:::

::: {.line}
[]{#l00132}[ 132]{.lineno} [// format described above.]{.comment}
:::

::: {.line}
[]{#l00133}[ 133]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00134}[ 134]{.lineno} [// This format is similar to the \`inputs\`
field in request proto of]{.comment}
:::

::: {.line}
[]{#l00135}[ 135]{.lineno} [// gRPC Predict API. And compact compared to
the row format]{.comment}
:::

::: {.line}
[]{#l00136}[ 136]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00137}[ 137]{.lineno} [// A sample (compare this to \"instances\"
above) is as follows:]{.comment}
:::

::: {.line}
[]{#l00138}[ 138]{.lineno} [// {]{.comment}
:::

::: {.line}
[]{#l00139}[ 139]{.lineno} [// \"inputs\": {]{.comment}
:::

::: {.line}
[]{#l00140}[ 140]{.lineno} [// \"tag\": \[\"foo\", \"bar\"\],]{.comment}
:::

::: {.line}
[]{#l00141}[ 141]{.lineno} [// \"signal\": \[1, 2, 3, 4, 5, 3, 4, 1, 2,
4\],]{.comment}
:::

::: {.line}
[]{#l00142}[ 142]{.lineno} [// \"sensor\": \[\[1, 2\], \[3, 4\], \[4,
5\], \[6, 8\]\]]{.comment}
:::

::: {.line}
[]{#l00143}[ 143]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00144}[ 144]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00145}[ 145]{.lineno} tensorflow::Status
FillPredictRequestFromJson(
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  [const]{.keyword} absl::string\_view json,
:::

::: {.line}
[]{#l00147}[ 147]{.lineno}  [const]{.keyword}
std::function\<tensorflow::Status(
:::

::: {.line}
[]{#l00148}[ 148]{.lineno}  [const]{.keyword} [string]{.keywordtype}&,
::google::protobuf::Map\<string, tensorflow::TensorInfo\>\*)\>&
:::

::: {.line}
[]{#l00149}[ 149]{.lineno}  get\_tensorinfo\_map,
:::

::: {.line}
[]{#l00150}[ 150]{.lineno}  PredictRequest\* request,
JsonPredictRequestFormat\* format);
:::

::: {.line}
[]{#l00151}[ 151]{.lineno} 
:::

::: {.line}
[]{#l00152}[ 152]{.lineno} [// Fills ClassificationRequest proto from a
JSON object.]{.comment}
:::

::: {.line}
[]{#l00153}[ 153]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00154}[ 154]{.lineno} [// \`json\` string is parsed to create
\`Example\` protos and added to]{.comment}
:::

::: {.line}
[]{#l00155}[ 155]{.lineno} [//
\`ClassificationRequest.inputs\`.]{.comment}
:::

::: {.line}
[]{#l00156}[ 156]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00157}[ 157]{.lineno} [// Following fields of the request proto are
filled in:]{.comment}
:::

::: {.line}
[]{#l00158}[ 158]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00159}[ 159]{.lineno} [// \`model\_spec.signature\_name\`
(string)]{.comment}
:::

::: {.line}
[]{#l00160}[ 160]{.lineno} [// \`input\` (list of example
protos)]{.comment}
:::

::: {.line}
[]{#l00161}[ 161]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00162}[ 162]{.lineno} [// The JSON object is expected to be
formatted as follows:]{.comment}
:::

::: {.line}
[]{#l00163}[ 163]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00164}[ 164]{.lineno} [// {]{.comment}
:::

::: {.line}
[]{#l00165}[ 165]{.lineno} [// \"signature\_name\":
\<string\>]{.comment}
:::

::: {.line}
[]{#l00166}[ 166]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00167}[ 167]{.lineno} [// \"context\": {]{.comment}
:::

::: {.line}
[]{#l00168}[ 168]{.lineno} [// // Common (example) context shared by all
examples.]{.comment}
:::

::: {.line}
[]{#l00169}[ 169]{.lineno} [// \"\<feature\_name3\>\":
\<value\>\|\<list\>]{.comment}
:::

::: {.line}
[]{#l00170}[ 170]{.lineno} [// \"\<feature\_name4\>\":
\<value\>\|\<list\>]{.comment}
:::

::: {.line}
[]{#l00171}[ 171]{.lineno} [// },]{.comment}
:::

::: {.line}
[]{#l00172}[ 172]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00173}[ 173]{.lineno} [// \"examples\": \[]{.comment}
:::

::: {.line}
[]{#l00174}[ 174]{.lineno} [// {]{.comment}
:::

::: {.line}
[]{#l00175}[ 175]{.lineno} [// // Example 1]{.comment}
:::

::: {.line}
[]{#l00176}[ 176]{.lineno} [// \"\<feature\_name\>\":
\<value\>\|\<list\>]{.comment}
:::

::: {.line}
[]{#l00177}[ 177]{.lineno} [// \"\<feature\_name2\>\":
\<value\>\|\<list\>]{.comment}
:::

::: {.line}
[]{#l00178}[ 178]{.lineno} [// },]{.comment}
:::

::: {.line}
[]{#l00179}[ 179]{.lineno} [// {]{.comment}
:::

::: {.line}
[]{#l00180}[ 180]{.lineno} [// // Example 2]{.comment}
:::

::: {.line}
[]{#l00181}[ 181]{.lineno} [// \"\<feature\_name\>\":
\<value\>\|\<list\>]{.comment}
:::

::: {.line}
[]{#l00182}[ 182]{.lineno} [// \"\<feature\_name2\>\":
\<value\>\|\<list\>]{.comment}
:::

::: {.line}
[]{#l00183}[ 183]{.lineno} [// },]{.comment}
:::

::: {.line}
[]{#l00184}[ 184]{.lineno} [// \]]{.comment}
:::

::: {.line}
[]{#l00185}[ 185]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00186}[ 186]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00187}[ 187]{.lineno} [// The \"signature\_name\" is \*optional\*
(if not specified, default serving]{.comment}
:::

::: {.line}
[]{#l00188}[ 188]{.lineno} [// signature is used). \"context\" is also
optional. \"exampless\" represents]{.comment}
:::

::: {.line}
[]{#l00189}[ 189]{.lineno} [// list of examples. Any other keys in the
top-level JSON object are ignored.]{.comment}
:::

::: {.line}
[]{#l00190}[ 190]{.lineno} tensorflow::Status
FillClassificationRequestFromJson(
:::

::: {.line}
[]{#l00191}[ 191]{.lineno}  [const]{.keyword} absl::string\_view json,
ClassificationRequest\* request);
:::

::: {.line}
[]{#l00192}[ 192]{.lineno} 
:::

::: {.line}
[]{#l00193}[ 193]{.lineno} [// Same as
FillClassificationRequestFromJson() but fills a
RegressionRequest.]{.comment}
:::

::: {.line}
[]{#l00194}[ 194]{.lineno} [// See comments above on how Example protos
are expected to be formatted.]{.comment}
:::

::: {.line}
[]{#l00195}[ 195]{.lineno} tensorflow::Status
FillRegressionRequestFromJson([const]{.keyword} absl::string\_view json,
:::

::: {.line}
[]{#l00196}[ 196]{.lineno}  RegressionRequest\* request);
:::

::: {.line}
[]{#l00197}[ 197]{.lineno} 
:::

::: {.line}
[]{#l00198}[ 198]{.lineno} [// Make JSON object from
TensorProtos.]{.comment}
:::

::: {.line}
[]{#l00199}[ 199]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00200}[ 200]{.lineno} [// \`tensor\_map\` contains a map of
name/alias tensor names (as it appears in the]{.comment}
:::

::: {.line}
[]{#l00201}[ 201]{.lineno} [// TensorFlow graph) to tensor protos. The
output \`json\` string is JSON object]{.comment}
:::

::: {.line}
[]{#l00202}[ 202]{.lineno} [// containing all the tensors represented by
these tensor protos. The]{.comment}
:::

::: {.line}
[]{#l00203}[ 203]{.lineno} [// composition of output JSON depends on
\`format\` (read further for details).]{.comment}
:::

::: {.line}
[]{#l00204}[ 204]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00205}[ 205]{.lineno} [// In case of error the contents of output
\`json\` should not be used.]{.comment}
:::

::: {.line}
[]{#l00206}[ 206]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00207}[ 207]{.lineno} [// Tensors containing binary data (e.g.
image bytes) are base64 encoded in the]{.comment}
:::

::: {.line}
[]{#l00208}[ 208]{.lineno} [// JSON object. The name/alias for these
tensors MUST have \"\_bytes\" as suffix,]{.comment}
:::

::: {.line}
[]{#l00209}[ 209]{.lineno} [// to ensure JSON has correct (base64)
encoding, otherwise the resulting JSON]{.comment}
:::

::: {.line}
[]{#l00210}[ 210]{.lineno} [// may not represent the output correctly
and/or may not be parsable.]{.comment}
:::

::: {.line}
[]{#l00211}[ 211]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00212}[ 212]{.lineno} [// Formatting when \`format\` is
\`kRow\`:]{.comment}
:::

::: {.line}
[]{#l00213}[ 213]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00214}[ 214]{.lineno} [// Tensors appear as list (with \"batch\"
size elements) keyed by \"predictions\"]{.comment}
:::

::: {.line}
[]{#l00215}[ 215]{.lineno} [// in the JSON object:]{.comment}
:::

::: {.line}
[]{#l00216}[ 216]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00217}[ 217]{.lineno} [// {]{.comment}
:::

::: {.line}
[]{#l00218}[ 218]{.lineno} [// \"predictions\": \[
\<value\>\|\<(nested)list\>\|\<object\>, \...\]]{.comment}
:::

::: {.line}
[]{#l00219}[ 219]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00220}[ 220]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00221}[ 221]{.lineno} [// If \`tensor\_map\` contains only one
key/named tensor, the \"predictions\" key]{.comment}
:::

::: {.line}
[]{#l00222}[ 222]{.lineno} [// contains a array of \<value\> or
\<(nested)list\> otherwise it is an array of]{.comment}
:::

::: {.line}
[]{#l00223}[ 223]{.lineno} [// JSON objects. See comments for
FillPredictRequestFromJson() above for]{.comment}
:::

::: {.line}
[]{#l00224}[ 224]{.lineno} [// formatting details (and unit-test of
examples).]{.comment}
:::

::: {.line}
[]{#l00225}[ 225]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00226}[ 226]{.lineno} [// The first dimension in each of these
tensors is assumed to be the \"batch\"]{.comment}
:::

::: {.line}
[]{#l00227}[ 227]{.lineno} [// size and it is expected that all tensors
have the \*same\* batch size \--]{.comment}
:::

::: {.line}
[]{#l00228}[ 228]{.lineno} [// otherwise we return an error.]{.comment}
:::

::: {.line}
[]{#l00229}[ 229]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00230}[ 230]{.lineno} [// Note, this formatting is similar to CMLE
predict API:]{.comment}
:::

::: {.line}
[]{#l00231}[ 231]{.lineno} [//
https://cloud.google.com/ml-engine/docs/v1/predict-request\#response-body]{.comment}
:::

::: {.line}
[]{#l00232}[ 232]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00233}[ 233]{.lineno} [// Formatting when \`format\` is
\`kColumnar\`]{.comment}
:::

::: {.line}
[]{#l00234}[ 234]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00235}[ 235]{.lineno} [// Tensors appear as list (when there is
only one named output) or as a JSON]{.comment}
:::

::: {.line}
[]{#l00236}[ 236]{.lineno} [// object, with one key-value pair for each
named input, keyed by \"outputs\"]{.comment}
:::

::: {.line}
[]{#l00237}[ 237]{.lineno} [// in the JSON object.]{.comment}
:::

::: {.line}
[]{#l00238}[ 238]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00239}[ 239]{.lineno} [// Unlike \`kRow\` format (see above) each
named tensor can have different first]{.comment}
:::

::: {.line}
[]{#l00240}[ 240]{.lineno} [// dimension. This format is compact and
matches closely with the response]{.comment}
:::

::: {.line}
[]{#l00241}[ 241]{.lineno} [// proto of the gRPC predict API.]{.comment}
:::

::: {.line}
[]{#l00242}[ 242]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00243}[ 243]{.lineno} [// Only one named output:]{.comment}
:::

::: {.line}
[]{#l00244}[ 244]{.lineno} [// {]{.comment}
:::

::: {.line}
[]{#l00245}[ 245]{.lineno} [// \"outputs\": \[
\<value\>\|\<(nested)list\> \]]{.comment}
:::

::: {.line}
[]{#l00246}[ 246]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00247}[ 247]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00248}[ 248]{.lineno} [// Multiple named output:]{.comment}
:::

::: {.line}
[]{#l00249}[ 249]{.lineno} [// {]{.comment}
:::

::: {.line}
[]{#l00250}[ 250]{.lineno} [// \"outputs\": {]{.comment}
:::

::: {.line}
[]{#l00251}[ 251]{.lineno} [// \"named\_output\_foo\": \[
\<value\>\|\<(nested)list\> \],]{.comment}
:::

::: {.line}
[]{#l00252}[ 252]{.lineno} [// \"named\_output\_bar\": \[
\<value\>\|\<(nested)list\> \],]{.comment}
:::

::: {.line}
[]{#l00253}[ 253]{.lineno} [// \...]{.comment}
:::

::: {.line}
[]{#l00254}[ 254]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00255}[ 255]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00256}[ 256]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00257}[ 257]{.lineno} [// See comments for
FillPredictRequestFromJson() above for formatting details]{.comment}
:::

::: {.line}
[]{#l00258}[ 258]{.lineno} [// (and unit-test of examples).]{.comment}
:::

::: {.line}
[]{#l00259}[ 259]{.lineno} tensorflow::Status MakeJsonFromTensors(
:::

::: {.line}
[]{#l00260}[ 260]{.lineno}  const ::google::protobuf::Map\<string,
tensorflow::TensorProto\>& tensor\_map,
:::

::: {.line}
[]{#l00261}[ 261]{.lineno}  JsonPredictRequestFormat format,
[string]{.keywordtype}\* json);
:::

::: {.line}
[]{#l00262}[ 262]{.lineno} 
:::

::: {.line}
[]{#l00263}[ 263]{.lineno} [// Make JSON object from
ClassificationResult proto.]{.comment}
:::

::: {.line}
[]{#l00264}[ 264]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00265}[ 265]{.lineno} [// The output JSON object is formatted as
follows:]{.comment}
:::

::: {.line}
[]{#l00266}[ 266]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00267}[ 267]{.lineno} [// {]{.comment}
:::

::: {.line}
[]{#l00268}[ 268]{.lineno} [// \"result\": \[]{.comment}
:::

::: {.line}
[]{#l00269}[ 269]{.lineno} [// // List of class label/score pairs for
first Example (in request)]{.comment}
:::

::: {.line}
[]{#l00270}[ 270]{.lineno} [// \[ \[ \<label1\>, \<score1\> \], \[
\<label2\>, \<score2\> \], \... \],]{.comment}
:::

::: {.line}
[]{#l00271}[ 271]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00272}[ 272]{.lineno} [// // List of class label/score pairs for
next Example (in request)]{.comment}
:::

::: {.line}
[]{#l00273}[ 273]{.lineno} [// \[ \[ \<label1\>, \<score1\> \], \[
\<label2\>, \<score2\> \], \... \],]{.comment}
:::

::: {.line}
[]{#l00274}[ 274]{.lineno} [// \...]{.comment}
:::

::: {.line}
[]{#l00275}[ 275]{.lineno} [// \]]{.comment}
:::

::: {.line}
[]{#l00276}[ 276]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00277}[ 277]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00278}[ 278]{.lineno} [// Note, all the results are keyed by
\"result\" key in the JSON object, and]{.comment}
:::

::: {.line}
[]{#l00279}[ 279]{.lineno} [// they are ordered to match the
input/request ordering of Examples. \<label\>]{.comment}
:::

::: {.line}
[]{#l00280}[ 280]{.lineno} [// is a string, and \<score\> is a float
number. \<label\> can be missing from]{.comment}
:::

::: {.line}
[]{#l00281}[ 281]{.lineno} [// the results of graph evaluation, and
these would appear as empty strings]{.comment}
:::

::: {.line}
[]{#l00282}[ 282]{.lineno} [// in above JSON.]{.comment}
:::

::: {.line}
[]{#l00283}[ 283]{.lineno} tensorflow::Status
MakeJsonFromClassificationResult(
:::

::: {.line}
[]{#l00284}[ 284]{.lineno}  [const]{.keyword} ClassificationResult&
result, [string]{.keywordtype}\* json);
:::

::: {.line}
[]{#l00285}[ 285]{.lineno} 
:::

::: {.line}
[]{#l00286}[ 286]{.lineno} [// Make JSON object from RegressionResult
proto.]{.comment}
:::

::: {.line}
[]{#l00287}[ 287]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00288}[ 288]{.lineno} [// The output JSON object is formatted as
follows:]{.comment}
:::

::: {.line}
[]{#l00289}[ 289]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00290}[ 290]{.lineno} [// {]{.comment}
:::

::: {.line}
[]{#l00291}[ 291]{.lineno} [// // One regression value for each example
in the request in the same order.]{.comment}
:::

::: {.line}
[]{#l00292}[ 292]{.lineno} [// \"result\": \[ \<value1\>, \<value2\>,
\<value3\>, \...\]]{.comment}
:::

::: {.line}
[]{#l00293}[ 293]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00294}[ 294]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00295}[ 295]{.lineno} [// Note, all the results are keyed by
\"result\" key in the JSON object.]{.comment}
:::

::: {.line}
[]{#l00296}[ 296]{.lineno} [// \<value\> is a float number.]{.comment}
:::

::: {.line}
[]{#l00297}[ 297]{.lineno} tensorflow::Status
MakeJsonFromRegressionResult([const]{.keyword} RegressionResult& result,
:::

::: {.line}
[]{#l00298}[ 298]{.lineno}  [string]{.keywordtype}\* json);
:::

::: {.line}
[]{#l00299}[ 299]{.lineno} 
:::

::: {.line}
[]{#l00300}[ 300]{.lineno} [// Make JSON object from Status.]{.comment}
:::

::: {.line}
[]{#l00301}[ 301]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00302}[ 302]{.lineno} [// The output JSON object is formatted as
follows:]{.comment}
:::

::: {.line}
[]{#l00303}[ 303]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00304}[ 304]{.lineno} [// {]{.comment}
:::

::: {.line}
[]{#l00305}[ 305]{.lineno} [// \"error\": \"\<status error
message\>\"]{.comment}
:::

::: {.line}
[]{#l00306}[ 306]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00307}[ 307]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00308}[ 308]{.lineno} [// If \`status\` is OK then we do not append
anything to output \`json\`.]{.comment}
:::

::: {.line}
[]{#l00309}[ 309]{.lineno} [void]{.keywordtype}
MakeJsonFromStatus([const]{.keyword} tensorflow::Status& status,
[string]{.keywordtype}\* json);
:::

::: {.line}
[]{#l00310}[ 310]{.lineno} 
:::

::: {.line}
[]{#l00311}[ 311]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00312}[ 312]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00313}[ 313]{.lineno} 
:::

::: {.line}
[]{#l00314}[ 314]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_UTIL\_JSON\_TENSOR\_H\_]{.comment}
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

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
servable\_data.h
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
TENSORFLOW\_SERVING\_CORE\_SERVABLE\_DATA\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_SERVABLE\_DATA\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<algorithm\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<type\_traits\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} 
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow/core/platform/logging.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_id.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} 
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} 
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [// A servable id, and associated with it
either an error, or data of type T.]{.comment}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [// REQUIRES: T is move-constructible. T
cannot be Status.]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00032}[
[32](classtensorflow_1_1serving_1_1ServableData.html){.line}]{.lineno} [class
]{.keyword}[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.code}
{
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} 
static\_assert(std::is\_move\_constructible\<T\>::value,
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  [\"ServableData\<T\> requires that T is
move-constructible.\"]{.stringliteral});
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  static\_assert(
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  !std::is\_same\<T, Status\>::value,
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [\"ServableData\<T\> requires that T not be
tensorflow::serving::Status.\"]{.stringliteral});
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [// Creates a ServableData\<T\> with an okay
status.]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} 
[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.code}([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
[id]{.keywordtype}, T data);
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [// Creates a ServableData\<T\> with an error
status. Uses a default-constructed]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [// data value. CHECK-fails if
\'error.ok()\'.]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.code}([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
[id]{.keywordtype}, [const]{.keyword} Status& error);
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} 
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [// Copy constructor.]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} 
[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.code}([const]{.keyword}
[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.code}&
other) = [default]{.keywordflow};
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [// Assignment operator.]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.code}&
operator=([const]{.keyword}
[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.code}&
other) = [default]{.keywordflow};
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} 
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [// Move constructor.]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} 
[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.code}([ServableData](classtensorflow_1_1serving_1_1ServableData.html){.code}&&
other) = [default]{.keywordflow};
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} 
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
id()[ const ]{.keyword}{ [return]{.keywordflow} id\_; }
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} 
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [const]{.keyword} Status& status()[ const
]{.keyword}{ [return]{.keywordflow} status\_; }
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} 
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [// Returns a reference to the data, or
CHECK-fails if !this-\>ok().]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [const]{.keyword} T& DataOrDie()
[const]{.keyword};
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  T& DataOrDie();
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} 
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  [// Moves the data out of this object and
returns it, or CHECK-fails if]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [// !this-\>ok().]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  T ConsumeDataOrDie();
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.code}()
= [delete]{.keyword};
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} 
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  [const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}
id\_;
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [const]{.keyword} Status status\_;
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  T data\_;
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} };
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} 
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} [// Helper static method to create a
ServableData object. Caller may skip]{.comment}
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} [// specifying the template argument because
of ADL (argument dependent lookup)]{.comment}
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} [// unlike the ctor.]{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00080}[
80]{.lineno} [ServableData\<T\>](classtensorflow_1_1serving_1_1ServableData.html){.code}
CreateServableData([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
[id]{.keywordtype}, T data);
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} 
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} [// Implementation details follow. API users
need not read.]{.comment}
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} 
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00086}[
86]{.lineno} [ServableData\<T\>::ServableData](classtensorflow_1_1serving_1_1ServableData.html){.code}([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
[id]{.keywordtype}, T data)
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  : id\_(id), status\_(Status()),
data\_(std::move(data)) {}
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} 
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00090}[
90]{.lineno} ServableData\<T\>::ServableData([const]{.keyword}
ServableId& [id]{.keywordtype}, [const]{.keyword} Status& error)
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  : id\_(id), status\_(error) {
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  CHECK(!error.ok());
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} }
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} 
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} [const]{.keyword} T&
ServableData\<T\>::DataOrDie()[ const ]{.keyword}{
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  CHECK(status\_.ok());
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  [return]{.keywordflow} data\_;
:::

::: {.line}
[]{#l00099}[ 99]{.lineno} }
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} 
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00102}[ 102]{.lineno} T& ServableData\<T\>::DataOrDie() {
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  CHECK(status\_.ok());
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  [return]{.keywordflow} data\_;
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} }
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} 
:::

::: {.line}
[]{#l00107}[ 107]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} T ServableData\<T\>::ConsumeDataOrDie() {
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  [return]{.keywordflow}
std::move(DataOrDie());
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} }
:::

::: {.line}
[]{#l00111}[ 111]{.lineno} 
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} ServableData\<T\>
CreateServableData([const]{.keyword} ServableId& [id]{.keywordtype}, T
data) {
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [return]{.keywordflow}
ServableData\<T\>([id]{.keywordtype}, std::move(data));
:::

::: {.line}
[]{#l00115}[ 115]{.lineno} }
:::

::: {.line}
[]{#l00116}[ 116]{.lineno} 
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00118}[ 118]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00119}[ 119]{.lineno} 
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_SERVABLE\_DATA\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1ServableData_html .ttc}
::: {.ttname}
[tensorflow::serving::ServableData](classtensorflow_1_1serving_1_1ServableData.html)
:::

::: {.ttdef}
**Definition:** servable\_data.h:32
:::
:::

::: {#astructtensorflow_1_1serving_1_1ServableId_html .ttc}
::: {.ttname}
[tensorflow::serving::ServableId](structtensorflow_1_1serving_1_1ServableId.html)
:::

::: {.ttdef}
**Definition:** servable\_id.h:33
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

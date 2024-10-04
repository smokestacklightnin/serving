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
static\_source\_router.h
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
TENSORFLOW\_SERVING\_CORE\_STATIC\_SOURCE\_ROUTER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_STATIC\_SOURCE\_ROUTER\_H\_]{.preprocessor}
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
[]{#l00021}[ 21]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} 
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow/core/lib/strings/str\_util.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/core/source\_router.h\"]{.preprocessor}
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
[]{#l00030}[ 30]{.lineno} [// A SourceRouter with N
statically-configured output ports. Items are routed to]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [// output ports based on substring matching
against the servable name. The]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// router is configured with N-1 substrings,
with \"fall-through\" semantics. In]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// particular: The substrings are numbered 0,
1, \..., N-2. Items whose servable]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// name matches substring 0 are sent to port
0; items that fail to match]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [// substring 0 but do match substring 1 are
sent to port 1; and so on. Items]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [// that match none of the substrings are sent
to port N-1.]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00038}[
[38](classtensorflow_1_1serving_1_1StaticSourceRouter.html){.line}]{.lineno} [class
]{.keyword}[StaticSourceRouter](classtensorflow_1_1serving_1_1StaticSourceRouter.html){.code}
final : [public]{.keyword}
[SourceRouter](classtensorflow_1_1serving_1_1SourceRouter.html){.code}\<T\>
{
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [// Creates a StaticSourceRouter with
\'route\_substrings.size() + 1\' output]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [// ports, based on cascading substring
matching as described above.]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [static]{.keyword} Status
Create([const]{.keyword} std::vector\<string\>& route\_substrings,
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} 
std::unique\_ptr\<[StaticSourceRouter\<T\>](classtensorflow_1_1serving_1_1StaticSourceRouter.html){.code}\>\*
result);
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
\~[StaticSourceRouter](classtensorflow_1_1serving_1_1StaticSourceRouter.html){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [protected]{.keyword}:
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [int]{.keywordtype} num\_output\_ports()[
const override ]{.keyword}{
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [return]{.keywordflow}
routes\_except\_default\_.size() + 1;
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  }
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} 
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [int]{.keywordtype} Route([const]{.keyword}
StringPiece servable\_name,
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [const]{.keyword}
std::vector\<[ServableData\<T\>](classtensorflow_1_1serving_1_1ServableData.html){.code}\>&
versions) [override]{.keyword};
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} 
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [explicit]{.keyword}
[StaticSourceRouter](classtensorflow_1_1serving_1_1StaticSourceRouter.html){.code}([const]{.keyword}
std::vector\<string\>& route\_substrings);
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} 
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [// The substrings of the first N-1 routes
(the Nth route is the default]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [// route).]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  std::vector\<string\>
routes\_except\_default\_;
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([StaticSourceRouter](classtensorflow_1_1serving_1_1StaticSourceRouter.html){.code});
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} };
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} 
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} [// Implementation details follow. API users
need not read.]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} 
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} Status
[StaticSourceRouter\<T\>::Create](classtensorflow_1_1serving_1_1StaticSourceRouter.html){.code}(
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [const]{.keyword} std::vector\<string\>&
route\_substrings,
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} 
std::unique\_ptr\<[StaticSourceRouter\<T\>](classtensorflow_1_1serving_1_1StaticSourceRouter.html){.code}\>\*
result) {
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  result-\>reset([new]{.keyword}
[StaticSourceRouter\<T\>](classtensorflow_1_1serving_1_1StaticSourceRouter.html){.code}(route\_substrings));
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} }
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} 
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00076}[
76]{.lineno} StaticSourceRouter\<T\>::\~StaticSourceRouter() {
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  TargetBase\<T\>::Detach();
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} }
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} 
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} [int]{.keywordtype}
StaticSourceRouter\<T\>::Route([const]{.keyword} StringPiece
servable\_name,
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  [const]{.keyword}
std::vector\<ServableData\<T\>\>& versions) {
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  [for]{.keywordflow} ([int]{.keywordtype} i =
0; i \< routes\_except\_default\_.size(); ++i) {
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [if]{.keywordflow}
(str\_util::StrContains(servable\_name, routes\_except\_default\_\[i\]))
{
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  VLOG(2) \<\< [\"Routing servable(s) from
stream \"]{.stringliteral} \<\< servable\_name
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  \<\< [\" to route \"]{.stringliteral} \<\< i;
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  [return]{.keywordflow} i;
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  }
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  }
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  [// None of the substrings matched, so return
the \"default\" Nth route.]{.comment}
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  VLOG(2) \<\< [\"Routing servable(s) from
stream \"]{.stringliteral} \<\< servable\_name
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  \<\< [\" to default route \"]{.stringliteral}
\<\< routes\_except\_default\_.size();
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  [return]{.keywordflow}
routes\_except\_default\_.size();
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} }
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} 
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} StaticSourceRouter\<T\>::StaticSourceRouter(
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  [const]{.keyword} std::vector\<string\>&
route\_substrings)
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  :
routes\_except\_default\_(route\_substrings) {}
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} 
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00102}[ 102]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00103}[ 103]{.lineno} 
:::

::: {.line}
[]{#l00104}[ 104]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_STATIC\_SOURCE\_ROUTER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1ServableData_html .ttc}
::: {.ttname}
[tensorflow::serving::ServableData](classtensorflow_1_1serving_1_1ServableData.html)
:::

::: {.ttdef}
**Definition:** servable\_data.h:32
:::
:::

::: {#aclasstensorflow_1_1serving_1_1SourceRouter_html .ttc}
::: {.ttname}
[tensorflow::serving::SourceRouter](classtensorflow_1_1serving_1_1SourceRouter.html)
:::

::: {.ttdef}
**Definition:** source\_router.h:52
:::
:::

::: {#aclasstensorflow_1_1serving_1_1StaticSourceRouter_html .ttc}
::: {.ttname}
[tensorflow::serving::StaticSourceRouter](classtensorflow_1_1serving_1_1StaticSourceRouter.html)
:::

::: {.ttdef}
**Definition:** static\_source\_router.h:38
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

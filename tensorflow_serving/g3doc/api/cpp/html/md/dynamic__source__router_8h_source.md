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
dynamic\_source\_router.h
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
TENSORFLOW\_SERVING\_CORE\_DYNAMIC\_SOURCE\_ROUTER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_DYNAMIC\_SOURCE\_ROUTER\_H\_]{.preprocessor}
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
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow\_serving/core/source\_router.h\"]{.preprocessor}
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
[]{#l00029}[ 29]{.lineno} [// A SourceRouter with a fixed set of N
output ports, and a dynamically]{.comment}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [// reconfigurable map from servable name to
port. The route map can only]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [// reference the first N-1 ports; the Nth
port is reserved for servables not]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// found in the route map.]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00034}[
[34](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.line}]{.lineno} [class
]{.keyword}[DynamicSourceRouter](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.code}
final : [public]{.keyword}
[SourceRouter](classtensorflow_1_1serving_1_1SourceRouter.html){.code}\<T\>
{
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  [// A servable name -\> output port
map.]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [using]{.keyword} Routes = std::map\<string,
int\>;
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [// Creates a DynamicSourceRouter with
\'num\_output\_ports\' output ports and an]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [// (initial) route map given by
\'routes\'.]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [static]{.keyword} Status
Create([int]{.keywordtype} num\_output\_ports, [const]{.keyword} Routes&
routes,
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
std::unique\_ptr\<[DynamicSourceRouter\<T\>](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.code}\>\*
result);
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} 
\~[DynamicSourceRouter](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [// Gets the current route map.]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  Routes GetRoutes() [const]{.keyword};
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [// Sets the route map to
\'routes\'.]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  Status UpdateRoutes([const]{.keyword} Routes&
routes);
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} 
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [protected]{.keyword}:
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [int]{.keywordtype} num\_output\_ports()[
const override ]{.keyword}{ [return]{.keywordflow} num\_output\_ports\_;
}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} 
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [int]{.keywordtype} Route([const]{.keyword}
StringPiece servable\_name,
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [const]{.keyword}
std::vector\<[ServableData\<T\>](classtensorflow_1_1serving_1_1ServableData.html){.code}\>&
versions) [override]{.keyword};
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} 
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} 
[DynamicSourceRouter](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.code}([int]{.keywordtype}
num\_output\_ports, [const]{.keyword} Routes& routes);
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} 
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [// Returns an error if \'routes\' is
invalid, given \'num\_output\_ports\'.]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [static]{.keyword} Status
ValidateRoutes([int]{.keywordtype} num\_output\_ports, [const]{.keyword}
Routes& routes);
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} 
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [const]{.keyword} [int]{.keywordtype}
num\_output\_ports\_;
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [mutable]{.keyword} mutex routes\_mu\_;
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  Routes routes\_
TF\_GUARDED\_BY(routes\_mu\_);
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([DynamicSourceRouter](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.code});
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} };
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} 
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} [// Implementation details follow. API users
need not read.]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} 
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} Status
[DynamicSourceRouter\<T\>::Create](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.code}(
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [int]{.keywordtype} num\_output\_ports,
[const]{.keyword} Routes& routes,
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} 
std::unique\_ptr\<[DynamicSourceRouter\<T\>](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.code}\>\*
result) {
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} 
TF\_RETURN\_IF\_ERROR(ValidateRoutes(num\_output\_ports, routes));
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  result-\>reset([new]{.keyword}
[DynamicSourceRouter\<T\>](classtensorflow_1_1serving_1_1DynamicSourceRouter.html){.code}(num\_output\_ports,
routes));
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} }
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} 
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00084}[
84]{.lineno} DynamicSourceRouter\<T\>::\~DynamicSourceRouter() {
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  TargetBase\<T\>::Detach();
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} }
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} 
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} [typename]{.keyword}
DynamicSourceRouter\<T\>::Routes
DynamicSourceRouter\<T\>::GetRoutes()[]{.keyword}
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} [ const ]{.keyword}{
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  mutex\_lock l(routes\_mu\_);
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [return]{.keywordflow} routes\_;
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
[]{#l00096}[ 96]{.lineno} Status
DynamicSourceRouter\<T\>::UpdateRoutes([const]{.keyword} Routes& routes)
{
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} 
TF\_RETURN\_IF\_ERROR(ValidateRoutes(num\_output\_ports\_, routes));
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  {
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  mutex\_lock l(routes\_mu\_);
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  routes\_ = routes;
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  }
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00103}[ 103]{.lineno} }
:::

::: {.line}
[]{#l00104}[ 104]{.lineno} 
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} [int]{.keywordtype}
DynamicSourceRouter\<T\>::Route(
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [const]{.keyword} StringPiece
servable\_name,
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  [const]{.keyword}
std::vector\<ServableData\<T\>\>& versions) {
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  mutex\_lock l(routes\_mu\_);
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  [auto]{.keyword} it =
routes\_.find([string]{.keywordtype}(servable\_name));
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  [if]{.keywordflow} (it == routes\_.end()) {
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  LOG(INFO) \<\< [\"Routing servable(s) from
stream \"]{.stringliteral} \<\< servable\_name
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  \<\< [\" to default output port
\"]{.stringliteral} \<\< num\_output\_ports\_ - 1;
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [return]{.keywordflow} num\_output\_ports\_
- 1;
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  } [else]{.keywordflow} {
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  [return]{.keywordflow} it-\>second;
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  }
:::

::: {.line}
[]{#l00118}[ 118]{.lineno} }
:::

::: {.line}
[]{#l00119}[ 119]{.lineno} 
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00121}[
121]{.lineno} DynamicSourceRouter\<T\>::DynamicSourceRouter([int]{.keywordtype}
num\_output\_ports,
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  [const]{.keyword} Routes& routes)
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  : num\_output\_ports\_(num\_output\_ports),
routes\_(routes) {}
:::

::: {.line}
[]{#l00124}[ 124]{.lineno} 
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} Status
DynamicSourceRouter\<T\>::ValidateRoutes([int]{.keywordtype}
num\_output\_ports,
:::

::: {.line}
[]{#l00127}[ 127]{.lineno}  [const]{.keyword} Routes& routes) {
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  [for]{.keywordflow} ([const]{.keyword}
[auto]{.keyword}& entry : routes) {
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  [const]{.keyword} [int]{.keywordtype} port =
entry.second;
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  [if]{.keywordflow} (port \< 0 \|\| port \>=
num\_output\_ports) {
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  [return]{.keywordflow}
errors::InvalidArgument(
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  strings::StrCat([\"Port number out of range:
\"]{.stringliteral}, port));
:::

::: {.line}
[]{#l00133}[ 133]{.lineno}  }
:::

::: {.line}
[]{#l00134}[ 134]{.lineno}  [if]{.keywordflow} (port ==
num\_output\_ports - 1) {
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  [return]{.keywordflow}
errors::InvalidArgument(
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  [\"Last port cannot be used in route map,
since it\'s reserved for the \"]{.stringliteral}
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  [\"default route\"]{.stringliteral});
:::

::: {.line}
[]{#l00138}[ 138]{.lineno}  }
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  }
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00141}[ 141]{.lineno} }
:::

::: {.line}
[]{#l00142}[ 142]{.lineno} 
:::

::: {.line}
[]{#l00143}[ 143]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00144}[ 144]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00145}[ 145]{.lineno} 
:::

::: {.line}
[]{#l00146}[ 146]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_DYNAMIC\_SOURCE\_ROUTER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1DynamicSourceRouter_html .ttc}
::: {.ttname}
[tensorflow::serving::DynamicSourceRouter](classtensorflow_1_1serving_1_1DynamicSourceRouter.html)
:::

::: {.ttdef}
**Definition:** dynamic\_source\_router.h:34
:::
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
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

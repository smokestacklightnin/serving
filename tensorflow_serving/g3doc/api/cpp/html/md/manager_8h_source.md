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
manager.h
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
TENSORFLOW\_SERVING\_CORE\_MANAGER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_MANAGER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<algorithm\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<map\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} 
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"absl/types/optional.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/lib/core/errors.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow/core/lib/strings/strcat.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow/core/platform/types.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_handle.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_id.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} 
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} 
:::

::: {.line}
[]{#l00039}[
[39](structtensorflow_1_1serving_1_1ServableRequest.html){.line}]{.lineno} [struct
]{.keyword}[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.code}
{
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [// Initialization factories, for convenience
and readability.]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [static]{.keyword}
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.code}
Specific([const]{.keyword} [string]{.keywordtype}& name,
[const]{.keyword} int64\_t version);
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [static]{.keyword}
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.code}
Earliest([const]{.keyword} [string]{.keywordtype}& name);
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [static]{.keyword}
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.code}
Latest([const]{.keyword} [string]{.keywordtype}& name);
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [static]{.keyword}
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.code}
FromId([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
[id]{.keywordtype});
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [// The name of a servable stream.]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [string]{.keywordtype} name;
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} 
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [// An optional specific version number to
use.]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  absl::optional\<int64\_t\> version;
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [// How to choose a version number
automatically, if \'version\' is left unset.]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [enum class]{.keyword} AutoVersionPolicy {
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [// Choose the loaded version with the
smallest version number.]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  kEarliest,
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} 
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [// Choose the loaded version with the
largest version number.]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  kLatest,
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  };
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  AutoVersionPolicy auto\_version\_policy =
AutoVersionPolicy::kLatest;
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} 
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [// Emits a string representation; for
logging and debugging use only.]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [string]{.keywordtype} DebugString()
[const]{.keyword};
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [// Legacy constructors. Do not use in new
code.]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} 
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.code}([const]{.keyword}
[string]{.keywordtype}& name\_in,
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [const]{.keyword} absl::optional\<int64\_t\>&
version\_in)
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  : name(name\_in),
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  version(version\_in),
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} 
auto\_version\_policy(AutoVersionPolicy::kLatest) {}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} };
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} 
:::

::: {.line}
[]{#l00077}[
[77](classtensorflow_1_1serving_1_1Manager.html){.line}]{.lineno} [class
]{.keyword}[Manager](classtensorflow_1_1serving_1_1Manager.html){.code}
{
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  [virtual]{.keyword}
\~[Manager](classtensorflow_1_1serving_1_1Manager.html){.code}() =
[default]{.keywordflow};
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} 
:::

::: {.line}
[]{#l00083}[
[83](classtensorflow_1_1serving_1_1Manager.html#a10694eb8c3e845e4738788092057b7ef){.line}]{.lineno} 
[virtual]{.keyword} std::vector\<ServableId\>
[ListAvailableServableIds](classtensorflow_1_1serving_1_1Manager.html#a10694eb8c3e845e4738788092057b7ef){.code}()
[const]{.keyword} = 0;
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} 
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  std::map\<ServableId, ServableHandle\<T\>\>
[GetAvailableServableHandles](classtensorflow_1_1serving_1_1Manager.html#a8ad1c3155120737e5a41776ceeff6aaa){.code}()
[const]{.keyword};
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} 
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  Status
[GetServableHandle](classtensorflow_1_1serving_1_1Manager.html#aca70babd38f4b416cf27bbf40f8bb093){.code}([const]{.keyword}
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.code}&
request,
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} 
[ServableHandle\<T\>](classtensorflow_1_1serving_1_1ServableHandle.html){.code}\*
[const]{.keyword} handle);
:::

::: {.line}
[]{#l00102}[ 102]{.lineno} 
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  [friend]{.keyword} [class
]{.keyword}[ManagerWrapper](classtensorflow_1_1serving_1_1ManagerWrapper.html){.code};
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} 
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  [// Returns an UntypedServableHandle given a
ServableRequest.]{.comment}
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [// Returns error if no such Servable is
available \-- e.g. not yet loaded, has]{.comment}
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  [// been quiesced/unloaded, etc.]{.comment}
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  [virtual]{.keyword} Status
GetUntypedServableHandle(
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  [const]{.keyword}
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.code}&
request,
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  std::unique\_ptr\<UntypedServableHandle\>\*
untyped\_handle) = 0;
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} 
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  [// Returns a map of all the available
servable ids to their corresponding]{.comment}
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [// UntypedServableHandles.]{.comment}
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  [virtual]{.keyword} std::map\<ServableId,
std::unique\_ptr\<UntypedServableHandle\>\>
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  GetAvailableUntypedServableHandles()
[const]{.keyword} = 0;
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} };
:::

::: {.line}
[]{#l00118}[ 118]{.lineno} 
:::

::: {.line}
[]{#l00119}[ 119]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} [// Implementation details follow. API users
need not read.]{.comment}
:::

::: {.line}
[]{#l00121}[ 121]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} 
:::

::: {.line}
[]{#l00123}[ 123]{.lineno} [inline]{.keyword}
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.code}
ServableRequest::Specific([const]{.keyword} [string]{.keywordtype}&
name,
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  [const]{.keyword} int64\_t version) {
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} 
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.code}
request;
:::

::: {.line}
[]{#l00126}[ 126]{.lineno}  request.name = name;
:::

::: {.line}
[]{#l00127}[ 127]{.lineno}  request.version = version;
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  [return]{.keywordflow} request;
:::

::: {.line}
[]{#l00129}[ 129]{.lineno} }
:::

::: {.line}
[]{#l00130}[ 130]{.lineno} 
:::

::: {.line}
[]{#l00131}[ 131]{.lineno} [inline]{.keyword} ServableRequest
ServableRequest::Earliest([const]{.keyword} [string]{.keywordtype}&
name) {
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  ServableRequest request;
:::

::: {.line}
[]{#l00133}[ 133]{.lineno}  request.name = name;
:::

::: {.line}
[]{#l00134}[ 134]{.lineno}  request.auto\_version\_policy =
AutoVersionPolicy::kEarliest;
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  [return]{.keywordflow} request;
:::

::: {.line}
[]{#l00136}[ 136]{.lineno} }
:::

::: {.line}
[]{#l00137}[ 137]{.lineno} 
:::

::: {.line}
[]{#l00138}[ 138]{.lineno} [inline]{.keyword} ServableRequest
ServableRequest::Latest([const]{.keyword} [string]{.keywordtype}& name)
{
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  ServableRequest request;
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  request.name = name;
:::

::: {.line}
[]{#l00141}[ 141]{.lineno}  request.auto\_version\_policy =
AutoVersionPolicy::kLatest;
:::

::: {.line}
[]{#l00142}[ 142]{.lineno}  [return]{.keywordflow} request;
:::

::: {.line}
[]{#l00143}[ 143]{.lineno} }
:::

::: {.line}
[]{#l00144}[ 144]{.lineno} 
:::

::: {.line}
[]{#l00145}[ 145]{.lineno} [inline]{.keyword} ServableRequest
ServableRequest::FromId([const]{.keyword} ServableId&
[id]{.keywordtype}) {
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  DCHECK\_GE([id]{.keywordtype}.version, 0);
:::

::: {.line}
[]{#l00147}[ 147]{.lineno}  [return]{.keywordflow}
Specific([id]{.keywordtype}.name, [id]{.keywordtype}.version);
:::

::: {.line}
[]{#l00148}[ 148]{.lineno} }
:::

::: {.line}
[]{#l00149}[ 149]{.lineno} 
:::

::: {.line}
[]{#l00150}[ 150]{.lineno} [inline]{.keyword} [string]{.keywordtype}
ServableRequest::DebugString()[ const ]{.keyword}{
:::

::: {.line}
[]{#l00151}[ 151]{.lineno}  [if]{.keywordflow} (version) {
:::

::: {.line}
[]{#l00152}[ 152]{.lineno}  [return]{.keywordflow}
strings::StrCat([\"Specific(\"]{.stringliteral}, name, [\",
\"]{.stringliteral}, version.value(), [\")\"]{.stringliteral});
:::

::: {.line}
[]{#l00153}[ 153]{.lineno}  } [else]{.keywordflow} {
:::

::: {.line}
[]{#l00154}[ 154]{.lineno}  [switch]{.keywordflow}
(auto\_version\_policy) {
:::

::: {.line}
[]{#l00155}[ 155]{.lineno}  [case]{.keywordflow}
AutoVersionPolicy::kEarliest:
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  [return]{.keywordflow}
strings::StrCat([\"Earliest(\"]{.stringliteral}, name,
[\")\"]{.stringliteral});
:::

::: {.line}
[]{#l00157}[ 157]{.lineno}  [case]{.keywordflow}
AutoVersionPolicy::kLatest:
:::

::: {.line}
[]{#l00158}[ 158]{.lineno}  [return]{.keywordflow}
strings::StrCat([\"Latest(\"]{.stringliteral}, name,
[\")\"]{.stringliteral});
:::

::: {.line}
[]{#l00159}[ 159]{.lineno}  }
:::

::: {.line}
[]{#l00160}[ 160]{.lineno}  }
:::

::: {.line}
[]{#l00161}[ 161]{.lineno} }
:::

::: {.line}
[]{#l00162}[ 162]{.lineno} 
:::

::: {.line}
[]{#l00163}[ 163]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00164}[
[164](classtensorflow_1_1serving_1_1Manager.html#aca70babd38f4b416cf27bbf40f8bb093){.line}]{.lineno} Status
[Manager::GetServableHandle](classtensorflow_1_1serving_1_1Manager.html#aca70babd38f4b416cf27bbf40f8bb093){.code}([const]{.keyword}
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.code}&
request,
:::

::: {.line}
[]{#l00165}[ 165]{.lineno} 
[ServableHandle\<T\>](classtensorflow_1_1serving_1_1ServableHandle.html){.code}\*
[const]{.keyword} handle) {
:::

::: {.line}
[]{#l00166}[ 166]{.lineno}  std::unique\_ptr\<UntypedServableHandle\>
untyped\_handle;
:::

::: {.line}
[]{#l00167}[ 167]{.lineno} 
TF\_RETURN\_IF\_ERROR(GetUntypedServableHandle(request,
&untyped\_handle));
:::

::: {.line}
[]{#l00168}[ 168]{.lineno}  [if]{.keywordflow} (untyped\_handle ==
[nullptr]{.keyword}) {
:::

::: {.line}
[]{#l00169}[ 169]{.lineno}  [return]{.keywordflow}
errors::Internal([\"Manager returned a null handle with OK
status.\"]{.stringliteral});
:::

::: {.line}
[]{#l00170}[ 170]{.lineno}  }
:::

::: {.line}
[]{#l00171}[ 171]{.lineno}  \*handle =
[ServableHandle\<T\>](classtensorflow_1_1serving_1_1ServableHandle.html){.code}(std::move(untyped\_handle));
:::

::: {.line}
[]{#l00172}[ 172]{.lineno}  [if]{.keywordflow} (handle-\>get() ==
[nullptr]{.keyword}) {
:::

::: {.line}
[]{#l00173}[ 173]{.lineno}  [return]{.keywordflow}
errors::InvalidArgument(
:::

::: {.line}
[]{#l00174}[ 174]{.lineno}  [\"Servable type doesn\'t match the asked
for type.\"]{.stringliteral});
:::

::: {.line}
[]{#l00175}[ 175]{.lineno}  }
:::

::: {.line}
[]{#l00176}[ 176]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00177}[ 177]{.lineno} }
:::

::: {.line}
[]{#l00178}[ 178]{.lineno} 
:::

::: {.line}
[]{#l00179}[ 179]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00180}[
[180](classtensorflow_1_1serving_1_1Manager.html#a8ad1c3155120737e5a41776ceeff6aaa){.line}]{.lineno} std::map\<ServableId,
ServableHandle\<T\>\>
[Manager::GetAvailableServableHandles](classtensorflow_1_1serving_1_1Manager.html#a8ad1c3155120737e5a41776ceeff6aaa){.code}()[]{.keyword}
:::

::: {.line}
[]{#l00181}[ 181]{.lineno} [ const ]{.keyword}{
:::

::: {.line}
[]{#l00182}[ 182]{.lineno}  std::map\<ServableId, ServableHandle\<T\>\>
id\_and\_handles;
:::

::: {.line}
[]{#l00183}[ 183]{.lineno}  std::map\<ServableId,
std::unique\_ptr\<UntypedServableHandle\>\>
:::

::: {.line}
[]{#l00184}[ 184]{.lineno}  id\_and\_untyped\_handles =
GetAvailableUntypedServableHandles();
:::

::: {.line}
[]{#l00185}[ 185]{.lineno}  [for]{.keywordflow} ([auto]{.keyword}&
id\_and\_untyped\_handle : id\_and\_untyped\_handles) {
:::

::: {.line}
[]{#l00186}[ 186]{.lineno}  [auto]{.keyword} handle =
[ServableHandle\<T\>](classtensorflow_1_1serving_1_1ServableHandle.html){.code}(std::move(id\_and\_untyped\_handle.second));
:::

::: {.line}
[]{#l00187}[ 187]{.lineno}  [if]{.keywordflow} (handle.get() !=
[nullptr]{.keyword}) {
:::

::: {.line}
[]{#l00188}[ 188]{.lineno} 
id\_and\_handles.emplace(id\_and\_untyped\_handle.first,
std::move(handle));
:::

::: {.line}
[]{#l00189}[ 189]{.lineno}  }
:::

::: {.line}
[]{#l00190}[ 190]{.lineno}  }
:::

::: {.line}
[]{#l00191}[ 191]{.lineno}  [return]{.keywordflow} id\_and\_handles;
:::

::: {.line}
[]{#l00192}[ 192]{.lineno} }
:::

::: {.line}
[]{#l00193}[ 193]{.lineno} 
:::

::: {.line}
[]{#l00194}[ 194]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00195}[ 195]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00196}[ 196]{.lineno} 
:::

::: {.line}
[]{#l00197}[ 197]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_MANAGER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1ManagerWrapper_html .ttc}
::: {.ttname}
[tensorflow::serving::ManagerWrapper](classtensorflow_1_1serving_1_1ManagerWrapper.html)
:::

::: {.ttdef}
**Definition:** manager\_wrapper.h:34
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Manager_html .ttc}
::: {.ttname}
[tensorflow::serving::Manager](classtensorflow_1_1serving_1_1Manager.html)
:::

::: {.ttdef}
**Definition:** manager.h:77
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Manager_html_a10694eb8c3e845e4738788092057b7ef .ttc}
::: {.ttname}
[tensorflow::serving::Manager::ListAvailableServableIds](classtensorflow_1_1serving_1_1Manager.html#a10694eb8c3e845e4738788092057b7ef)
:::

::: {.ttdeci}
virtual std::vector\< ServableId \> ListAvailableServableIds() const =0
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Manager_html_a8ad1c3155120737e5a41776ceeff6aaa .ttc}
::: {.ttname}
[tensorflow::serving::Manager::GetAvailableServableHandles](classtensorflow_1_1serving_1_1Manager.html#a8ad1c3155120737e5a41776ceeff6aaa)
:::

::: {.ttdeci}
std::map\< ServableId, ServableHandle\< T \> \>
GetAvailableServableHandles() const
:::

::: {.ttdef}
**Definition:** manager.h:180
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Manager_html_aca70babd38f4b416cf27bbf40f8bb093 .ttc}
::: {.ttname}
[tensorflow::serving::Manager::GetServableHandle](classtensorflow_1_1serving_1_1Manager.html#aca70babd38f4b416cf27bbf40f8bb093)
:::

::: {.ttdeci}
Status GetServableHandle(const ServableRequest &request,
ServableHandle\< T \> \*const handle)
:::

::: {.ttdef}
**Definition:** manager.h:164
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServableHandle_html .ttc}
::: {.ttname}
[tensorflow::serving::ServableHandle](classtensorflow_1_1serving_1_1ServableHandle.html)
:::

::: {.ttdef}
**Definition:** servable\_handle.h:75
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

::: {#astructtensorflow_1_1serving_1_1ServableRequest_html .ttc}
::: {.ttname}
[tensorflow::serving::ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html)
:::

::: {.ttdef}
**Definition:** manager.h:39
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

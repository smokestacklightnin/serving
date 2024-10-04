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
servable\_state.h
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
TENSORFLOW\_SERVING\_CORE\_SERVABLE\_STATE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_SERVABLE\_STATE\_H\_]{.preprocessor}
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
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_id.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} 
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} 
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [// The state of a servable. Typically
published on an EventBus by a manager.]{.comment}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [// Since managers (and EventBus
implementations) can in general have multiple]{.comment}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [// threads, this is really a snapshot of a
servable\'s recent state, not a]{.comment}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [// guarantee about its current
state.]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// Note that this is a semantic state, meant
to be independent of the]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// implementation of a particular kind of
manager.]{.comment}
:::

::: {.line}
[]{#l00034}[
[34](structtensorflow_1_1serving_1_1ServableState.html){.line}]{.lineno} [struct
]{.keyword}[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.code}
{
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  [// The identifier of the servable whose
state is represented.]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code} id;
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} 
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  [// The state of the servable as maintained
by a manager. These states can only]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [// transition from higher to lower ones on
this list.]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [enum class]{.keyword} ManagerState : int {
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [// The manager is tracking this servable,
but has not initiated any action]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [// pertaining to it.]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  kStart,
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [// The manager has decided to load this
servable. In particular, checks]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [// around resource availability and other
aspects have passed, and the]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [// manager is about to invoke the loader\'s
Load() method.]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  kLoading,
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [// The manager has successfully loaded this
servable and made it available]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [// for serving (i.e. GetServableHandle(id)
will succeed). To avoid races,]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [// this state is not reported until
\*after\* the servable is made available.]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  kAvailable,
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} 
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [// The manager has decided to make this
servable unavailable, and unload it.]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [// To avoid races, this state is reported
\*before\* the servable is made]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [// unavailable.]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  kUnloading,
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} 
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [// This servable has reached the end of its
journey in the manager. Either]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [// it loaded and ultimately unloaded
successfully, or it hit an error at]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [// some point in its lifecycle.]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  kEnd,
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  };
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} 
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [static]{.keyword} [string]{.keywordtype}
ManagerStateString(ManagerState state) {
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [switch]{.keywordflow} (state) {
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [case]{.keywordflow} ManagerState::kStart:
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [return]{.keywordflow}
[\"Start\"]{.stringliteral};
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [case]{.keywordflow} ManagerState::kLoading:
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  [return]{.keywordflow}
[\"Loading\"]{.stringliteral};
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [case]{.keywordflow}
ManagerState::kAvailable:
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [return]{.keywordflow}
[\"Available\"]{.stringliteral};
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  [case]{.keywordflow}
ManagerState::kUnloading:
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [return]{.keywordflow}
[\"Unloading\"]{.stringliteral};
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [case]{.keywordflow} ManagerState::kEnd:
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [return]{.keywordflow}
[\"End\"]{.stringliteral};
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  }
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  }
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} 
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  ManagerState manager\_state;
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} 
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  [// Whether anything has gone wrong with this
servable. If not OK, the error]{.comment}
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [// could be something that occurred in a
Source or SourceAdapter, in the]{.comment}
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  [// servable\'s Loader, in the Manager, or
elsewhere. All errors pertaining to]{.comment}
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  [// the servable are reported here,
regardless of origin.]{.comment}
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  Status health;
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} 
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [// Returns a string representation of this
object. Useful in logging.]{.comment}
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  [string]{.keywordtype} DebugString()[ const
]{.keyword}{
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  [return]{.keywordflow} strings::StrCat([\"id:
\"]{.stringliteral}, [id]{.keywordtype}.DebugString(), [\"
manager\_state: \"]{.stringliteral},
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  ManagerStateString(manager\_state),
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  [\" health: \"]{.stringliteral},
health.ToString());
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  }
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} };
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} 
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} [inline]{.keyword} [bool]{.keywordtype}
operator==([const]{.keyword}
[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.code}&
a, [const]{.keyword}
[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.code}&
b) {
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  [return]{.keywordflow} a.id == b.id &&
a.manager\_state == b.manager\_state &&
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  a.health == b.health;
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} }
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} 
:::

::: {.line}
[]{#l00102}[ 102]{.lineno} [inline]{.keyword} [bool]{.keywordtype}
operator!=([const]{.keyword} ServableState& a, [const]{.keyword}
ServableState& b) {
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  [return]{.keywordflow} !(a == b);
:::

::: {.line}
[]{#l00104}[ 104]{.lineno} }
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} 
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} [inline]{.keyword} std::ostream&
operator\<\<(std::ostream& os, [const]{.keyword} ServableState& state) {
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [return]{.keywordflow} os \<\<
state.DebugString();
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} }
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} 
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00111}[ 111]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} 
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_SERVABLE\_STATE\_H\_]{.comment}
:::

::: {#astructtensorflow_1_1serving_1_1ServableId_html .ttc}
::: {.ttname}
[tensorflow::serving::ServableId](structtensorflow_1_1serving_1_1ServableId.html)
:::

::: {.ttdef}
**Definition:** servable\_id.h:33
:::
:::

::: {#astructtensorflow_1_1serving_1_1ServableState_html .ttc}
::: {.ttname}
[tensorflow::serving::ServableState](structtensorflow_1_1serving_1_1ServableState.html)
:::

::: {.ttdef}
**Definition:** servable\_state.h:34
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

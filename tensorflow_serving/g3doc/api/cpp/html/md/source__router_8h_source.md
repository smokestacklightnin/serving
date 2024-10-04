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
source\_router.h
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
TENSORFLOW\_SERVING\_CORE\_SOURCE\_ROUTER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_SOURCE\_ROUTER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<algorithm\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} 
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow/core/lib/core/notification.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow\_serving/core/source.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/core/source\_adapter.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/core/target.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} 
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} 
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [// A module that splits aspired-version calls
from one input to multiple outputs]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// based on some criterion, e.g. the servable
name. There is a single input]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// \"port\" represented by
Target\<T\>::SetAspiredVersions(), and N output \"ports\",]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// each of type Source\<T\>, numbered 0, 1,
2, \...]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [// For a typical use-case, consider a server
hosting multiple kinds of servables]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [// (say, apple servables and orange
servables). Perhaps both kinds of servables]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [// arrive via file-system paths, a
la:]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [// /path/to/some/apple/servable]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [// /path/to/some/orange/servable]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [// where the servable kinds are distinguished
based on the presence of \"apple\"]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [// or \"orange\" in the path. A SourceRouter
can be interposed between a file-]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [// system monitoring Source\<StoragePath\>,
and a pair of SourceAdapters (one that]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [// emits loaders of apple servables, and one
that emits loaders of orange]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [// servables), to route each path to the
appropriate SourceAdapter.]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [// IMPORTANT: Every leaf derived class must
call Detach() at the top of its]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [// destructor. (See documentation on
TargetBase::Detach() in target.h.) Doing so]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [// ensures that no virtual method calls are
in flight during destruction of]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [// member variables.]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00052}[
[52](classtensorflow_1_1serving_1_1SourceRouter.html){.line}]{.lineno} [class
]{.keyword}[SourceRouter](classtensorflow_1_1serving_1_1SourceRouter.html){.code}
: [public]{.keyword}
[TargetBase](classtensorflow_1_1serving_1_1TargetBase.html){.code}\<T\>
{
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [static]{.keyword} constexpr
[int]{.keywordtype} kNoRoute = -1;
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} 
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} 
\~[SourceRouter](classtensorflow_1_1serving_1_1SourceRouter.html){.code}()
[override]{.keyword} = 0;
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} 
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [// Returns a vector of N source pointers,
corresponding to the N output ports]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [// of the router. The caller must invoke
ConnectSourceToTarget() (or directly]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [// call SetAspiredVersionsCallback()) on
each of them to arrange to route]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [// items to various upstream targets. That
must be done exactly once, and]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [// before calling SetAspiredVersions() on
the router.]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  std::vector\<Source\<T\>\*\>
GetOutputPorts();
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [// Implemented in terms of Route(), defined
below and written by the subclass.]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [void]{.keywordtype}
SetAspiredVersions([const]{.keyword} StringPiece servable\_name,
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
std::vector\<[ServableData\<T\>](classtensorflow_1_1serving_1_1ServableData.html){.code}\>
versions) [final]{.keyword};
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} 
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [protected]{.keyword}:
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [// This is an abstract class.]{.comment}
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} 
[SourceRouter](classtensorflow_1_1serving_1_1SourceRouter.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} 
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [// Returns the number of output ports. Must
be \> 0 and fixed for the lifetime]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  [// of the router. To be written by the
implementing subclass.]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [virtual]{.keyword} [int]{.keywordtype}
num\_output\_ports() [const]{.keyword} = 0;
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} 
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [// Returns \`kNoRoute\` or a valid output
port \# in \[0, num\_output\_ports() - 1\].]{.comment}
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [// Aspired-versions requests will be routed
to the output port corresponding]{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  [// to the returned port number. If
\`kNoRoute\` is returned, the aspired-version]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [// request will be discarded silently. To be
written by the implementing]{.comment}
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  [// subclass.]{.comment}
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  [virtual]{.keyword} [int]{.keywordtype}
Route([const]{.keyword} StringPiece servable\_name,
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  [const]{.keyword}
std::vector\<[ServableData\<T\>](classtensorflow_1_1serving_1_1ServableData.html){.code}\>&
versions) = 0;
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} 
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  [// The num\_output\_ports() output ports.
Each one is an IdentitySourceAdapter.]{.comment}
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  [// Populated in GetOutputPorts().]{.comment}
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} 
std::vector\<std::unique\_ptr\<SourceAdapter\<T, T\>\>\>
output\_ports\_;
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} 
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  [// Has \'output\_ports\_\' been populated
yet, so that the SourceAdapter is ready]{.comment}
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  [// to propagate aspired versions?]{.comment}
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  Notification output\_ports\_created\_;
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} };
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} 
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} [// Implementation details follow. API users
need not read.]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} 
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} [namespace ]{.keyword}internal {
:::

::: {.line}
[]{#l00099}[ 99]{.lineno} 
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} [// A SourceAdapter that passes through data
unchanged. Used to implement the]{.comment}
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} [// output ports.]{.comment}
:::

::: {.line}
[]{#l00102}[ 102]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00103}[
[103](classtensorflow_1_1serving_1_1internal_1_1IdentitySourceAdapter.html){.line}]{.lineno} [class
]{.keyword}[IdentitySourceAdapter](classtensorflow_1_1serving_1_1internal_1_1IdentitySourceAdapter.html){.code}
final : [public]{.keyword}
[SourceAdapter](classtensorflow_1_1serving_1_1SourceAdapter.html){.code}\<T,
T\> {
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} 
[IdentitySourceAdapter](classtensorflow_1_1serving_1_1internal_1_1IdentitySourceAdapter.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} 
\~[IdentitySourceAdapter](classtensorflow_1_1serving_1_1internal_1_1IdentitySourceAdapter.html){.code}()[
override ]{.keyword}{
[TargetBase\<T\>::Detach](classtensorflow_1_1serving_1_1TargetBase.html){.code}();
}
:::

::: {.line}
[]{#l00107}[ 107]{.lineno} 
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  std::vector\<ServableData\<T\>\> Adapt(
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  [const]{.keyword} StringPiece
servable\_name,
:::

::: {.line}
[]{#l00111}[ 111]{.lineno} 
std::vector\<[ServableData\<T\>](classtensorflow_1_1serving_1_1ServableData.html){.code}\>
versions) [final]{.keyword};
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} 
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([IdentitySourceAdapter](classtensorflow_1_1serving_1_1internal_1_1IdentitySourceAdapter.html){.code});
:::

::: {.line}
[]{#l00114}[ 114]{.lineno} };
:::

::: {.line}
[]{#l00115}[ 115]{.lineno} 
:::

::: {.line}
[]{#l00116}[ 116]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} std::vector\<ServableData\<T\>\>
[IdentitySourceAdapter\<T\>::Adapt](classtensorflow_1_1serving_1_1internal_1_1IdentitySourceAdapter.html){.code}(
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  [const]{.keyword} StringPiece
servable\_name,
std::vector\<[ServableData\<T\>](classtensorflow_1_1serving_1_1ServableData.html){.code}\>
versions) {
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  [return]{.keywordflow} versions;
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} }
:::

::: {.line}
[]{#l00121}[ 121]{.lineno} 
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} } [// namespace internal]{.comment}
:::

::: {.line}
[]{#l00123}[ 123]{.lineno} 
:::

::: {.line}
[]{#l00124}[ 124]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} SourceRouter\<T\>::\~SourceRouter() {}
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} 
:::

::: {.line}
[]{#l00127}[ 127]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00128}[ 128]{.lineno} std::vector\<Source\<T\>\*\>
SourceRouter\<T\>::GetOutputPorts() {
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  [if]{.keywordflow}
(!output\_ports\_created\_.HasBeenNotified()) {
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  [int]{.keywordtype} num\_ports =
num\_output\_ports();
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  [if]{.keywordflow} (num\_ports \< 1) {
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  LOG(ERROR) \<\< [\"SourceRouter abstraction
used improperly; \"]{.stringliteral}
:::

::: {.line}
[]{#l00133}[ 133]{.lineno}  [\"num\_output\_ports() must return a number
greater than 0\"]{.stringliteral};
:::

::: {.line}
[]{#l00134}[ 134]{.lineno}  DCHECK([false]{.keyword});
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  num\_ports = 1;
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  }
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  [for]{.keywordflow} ([int]{.keywordtype} i =
0; i \< num\_ports; ++i) {
:::

::: {.line}
[]{#l00138}[ 138]{.lineno} 
output\_ports\_.emplace\_back([new]{.keyword}
internal::IdentitySourceAdapter\<T\>);
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  }
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  output\_ports\_created\_.Notify();
:::

::: {.line}
[]{#l00141}[ 141]{.lineno}  }
:::

::: {.line}
[]{#l00142}[ 142]{.lineno} 
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  std::vector\<Source\<T\>\*\> result;
:::

::: {.line}
[]{#l00144}[ 144]{.lineno}  [for]{.keywordflow} ([auto]{.keyword}&
output\_port : output\_ports\_) {
:::

::: {.line}
[]{#l00145}[ 145]{.lineno}  result.push\_back(output\_port.get());
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  }
:::

::: {.line}
[]{#l00147}[ 147]{.lineno}  [return]{.keywordflow} result;
:::

::: {.line}
[]{#l00148}[ 148]{.lineno} }
:::

::: {.line}
[]{#l00149}[ 149]{.lineno} 
:::

::: {.line}
[]{#l00150}[ 150]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00151}[ 151]{.lineno} [void]{.keywordtype}
SourceRouter\<T\>::SetAspiredVersions(
:::

::: {.line}
[]{#l00152}[ 152]{.lineno}  [const]{.keyword} StringPiece
servable\_name, std::vector\<ServableData\<T\>\> versions) {
:::

::: {.line}
[]{#l00153}[ 153]{.lineno} 
output\_ports\_created\_.WaitForNotification();
:::

::: {.line}
[]{#l00154}[ 154]{.lineno}  [int]{.keywordtype} output\_port =
Route(servable\_name, versions);
:::

::: {.line}
[]{#l00155}[ 155]{.lineno}  [if]{.keywordflow} (output\_port ==
kNoRoute) {
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  [return]{.keywordflow};
:::

::: {.line}
[]{#l00157}[ 157]{.lineno}  }
:::

::: {.line}
[]{#l00158}[ 158]{.lineno}  [if]{.keywordflow} (output\_port \< 0 \|\|
output\_port \> output\_ports\_.size() - 1) {
:::

::: {.line}
[]{#l00159}[ 159]{.lineno}  LOG(ERROR)
:::

::: {.line}
[]{#l00160}[ 160]{.lineno}  \<\< [\"SourceRouter abstraction used
improperly; Route() must return \"]{.stringliteral}
:::

::: {.line}
[]{#l00161}[ 161]{.lineno}  [\"kNoRoute or a value in \[0,
num\_output\_ports()-1\]; suppressing the \"]{.stringliteral}
:::

::: {.line}
[]{#l00162}[ 162]{.lineno}  [\"aspired-versions
request\"]{.stringliteral};
:::

::: {.line}
[]{#l00163}[ 163]{.lineno}  DCHECK([false]{.keyword});
:::

::: {.line}
[]{#l00164}[ 164]{.lineno}  [return]{.keywordflow};
:::

::: {.line}
[]{#l00165}[ 165]{.lineno}  }
:::

::: {.line}
[]{#l00166}[ 166]{.lineno} 
output\_ports\_\[output\_port\]-\>SetAspiredVersions(servable\_name,
:::

::: {.line}
[]{#l00167}[ 167]{.lineno}  std::move(versions));
:::

::: {.line}
[]{#l00168}[ 168]{.lineno} }
:::

::: {.line}
[]{#l00169}[ 169]{.lineno} 
:::

::: {.line}
[]{#l00170}[ 170]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00171}[ 171]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00172}[ 172]{.lineno} 
:::

::: {.line}
[]{#l00173}[ 173]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_SOURCE\_ROUTER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1ServableData_html .ttc}
::: {.ttname}
[tensorflow::serving::ServableData](classtensorflow_1_1serving_1_1ServableData.html)
:::

::: {.ttdef}
**Definition:** servable\_data.h:32
:::
:::

::: {#aclasstensorflow_1_1serving_1_1SourceAdapter_html .ttc}
::: {.ttname}
[tensorflow::serving::SourceAdapter](classtensorflow_1_1serving_1_1SourceAdapter.html)
:::

::: {.ttdef}
**Definition:** source\_adapter.h:59
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

::: {#aclasstensorflow_1_1serving_1_1TargetBase_html .ttc}
::: {.ttname}
[tensorflow::serving::TargetBase](classtensorflow_1_1serving_1_1TargetBase.html)
:::

::: {.ttdef}
**Definition:** target.h:61
:::
:::

::: {#aclasstensorflow_1_1serving_1_1internal_1_1IdentitySourceAdapter_html .ttc}
::: {.ttname}
[tensorflow::serving::internal::IdentitySourceAdapter](classtensorflow_1_1serving_1_1internal_1_1IdentitySourceAdapter.html)
:::

::: {.ttdef}
**Definition:** source\_router.h:103
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

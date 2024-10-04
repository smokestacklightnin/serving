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
target.h
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
TENSORFLOW\_SERVING\_CORE\_TARGET\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_TARGET\_H\_]{.preprocessor}
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
\"tensorflow/core/lib/core/stringpiece.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/lib/io/path.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/lib/strings/strcat.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_data.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow\_serving/core/source.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow\_serving/util/observer.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} 
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} 
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// An abstraction for a module that receives
instructions on servables to load,]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [// from a Source. See source.h for
documentation.]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00037}[
[37](classtensorflow_1_1serving_1_1Target.html){.line}]{.lineno} [class
]{.keyword}[Target](classtensorflow_1_1serving_1_1Target.html){.code} {
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [virtual]{.keyword}
\~[Target](classtensorflow_1_1serving_1_1Target.html){.code}() =
[default]{.keywordflow};
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [// Supplies a callback for a Source to use
to supply aspired versions. See]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [// Source\<T\>::AspiredVersionsCallback for
the semantics of aspired versions.]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [// The returned function satisfies these
properties:]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [// - It is thread-safe.]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [// - It is valid forever, even after this
Target object has been destroyed.]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [// After this Target is gone, the function
becomes a no-op.]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [// - It blocks until the target has been
fully set up and is able to handle]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [// the incoming request.]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [virtual]{.keyword} [typename]{.keyword}
[Source\<T\>::AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f){.code}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  GetAspiredVersionsCallback() = 0;
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} };
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} 
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [// A base class for Target implementations.
Takes care of ensuring that the]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} [// emitted aspired-versions callbacks outlive
the Target object. Target]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} [// implementations should extend
TargetBase.]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} [// IMPORTANT: Every leaf derived class must
call Detach() at the top of its]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} [// destructor. (See documentation on Detach()
below.)]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00061}[
[61](classtensorflow_1_1serving_1_1TargetBase.html){.line}]{.lineno} [class
]{.keyword}[TargetBase](classtensorflow_1_1serving_1_1TargetBase.html){.code}
: [public]{.keyword}
[Target](classtensorflow_1_1serving_1_1Target.html){.code}\<T\> {
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} 
\~[TargetBase](classtensorflow_1_1serving_1_1TargetBase.html){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [typename]{.keyword}
[Source\<T\>::AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f){.code}
GetAspiredVersionsCallback()
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [final]{.keyword};
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [protected]{.keyword}:
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [// This is an abstract class.]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} 
[TargetBase](classtensorflow_1_1serving_1_1TargetBase.html){.code}();
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} 
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [// A method supplied by the implementing
subclass to handle incoming aspired-]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [// versions requests from
sources.]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [// IMPORTANT: The SetAspiredVersions()
implementation must be thread-safe, to]{.comment}
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [// handle the case of multiple sources (or
one multi-threaded source).]{.comment}
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [// May block until the target has been fully
set up and is able to handle the]{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  [// incoming request.]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [virtual]{.keyword} [void]{.keywordtype}
SetAspiredVersions([const]{.keyword} StringPiece servable\_name,
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} 
std::vector\<[ServableData\<T\>](classtensorflow_1_1serving_1_1ServableData.html){.code}\>
versions) = 0;
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} 
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  [// Stops receiving SetAspiredVersions()
calls. Every leaf derived class (i.e.]{.comment}
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [// sub-sub-\...-class with no children) must
call Detach() at the top of its]{.comment}
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  [// destructor to avoid races with state
destruction. After Detach() returns,]{.comment}
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  [// it is guaranteed that no
SetAspiredVersions() calls are running (in any]{.comment}
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  [// thread) and no new ones can run. Detach()
must be called exactly once.]{.comment}
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  [void]{.keywordtype} Detach();
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} 
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  [// Used to synchronize all class state. The
shared pointer permits use in an]{.comment}
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [// observer lambda while being impervious to
this class\'s destruction.]{.comment}
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  [mutable]{.keyword} std::shared\_ptr\<mutex\>
mu\_;
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} 
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  [// Notified when Detach() has been called.
The shared pointer permits use in]{.comment}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  [// an observer lambda while being impervious
to this class\'s destruction.]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  std::shared\_ptr\<Notification\> detached\_;
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} 
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  [// An observer object that forwards to
SetAspiredVersions(), if not detached.]{.comment}
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  std::unique\_ptr\<Observer\<const
StringPiece, std::vector\<ServableData\<T\>\>\>\>
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  observer\_;
:::

::: {.line}
[]{#l00102}[ 102]{.lineno} };
:::

::: {.line}
[]{#l00103}[ 103]{.lineno} 
:::

::: {.line}
[]{#l00104}[ 104]{.lineno} [// Connects a source to a target, s.t. the
target will receive the source\'s]{.comment}
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} [// aspired-versions requests.]{.comment}
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00107}[ 107]{.lineno} [void]{.keywordtype}
ConnectSourceToTarget([Source\<T\>](classtensorflow_1_1serving_1_1Source.html){.code}\*
source,
[Target\<T\>](classtensorflow_1_1serving_1_1Target.html){.code}\*
target);
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} 
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} [// Implementation details follow. API users
need not read.]{.comment}
:::

::: {.line}
[]{#l00111}[ 111]{.lineno} 
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00113}[
113]{.lineno} [TargetBase\<T\>::TargetBase](classtensorflow_1_1serving_1_1TargetBase.html){.code}()
: mu\_(new mutex), detached\_(new Notification) {
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  std::shared\_ptr\<mutex\> mu = mu\_;
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  std::shared\_ptr\<Notification\> detached =
detached\_;
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  observer\_.reset([new]{.keyword}
[Observer](classtensorflow_1_1serving_1_1Observer.html){.code}\<[const]{.keyword}
StringPiece,
std::vector\<[ServableData\<T\>](classtensorflow_1_1serving_1_1ServableData.html){.code}\>\>(
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  \[mu, detached,
[this]{.keyword}\]([const]{.keyword} StringPiece servable\_name,
:::

::: {.line}
[]{#l00118}[ 118]{.lineno} 
std::vector\<[ServableData\<T\>](classtensorflow_1_1serving_1_1ServableData.html){.code}\>
versions) {
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  mutex\_lock l(\*mu);
:::

::: {.line}
[]{#l00120}[ 120]{.lineno}  [if]{.keywordflow}
(detached-\>HasBeenNotified()) {
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  [// We\'re detached. Perform a
no-op.]{.comment}
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  [return]{.keywordflow};
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  }
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  this-\>SetAspiredVersions(servable\_name,
std::move(versions));
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  }));
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} }
:::

::: {.line}
[]{#l00127}[ 127]{.lineno} 
:::

::: {.line}
[]{#l00128}[ 128]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00129}[ 129]{.lineno} TargetBase\<T\>::\~TargetBase() {
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  DCHECK(detached\_-\>HasBeenNotified()) \<\<
[\"Detach() must be called exactly \"]{.stringliteral}
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  [\"once, at the top of the leaf
\"]{.stringliteral}
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  [\"derived class\'s
destructor\"]{.stringliteral};
:::

::: {.line}
[]{#l00133}[ 133]{.lineno} }
:::

::: {.line}
[]{#l00134}[ 134]{.lineno} 
:::

::: {.line}
[]{#l00135}[ 135]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00136}[ 136]{.lineno} [typename]{.keyword}
[Source\<T\>::AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f){.code}
:::

::: {.line}
[]{#l00137}[ 137]{.lineno} TargetBase\<T\>::GetAspiredVersionsCallback()
{
:::

::: {.line}
[]{#l00138}[ 138]{.lineno}  mutex\_lock l(\*mu\_);
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  [if]{.keywordflow}
(detached\_-\>HasBeenNotified()) {
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  [// We\'re detached. Return a no-op
callback.]{.comment}
:::

::: {.line}
[]{#l00141}[ 141]{.lineno}  [return]{.keywordflow}
\[\]([const]{.keyword} StringPiece, std::vector\<ServableData\<T\>\>)
{};
:::

::: {.line}
[]{#l00142}[ 142]{.lineno}  }
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  [return]{.keywordflow}
observer\_-\>Notifier();
:::

::: {.line}
[]{#l00144}[ 144]{.lineno} }
:::

::: {.line}
[]{#l00145}[ 145]{.lineno} 
:::

::: {.line}
[]{#l00146}[ 146]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00147}[ 147]{.lineno} [void]{.keywordtype}
TargetBase\<T\>::Detach() {
:::

::: {.line}
[]{#l00148}[ 148]{.lineno}  DCHECK(!detached\_-\>HasBeenNotified()) \<\<
[\"Detach() must be called exactly \"]{.stringliteral}
:::

::: {.line}
[]{#l00149}[ 149]{.lineno}  [\"once, at the top of the leaf
\"]{.stringliteral}
:::

::: {.line}
[]{#l00150}[ 150]{.lineno}  [\"derived class\'s
destructor\"]{.stringliteral};
:::

::: {.line}
[]{#l00151}[ 151]{.lineno} 
:::

::: {.line}
[]{#l00152}[ 152]{.lineno}  [// We defer deleting the observer until
after we\'ve released the lock, to]{.comment}
:::

::: {.line}
[]{#l00153}[ 153]{.lineno}  [// avoid a deadlock with the observer\'s
internal lock when it calls our]{.comment}
:::

::: {.line}
[]{#l00154}[ 154]{.lineno}  [// lambda.]{.comment}
:::

::: {.line}
[]{#l00155}[ 155]{.lineno}  std::unique\_ptr\<Observer\<const
StringPiece, std::vector\<ServableData\<T\>\>\>\>
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  detached\_observer;
:::

::: {.line}
[]{#l00157}[ 157]{.lineno}  {
:::

::: {.line}
[]{#l00158}[ 158]{.lineno}  mutex\_lock l(\*mu\_);
:::

::: {.line}
[]{#l00159}[ 159]{.lineno}  detached\_observer = std::move(observer\_);
:::

::: {.line}
[]{#l00160}[ 160]{.lineno}  [if]{.keywordflow}
(!detached\_-\>HasBeenNotified()) {
:::

::: {.line}
[]{#l00161}[ 161]{.lineno}  detached\_-\>Notify();
:::

::: {.line}
[]{#l00162}[ 162]{.lineno}  }
:::

::: {.line}
[]{#l00163}[ 163]{.lineno}  }
:::

::: {.line}
[]{#l00164}[ 164]{.lineno} }
:::

::: {.line}
[]{#l00165}[ 165]{.lineno} 
:::

::: {.line}
[]{#l00166}[ 166]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00167}[ 167]{.lineno} [void]{.keywordtype}
ConnectSourceToTarget(Source\<T\>\* source, Target\<T\>\* target) {
:::

::: {.line}
[]{#l00168}[ 168]{.lineno} 
source-\>SetAspiredVersionsCallback(target-\>GetAspiredVersionsCallback());
:::

::: {.line}
[]{#l00169}[ 169]{.lineno} }
:::

::: {.line}
[]{#l00170}[ 170]{.lineno} 
:::

::: {.line}
[]{#l00171}[ 171]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00172}[ 172]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00173}[ 173]{.lineno} 
:::

::: {.line}
[]{#l00174}[ 174]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_TARGET\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1Observer_html .ttc}
::: {.ttname}
[tensorflow::serving::Observer](classtensorflow_1_1serving_1_1Observer.html)
:::

::: {.ttdef}
**Definition:** observer.h:60
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

::: {#aclasstensorflow_1_1serving_1_1Source_html .ttc}
::: {.ttname}
[tensorflow::serving::Source](classtensorflow_1_1serving_1_1Source.html)
:::

::: {.ttdef}
**Definition:** source.h:65
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Source_html_aeb281087e1478b0ff4a74e3f60496c6f .ttc}
::: {.ttname}
[tensorflow::serving::Source::AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f)
:::

::: {.ttdeci}
std::function\< void(const StringPiece servable\_name, std::vector\<
ServableData\< T \> \> versions)\> AspiredVersionsCallback
:::

::: {.ttdef}
**Definition:** source.h:88
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

::: {#aclasstensorflow_1_1serving_1_1Target_html .ttc}
::: {.ttname}
[tensorflow::serving::Target](classtensorflow_1_1serving_1_1Target.html)
:::

::: {.ttdef}
**Definition:** target.h:37
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

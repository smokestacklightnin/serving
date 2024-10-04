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
observer.h
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
TENSORFLOW\_SERVING\_UTIL\_OBSERVER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_UTIL\_OBSERVER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<algorithm\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<functional\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} 
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow/core/platform/logging.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/platform/mutex.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow/core/platform/thread\_annotations.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow/core/platform/types.h\"]{.preprocessor}
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
[]{#l00033}[ 33]{.lineno} [// An observer calls a std::function whenever
a specific event happens. The]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// difference between an observer and a plain
std::function is that it is safe]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [// to destroy an observer even while external
code may be notifying it.]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [// Example use:]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [// void ObserveSomeNotifications()
{]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [// mutex mu;]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [// int num\_notifications = 0;]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [// Observer\<\> observer(\[&\](){ mutex\_lock
l(mu); ++num\_notifications; });]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [//
AsynchronouslySendNotificationsForAWhile(observer.Notifier());]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [// SleepForALittleWhile();]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [// {]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [// mutex\_lock l(mu);]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [// LOG(INFO) \<\< \"Currently \" \<\<
num\_notifications \<\< \" notifications\";]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [// // Let \'observer\' fall out of scope and
be deleted. Any future]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [// // notifications will be
no-ops.]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [// Note that the current implementation
serializes the notification calls, so it]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} [// should not be used with long notifications
if the inability to overlap them]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [// would be critical for
performance.]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} [// Note that naive use of this class will
result in \"orphaned\", no-op instances]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} [// std::function laying around. If this is a
concern please use ObserverList to]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} [// manage large collections of
observers.]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} [template]{.keyword}
\<[typename]{.keyword}\... Args\>
:::

::: {.line}
[]{#l00060}[
[60](classtensorflow_1_1serving_1_1Observer.html){.line}]{.lineno} [class
]{.keyword}[Observer](classtensorflow_1_1serving_1_1Observer.html){.code}
{
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [// The type of function that this observer
will wrap.]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [using]{.keyword} Function =
std::function\<void(Args\...)\>;
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [// Wraps \'f\' as an observer.]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [explicit]{.keyword}
[Observer](classtensorflow_1_1serving_1_1Observer.html){.code}(Function
f) : impl\_(std::make\_shared\<Impl\>(std::move(f))) {}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [// Destruction will cause all notifiers to
become no-ops.]{.comment}
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
\~[Observer](classtensorflow_1_1serving_1_1Observer.html){.code}() {
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [if]{.keywordflow} (impl\_ !=
[nullptr]{.keyword}) {
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  impl\_-\>Orphan();
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  }
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  }
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} 
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [// Returns a function that will notify this
observer for its lifetime.]{.comment}
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [// Becomes a no-op after the observer is
destroyed.]{.comment}
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  Function Notifier()[ const ]{.keyword}{
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [auto]{.keyword} impl = impl\_;
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  DCHECK(impl != [nullptr]{.keyword}); [// An
implementation invariant.]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [return]{.keywordflow} \[impl\](Args\...
args) { impl-\>Notify(std::forward\<Args\>(args)\...); };
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  }
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} 
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [template]{.keyword}
\<[typename]{.keyword}\... T\>
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  [friend]{.keyword} [class
]{.keyword}[ObserverList](classtensorflow_1_1serving_1_1ObserverList.html){.code};
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} 
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  [// The underlying implementation.]{.comment}
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  [class
]{.keyword}[Impl](classtensorflow_1_1serving_1_1Observer_1_1Impl.html){.code};
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} 
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  [// The implementation, shared with this
object and all notifiers.]{.comment}
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  std::shared\_ptr\<Impl\> impl\_;
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} 
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([Observer](classtensorflow_1_1serving_1_1Observer.html){.code});
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} };
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} 
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} [// An observer list is essentially a
std::vector\<Observer\>, the key difference]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} [// is that an ObserverList will garbage
collect orphaned notifiers.]{.comment}
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} [template]{.keyword}
\<[typename]{.keyword}\... Args\>
:::

::: {.line}
[]{#l00099}[
[99](classtensorflow_1_1serving_1_1ObserverList.html){.line}]{.lineno} [class
]{.keyword}[ObserverList](classtensorflow_1_1serving_1_1ObserverList.html){.code}
{
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  [// Add an observer to the list.]{.comment}
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [void]{.keywordtype} Add([const]{.keyword}
[Observer\<Args\...\>](classtensorflow_1_1serving_1_1Observer.html){.code}&
new\_observer) {
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  [// Try to reuse an existing slot if
possible.]{.comment}
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  [for]{.keywordflow} ([auto]{.keyword}&
observer : observers\_) {
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  [if]{.keywordflow} (observer-\>IsOrphaned())
{
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  observer = new\_observer.impl\_;
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [return]{.keywordflow};
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  }
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  }
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} 
observers\_.push\_back(new\_observer.impl\_);
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  }
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} 
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  [// Notify all observers in the
list.]{.comment}
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [void]{.keywordtype} Notify(Args\... args) {
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  [for]{.keywordflow} ([const]{.keyword}
[auto]{.keyword}& observer : observers\_) {
:::

::: {.line}
[]{#l00116}[ 116]{.lineno} 
observer-\>Notify(std::forward\<Args\>(args)\...);
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  }
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  }
:::

::: {.line}
[]{#l00119}[ 119]{.lineno} 
:::

::: {.line}
[]{#l00120}[ 120]{.lineno}  [// Clear all observers from this
list.]{.comment}
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  [void]{.keywordtype} Clear() {
observers\_.clear(); }
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} 
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  [// The impls of all observers added to this
list.]{.comment}
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} 
std::vector\<std::shared\_ptr\<[typename]{.keyword}
[Observer](classtensorflow_1_1serving_1_1Observer.html){.code}\<Args\...\>::Impl\>\>
observers\_;
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} };
:::

::: {.line}
[]{#l00127}[ 127]{.lineno} 
:::

::: {.line}
[]{#l00129}[ 129]{.lineno} [// Implementation details follow. API users
need not read.]{.comment}
:::

::: {.line}
[]{#l00130}[ 130]{.lineno} 
:::

::: {.line}
[]{#l00131}[ 131]{.lineno} [template]{.keyword}
\<[typename]{.keyword}\... Args\>
:::

::: {.line}
[]{#l00132}[
[132](classtensorflow_1_1serving_1_1Observer_1_1Impl.html){.line}]{.lineno} [class
]{.keyword}[Observer](classtensorflow_1_1serving_1_1Observer.html){.code}\<Args\...\>::[Impl](classtensorflow_1_1serving_1_1Observer_1_1Impl.html){.code}
{
:::

::: {.line}
[]{#l00133}[ 133]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00134}[ 134]{.lineno}  [explicit]{.keyword}
[Impl](classtensorflow_1_1serving_1_1Observer_1_1Impl.html){.code}(Function
f) : f\_(std::move(f)) {}
:::

::: {.line}
[]{#l00135}[ 135]{.lineno} 
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  [bool]{.keywordtype} IsOrphaned()[ const
]{.keyword}{
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  mutex\_lock lock(mutex\_);
:::

::: {.line}
[]{#l00138}[ 138]{.lineno}  [return]{.keywordflow} f\_ ==
[nullptr]{.keyword};
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  }
:::

::: {.line}
[]{#l00140}[ 140]{.lineno} 
:::

::: {.line}
[]{#l00141}[ 141]{.lineno}  [void]{.keywordtype} Orphan() {
:::

::: {.line}
[]{#l00142}[ 142]{.lineno}  mutex\_lock lock(mutex\_);
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  f\_ = [nullptr]{.keyword};
:::

::: {.line}
[]{#l00144}[ 144]{.lineno}  }
:::

::: {.line}
[]{#l00145}[ 145]{.lineno} 
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  [void]{.keywordtype} Notify(Args\... args)[
const ]{.keyword}{
:::

::: {.line}
[]{#l00147}[ 147]{.lineno}  mutex\_lock lock(mutex\_);
:::

::: {.line}
[]{#l00148}[ 148]{.lineno}  [if]{.keywordflow} (f\_ !=
[nullptr]{.keyword}) {
:::

::: {.line}
[]{#l00149}[ 149]{.lineno}  f\_(std::forward\<Args\>(args)\...);
:::

::: {.line}
[]{#l00150}[ 150]{.lineno}  }
:::

::: {.line}
[]{#l00151}[ 151]{.lineno}  }
:::

::: {.line}
[]{#l00152}[ 152]{.lineno} 
:::

::: {.line}
[]{#l00153}[ 153]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00154}[ 154]{.lineno}  [mutable]{.keyword} mutex mutex\_;
:::

::: {.line}
[]{#l00155}[ 155]{.lineno}  [// The function to call when an observed
even occurs.]{.comment}
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  Function f\_ TF\_GUARDED\_BY(mutex\_);
:::

::: {.line}
[]{#l00157}[ 157]{.lineno} };
:::

::: {.line}
[]{#l00158}[ 158]{.lineno} 
:::

::: {.line}
[]{#l00159}[ 159]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00160}[ 160]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00161}[ 161]{.lineno} 
:::

::: {.line}
[]{#l00162}[ 162]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_UTIL\_OBSERVER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1ObserverList_html .ttc}
::: {.ttname}
[tensorflow::serving::ObserverList](classtensorflow_1_1serving_1_1ObserverList.html)
:::

::: {.ttdef}
**Definition:** observer.h:99
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Observer_1_1Impl_html .ttc}
::: {.ttname}
[tensorflow::serving::Observer::Impl](classtensorflow_1_1serving_1_1Observer_1_1Impl.html)
:::

::: {.ttdef}
**Definition:** observer.h:132
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Observer_html .ttc}
::: {.ttname}
[tensorflow::serving::Observer](classtensorflow_1_1serving_1_1Observer.html)
:::

::: {.ttdef}
**Definition:** observer.h:60
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

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
fast\_read\_dynamic\_ptr.h
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
TENSORFLOW\_SERVING\_UTIL\_FAST\_READ\_DYNAMIC\_PTR\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_UTIL\_FAST\_READ\_DYNAMIC\_PTR\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<algorithm\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<atomic\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<functional\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} 
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/lib/core/notification.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/platform/cpu\_info.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow/core/platform/mutex.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow/core/platform/random.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow/core/platform/types.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} 
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} 
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [// FastReadDynamicPtr\<\> is a thread-safe
class used to manage an object that]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [// needs to be updated occasionally while
being accessed from multiple threads.]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [// Typical use requires construction of a new
object while the old object is]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [// still being used, calling Update() when
the new object is ready. Access to]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [// the object is asynchronous relative to
update operations, so pointers may]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [// exist to both the old and the new object
at the same time (although there can]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [// never be more than two objects
concurrently). After the update begins, any]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [// new calls to get() will point to the new
object. The update will then block]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [// until all pointers to the old object go
out of scope. This is achieved via a]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [// reference counted smart
pointer.]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [// This class is functionally very similar to
using a shared\_ptr guarded by a]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [// mutex, with the important distinction that
it provides finer control over]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [// which thread destroys the object, the
number of live objects, the ability to]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [// recycle old objects if desired, and it
forces an efficient pattern for]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} [// updating data (swapping in a pointer
rather than in-place modification).]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} [// Example Use:]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} [// In initialization code:]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} [// FastReadDynamicPtr\<HeavyWeightObject\>
ptr{InitialValue()};]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} [// From updating thread (executes
infrequently, not performance sensitive):]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} [// std::unique\_ptr\<HeavyWeightObject\>
new\_object(LongRunningFunction());]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} [// std::unique\_ptr\<HeavyWeightObject\>
old\_object =]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} [//
ptr.Update(std::move(new\_object));]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} [// // Reuse old\_object, or just destroy
it.]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} [// From reading thread (executes frequently,
high performance requirements):]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} [// auto object = ptr.get();]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} [// if (object != nullptr) {]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} [// HandleRequest(object.get());]{.comment}
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} [// }]{.comment}
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} [// Care must be taken to not call
FastReadDynamicPtr::Update() from a thread]{.comment}
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} [// that owns any instances of
FastReadDynamicPtr::ReadPtr, or else deadlock may]{.comment}
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} [// occur.]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} 
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} [// FastReadDynamicPtr, below, is templatized
both on the type pointed to, and on]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} [// a concept named \"ReadPtrHolder\", which
holds the ReadPtrs for the]{.comment}
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} [// FastReadDynamicPtr instance. While we
could hold the ReadPtr with just a]{.comment}
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} [// single ReadPtr and a mutex (see
SingleReadPtr, below) having a separate]{.comment}
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} [// concept lets us use higher performance
mechanisms like sharding the ReadPtrs]{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} [// to reduce contention.]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} [namespace
]{.keyword}internal\_read\_ptr\_holder {
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} [class ]{.keyword}ShardedReadPtrs;
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} } [// namespace
internal\_read\_ptr\_holder]{.comment}
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} 
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} [template]{.keyword} \<[typename]{.keyword} T,
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  [typename]{.keyword} ReadPtrHolder =
internal\_read\_ptr\_holder::ShardedReadPtrs\<T\>\>
:::

::: {.line}
[]{#l00087}[
[87](classtensorflow_1_1serving_1_1FastReadDynamicPtr.html){.line}]{.lineno} [class
]{.keyword}[FastReadDynamicPtr](classtensorflow_1_1serving_1_1FastReadDynamicPtr.html){.code}
{
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [// Short, documentative names for the types
of smart pointers we use. Callers]{.comment}
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  [// are not required to use these names;
shared\_ptr and unique\_ptr are part of]{.comment}
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  [// the interface. This is particularly
useful for calling the aliased pointer]{.comment}
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [// constructor of shared\_ptr.]{.comment}
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} 
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  [// Used when providing a read-only pointer.
Never actually used to own an]{.comment}
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  [// object.]{.comment}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  [using]{.keyword} ReadPtr =
std::shared\_ptr\<const T\>;
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} 
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  [// Used when an object is owned.]{.comment}
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  [using]{.keyword} OwnedPtr =
std::unique\_ptr\<T\>;
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} 
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  [// Initially contains a null pointer by
default.]{.comment}
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [explicit]{.keyword}
[FastReadDynamicPtr](classtensorflow_1_1serving_1_1FastReadDynamicPtr.html){.code}(OwnedPtr
= [nullptr]{.keyword});
:::

::: {.line}
[]{#l00103}[ 103]{.lineno} 
\~[FastReadDynamicPtr](classtensorflow_1_1serving_1_1FastReadDynamicPtr.html){.code}();
:::

::: {.line}
[]{#l00104}[ 104]{.lineno} 
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  [// Updates the current object with a new
one, returning the old object. This]{.comment}
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  [// method will block until all ReadPtrs
that point to the previous object have]{.comment}
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [// been destroyed, guaranteeing that the
result is truly unique upon return.]{.comment}
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  [// This method may be called with a null
pointer.]{.comment}
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  [// If the current thread owns any ReadPtrs
to the current object, this method]{.comment}
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  [// will deadlock.]{.comment}
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  OwnedPtr Update(OwnedPtr new\_object);
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} 
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [// Returns a read-only pointer to the
current object. The object will not be]{.comment}
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  [// invalidated as long as the returned
ReadPtr hasn\'t been destroyed. The]{.comment}
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  [// return value may be null if update
hasn\'t been called and if no initial]{.comment}
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  [// value is provided.]{.comment}
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  [// Note that Update() should not be called
from this thread while the returned]{.comment}
:::

::: {.line}
[]{#l00120}[ 120]{.lineno}  [// ReadPtr is in scope, or deadlock will
occur.]{.comment}
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  ReadPtr get() [const]{.keyword};
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} 
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  [// ShareableOwnedPtr wraps an OwnedPtr with
an interface that can provide]{.comment}
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  [// multiple independent ReadPtrs to it.
These ReadPtrs will have separate]{.comment}
:::

::: {.line}
[]{#l00126}[ 126]{.lineno}  [// reference counts to reduce
contention.]{.comment}
:::

::: {.line}
[]{#l00127}[ 127]{.lineno}  [class
]{.keyword}[ShareableOwnedPtr](classtensorflow_1_1serving_1_1FastReadDynamicPtr_1_1ShareableOwnedPtr.html){.code};
:::

::: {.line}
[]{#l00128}[ 128]{.lineno} 
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  mutex mu\_;
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  std::unique\_ptr\<ShareableOwnedPtr\>
shareable\_;
:::

::: {.line}
[]{#l00131}[ 131]{.lineno} 
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  ReadPtrHolder read\_ptrs\_;
:::

::: {.line}
[]{#l00133}[ 133]{.lineno} 
:::

::: {.line}
[]{#l00134}[ 134]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([FastReadDynamicPtr](classtensorflow_1_1serving_1_1FastReadDynamicPtr.html){.code});
:::

::: {.line}
[]{#l00135}[ 135]{.lineno} };
:::

::: {.line}
[]{#l00136}[ 136]{.lineno} 
:::

::: {.line}
[]{#l00137}[ 137]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T, [typename]{.keyword} ReadPtrHolder\>
:::

::: {.line}
[]{#l00138}[
[138](classtensorflow_1_1serving_1_1FastReadDynamicPtr_1_1ShareableOwnedPtr.html){.line}]{.lineno} [class
]{.keyword}[FastReadDynamicPtr](classtensorflow_1_1serving_1_1FastReadDynamicPtr.html){.code}\<T,
ReadPtrHolder\>::[ShareableOwnedPtr](classtensorflow_1_1serving_1_1FastReadDynamicPtr_1_1ShareableOwnedPtr.html){.code}
{
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  [explicit]{.keyword}
[ShareableOwnedPtr](classtensorflow_1_1serving_1_1FastReadDynamicPtr_1_1ShareableOwnedPtr.html){.code}(OwnedPtr
p) : owned\_(std::move(p)) {}
:::

::: {.line}
[]{#l00141}[ 141]{.lineno} 
:::

::: {.line}
[]{#l00142}[ 142]{.lineno}  [// Returns a new, independent ReadPtr
referencing the held OwnedPtr.]{.comment}
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  [// Release() will not return the OwnedPtr
until the returned ReadPtr and all]{.comment}
:::

::: {.line}
[]{#l00144}[ 144]{.lineno}  [// its copies are destroyed.]{.comment}
:::

::: {.line}
[]{#l00145}[ 145]{.lineno}  ReadPtr NewShare() {
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  [if]{.keywordflow} (owned\_ ==
[nullptr]{.keyword}) {
:::

::: {.line}
[]{#l00147}[ 147]{.lineno}  [return]{.keywordflow} [nullptr]{.keyword};
:::

::: {.line}
[]{#l00148}[ 148]{.lineno}  }
:::

::: {.line}
[]{#l00149}[ 149]{.lineno}  shares\_.fetch\_add(1,
std::memory\_order\_release);
:::

::: {.line}
[]{#l00150}[ 150]{.lineno}  [return]{.keywordflow}
std::shared\_ptr\<T\>(owned\_.get(), \[[this]{.keyword}\](T\* p) {
DecRef(); });
:::

::: {.line}
[]{#l00151}[ 151]{.lineno}  }
:::

::: {.line}
[]{#l00152}[ 152]{.lineno} 
:::

::: {.line}
[]{#l00153}[ 153]{.lineno}  [// Waits until all shares have been
destroyed, and then returns the OwnedPtr.]{.comment}
:::

::: {.line}
[]{#l00154}[ 154]{.lineno}  [// No methods should be called after this
one.]{.comment}
:::

::: {.line}
[]{#l00155}[ 155]{.lineno}  OwnedPtr Release() && {
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  DecRef();
:::

::: {.line}
[]{#l00157}[ 157]{.lineno}  no\_longer\_shared\_.WaitForNotification();
:::

::: {.line}
[]{#l00158}[ 158]{.lineno}  [return]{.keywordflow} std::move(owned\_);
:::

::: {.line}
[]{#l00159}[ 159]{.lineno}  }
:::

::: {.line}
[]{#l00160}[ 160]{.lineno} 
:::

::: {.line}
[]{#l00161}[ 161]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00162}[ 162]{.lineno}  [void]{.keywordtype} DecRef() {
:::

::: {.line}
[]{#l00163}[ 163]{.lineno}  [if]{.keywordflow} (shares\_.fetch\_sub(1,
std::memory\_order\_acq\_rel) == 1) {
:::

::: {.line}
[]{#l00164}[ 164]{.lineno}  no\_longer\_shared\_.Notify();
:::

::: {.line}
[]{#l00165}[ 165]{.lineno}  }
:::

::: {.line}
[]{#l00166}[ 166]{.lineno}  }
:::

::: {.line}
[]{#l00167}[ 167]{.lineno} 
:::

::: {.line}
[]{#l00168}[ 168]{.lineno}  OwnedPtr owned\_;
:::

::: {.line}
[]{#l00169}[ 169]{.lineno}  [// The number of times we\'ve shared the
pointer. This defaults to 1 so we can]{.comment}
:::

::: {.line}
[]{#l00170}[ 170]{.lineno}  [// safely and incrementally hand out
shares, without worrying that]{.comment}
:::

::: {.line}
[]{#l00171}[ 171]{.lineno}  [// no\_longer\_shared\_ will be notified
until Release() has been called, which]{.comment}
:::

::: {.line}
[]{#l00172}[ 172]{.lineno}  [// decrements this before waiting for a
notification.]{.comment}
:::

::: {.line}
[]{#l00173}[ 173]{.lineno}  std::atomic\<uint32\> shares\_ = {1};
:::

::: {.line}
[]{#l00174}[ 174]{.lineno}  [// When shares\_ goes to zero, this will be
notified.]{.comment}
:::

::: {.line}
[]{#l00175}[ 175]{.lineno}  Notification no\_longer\_shared\_;
:::

::: {.line}
[]{#l00176}[ 176]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([ShareableOwnedPtr](classtensorflow_1_1serving_1_1FastReadDynamicPtr_1_1ShareableOwnedPtr.html){.code});
:::

::: {.line}
[]{#l00177}[ 177]{.lineno} };
:::

::: {.line}
[]{#l00178}[ 178]{.lineno} 
:::

::: {.line}
[]{#l00179}[ 179]{.lineno} [namespace
]{.keyword}internal\_read\_ptr\_holder {
:::

::: {.line}
[]{#l00180}[ 180]{.lineno} [// ReadPtrHolders must provide two
methods:]{.comment}
:::

::: {.line}
[]{#l00181}[ 181]{.lineno} [// 1. get(), which must be thread safe, and
returns a shared\_ptr\<const T\>, and]{.comment}
:::

::: {.line}
[]{#l00182}[ 182]{.lineno} [// 2. update(), which takes a factory
function f (which returns a]{.comment}
:::

::: {.line}
[]{#l00183}[ 183]{.lineno} [// std::shared\_ptr\<const T\>), calls it
one or more times, and updates the]{.comment}
:::

::: {.line}
[]{#l00184}[ 184]{.lineno} [// internal state to match. get() after an
update() call should return one]{.comment}
:::

::: {.line}
[]{#l00185}[ 185]{.lineno} [// of the pointers produced by the factory.
update() is not required to be]{.comment}
:::

::: {.line}
[]{#l00186}[ 186]{.lineno} [// thread-safe against other callers (but
must be thread-safe against]{.comment}
:::

::: {.line}
[]{#l00187}[ 187]{.lineno} [// parallel get() calls); it will only ever
be called under a lock.]{.comment}
:::

::: {.line}
[]{#l00188}[ 188]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00189}[ 189]{.lineno} [// The Factory-based interface of update()
may seem strange, but it allows]{.comment}
:::

::: {.line}
[]{#l00190}[ 190]{.lineno} [// ReadPtrHolders to hold several distinct
ReadPtrs.]{.comment}
:::

::: {.line}
[]{#l00191}[ 191]{.lineno} 
:::

::: {.line}
[]{#l00192}[ 192]{.lineno} [// SingleReadDPtr is the simplest possible
implementation of a ReadPtrHolder,]{.comment}
:::

::: {.line}
[]{#l00193}[ 193]{.lineno} [// but it causes every reader to contend on
both the mutex\_lock and the atomic]{.comment}
:::

::: {.line}
[]{#l00194}[ 194]{.lineno} [// reference count for the ReadPtr it holds.
By default we use ShardedReadPtrs,]{.comment}
:::

::: {.line}
[]{#l00195}[ 195]{.lineno} [// below, which avoids both of these
pitfalls. SingleReadPtr here is useful]{.comment}
:::

::: {.line}
[]{#l00196}[ 196]{.lineno} [// primarily for benchmarking and for
ensuring that no reader ever goes \"back in]{.comment}
:::

::: {.line}
[]{#l00197}[ 197]{.lineno} [// time\": in the sharded implementation,
below, it\'s possible for a reader to]{.comment}
:::

::: {.line}
[]{#l00198}[ 198]{.lineno} [// see a new version and then see an older
version in get(), if the writer is in]{.comment}
:::

::: {.line}
[]{#l00199}[ 199]{.lineno} [// the midst of an update() call.]{.comment}
:::

::: {.line}
[]{#l00200}[ 200]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00201}[ 201]{.lineno} [// If you don\'t care about contention and
you want to save memory, you might]{.comment}
:::

::: {.line}
[]{#l00202}[ 202]{.lineno} [// want to use this.]{.comment}
:::

::: {.line}
[]{#l00203}[ 203]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00204}[
[204](classtensorflow_1_1serving_1_1internal__read__ptr__holder_1_1SingleReadPtr.html){.line}]{.lineno} [class
]{.keyword}[SingleReadPtr](classtensorflow_1_1serving_1_1internal__read__ptr__holder_1_1SingleReadPtr.html){.code}
{
:::

::: {.line}
[]{#l00205}[ 205]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00206}[ 206]{.lineno}  std::shared\_ptr\<const T\> get()[ const
]{.keyword}{
:::

::: {.line}
[]{#l00207}[ 207]{.lineno}  mutex\_lock lock(mu\_);
:::

::: {.line}
[]{#l00208}[ 208]{.lineno}  [return]{.keywordflow} p\_;
:::

::: {.line}
[]{#l00209}[ 209]{.lineno}  }
:::

::: {.line}
[]{#l00210}[ 210]{.lineno} 
:::

::: {.line}
[]{#l00211}[ 211]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
Factory\>
:::

::: {.line}
[]{#l00212}[ 212]{.lineno}  [void]{.keywordtype}
update([const]{.keyword} Factory& f) {
:::

::: {.line}
[]{#l00213}[ 213]{.lineno}  [auto]{.keyword} p = f();
:::

::: {.line}
[]{#l00214}[ 214]{.lineno}  mutex\_lock lock(mu\_);
:::

::: {.line}
[]{#l00215}[ 215]{.lineno}  p\_.swap(p);
:::

::: {.line}
[]{#l00216}[ 216]{.lineno}  }
:::

::: {.line}
[]{#l00217}[ 217]{.lineno} 
:::

::: {.line}
[]{#l00218}[ 218]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00219}[ 219]{.lineno}  [mutable]{.keyword} mutex mu\_;
:::

::: {.line}
[]{#l00220}[ 220]{.lineno}  std::shared\_ptr\<const T\> p\_;
:::

::: {.line}
[]{#l00221}[ 221]{.lineno} };
:::

::: {.line}
[]{#l00222}[ 222]{.lineno} 
:::

::: {.line}
[]{#l00223}[ 223]{.lineno} [// This maintains a set of sharded ReadPtrs.
It tries to shard one ReadPtr per]{.comment}
:::

::: {.line}
[]{#l00224}[ 224]{.lineno} [// CPU, but if the port::NumTotalCPUs or
port::GetCurrentCPU fails, it falls]{.comment}
:::

::: {.line}
[]{#l00225}[ 225]{.lineno} [// back to random sharding.]{.comment}
:::

::: {.line}
[]{#l00226}[ 226]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00227}[
[227](classtensorflow_1_1serving_1_1internal__read__ptr__holder_1_1ShardedReadPtrs.html){.line}]{.lineno} [class
]{.keyword}[ShardedReadPtrs](classtensorflow_1_1serving_1_1internal__read__ptr__holder_1_1ShardedReadPtrs.html){.code}
{
:::

::: {.line}
[]{#l00228}[ 228]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00229}[ 229]{.lineno} 
[ShardedReadPtrs](classtensorflow_1_1serving_1_1internal__read__ptr__holder_1_1ShardedReadPtrs.html){.code}()
: shards\_([new]{.keyword} PaddedThreadSafeSharedPtr\[num\_shards\_\])
{}
:::

::: {.line}
[]{#l00230}[ 230]{.lineno} 
:::

::: {.line}
[]{#l00231}[ 231]{.lineno}  std::shared\_ptr\<const T\> get()[ const
]{.keyword}{
:::

::: {.line}
[]{#l00232}[ 232]{.lineno}  [const]{.keyword} [int]{.keywordtype} shard
= GetShard();
:::

::: {.line}
[]{#l00233}[ 233]{.lineno}  mutex\_lock lock(shards\_\[shard\].mu);
:::

::: {.line}
[]{#l00234}[ 234]{.lineno}  [return]{.keywordflow}
shards\_\[shard\].ps\[index\_.load(std::memory\_order\_acquire)\];
:::

::: {.line}
[]{#l00235}[ 235]{.lineno}  }
:::

::: {.line}
[]{#l00236}[ 236]{.lineno} 
:::

::: {.line}
[]{#l00237}[ 237]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
Factory\>
:::

::: {.line}
[]{#l00238}[ 238]{.lineno}  [void]{.keywordtype}
update([const]{.keyword} Factory& f) {
:::

::: {.line}
[]{#l00239}[ 239]{.lineno}  [// First we\'ll update all the pointers
into each shard\'s next\_index, then]{.comment}
:::

::: {.line}
[]{#l00240}[ 240]{.lineno}  [// we\'ll change index\_ to point to those
new pointers, then we\'ll get rid of]{.comment}
:::

::: {.line}
[]{#l00241}[ 241]{.lineno}  [// orig\_index. This ensures temporal
consistency, so no reader ever goes]{.comment}
:::

::: {.line}
[]{#l00242}[ 242]{.lineno}  [// back in time: all readers advance to
next\_index together, when we write]{.comment}
:::

::: {.line}
[]{#l00243}[ 243]{.lineno}  [// to index\_.]{.comment}
:::

::: {.line}
[]{#l00244}[ 244]{.lineno}  [const]{.keyword} uint32 orig\_index =
index\_.load(std::memory\_order\_acquire);
:::

::: {.line}
[]{#l00245}[ 245]{.lineno}  [const]{.keyword} uint32 next\_index =
orig\_index ? 0 : 1;
:::

::: {.line}
[]{#l00246}[ 246]{.lineno}  [for]{.keywordflow} ([int]{.keywordtype}
shard = 0; shard \< num\_shards\_; ++shard) {
:::

::: {.line}
[]{#l00247}[ 247]{.lineno}  [auto]{.keyword} p = f();
:::

::: {.line}
[]{#l00248}[ 248]{.lineno}  mutex\_lock lock(shards\_\[shard\].mu);
:::

::: {.line}
[]{#l00249}[ 249]{.lineno}  shards\_\[shard\].ps\[next\_index\] =
std::move(p);
:::

::: {.line}
[]{#l00250}[ 250]{.lineno}  }
:::

::: {.line}
[]{#l00251}[ 251]{.lineno}  index\_.store(next\_index,
std::memory\_order\_release);
:::

::: {.line}
[]{#l00252}[ 252]{.lineno}  [for]{.keywordflow} ([int]{.keywordtype}
shard = 0; shard \< num\_shards\_; ++shard) {
:::

::: {.line}
[]{#l00253}[ 253]{.lineno}  std::shared\_ptr\<const T\> p;
:::

::: {.line}
[]{#l00254}[ 254]{.lineno}  mutex\_lock lock(shards\_\[shard\].mu);
:::

::: {.line}
[]{#l00255}[ 255]{.lineno}  shards\_\[shard\].ps\[orig\_index\].swap(p);
:::

::: {.line}
[]{#l00256}[ 256]{.lineno}  }
:::

::: {.line}
[]{#l00257}[ 257]{.lineno}  }
:::

::: {.line}
[]{#l00258}[ 258]{.lineno} 
:::

::: {.line}
[]{#l00259}[ 259]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00260}[ 260]{.lineno}  [// NOTE: If a std::atomic\_shared\_ptr is
ever available, it would be reasonable]{.comment}
:::

::: {.line}
[]{#l00261}[ 261]{.lineno}  [// to use that here for improved
performance.]{.comment}
:::

::: {.line}
[]{#l00262}[ 262]{.lineno}  [struct ]{.keyword}ThreadSafeSharedPtr {
:::

::: {.line}
[]{#l00263}[ 263]{.lineno}  std::shared\_ptr\<const T\> ps\[2\];
:::

::: {.line}
[]{#l00264}[ 264]{.lineno}  mutex mu;
:::

::: {.line}
[]{#l00265}[ 265]{.lineno}  };
:::

::: {.line}
[]{#l00266}[ 266]{.lineno} 
:::

::: {.line}
[]{#l00267}[ 267]{.lineno}  [// We pad the pointers to ensure that
individual shards don\'t experience false]{.comment}
:::

::: {.line}
[]{#l00268}[ 268]{.lineno}  [// sharing between threads.]{.comment}
:::

::: {.line}
[]{#l00269}[ 269]{.lineno}  [struct ]{.keyword}PaddedThreadSafeSharedPtr
: [public]{.keyword} ThreadSafeSharedPtr {
:::

::: {.line}
[]{#l00270}[ 270]{.lineno}  [char]{.keywordtype} padding\[64 -
[sizeof]{.keyword}(ThreadSafeSharedPtr)\];
:::

::: {.line}
[]{#l00271}[ 271]{.lineno}  };
:::

::: {.line}
[]{#l00272}[ 272]{.lineno} 
static\_assert([sizeof]{.keyword}(PaddedThreadSafeSharedPtr) \>= 64,
:::

::: {.line}
[]{#l00273}[ 273]{.lineno}  [\"PaddedThreadSafeSharedPtr should be at
least 64 bytes.\"]{.stringliteral});
:::

::: {.line}
[]{#l00274}[ 274]{.lineno} 
:::

::: {.line}
[]{#l00275}[ 275]{.lineno}  [static]{.keyword} constexpr
[int]{.keywordtype} kRandomShards = 16;
:::

::: {.line}
[]{#l00276}[ 276]{.lineno}  [int]{.keywordtype} GetShard()[ const
]{.keyword}{
:::

::: {.line}
[]{#l00277}[ 277]{.lineno}  [const]{.keyword} [int]{.keywordtype} cpu =
port::GetCurrentCPU();
:::

::: {.line}
[]{#l00278}[ 278]{.lineno}  [if]{.keywordflow} (cpu != -1) {
:::

::: {.line}
[]{#l00279}[ 279]{.lineno}  [return]{.keywordflow} cpu;
:::

::: {.line}
[]{#l00280}[ 280]{.lineno}  }
:::

::: {.line}
[]{#l00281}[ 281]{.lineno}  [// Otherwise, return a random shard.
random::New64 would introduce a mutex]{.comment}
:::

::: {.line}
[]{#l00282}[ 282]{.lineno}  [// lock here, which would defeat the
purpose of the sharding. Similarly, a]{.comment}
:::

::: {.line}
[]{#l00283}[ 283]{.lineno}  [// static std::atomic\<uint64\_t\>, if
updated with any memory order other than]{.comment}
:::

::: {.line}
[]{#l00284}[ 284]{.lineno}  [// std::memory\_order\_relaxed, would
re-introduce contention on that memory]{.comment}
:::

::: {.line}
[]{#l00285}[ 285]{.lineno}  [// location. A thread\_local sidesteps both
problems with only eight bytes]{.comment}
:::

::: {.line}
[]{#l00286}[ 286]{.lineno}  [// per thread of overhead.]{.comment}
:::

::: {.line}
[]{#l00287}[ 287]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00288}[ 288]{.lineno}  [// MCGs need to be seeded with an odd
number, so we ensure the lowest bit is]{.comment}
:::

::: {.line}
[]{#l00289}[ 289]{.lineno}  [// set.]{.comment}
:::

::: {.line}
[]{#l00290}[ 290]{.lineno}  thread\_local uint64\_t state =
{random::New64() \| 1ULL};
:::

::: {.line}
[]{#l00291}[ 291]{.lineno}  [// We just need something simple and good
enough. The multiplier here was]{.comment}
:::

::: {.line}
[]{#l00292}[ 292]{.lineno}  [// picked from \"COMPUTATIONALLY EASY,
SPECTRALLY GOOD MULTIPLIERS FOR]{.comment}
:::

::: {.line}
[]{#l00293}[ 293]{.lineno}  [// CONGRUENTIAL PSEUDORANDOM NUMBER
GENERATORS\" by Steele and Vigna.]{.comment}
:::

::: {.line}
[]{#l00294}[ 294]{.lineno}  state \*= 0xd09d;
:::

::: {.line}
[]{#l00295}[ 295]{.lineno}  [// Update this shift if kRandomShards
changes.]{.comment}
:::

::: {.line}
[]{#l00296}[ 296]{.lineno}  [return]{.keywordflow} state \>\> 60;
:::

::: {.line}
[]{#l00297}[ 297]{.lineno}  }
:::

::: {.line}
[]{#l00298}[ 298]{.lineno} 
:::

::: {.line}
[]{#l00299}[ 299]{.lineno}  [protected]{.keyword}:
:::

::: {.line}
[]{#l00300}[ 300]{.lineno}  [const]{.keyword} [int]{.keywordtype}
num\_shards\_ =
:::

::: {.line}
[]{#l00301}[ 301]{.lineno}  port::NumTotalCPUs() == -1 ? kRandomShards :
port::NumTotalCPUs();
:::

::: {.line}
[]{#l00302}[ 302]{.lineno}  std::atomic\<uint32\> index\_{0};
:::

::: {.line}
[]{#l00303}[ 303]{.lineno} 
std::unique\_ptr\<PaddedThreadSafeSharedPtr\[\]\> shards\_;
:::

::: {.line}
[]{#l00304}[ 304]{.lineno} };
:::

::: {.line}
[]{#l00305}[ 305]{.lineno} 
:::

::: {.line}
[]{#l00306}[ 306]{.lineno} } [// namespace
internal\_read\_ptr\_holder]{.comment}
:::

::: {.line}
[]{#l00307}[ 307]{.lineno} 
:::

::: {.line}
[]{#l00308}[ 308]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T, [typename]{.keyword} ReadPtrHolder\>
:::

::: {.line}
[]{#l00309}[ 309]{.lineno} [FastReadDynamicPtr\<T,
ReadPtrHolder\>::FastReadDynamicPtr](classtensorflow_1_1serving_1_1FastReadDynamicPtr.html){.code}(OwnedPtr
p) {
:::

::: {.line}
[]{#l00310}[ 310]{.lineno}  [if]{.keywordflow} (p !=
[nullptr]{.keyword}) {
:::

::: {.line}
[]{#l00311}[ 311]{.lineno}  Update(std::move(p));
:::

::: {.line}
[]{#l00312}[ 312]{.lineno}  }
:::

::: {.line}
[]{#l00313}[ 313]{.lineno} }
:::

::: {.line}
[]{#l00314}[ 314]{.lineno} 
:::

::: {.line}
[]{#l00315}[ 315]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T, [typename]{.keyword} ReadPtrHolder\>
:::

::: {.line}
[]{#l00316}[ 316]{.lineno} FastReadDynamicPtr\<T,
ReadPtrHolder\>::\~FastReadDynamicPtr() {
:::

::: {.line}
[]{#l00317}[ 317]{.lineno}  [// Force a wait until all outstanding
ReadPtrs are destroyed.]{.comment}
:::

::: {.line}
[]{#l00318}[ 318]{.lineno}  Update([nullptr]{.keyword});
:::

::: {.line}
[]{#l00319}[ 319]{.lineno} }
:::

::: {.line}
[]{#l00320}[ 320]{.lineno} 
:::

::: {.line}
[]{#l00321}[ 321]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T, [typename]{.keyword} ReadPtrHolder\>
:::

::: {.line}
[]{#l00322}[ 322]{.lineno} std::unique\_ptr\<T\> FastReadDynamicPtr\<T,
ReadPtrHolder\>::Update(
:::

::: {.line}
[]{#l00323}[ 323]{.lineno}  OwnedPtr new\_object) {
:::

::: {.line}
[]{#l00324}[ 324]{.lineno}  std::unique\_ptr\<ShareableOwnedPtr\>
shareable(
:::

::: {.line}
[]{#l00325}[ 325]{.lineno}  [new]{.keyword}
ShareableOwnedPtr(std::move(new\_object)));
:::

::: {.line}
[]{#l00326}[ 326]{.lineno}  {
:::

::: {.line}
[]{#l00327}[ 327]{.lineno}  mutex\_lock lock(mu\_);
:::

::: {.line}
[]{#l00328}[ 328]{.lineno}  read\_ptrs\_.update(\[&\] {
[return]{.keywordflow} shareable-\>NewShare(); });
:::

::: {.line}
[]{#l00329}[ 329]{.lineno}  shareable\_.swap(shareable);
:::

::: {.line}
[]{#l00330}[ 330]{.lineno}  }
:::

::: {.line}
[]{#l00331}[ 331]{.lineno}  [return]{.keywordflow} shareable ==
[nullptr]{.keyword} ? nullptr : std::move(\*shareable).Release();
:::

::: {.line}
[]{#l00332}[ 332]{.lineno} }
:::

::: {.line}
[]{#l00333}[ 333]{.lineno} 
:::

::: {.line}
[]{#l00334}[ 334]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T, [typename]{.keyword} ReadPtrHolder\>
:::

::: {.line}
[]{#l00335}[ 335]{.lineno} std::shared\_ptr\<const T\>
FastReadDynamicPtr\<T, ReadPtrHolder\>::get()[ const ]{.keyword}{
:::

::: {.line}
[]{#l00336}[ 336]{.lineno}  [return]{.keywordflow} read\_ptrs\_.get();
:::

::: {.line}
[]{#l00337}[ 337]{.lineno} }
:::

::: {.line}
[]{#l00338}[ 338]{.lineno} 
:::

::: {.line}
[]{#l00339}[ 339]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00340}[ 340]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00341}[ 341]{.lineno} 
:::

::: {.line}
[]{#l00342}[ 342]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_UTIL\_FAST\_READ\_DYNAMIC\_PTR\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1FastReadDynamicPtr_1_1ShareableOwnedPtr_html .ttc}
::: {.ttname}
[tensorflow::serving::FastReadDynamicPtr::ShareableOwnedPtr](classtensorflow_1_1serving_1_1FastReadDynamicPtr_1_1ShareableOwnedPtr.html)
:::

::: {.ttdef}
**Definition:** fast\_read\_dynamic\_ptr.h:138
:::
:::

::: {#aclasstensorflow_1_1serving_1_1FastReadDynamicPtr_html .ttc}
::: {.ttname}
[tensorflow::serving::FastReadDynamicPtr](classtensorflow_1_1serving_1_1FastReadDynamicPtr.html)
:::

::: {.ttdef}
**Definition:** fast\_read\_dynamic\_ptr.h:87
:::
:::

::: {#aclasstensorflow_1_1serving_1_1internal__read__ptr__holder_1_1ShardedReadPtrs_html .ttc}
::: {.ttname}
[tensorflow::serving::internal\_read\_ptr\_holder::ShardedReadPtrs](classtensorflow_1_1serving_1_1internal__read__ptr__holder_1_1ShardedReadPtrs.html)
:::

::: {.ttdef}
**Definition:** fast\_read\_dynamic\_ptr.h:227
:::
:::

::: {#aclasstensorflow_1_1serving_1_1internal__read__ptr__holder_1_1SingleReadPtr_html .ttc}
::: {.ttname}
[tensorflow::serving::internal\_read\_ptr\_holder::SingleReadPtr](classtensorflow_1_1serving_1_1internal__read__ptr__holder_1_1SingleReadPtr.html)
:::

::: {.ttdef}
**Definition:** fast\_read\_dynamic\_ptr.h:204
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

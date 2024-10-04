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
any\_ptr.h
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
TENSORFLOW\_SERVING\_UTIL\_ANY\_PTR\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_UTIL\_ANY\_PTR\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<cstddef\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} 
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} 
:::

::: {.line}
[]{#l00065}[
[65](classtensorflow_1_1serving_1_1AnyPtr.html){.line}]{.lineno} [class
]{.keyword}[AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html){.code} {
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00068}[
[68](classtensorflow_1_1serving_1_1AnyPtr.html#a0250c65b7f2f4747e8050620f498b51c){.line}]{.lineno} 
[AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html#a0250c65b7f2f4747e8050620f498b51c){.code}()
: type\_id\_(FastTypeId\<void\>()), ptr\_(nullptr) {}
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
:::

::: {.line}
[]{#l00071}[
[71](classtensorflow_1_1serving_1_1AnyPtr.html#a9e716e1e923c2094e4e88e83d9800595){.line}]{.lineno} 
[AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html#a9e716e1e923c2094e4e88e83d9800595){.code}(std::nullptr\_t)
: [AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html){.code}() {} [//
NOLINT]{.comment}
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} 
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00075}[
[75](classtensorflow_1_1serving_1_1AnyPtr.html#a90f5c7399a7ae6d4847d9f86669fcab7){.line}]{.lineno} 
[AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html#a90f5c7399a7ae6d4847d9f86669fcab7){.code}(T\*
ptr) [// NOLINT]{.comment}
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  : type\_id\_(FastTypeId\<T\>()),
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [// We need a double cast here, first to drop
the type, and second to]{.comment}
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [// drop constness. We always cast back to
the appropriate type and]{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  [// constness in get\<\>(), since FastTypeId
is different for a const and]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [// non-const T.]{.comment}
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} 
ptr\_(const\_cast\<void\*\>(reinterpret\_cast\<const void\*\>(ptr))) {}
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} 
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00085}[
[85](classtensorflow_1_1serving_1_1AnyPtr.html#a357cf7dcf137a8064c393b486509d218){.line}]{.lineno} 
T\*
[get](classtensorflow_1_1serving_1_1AnyPtr.html#a357cf7dcf137a8064c393b486509d218){.code}()[
const ]{.keyword}{
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  [if]{.keywordflow} (type\_id\_ !=
FastTypeId\<T\>()) {
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  [return]{.keywordflow} [nullptr]{.keyword};
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  }
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [return]{.keywordflow}
[reinterpret\_cast\<]{.keyword}T\*[\>]{.keyword}(ptr\_);
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  }
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} 
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
Type\>
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  [static]{.keyword} [size\_t]{.keywordtype}
FastTypeId() {
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  [// Use a static variable to get a unique
per-type address.]{.comment}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  [static]{.keyword} [int]{.keywordtype} dummy;
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  [return]{.keywordflow}
[reinterpret\_cast\<]{.keyword}std::size\_t[\>]{.keyword}(&dummy);
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  }
:::

::: {.line}
[]{#l00099}[ 99]{.lineno} 
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  [// The code for the type of
\'ptr\_\'.]{.comment}
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  std::size\_t type\_id\_;
:::

::: {.line}
[]{#l00102}[ 102]{.lineno} 
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  [// The underlying pointer.]{.comment}
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  [void]{.keywordtype}\* ptr\_;
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} };
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} 
:::

::: {.line}
[]{#l00109}[
[109](classtensorflow_1_1serving_1_1UniqueAnyPtr.html){.line}]{.lineno} [class
]{.keyword}[UniqueAnyPtr](classtensorflow_1_1serving_1_1UniqueAnyPtr.html){.code}
{
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00112}[
[112](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#a2289c5328e883bc22bd79fc7b7262244){.line}]{.lineno} 
[UniqueAnyPtr](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#a2289c5328e883bc22bd79fc7b7262244){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} 
[UniqueAnyPtr](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#a2289c5328e883bc22bd79fc7b7262244){.code}(std::nullptr\_t)
:
[UniqueAnyPtr](classtensorflow_1_1serving_1_1UniqueAnyPtr.html){.code}()
{} [// NOLINT]{.comment}
:::

::: {.line}
[]{#l00114}[ 114]{.lineno} 
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00117}[
[117](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#ae33840e17d58e1e45a77306e8c0312a5){.line}]{.lineno} 
[explicit]{.keyword}
[UniqueAnyPtr](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#ae33840e17d58e1e45a77306e8c0312a5){.code}(std::unique\_ptr\<T\>
ptr)
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  : ptr\_(ptr.release()),
deleter\_(DeleterForType\<T\>()) {}
:::

::: {.line}
[]{#l00119}[ 119]{.lineno} 
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} 
\~[UniqueAnyPtr](classtensorflow_1_1serving_1_1UniqueAnyPtr.html){.code}()
{ deleter\_(ptr\_); }
:::

::: {.line}
[]{#l00121}[ 121]{.lineno} 
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  [// Disable copy.]{.comment}
:::

::: {.line}
[]{#l00123}[ 123]{.lineno} 
[UniqueAnyPtr](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#a2289c5328e883bc22bd79fc7b7262244){.code}([const]{.keyword}
[UniqueAnyPtr](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#a2289c5328e883bc22bd79fc7b7262244){.code}&
other) = [delete]{.keyword};
:::

::: {.line}
[]{#l00124}[ 124]{.lineno} 
[UniqueAnyPtr](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#a2289c5328e883bc22bd79fc7b7262244){.code}&
operator=([const]{.keyword}
[UniqueAnyPtr](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#a2289c5328e883bc22bd79fc7b7262244){.code}&
other) = [delete]{.keyword};
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} 
:::

::: {.line}
[]{#l00126}[ 126]{.lineno}  [// Allow move.]{.comment}
:::

::: {.line}
[]{#l00127}[ 127]{.lineno} 
[UniqueAnyPtr](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#a2289c5328e883bc22bd79fc7b7262244){.code}([UniqueAnyPtr](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#a2289c5328e883bc22bd79fc7b7262244){.code}&&
other) { swap(other); }
:::

::: {.line}
[]{#l00128}[ 128]{.lineno} 
:::

::: {.line}
[]{#l00129}[ 129]{.lineno} 
[UniqueAnyPtr](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#a2289c5328e883bc22bd79fc7b7262244){.code}&
operator=([UniqueAnyPtr](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#a2289c5328e883bc22bd79fc7b7262244){.code}&&
other) {
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  swap(other);
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  [return]{.keywordflow} \*[this]{.keyword};
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  }
:::

::: {.line}
[]{#l00133}[ 133]{.lineno} 
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00136}[
[136](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#acb57a78f3357bd37e85a25ca707d692b){.line}]{.lineno} 
T\*
[get](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#acb57a78f3357bd37e85a25ca707d692b){.code}()[
const ]{.keyword}{
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  [return]{.keywordflow}
ptr\_.[get](classtensorflow_1_1serving_1_1AnyPtr.html#a357cf7dcf137a8064c393b486509d218){.code}\<T\>();
:::

::: {.line}
[]{#l00138}[ 138]{.lineno}  }
:::

::: {.line}
[]{#l00139}[ 139]{.lineno} 
:::

::: {.line}
[]{#l00141}[
[141](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#a5b06edf7f9381bbae5a1fbc903d0e2f0){.line}]{.lineno} 
[const]{.keyword}
[AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html){.code}&
[as\_any\_ptr](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#a5b06edf7f9381bbae5a1fbc903d0e2f0){.code}()[
const ]{.keyword}{ [return]{.keywordflow} ptr\_; }
:::

::: {.line}
[]{#l00142}[ 142]{.lineno} 
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  [void]{.keywordtype}
swap([UniqueAnyPtr](classtensorflow_1_1serving_1_1UniqueAnyPtr.html){.code}&
other) {
:::

::: {.line}
[]{#l00144}[ 144]{.lineno}  using ::std::swap;
:::

::: {.line}
[]{#l00145}[ 145]{.lineno}  swap(ptr\_, other.ptr\_);
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  swap(deleter\_, other.deleter\_);
:::

::: {.line}
[]{#l00147}[ 147]{.lineno}  }
:::

::: {.line}
[]{#l00148}[ 148]{.lineno} 
:::

::: {.line}
[]{#l00149}[ 149]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00150}[ 150]{.lineno}  [// We use a raw function pointer. This
eliminates the copy and calling]{.comment}
:::

::: {.line}
[]{#l00151}[ 151]{.lineno}  [// overhead of std::function.]{.comment}
:::

::: {.line}
[]{#l00152}[ 152]{.lineno}  [using]{.keyword} Deleter = void (\*)(AnyPtr
ptr);
:::

::: {.line}
[]{#l00153}[ 153]{.lineno} 
:::

::: {.line}
[]{#l00154}[ 154]{.lineno}  [// Returns a \'Deleter\' that will delete
it\'s argument as an instance of \'T\'.]{.comment}
:::

::: {.line}
[]{#l00155}[ 155]{.lineno}  [// Always returns the same value for the
same \'T\'.]{.comment}
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00157}[ 157]{.lineno}  [static]{.keyword} Deleter DeleterForType()
{
:::

::: {.line}
[]{#l00158}[ 158]{.lineno}  [return]{.keywordflow} \[\](AnyPtr ptr) {
[delete]{.keyword} ptr.get\<T\>(); };
:::

::: {.line}
[]{#l00159}[ 159]{.lineno}  }
:::

::: {.line}
[]{#l00160}[ 160]{.lineno} 
:::

::: {.line}
[]{#l00161}[ 161]{.lineno}  [static]{.keyword} Deleter NoOpDeleter() {
:::

::: {.line}
[]{#l00162}[ 162]{.lineno}  [return]{.keywordflow} \[\](AnyPtr ptr) {};
:::

::: {.line}
[]{#l00163}[ 163]{.lineno}  }
:::

::: {.line}
[]{#l00164}[ 164]{.lineno} 
:::

::: {.line}
[]{#l00165}[ 165]{.lineno}  AnyPtr ptr\_ = [nullptr]{.keyword};
:::

::: {.line}
[]{#l00166}[ 166]{.lineno}  Deleter deleter\_ = NoOpDeleter();
:::

::: {.line}
[]{#l00167}[ 167]{.lineno} };
:::

::: {.line}
[]{#l00168}[ 168]{.lineno} 
:::

::: {.line}
[]{#l00169}[ 169]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00170}[ 170]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00171}[ 171]{.lineno} 
:::

::: {.line}
[]{#l00172}[ 172]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_UTIL\_ANY\_PTR\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1AnyPtr_html .ttc}
::: {.ttname}
[tensorflow::serving::AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html)
:::

::: {.ttdef}
**Definition:** any\_ptr.h:65
:::
:::

::: {#aclasstensorflow_1_1serving_1_1AnyPtr_html_a0250c65b7f2f4747e8050620f498b51c .ttc}
::: {.ttname}
[tensorflow::serving::AnyPtr::AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html#a0250c65b7f2f4747e8050620f498b51c)
:::

::: {.ttdeci}
AnyPtr()
:::

::: {.ttdoc}
AnyPtr is void and null by default.
:::

::: {.ttdef}
**Definition:** any\_ptr.h:68
:::
:::

::: {#aclasstensorflow_1_1serving_1_1AnyPtr_html_a357cf7dcf137a8064c393b486509d218 .ttc}
::: {.ttname}
[tensorflow::serving::AnyPtr::get](classtensorflow_1_1serving_1_1AnyPtr.html#a357cf7dcf137a8064c393b486509d218)
:::

::: {.ttdeci}
T \* get() const
:::

::: {.ttdoc}
Accessor for the underlying pointer if it is of type T, otherwise null.
:::

::: {.ttdef}
**Definition:** any\_ptr.h:85
:::
:::

::: {#aclasstensorflow_1_1serving_1_1AnyPtr_html_a90f5c7399a7ae6d4847d9f86669fcab7 .ttc}
::: {.ttname}
[tensorflow::serving::AnyPtr::AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html#a90f5c7399a7ae6d4847d9f86669fcab7)
:::

::: {.ttdeci}
AnyPtr(T \*ptr)
:::

::: {.ttdoc}
Construct from a pointer to any type.
:::

::: {.ttdef}
**Definition:** any\_ptr.h:75
:::
:::

::: {#aclasstensorflow_1_1serving_1_1AnyPtr_html_a9e716e1e923c2094e4e88e83d9800595 .ttc}
::: {.ttname}
[tensorflow::serving::AnyPtr::AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html#a9e716e1e923c2094e4e88e83d9800595)
:::

::: {.ttdeci}
AnyPtr(std::nullptr\_t)
:::

::: {.ttdoc}
Implicit construction from nullptr.
:::

::: {.ttdef}
**Definition:** any\_ptr.h:71
:::
:::

::: {#aclasstensorflow_1_1serving_1_1UniqueAnyPtr_html .ttc}
::: {.ttname}
[tensorflow::serving::UniqueAnyPtr](classtensorflow_1_1serving_1_1UniqueAnyPtr.html)
:::

::: {.ttdef}
**Definition:** any\_ptr.h:109
:::
:::

::: {#aclasstensorflow_1_1serving_1_1UniqueAnyPtr_html_a2289c5328e883bc22bd79fc7b7262244 .ttc}
::: {.ttname}
[tensorflow::serving::UniqueAnyPtr::UniqueAnyPtr](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#a2289c5328e883bc22bd79fc7b7262244)
:::

::: {.ttdeci}
UniqueAnyPtr()=default
:::

::: {.ttdoc}
UniqueAnyPtr is void and null by default.
:::
:::

::: {#aclasstensorflow_1_1serving_1_1UniqueAnyPtr_html_a5b06edf7f9381bbae5a1fbc903d0e2f0 .ttc}
::: {.ttname}
[tensorflow::serving::UniqueAnyPtr::as\_any\_ptr](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#a5b06edf7f9381bbae5a1fbc903d0e2f0)
:::

::: {.ttdeci}
const AnyPtr & as\_any\_ptr() const
:::

::: {.ttdoc}
Accessor for the underlying pointer as an AnyPtr.
:::

::: {.ttdef}
**Definition:** any\_ptr.h:141
:::
:::

::: {#aclasstensorflow_1_1serving_1_1UniqueAnyPtr_html_acb57a78f3357bd37e85a25ca707d692b .ttc}
::: {.ttname}
[tensorflow::serving::UniqueAnyPtr::get](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#acb57a78f3357bd37e85a25ca707d692b)
:::

::: {.ttdeci}
T \* get() const
:::

::: {.ttdoc}
Accessor for the underlying pointer if it is of type T, otherwise null.
:::

::: {.ttdef}
**Definition:** any\_ptr.h:136
:::
:::

::: {#aclasstensorflow_1_1serving_1_1UniqueAnyPtr_html_ae33840e17d58e1e45a77306e8c0312a5 .ttc}
::: {.ttname}
[tensorflow::serving::UniqueAnyPtr::UniqueAnyPtr](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#ae33840e17d58e1e45a77306e8c0312a5)
:::

::: {.ttdeci}
UniqueAnyPtr(std::unique\_ptr\< T \> ptr)
:::

::: {.ttdoc}
Construct from a unique pointer to any type.
:::

::: {.ttdef}
**Definition:** any\_ptr.h:117
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

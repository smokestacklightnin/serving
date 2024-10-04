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
servable\_handle.h
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
TENSORFLOW\_SERVING\_CORE\_SERVABLE\_HANDLE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_SERVABLE\_HANDLE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<algorithm\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<cstddef\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<type\_traits\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} 
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow\_serving/core/loader.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/util/any\_ptr.h\"]{.preprocessor}
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
[]{#l00035}[
[35](classtensorflow_1_1serving_1_1UntypedServableHandle.html){.line}]{.lineno} [class
]{.keyword}[UntypedServableHandle](classtensorflow_1_1serving_1_1UntypedServableHandle.html){.code}
{
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [virtual]{.keyword}
\~[UntypedServableHandle](classtensorflow_1_1serving_1_1UntypedServableHandle.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [virtual]{.keyword} [const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
id() [const]{.keyword} = 0;
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [virtual]{.keyword}
[AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html){.code} servable() =
0;
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} };
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} 
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00075}[
[75](classtensorflow_1_1serving_1_1ServableHandle.html){.line}]{.lineno} [class
]{.keyword}[ServableHandle](classtensorflow_1_1serving_1_1ServableHandle.html){.code}
{
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  static\_assert(!std::is\_pointer\<T\>::value,
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [\"Servables are implicitly passed as
pointers, please use T \"]{.stringliteral}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  [\"instead of T\*.\"]{.stringliteral});
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} 
:::

::: {.line}
[]{#l00082}[
[82](classtensorflow_1_1serving_1_1ServableHandle.html#afa693e4f7cf135262c7f0babfc4d42ec){.line}]{.lineno} 
[ServableHandle](classtensorflow_1_1serving_1_1ServableHandle.html#afa693e4f7cf135262c7f0babfc4d42ec){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} 
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
id()[ const ]{.keyword}{ [return]{.keywordflow}
untyped\_handle\_-\>id(); }
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} 
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  [// Smart pointer operations.]{.comment}
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} 
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  T& operator\*()[ const ]{.keyword}{
[return]{.keywordflow} \*get(); }
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} 
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  T\* operator-\>()[ const ]{.keyword}{
[return]{.keywordflow} get(); }
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} 
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  T\* get()[ const ]{.keyword}{
[return]{.keywordflow} servable\_; }
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} 
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  [operator]{.keyword} bool()[ const
]{.keyword}{ [return]{.keywordflow} get() != [nullptr]{.keyword}; }
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} 
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  [// See the end of this file for comparison
operators, which must be declared]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  [// at namespace scope to support
left-hand-side arguments of different types.]{.comment}
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} 
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  [friend]{.keyword} [class
]{.keyword}Manager;
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} 
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [explicit]{.keyword}
[ServableHandle](classtensorflow_1_1serving_1_1ServableHandle.html#afa693e4f7cf135262c7f0babfc4d42ec){.code}(std::unique\_ptr\<UntypedServableHandle\>
untyped\_handle)
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  :
untyped\_handle\_(std::move(untyped\_handle)),
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  servable\_(untyped\_handle\_ == nullptr
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  ? nullptr
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  : untyped\_handle\_-\>servable().get\<T\>())
{}
:::

::: {.line}
[]{#l00107}[ 107]{.lineno} 
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  std::unique\_ptr\<UntypedServableHandle\>
untyped\_handle\_;
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  T\* servable\_ = [nullptr]{.keyword};
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} };
:::

::: {.line}
[]{#l00111}[ 111]{.lineno} 
:::

::: {.line}
[]{#l00114}[
[114](classtensorflow_1_1serving_1_1SharedPtrHandle.html){.line}]{.lineno} [class
]{.keyword}[SharedPtrHandle](classtensorflow_1_1serving_1_1SharedPtrHandle.html){.code}
final : [public]{.keyword}
[UntypedServableHandle](classtensorflow_1_1serving_1_1UntypedServableHandle.html){.code}
{
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00116}[ 116]{.lineno} 
\~[SharedPtrHandle](classtensorflow_1_1serving_1_1SharedPtrHandle.html){.code}()
[override]{.keyword} = [default]{.keywordflow};
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} 
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  [explicit]{.keyword}
[SharedPtrHandle](classtensorflow_1_1serving_1_1SharedPtrHandle.html){.code}([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
[id]{.keywordtype}, std::shared\_ptr\<Loader\> loader)
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  : id\_([id]{.keywordtype}),
loader\_(std::move(loader)) {}
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} 
:::

::: {.line}
[]{#l00121}[ 121]{.lineno} 
[AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html){.code} servable()[
override ]{.keyword}{ [return]{.keywordflow} loader\_-\>servable(); }
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} 
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  [const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
id()[ const override ]{.keyword}{ [return]{.keywordflow} id\_; }
:::

::: {.line}
[]{#l00124}[ 124]{.lineno} 
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00126}[ 126]{.lineno}  [const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}
id\_;
:::

::: {.line}
[]{#l00127}[ 127]{.lineno}  std::shared\_ptr\<Loader\> loader\_;
:::

::: {.line}
[]{#l00128}[ 128]{.lineno} };
:::

::: {.line}
[]{#l00129}[ 129]{.lineno} 
:::

::: {.line}
[]{#l00130}[ 130]{.lineno} [// We compare handles using both the
servable pointer and the id. So if you]{.comment}
:::

::: {.line}
[]{#l00131}[ 131]{.lineno} [// share the same pointer amongst different
versions, the handles won\'t be]{.comment}
:::

::: {.line}
[]{#l00132}[ 132]{.lineno} [// equal.]{.comment}
:::

::: {.line}
[]{#l00133}[ 133]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T, [typename]{.keyword} U\>
:::

::: {.line}
[]{#l00134}[ 134]{.lineno} constexpr [bool]{.keywordtype}
operator==([const]{.keyword}
[ServableHandle\<T\>](classtensorflow_1_1serving_1_1ServableHandle.html){.code}&
l,
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  [const]{.keyword}
[ServableHandle\<U\>](classtensorflow_1_1serving_1_1ServableHandle.html){.code}&
r) {
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  [return]{.keywordflow} l.get() == r.get() &&
l.id() == r.id();
:::

::: {.line}
[]{#l00137}[ 137]{.lineno} }
:::

::: {.line}
[]{#l00138}[ 138]{.lineno} 
:::

::: {.line}
[]{#l00139}[ 139]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T, [typename]{.keyword} U\>
:::

::: {.line}
[]{#l00140}[ 140]{.lineno} constexpr [bool]{.keywordtype}
operator!=([const]{.keyword} ServableHandle\<T\>& l,
:::

::: {.line}
[]{#l00141}[ 141]{.lineno}  [const]{.keyword} ServableHandle\<U\>& r) {
:::

::: {.line}
[]{#l00142}[ 142]{.lineno}  [return]{.keywordflow} !(l == r);
:::

::: {.line}
[]{#l00143}[ 143]{.lineno} }
:::

::: {.line}
[]{#l00144}[ 144]{.lineno} 
:::

::: {.line}
[]{#l00145}[ 145]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00146}[ 146]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00147}[ 147]{.lineno} 
:::

::: {.line}
[]{#l00148}[ 148]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_SERVABLE\_HANDLE\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1AnyPtr_html .ttc}
::: {.ttname}
[tensorflow::serving::AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html)
:::

::: {.ttdef}
**Definition:** any\_ptr.h:65
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

::: {#aclasstensorflow_1_1serving_1_1ServableHandle_html_afa693e4f7cf135262c7f0babfc4d42ec .ttc}
::: {.ttname}
[tensorflow::serving::ServableHandle::ServableHandle](classtensorflow_1_1serving_1_1ServableHandle.html#afa693e4f7cf135262c7f0babfc4d42ec)
:::

::: {.ttdeci}
ServableHandle()=default
:::

::: {.ttdoc}
ServableHandle is null by default.
:::
:::

::: {#aclasstensorflow_1_1serving_1_1SharedPtrHandle_html .ttc}
::: {.ttname}
[tensorflow::serving::SharedPtrHandle](classtensorflow_1_1serving_1_1SharedPtrHandle.html)
:::

::: {.ttdef}
**Definition:** servable\_handle.h:114
:::
:::

::: {#aclasstensorflow_1_1serving_1_1UntypedServableHandle_html .ttc}
::: {.ttname}
[tensorflow::serving::UntypedServableHandle](classtensorflow_1_1serving_1_1UntypedServableHandle.html)
:::

::: {.ttdef}
**Definition:** servable\_handle.h:35
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

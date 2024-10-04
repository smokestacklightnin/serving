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
-   [test\_util](dir_306b000a767a3d8d2b2841959aa6b5f0.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
servable\_handle\_test\_util.h
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
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_SERVABLE\_HANDLE\_TEST\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_SERVABLE\_HANDLE\_TEST\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include
\"tensorflow\_serving/core/manager.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_handle.h\"]{.preprocessor}
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
[]{#l00026}[ 26]{.lineno} [namespace ]{.keyword}test\_util {
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} 
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [// Wraps a pointer as a servable.]{.comment}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [// The ownership of \@p t is \*not\*
transferred to this function; t must outlive]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [// the returned ServableHandle.]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// Does a bit of type-gymnastics since
ServableHandles can only be constructed]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// by Managers.]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [static]{.keyword} ServableHandle\<T\>
WrapAsHandle([const]{.keyword} ServableId& [id]{.keywordtype}, T\* t) {
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [// A basic Handle that wraps a ServableId
and a pointer to a servable.]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [// Exactly the same objects that are used to
construct the DummyHandle are]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [// returned when the appropriate getter
functions are invoked.]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [class ]{.keyword}DummyHandle :
[public]{.keyword} UntypedServableHandle {
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [explicit]{.keyword}
DummyHandle([const]{.keyword} ServableId& [id]{.keywordtype}, T\*
servable)
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  : id\_(id), servable\_(servable) {}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  AnyPtr servable()[ override ]{.keyword}{
[return]{.keywordflow} servable\_; }
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [const]{.keyword} ServableId& id()[ const
override ]{.keyword}{ [return]{.keywordflow} id\_; }
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [const]{.keyword} ServableId id\_;
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  T\* servable\_;
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  };
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} 
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [// A Manager that always returns the same
servable when]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [// GetUntypedServableHandle is
invoked.]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [class ]{.keyword}DummyManager :
[public]{.keyword} Manager {
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [explicit]{.keyword}
DummyManager([const]{.keyword} ServableId& [id]{.keywordtype}, T\*
servable)
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  : id\_(id), servable\_(servable) {}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} 
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [// Resets the UntypedServableHandle to a new
DummyHandle that wraps the]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [// Servable and ServableId which this
DummyManager was created with.]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [// Always returns OK status.]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  Status GetUntypedServableHandle(
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [const]{.keyword} ServableRequest& request,
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  std::unique\_ptr\<UntypedServableHandle\>\*
result)[ override ]{.keyword}{
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  result-\>reset([new]{.keyword}
DummyHandle(id\_, servable\_));
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  }
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} 
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [// Unimplemented: always returns an empty
map.]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  std::map\<ServableId,
std::unique\_ptr\<UntypedServableHandle\>\>
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  GetAvailableUntypedServableHandles()[ const
override ]{.keyword}{
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [return]{.keywordflow} {};
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  }
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} 
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  [// Unimplemented: always returns an empty
vector.]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  std::vector\<ServableId\>
ListAvailableServableIds()[ const override ]{.keyword}{
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  [return]{.keywordflow} {};
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  }
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} 
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  [const]{.keyword} ServableId id\_;
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  T\* servable\_;
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  };
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} 
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  DummyManager manager{id, t};
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  ServableHandle\<T\> handle;
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} 
TF\_CHECK\_OK(manager.GetServableHandle({[\"Dummy\"]{.stringliteral},
0}, &handle));
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [return]{.keywordflow} handle;
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} }
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} 
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} } [// namespace test\_util]{.comment}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} 
:::

::: {.line}
[]{#l00099}[ 99]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_SERVABLE\_HANDLE\_TEST\_UTIL\_H\_]{.comment}
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

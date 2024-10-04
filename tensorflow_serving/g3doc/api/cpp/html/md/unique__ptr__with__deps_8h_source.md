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
unique\_ptr\_with\_deps.h
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
[]{#l00016}[ 16]{.lineno} [// A Unique Ptr like class that manages the
lifecycle of any dependencies in]{.comment}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [// addition to the primary owned
object.]{.comment}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [// This enables the use-case of returning
ownership of an object to some client]{.comment}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [// code without giving the client access to
the dependencies, and automatically]{.comment}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [// handling destruction upon destruction of
the primary owned object.]{.comment}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_UTIL\_UNIQUE\_PTR\_WITH\_DEPS\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#define
TENSORFLOW\_SERVING\_UTIL\_UNIQUE\_PTR\_WITH\_DEPS\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} 
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include \<algorithm\>]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} 
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow/core/platform/types.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include
\"tensorflow\_serving/util/any\_ptr.h\"]{.preprocessor}
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
[]{#l00036}[ 36]{.lineno} [// Holds an object with its dependencies. On
destruction deletes the main]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [// object and all dependencies, in the order
inverse to the order of]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [// AddDependency/SetOwned calls.]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [template]{.keyword}\<[typename]{.keyword} T\>
:::

::: {.line}
[]{#l00040}[
[40](classtensorflow_1_1serving_1_1UniquePtrWithDeps.html){.line}]{.lineno} [class
]{.keyword}[UniquePtrWithDeps](classtensorflow_1_1serving_1_1UniquePtrWithDeps.html){.code}
{
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
[UniquePtrWithDeps](classtensorflow_1_1serving_1_1UniquePtrWithDeps.html){.code}()
{}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [explicit]{.keyword}
[UniquePtrWithDeps](classtensorflow_1_1serving_1_1UniquePtrWithDeps.html){.code}(std::unique\_ptr\<T\>
[object]{.keywordtype}) {
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  SetOwned(std::move([object]{.keywordtype}));
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  }
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [explicit]{.keyword}
[UniquePtrWithDeps](classtensorflow_1_1serving_1_1UniquePtrWithDeps.html){.code}(T\*
owned\_object) { SetOwnedPtr(owned\_object); }
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
[UniquePtrWithDeps](classtensorflow_1_1serving_1_1UniquePtrWithDeps.html){.code}([UniquePtrWithDeps](classtensorflow_1_1serving_1_1UniquePtrWithDeps.html){.code}&&
other) = [default]{.keywordflow};
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} 
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
\~[UniquePtrWithDeps](classtensorflow_1_1serving_1_1UniquePtrWithDeps.html){.code}()
{
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [// Delete all dependencies, starting with
the one added last. Order of]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [// destructing elements in vector/list is
unspecified. The ownership of the]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [// main object is kept as one of the
dependencies.]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [while]{.keywordflow} (!deleters\_.empty()) {
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  deleters\_.pop\_back();
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  }
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  }
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} 
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
X\>
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  X\* AddDependency(std::unique\_ptr\<X\>
dependency) {
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  X\* raw = dependency.get();
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} 
deleters\_.emplace\_back(std::move(dependency));
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [return]{.keywordflow} raw;
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  }
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [void]{.keywordtype}
SetOwned(std::unique\_ptr\<T\> [object]{.keywordtype}) {
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  object\_ =
AddDependency\<T\>(std::move([object]{.keywordtype}));
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  }
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [void]{.keywordtype} SetOwnedPtr(T\*
owned\_object) {
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
SetOwned(std::unique\_ptr\<T\>(owned\_object));
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  }
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} 
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  T\* get()[ const ]{.keyword}{
[return]{.keywordflow} object\_; }
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [const]{.keyword} T& operator\*()[ const
]{.keyword}{ [return]{.keywordflow} \*object\_; }
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  T\* operator-\>()[ const ]{.keyword}{
[return]{.keywordflow} get(); }
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} 
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  std::vector\<UniqueAnyPtr\> deleters\_;
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  T\* object\_ = [nullptr]{.keyword};
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} };
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} 
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} 
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_UTIL\_UNIQUE\_PTR\_WITH\_DEPS\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1UniquePtrWithDeps_html .ttc}
::: {.ttname}
[tensorflow::serving::UniquePtrWithDeps](classtensorflow_1_1serving_1_1UniquePtrWithDeps.html)
:::

::: {.ttdef}
**Definition:** unique\_ptr\_with\_deps.h:40
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

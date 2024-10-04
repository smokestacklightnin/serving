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
manager\_wrapper.h
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
TENSORFLOW\_SERVING\_CORE\_MANAGER\_WRAPPER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_MANAGER\_WRAPPER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<map\>]{.preprocessor}
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
\"tensorflow\_serving/core/manager.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_id.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/util/unique\_ptr\_with\_deps.h\"]{.preprocessor}
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
[]{#l00030}[ 30]{.lineno} [// An implementation of Manager that
delegates all calls to another Manager.]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// May be useful to override just part of the
functionality of another Manager]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// or storing a Manager with its
dependencies.]{.comment}
:::

::: {.line}
[]{#l00034}[
[34](classtensorflow_1_1serving_1_1ManagerWrapper.html){.line}]{.lineno} [class
]{.keyword}[ManagerWrapper](classtensorflow_1_1serving_1_1ManagerWrapper.html){.code}
: [public]{.keyword}
[Manager](classtensorflow_1_1serving_1_1Manager.html){.code} {
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  [explicit]{.keyword}
[ManagerWrapper](classtensorflow_1_1serving_1_1ManagerWrapper.html){.code}([UniquePtrWithDeps\<Manager\>](classtensorflow_1_1serving_1_1UniquePtrWithDeps.html){.code}
wrapped);
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} 
\~[ManagerWrapper](classtensorflow_1_1serving_1_1ManagerWrapper.html){.code}()
[override]{.keyword} = [default]{.keywordflow};
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  std::vector\<ServableId\>
[ListAvailableServableIds](classtensorflow_1_1serving_1_1ManagerWrapper.html#a76a6e899de4dfca374b71c4ef415b3d0){.code}()
[const override]{.keyword};
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  Status GetUntypedServableHandle(
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [const]{.keyword}
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.code}&
request,
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  std::unique\_ptr\<UntypedServableHandle\>\*
untyped\_handle) [override]{.keyword};
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  std::map\<ServableId,
std::unique\_ptr\<UntypedServableHandle\>\>
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  GetAvailableUntypedServableHandles() [const
override]{.keyword};
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} 
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [const]{.keyword}
[UniquePtrWithDeps\<Manager\>](classtensorflow_1_1serving_1_1UniquePtrWithDeps.html){.code}
wrapped\_;
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} };
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} 
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_MANAGER\_WRAPPER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1ManagerWrapper_html .ttc}
::: {.ttname}
[tensorflow::serving::ManagerWrapper](classtensorflow_1_1serving_1_1ManagerWrapper.html)
:::

::: {.ttdef}
**Definition:** manager\_wrapper.h:34
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ManagerWrapper_html_a76a6e899de4dfca374b71c4ef415b3d0 .ttc}
::: {.ttname}
[tensorflow::serving::ManagerWrapper::ListAvailableServableIds](classtensorflow_1_1serving_1_1ManagerWrapper.html#a76a6e899de4dfca374b71c4ef415b3d0)
:::

::: {.ttdeci}
std::vector\< ServableId \> ListAvailableServableIds() const override
:::

::: {.ttdef}
**Definition:** manager\_wrapper.cc:29
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

::: {#aclasstensorflow_1_1serving_1_1UniquePtrWithDeps_html .ttc}
::: {.ttname}
[tensorflow::serving::UniquePtrWithDeps](classtensorflow_1_1serving_1_1UniquePtrWithDeps.html)
:::

::: {.ttdef}
**Definition:** unique\_ptr\_with\_deps.h:40
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

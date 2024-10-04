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
static\_manager.h
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
TENSORFLOW\_SERVING\_CORE\_STATIC\_MANAGER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_STATIC\_MANAGER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow/core/lib/core/errors.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow\_serving/core/basic\_manager.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow\_serving/core/manager.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_handle.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_id.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/core/simple\_loader.h\"]{.preprocessor}
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
[]{#l00031}[ 31]{.lineno} [// Builds a manager that holds a static set
of servables. The result is]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// immutable, and cannot be modified after
construction.]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// Typical callers will call AddServable()
for each desired servable, and then]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [// call Build() to produce a
Manager.]{.comment}
:::

::: {.line}
[]{#l00036}[
[36](classtensorflow_1_1serving_1_1StaticManagerBuilder.html){.line}]{.lineno} [class
]{.keyword}[StaticManagerBuilder](classtensorflow_1_1serving_1_1StaticManagerBuilder.html){.code}
{
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
[StaticManagerBuilder](classtensorflow_1_1serving_1_1StaticManagerBuilder.html){.code}();
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} 
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [// Adds a servable to the manager. Duplicate
IDs and null servables will fail]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [// to be added and return a failure
status.]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  Status AddServable([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
[id]{.keywordtype}, std::unique\_ptr\<T\> servable);
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [// Builds the manager. This builder should
not be reused after this.]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  std::unique\_ptr\<Manager\> Build();
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [// The manager we are building.]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  std::unique\_ptr\<BasicManager\>
basic\_manager\_;
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [// The health of the builder.]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  Status health\_;
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} };
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} 
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} [// Implementation details follow. Clients can
stop reading.]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} 
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} Status
StaticManagerBuilder::AddServable([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
[id]{.keywordtype},
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  std::unique\_ptr\<T\> servable) {
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [if]{.keywordflow} (servable ==
[nullptr]{.keyword}) {
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  [return]{.keywordflow}
errors::InvalidArgument([\"Servable cannot be null.\"]{.stringliteral});
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  }
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  TF\_RETURN\_IF\_ERROR(health\_);
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  DCHECK(basic\_manager\_ !=
[nullptr]{.keyword});
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} 
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
TF\_RETURN\_IF\_ERROR(basic\_manager\_-\>ManageServable(CreateServableData(
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [id]{.keywordtype},
std::unique\_ptr\<Loader\>([new]{.keyword} SimpleLoader\<T\>(
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  \[&servable\](std::unique\_ptr\<T\>\*
[const]{.keyword} returned\_servable) {
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  \*returned\_servable = std::move(servable);
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  },
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} 
SimpleLoader\<T\>::EstimateNoResources())))));
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  Status load\_status;
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  Notification load\_done;
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} 
basic\_manager\_-\>LoadServable([id]{.keywordtype},
\[&\]([const]{.keyword} Status& status) {
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  load\_status = status;
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  load\_done.Notify();
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  });
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  load\_done.WaitForNotification();
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  [return]{.keywordflow} load\_status;
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} }
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} 
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} 
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_STATIC\_MANAGER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1StaticManagerBuilder_html .ttc}
::: {.ttname}
[tensorflow::serving::StaticManagerBuilder](classtensorflow_1_1serving_1_1StaticManagerBuilder.html)
:::

::: {.ttdef}
**Definition:** static\_manager.h:36
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

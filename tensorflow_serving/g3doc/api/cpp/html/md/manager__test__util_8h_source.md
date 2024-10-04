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
manager\_test\_util.h
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
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_MANAGER\_TEST\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_MANAGER\_TEST\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include
\"tensorflow\_serving/core/aspired\_versions\_manager.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include
\"tensorflow\_serving/core/caching\_manager.h\"]{.preprocessor}
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
[]{#l00024}[ 24]{.lineno} [namespace ]{.keyword}test\_util {
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} 
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [// A test utility that provides access to
private AspiredVersionsManager]{.comment}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [// members.]{.comment}
:::

::: {.line}
[]{#l00028}[
[28](classtensorflow_1_1serving_1_1test__util_1_1AspiredVersionsManagerTestAccess.html){.line}]{.lineno} [class
]{.keyword}[AspiredVersionsManagerTestAccess](classtensorflow_1_1serving_1_1test__util_1_1AspiredVersionsManagerTestAccess.html){.code}
{
:::

::: {.line}
[]{#l00029}[ 29]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00030}[ 30]{.lineno}  [explicit]{.keyword}
[AspiredVersionsManagerTestAccess](classtensorflow_1_1serving_1_1test__util_1_1AspiredVersionsManagerTestAccess.html){.code}([AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.code}\*
manager);
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} 
:::

::: {.line}
[]{#l00032}[ 32]{.lineno}  [// Invokes FlushServables() on the
manager.]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno}  [void]{.keywordtype} FlushServables();
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} 
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  [// Invokes
HandlePendingAspiredVersionsRequests() on the manager.]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  [void]{.keywordtype}
HandlePendingAspiredVersionsRequests();
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} 
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  [// Invokes InvokePolicyAndExecuteAction() on
the manager.]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [void]{.keywordtype}
InvokePolicyAndExecuteAction();
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [void]{.keywordtype} SetNumLoadThreads(uint32
num\_load\_threads);
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  uint32 num\_load\_threads()
[const]{.keyword};
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [void]{.keywordtype} SetCustomSortActions(
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  AspiredVersionsManager::CustomSortActionsFn
custom\_sort\_actions);
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
[AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.code}\*
[const]{.keyword} manager\_;
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} 
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([AspiredVersionsManagerTestAccess](classtensorflow_1_1serving_1_1test__util_1_1AspiredVersionsManagerTestAccess.html){.code});
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} };
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} 
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [// A test utility that provides access to
private BasicManager members.]{.comment}
:::

::: {.line}
[]{#l00055}[
[55](classtensorflow_1_1serving_1_1test__util_1_1BasicManagerTestAccess.html){.line}]{.lineno} [class
]{.keyword}[BasicManagerTestAccess](classtensorflow_1_1serving_1_1test__util_1_1BasicManagerTestAccess.html){.code}
{
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [explicit]{.keyword}
[BasicManagerTestAccess](classtensorflow_1_1serving_1_1test__util_1_1BasicManagerTestAccess.html){.code}([BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.code}\*
manager);
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} 
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [void]{.keywordtype} SetNumLoadThreads(uint32
num\_load\_threads);
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  uint32 num\_load\_threads()
[const]{.keyword};
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} 
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
[BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.code}\*
[const]{.keyword} manager\_;
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} 
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([BasicManagerTestAccess](classtensorflow_1_1serving_1_1test__util_1_1BasicManagerTestAccess.html){.code});
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} };
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} 
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} [// A test utility that provides access to
private CachingManager members.]{.comment}
:::

::: {.line}
[]{#l00070}[
[70](classtensorflow_1_1serving_1_1test__util_1_1CachingManagerTestAccess.html){.line}]{.lineno} [class
]{.keyword}[CachingManagerTestAccess](classtensorflow_1_1serving_1_1test__util_1_1CachingManagerTestAccess.html){.code}
{
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [explicit]{.keyword}
[CachingManagerTestAccess](classtensorflow_1_1serving_1_1test__util_1_1CachingManagerTestAccess.html){.code}([CachingManager](classtensorflow_1_1serving_1_1CachingManager.html){.code}\*
manager);
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} 
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  [// Returns the size of the load-mutex map
that stores the mutex reference per]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [// servable-id requested for
load.]{.comment}
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  int64\_t GetLoadMutexMapSize()
[const]{.keyword};
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} 
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} 
[CachingManager](classtensorflow_1_1serving_1_1CachingManager.html){.code}\*
[const]{.keyword} manager\_;
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} 
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([CachingManagerTestAccess](classtensorflow_1_1serving_1_1test__util_1_1CachingManagerTestAccess.html){.code});
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} };
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} 
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} } [// namespace test\_util]{.comment}
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} 
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_MANAGER\_TEST\_UTIL\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1AspiredVersionsManager_html .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html)
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager.h:86
:::
:::

::: {#aclasstensorflow_1_1serving_1_1BasicManager_html .ttc}
::: {.ttname}
[tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html)
:::

::: {.ttdef}
**Definition:** basic\_manager.h:106
:::
:::

::: {#aclasstensorflow_1_1serving_1_1CachingManager_html .ttc}
::: {.ttname}
[tensorflow::serving::CachingManager](classtensorflow_1_1serving_1_1CachingManager.html)
:::

::: {.ttdef}
**Definition:** caching\_manager.h:45
:::
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1AspiredVersionsManagerTestAccess_html .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::AspiredVersionsManagerTestAccess](classtensorflow_1_1serving_1_1test__util_1_1AspiredVersionsManagerTestAccess.html)
:::

::: {.ttdef}
**Definition:** manager\_test\_util.h:28
:::
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1BasicManagerTestAccess_html .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::BasicManagerTestAccess](classtensorflow_1_1serving_1_1test__util_1_1BasicManagerTestAccess.html)
:::

::: {.ttdef}
**Definition:** manager\_test\_util.h:55
:::
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1CachingManagerTestAccess_html .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::CachingManagerTestAccess](classtensorflow_1_1serving_1_1test__util_1_1CachingManagerTestAccess.html)
:::

::: {.ttdef}
**Definition:** manager\_test\_util.h:70
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

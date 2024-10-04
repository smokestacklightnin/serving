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
-   [session\_bundle](dir_545072a0b62e8d32e4be92843450628a.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
graph\_rewriter.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2019 Google Inc. All Rights
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
TENSORFLOW\_SERVING\_SESSION\_BUNDLE\_GRAPH\_REWRITER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SESSION\_BUNDLE\_GRAPH\_REWRITER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<functional\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<utility\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} 
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"absl/base/thread\_annotations.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"absl/synchronization/mutex.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow/core/platform/errors.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/platform/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/protobuf/meta\_graph.pb.h\"]{.preprocessor}
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
[]{#l00031}[ 31]{.lineno} [// Class for registering a global graph
rewrite function.]{.comment}
:::

::: {.line}
[]{#l00032}[
[32](classtensorflow_1_1serving_1_1GraphRewriter.html){.line}]{.lineno} [class
]{.keyword}[GraphRewriter](classtensorflow_1_1serving_1_1GraphRewriter.html){.code}
{
:::

::: {.line}
[]{#l00033}[ 33]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  [static]{.keyword}
[GraphRewriter](classtensorflow_1_1serving_1_1GraphRewriter.html){.code}&
GetGlobal() {
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  [static]{.keyword} [auto]{.keyword}\*
[const]{.keyword} singleton = [new]{.keyword}
[GraphRewriter](classtensorflow_1_1serving_1_1GraphRewriter.html){.code}();
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  [return]{.keywordflow} \*singleton;
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  }
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  Status
Set(std::function\<Status(tensorflow::MetaGraphDef\*)\>&& rewriter) {
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  absl::MutexLock l(&m\_);
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [if]{.keywordflow} (rewriter\_ !=
[nullptr]{.keyword})
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [return]{.keywordflow}
errors::AlreadyExists([\"Graph rewriter already
set.\"]{.stringliteral});
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} 
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  rewriter\_ = std::move(rewriter);
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  }
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} 
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [// For testing only. Resets the rewriter to
nullptr]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  Status ResetForTesting() {
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  absl::MutexLock l(&m\_);
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  rewriter\_ = [nullptr]{.keyword};
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  }
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} 
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} 
std::function\<Status(tensorflow::MetaGraphDef\*)\>& Get() {
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  absl::MutexLock l(&m\_);
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [return]{.keywordflow} rewriter\_;
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  }
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [bool]{.keywordtype} IsRegistered() {
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  absl::MutexLock l(&m\_);
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [return]{.keywordflow} rewriter\_ !=
[nullptr]{.keyword};
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  }
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} 
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
[GraphRewriter](classtensorflow_1_1serving_1_1GraphRewriter.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} 
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  absl::Mutex m\_;
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} 
std::function\<Status(tensorflow::MetaGraphDef\*)\> rewriter\_
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  ABSL\_GUARDED\_BY(m\_);
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} };
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} 
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} [// EXPERIMENTAL. THE 2 METHODS BELOW MAY
CHANGE OR GO AWAY. USE WITH CAUTION.]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} [// Sets a global graph rewrite function that
is called on all saved models]{.comment}
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} [// immediately after metagraph load, but
before session creation. This function]{.comment}
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} [// can only be called once.]{.comment}
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} [inline]{.keyword} Status SetGraphRewriter(
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} 
std::function\<Status(tensorflow::MetaGraphDef\*)\>&& rewriter) {
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [return]{.keywordflow}
GraphRewriter::GetGlobal().Set(std::move(rewriter));
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} }
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} 
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} [// For testing only. Resets the experimental
graph rewriter above.]{.comment}
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} [inline]{.keyword} Status
ResetGraphRewriterForTesting() {
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  [return]{.keywordflow}
GraphRewriter::GetGlobal().ResetForTesting();
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} }
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} 
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} 
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SESSION\_BUNDLE\_GRAPH\_REWRITER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1GraphRewriter_html .ttc}
::: {.ttname}
[tensorflow::serving::GraphRewriter](classtensorflow_1_1serving_1_1GraphRewriter.html)
:::

::: {.ttdef}
**Definition:** graph\_rewriter.h:32
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

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
-   [servables](dir_e240d895a087fc4ce46e8f4c52318018.html){.el}
-   [tensorflow](dir_143c99ffaf6c8b3b63b06c22e49d7998.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
tfrt\_saved\_model\_source\_adapter.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2020 Google Inc. All Rights
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
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_TFRT\_SAVED\_MODEL\_SOURCE\_ADAPTER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_TFRT\_SAVED\_MODEL\_SOURCE\_ADAPTER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include
\"tensorflow/cc/saved\_model/loader.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow\_serving/core/simple\_loader.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow\_serving/core/source\_adapter.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow\_serving/core/storage\_path.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/tfrt\_saved\_model\_factory.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/tfrt\_saved\_model\_source\_adapter.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/tfrt\_servable.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} 
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} 
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// A SourceAdapter that creates
TfrtSavedModelServable Loaders from SavedModel]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// paths. It keeps a TfrtSavedModelFactory as
its state, which may house a batch]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// scheduler that is shared across all of the
SavedModel it emits.]{.comment}
:::

::: {.line}
[]{#l00035}[
[35](classtensorflow_1_1serving_1_1TfrtSavedModelSourceAdapter.html){.line}]{.lineno} [class
]{.keyword}[TfrtSavedModelSourceAdapter](classtensorflow_1_1serving_1_1TfrtSavedModelSourceAdapter.html){.code}
final
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  : [public]{.keyword}
[UnarySourceAdapter](classtensorflow_1_1serving_1_1UnarySourceAdapter.html){.code}\<StoragePath,
std::unique\_ptr\<Loader\>\> {
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  [static]{.keyword} Status
Create([const]{.keyword} TfrtSavedModelSourceAdapterConfig& config,
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} 
std::unique\_ptr\<TfrtSavedModelSourceAdapter\>\* adapter);
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} 
\~[TfrtSavedModelSourceAdapter](classtensorflow_1_1serving_1_1TfrtSavedModelSourceAdapter.html){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [friend]{.keyword} [class
]{.keyword}[TfrtSavedModelSourceAdapterCreator](classtensorflow_1_1serving_1_1TfrtSavedModelSourceAdapterCreator.html){.code};
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [explicit]{.keyword}
[TfrtSavedModelSourceAdapter](classtensorflow_1_1serving_1_1TfrtSavedModelSourceAdapter.html){.code}(
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  std::unique\_ptr\<TfrtSavedModelFactory\>
factory);
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} 
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  SimpleLoader\<Servable\>::CreatorVariant
GetServableCreator(
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  std::shared\_ptr\<TfrtSavedModelFactory\>
factory,
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [const]{.keyword} StoragePath& path)
[const]{.keyword};
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} 
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  Status Convert([const]{.keyword} StoragePath&
path,
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  std::unique\_ptr\<Loader\>\* loader)
[override]{.keyword};
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} 
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [// We use a shared ptr to share ownership
with Loaders we emit, in case they]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [// outlive this object.]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  std::shared\_ptr\<TfrtSavedModelFactory\>
factory\_;
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} 
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([TfrtSavedModelSourceAdapter](classtensorflow_1_1serving_1_1TfrtSavedModelSourceAdapter.html){.code});
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} };
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} 
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} 
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_TFRT\_SAVED\_MODEL\_SOURCE\_ADAPTER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1TfrtSavedModelSourceAdapterCreator_html .ttc}
::: {.ttname}
[tensorflow::serving::TfrtSavedModelSourceAdapterCreator](classtensorflow_1_1serving_1_1TfrtSavedModelSourceAdapterCreator.html)
:::

::: {.ttdef}
**Definition:** tfrt\_saved\_model\_source\_adapter.cc:95
:::
:::

::: {#aclasstensorflow_1_1serving_1_1TfrtSavedModelSourceAdapter_html .ttc}
::: {.ttname}
[tensorflow::serving::TfrtSavedModelSourceAdapter](classtensorflow_1_1serving_1_1TfrtSavedModelSourceAdapter.html)
:::

::: {.ttdef}
**Definition:** tfrt\_saved\_model\_source\_adapter.h:36
:::
:::

::: {#aclasstensorflow_1_1serving_1_1UnarySourceAdapter_html .ttc}
::: {.ttname}
[tensorflow::serving::UnarySourceAdapter](classtensorflow_1_1serving_1_1UnarySourceAdapter.html)
:::

::: {.ttdef}
**Definition:** source\_adapter.h:120
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

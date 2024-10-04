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
saved\_model\_bundle\_factory.h
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
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_SAVED\_MODEL\_BUNDLE\_FACTORY\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_SAVED\_MODEL\_BUNDLE\_FACTORY\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include
\"absl/types/optional.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include
\"tensorflow/cc/saved\_model/loader.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow/core/kernels/batching\_util/shared\_batch\_scheduler.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow\_serving/batching/batching\_session.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/core/loader.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/resources/resources.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/session\_bundle\_config.pb.h\"]{.preprocessor}
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
[]{#l00052}[
[52](classtensorflow_1_1serving_1_1SavedModelBundleFactory.html){.line}]{.lineno} [class
]{.keyword}[SavedModelBundleFactory](classtensorflow_1_1serving_1_1SavedModelBundleFactory.html){.code}
{
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [static]{.keyword} Status
[Create](classtensorflow_1_1serving_1_1SavedModelBundleFactory.html#a234678b40af9995c21a72d265540fdb9){.code}([const]{.keyword}
SessionBundleConfig& config,
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  std::unique\_ptr\<SavedModelBundleFactory\>\*
factory);
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  Status
[CreateSavedModelBundle](classtensorflow_1_1serving_1_1SavedModelBundleFactory.html#aa27eec255c83cd1d2f249a2e4a2d0526){.code}([const]{.keyword}
[string]{.keywordtype}& path,
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  std::unique\_ptr\<SavedModelBundle\>\*
bundle);
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} 
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  Status
[CreateSavedModelBundleWithMetadata](classtensorflow_1_1serving_1_1SavedModelBundleFactory.html#a88da623c02425fe3d01a21e13b956d49){.code}(
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [const]{.keyword}
[Loader::Metadata](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html){.code}&
metadata, [const]{.keyword} [string]{.keywordtype}& path,
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  std::unique\_ptr\<SavedModelBundle\>\*
bundle);
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} 
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  Status
[EstimateResourceRequirement](classtensorflow_1_1serving_1_1SavedModelBundleFactory.html#a4b897842868d8f090ebe972974e03bf7){.code}([const]{.keyword}
[string]{.keywordtype}& path,
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  ResourceAllocation\* estimate)
[const]{.keyword};
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} 
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [const]{.keyword} SessionBundleConfig&
config()[ const ]{.keyword}{ [return]{.keywordflow} config\_; }
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  SessionBundleConfig& mutable\_config() {
[return]{.keywordflow} config\_; }
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} 
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  [using]{.keyword} Batcher =
SharedBatchScheduler\<BatchingSessionTask\>;
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} 
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} 
[SavedModelBundleFactory](classtensorflow_1_1serving_1_1SavedModelBundleFactory.html){.code}([const]{.keyword}
SessionBundleConfig& config,
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  std::shared\_ptr\<Batcher\>
batch\_scheduler);
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} 
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  Status InternalCreateSavedModelBundle(
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  [const]{.keyword}
absl::optional\<Loader::Metadata\>& metadata, [const]{.keyword}
[string]{.keywordtype}& path,
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  std::unique\_ptr\<SavedModelBundle\>\*
bundle);
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} 
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  SessionBundleConfig config\_;
:::

::: {.line}
[]{#l00103}[ 103]{.lineno} 
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  [// A shared batch scheduler. One queue is
used for each session this factory]{.comment}
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  [// emits. If batching is not configured,
this remains null.]{.comment}
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  std::shared\_ptr\<Batcher\>
batch\_scheduler\_;
:::

::: {.line}
[]{#l00107}[ 107]{.lineno} 
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([SavedModelBundleFactory](classtensorflow_1_1serving_1_1SavedModelBundleFactory.html){.code});
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} };
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} 
:::

::: {.line}
[]{#l00111}[ 111]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} 
:::

::: {.line}
[]{#l00114}[ 114]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_SAVED\_MODEL\_BUNDLE\_FACTORY\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1SavedModelBundleFactory_html .ttc}
::: {.ttname}
[tensorflow::serving::SavedModelBundleFactory](classtensorflow_1_1serving_1_1SavedModelBundleFactory.html)
:::

::: {.ttdef}
**Definition:** saved\_model\_bundle\_factory.h:52
:::
:::

::: {#aclasstensorflow_1_1serving_1_1SavedModelBundleFactory_html_a234678b40af9995c21a72d265540fdb9 .ttc}
::: {.ttname}
[tensorflow::serving::SavedModelBundleFactory::Create](classtensorflow_1_1serving_1_1SavedModelBundleFactory.html#a234678b40af9995c21a72d265540fdb9)
:::

::: {.ttdeci}
static Status Create(const SessionBundleConfig &config,
std::unique\_ptr\< SavedModelBundleFactory \> \*factory)
:::

::: {.ttdef}
**Definition:** saved\_model\_bundle\_factory.cc:88
:::
:::

::: {#aclasstensorflow_1_1serving_1_1SavedModelBundleFactory_html_a4b897842868d8f090ebe972974e03bf7 .ttc}
::: {.ttname}
[tensorflow::serving::SavedModelBundleFactory::EstimateResourceRequirement](classtensorflow_1_1serving_1_1SavedModelBundleFactory.html#a4b897842868d8f090ebe972974e03bf7)
:::

::: {.ttdeci}
Status EstimateResourceRequirement(const string &path,
ResourceAllocation \*estimate) const
:::

::: {.ttdef}
**Definition:** saved\_model\_bundle\_factory.cc:100
:::
:::

::: {#aclasstensorflow_1_1serving_1_1SavedModelBundleFactory_html_a88da623c02425fe3d01a21e13b956d49 .ttc}
::: {.ttname}
[tensorflow::serving::SavedModelBundleFactory::CreateSavedModelBundleWithMetadata](classtensorflow_1_1serving_1_1SavedModelBundleFactory.html#a88da623c02425fe3d01a21e13b956d49)
:::

::: {.ttdeci}
Status CreateSavedModelBundleWithMetadata(const Loader::Metadata
&metadata, const string &path, std::unique\_ptr\< SavedModelBundle \>
\*bundle)
:::

::: {.ttdef}
**Definition:** saved\_model\_bundle\_factory.cc:106
:::
:::

::: {#aclasstensorflow_1_1serving_1_1SavedModelBundleFactory_html_aa27eec255c83cd1d2f249a2e4a2d0526 .ttc}
::: {.ttname}
[tensorflow::serving::SavedModelBundleFactory::CreateSavedModelBundle](classtensorflow_1_1serving_1_1SavedModelBundleFactory.html#aa27eec255c83cd1d2f249a2e4a2d0526)
:::

::: {.ttdeci}
Status CreateSavedModelBundle(const string &path, std::unique\_ptr\<
SavedModelBundle \> \*bundle)
:::

::: {.ttdef}
**Definition:** saved\_model\_bundle\_factory.cc:112
:::
:::

::: {#astructtensorflow_1_1serving_1_1Loader_1_1Metadata_html .ttc}
::: {.ttname}
[tensorflow::serving::Loader::Metadata](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html)
:::

::: {.ttdoc}
The metadata consists of the ServableId.
:::

::: {.ttdef}
**Definition:** loader.h:94
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

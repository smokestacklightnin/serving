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
mock\_loader.h
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
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_MOCK\_LOADER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_MOCK\_LOADER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<gmock/gmock.h\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow\_serving/core/loader.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow\_serving/util/any\_ptr.h\"]{.preprocessor}
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
[]{#l00028}[
[28](classtensorflow_1_1serving_1_1test__util_1_1MockLoader.html){.line}]{.lineno} [class
]{.keyword}[MockLoader](classtensorflow_1_1serving_1_1test__util_1_1MockLoader.html){.code}
: [public]{.keyword}
[Loader](classtensorflow_1_1serving_1_1Loader.html){.code} {
:::

::: {.line}
[]{#l00029}[ 29]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00030}[ 30]{.lineno}  MOCK\_METHOD(Status,
[EstimateResources](classtensorflow_1_1serving_1_1Loader.html#ab59db26b242a2224889bc7c5c6edae40){.code},
(ResourceAllocation \* estimate),
:::

::: {.line}
[]{#l00031}[ 31]{.lineno}  ([const]{.keyword}, [override]{.keyword}));
:::

::: {.line}
[]{#l00032}[ 32]{.lineno}  MOCK\_METHOD(Status,
[Load](classtensorflow_1_1serving_1_1Loader.html#a7dadc89ccbf488aae0102368261cc692){.code},
(), ([override]{.keyword}));
:::

::: {.line}
[]{#l00033}[ 33]{.lineno}  MOCK\_METHOD(Status,
[LoadWithMetadata](classtensorflow_1_1serving_1_1Loader.html#a7aebd433e4a782265d847e507f3bc824){.code},
([const]{.keyword}
[Metadata](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html){.code}&),
([override]{.keyword}));
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  MOCK\_METHOD([void]{.keywordtype},
[Unload](classtensorflow_1_1serving_1_1Loader.html#addca8f4264380e5e635bbe1197f5347f){.code},
(), ([override]{.keyword}));
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} 
MOCK\_METHOD([AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html){.code},
[servable](classtensorflow_1_1serving_1_1Loader.html#a640d67dc6ca9926595d29fdfe63868c1){.code},
(), ([override]{.keyword}));
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} };
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} 
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} } [// namespace test\_util]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} 
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_MOCK\_LOADER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1AnyPtr_html .ttc}
::: {.ttname}
[tensorflow::serving::AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html)
:::

::: {.ttdef}
**Definition:** any\_ptr.h:65
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Loader_html .ttc}
::: {.ttname}
[tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html)
:::

::: {.ttdef}
**Definition:** loader.h:56
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Loader_html_a640d67dc6ca9926595d29fdfe63868c1 .ttc}
::: {.ttname}
[tensorflow::serving::Loader::servable](classtensorflow_1_1serving_1_1Loader.html#a640d67dc6ca9926595d29fdfe63868c1)
:::

::: {.ttdeci}
virtual AnyPtr servable()=0
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Loader_html_a7aebd433e4a782265d847e507f3bc824 .ttc}
::: {.ttname}
[tensorflow::serving::Loader::LoadWithMetadata](classtensorflow_1_1serving_1_1Loader.html#a7aebd433e4a782265d847e507f3bc824)
:::

::: {.ttdeci}
virtual Status LoadWithMetadata(const Metadata &metadata)
:::

::: {.ttdef}
**Definition:** loader.h:102
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Loader_html_a7dadc89ccbf488aae0102368261cc692 .ttc}
::: {.ttname}
[tensorflow::serving::Loader::Load](classtensorflow_1_1serving_1_1Loader.html#a7dadc89ccbf488aae0102368261cc692)
:::

::: {.ttdeci}
virtual Status Load()
:::

::: {.ttdef}
**Definition:** loader.h:89
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Loader_html_ab59db26b242a2224889bc7c5c6edae40 .ttc}
::: {.ttname}
[tensorflow::serving::Loader::EstimateResources](classtensorflow_1_1serving_1_1Loader.html#ab59db26b242a2224889bc7c5c6edae40)
:::

::: {.ttdeci}
virtual Status EstimateResources(ResourceAllocation \*estimate) const =0
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Loader_html_addca8f4264380e5e635bbe1197f5347f .ttc}
::: {.ttname}
[tensorflow::serving::Loader::Unload](classtensorflow_1_1serving_1_1Loader.html#addca8f4264380e5e635bbe1197f5347f)
:::

::: {.ttdeci}
virtual void Unload()=0
:::
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1MockLoader_html .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::MockLoader](classtensorflow_1_1serving_1_1test__util_1_1MockLoader.html)
:::

::: {.ttdef}
**Definition:** mock\_loader.h:28
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

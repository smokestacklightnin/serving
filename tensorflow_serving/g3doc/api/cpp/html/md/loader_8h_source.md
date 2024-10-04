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
loader.h
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
TENSORFLOW\_SERVING\_CORE\_LOADER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_LOADER\_H\_]{.preprocessor}
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
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow\_serving/core/source.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow\_serving/resources/resources.pb.h\"]{.preprocessor}
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
[]{#l00056}[
[56](classtensorflow_1_1serving_1_1Loader.html){.line}]{.lineno} [class
]{.keyword}[Loader](classtensorflow_1_1serving_1_1Loader.html){.code} {
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00060}[
[60](classtensorflow_1_1serving_1_1Loader.html#ab12e7e4d5f33ade6dd73d7a30873c032){.line}]{.lineno} 
[virtual]{.keyword}
[\~Loader](classtensorflow_1_1serving_1_1Loader.html#ab12e7e4d5f33ade6dd73d7a30873c032){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} 
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [// include: (a) replace conservative
estimate with actual measurement]{.comment}
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [// once loaded in memory; (b) load process
consumes extra transient]{.comment}
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [// memory that is not used in steady-state
after the load completes.]{.comment}
:::

::: {.line}
[]{#l00082}[
[82](classtensorflow_1_1serving_1_1Loader.html#ab59db26b242a2224889bc7c5c6edae40){.line}]{.lineno} []{.comment}
[virtual]{.keyword} Status
[EstimateResources](classtensorflow_1_1serving_1_1Loader.html#ab59db26b242a2224889bc7c5c6edae40){.code}(ResourceAllocation\*
estimate) [const]{.keyword} = 0;
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} 
:::

::: {.line}
[]{#l00089}[
[89](classtensorflow_1_1serving_1_1Loader.html#a7dadc89ccbf488aae0102368261cc692){.line}]{.lineno} 
[virtual]{.keyword} Status
[Load](classtensorflow_1_1serving_1_1Loader.html#a7dadc89ccbf488aae0102368261cc692){.code}()
{
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  [return]{.keywordflow}
errors::Unimplemented([\"Load isn\'t implemented.\"]{.stringliteral});
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  }
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} 
:::

::: {.line}
[]{#l00094}[
[94](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html){.line}]{.lineno} 
[struct
]{.keyword}[Metadata](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html){.code}
{
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} 
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}
servable\_id;
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  };
:::

::: {.line}
[]{#l00102}[
[102](classtensorflow_1_1serving_1_1Loader.html#a7aebd433e4a782265d847e507f3bc824){.line}]{.lineno} 
[virtual]{.keyword} Status
[LoadWithMetadata](classtensorflow_1_1serving_1_1Loader.html#a7aebd433e4a782265d847e507f3bc824){.code}([const]{.keyword}
[Metadata](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html){.code}&
metadata) { [return]{.keywordflow}
[Load](classtensorflow_1_1serving_1_1Loader.html#a7dadc89ccbf488aae0102368261cc692){.code}();
}
:::

::: {.line}
[]{#l00103}[ 103]{.lineno} 
:::

::: {.line}
[]{#l00108}[
[108](classtensorflow_1_1serving_1_1Loader.html#addca8f4264380e5e635bbe1197f5347f){.line}]{.lineno} 
[virtual]{.keyword} [void]{.keywordtype}
[Unload](classtensorflow_1_1serving_1_1Loader.html#addca8f4264380e5e635bbe1197f5347f){.code}()
= 0;
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} 
:::

::: {.line}
[]{#l00138}[
[138](classtensorflow_1_1serving_1_1Loader.html#a640d67dc6ca9926595d29fdfe63868c1){.line}]{.lineno} 
[virtual]{.keyword}
[AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html){.code}
[servable](classtensorflow_1_1serving_1_1Loader.html#a640d67dc6ca9926595d29fdfe63868c1){.code}()
= 0;
:::

::: {.line}
[]{#l00139}[ 139]{.lineno} };
:::

::: {.line}
[]{#l00140}[ 140]{.lineno} 
:::

::: {.line}
[]{#l00141}[ 141]{.lineno} [inline]{.keyword} [bool]{.keywordtype}
operator==([const]{.keyword}
[Loader::Metadata](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html){.code}&
a, [const]{.keyword}
[Loader::Metadata](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html){.code}&
b) {
:::

::: {.line}
[]{#l00142}[ 142]{.lineno}  [return]{.keywordflow} a.servable\_id ==
b.servable\_id;
:::

::: {.line}
[]{#l00143}[ 143]{.lineno} }
:::

::: {.line}
[]{#l00144}[ 144]{.lineno} 
:::

::: {.line}
[]{#l00145}[ 145]{.lineno} [inline]{.keyword} [bool]{.keywordtype}
operator!=([const]{.keyword} Loader::Metadata& a, [const]{.keyword}
Loader::Metadata& b) {
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  [return]{.keywordflow} !(a == b);
:::

::: {.line}
[]{#l00147}[ 147]{.lineno} }
:::

::: {.line}
[]{#l00148}[ 148]{.lineno} 
:::

::: {.line}
[]{#l00155}[
[155](classtensorflow_1_1serving_1_1ResourceUnsafeLoader.html){.line}]{.lineno} [class
]{.keyword}[ResourceUnsafeLoader](classtensorflow_1_1serving_1_1ResourceUnsafeLoader.html){.code}
: [public]{.keyword}
[Loader](classtensorflow_1_1serving_1_1Loader.html){.code} {
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00157}[
[157](classtensorflow_1_1serving_1_1ResourceUnsafeLoader.html#a1a0c1398af9af54032ba16a79a9ecac4){.line}]{.lineno} 
Status
[EstimateResources](classtensorflow_1_1serving_1_1ResourceUnsafeLoader.html#a1a0c1398af9af54032ba16a79a9ecac4){.code}(ResourceAllocation\*
estimate) [const]{.keyword} [final]{.keyword} {
:::

::: {.line}
[]{#l00158}[ 158]{.lineno}  estimate-\>Clear();
:::

::: {.line}
[]{#l00159}[ 159]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00160}[ 160]{.lineno}  }
:::

::: {.line}
[]{#l00161}[ 161]{.lineno} };
:::

::: {.line}
[]{#l00162}[ 162]{.lineno} 
:::

::: {.line}
[]{#l00163}[ 163]{.lineno} [// A source that emits Loader unique
pointers.]{.comment}
:::

::: {.line}
[]{#l00164}[ 164]{.lineno} [using]{.keyword} LoaderSource =
Source\<std::unique\_ptr\<Loader\>\>;
:::

::: {.line}
[]{#l00165}[ 165]{.lineno} 
:::

::: {.line}
[]{#l00166}[ 166]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00167}[ 167]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00168}[ 168]{.lineno} 
:::

::: {.line}
[]{#l00169}[ 169]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_LOADER\_H\_]{.comment}
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

::: {#aclasstensorflow_1_1serving_1_1Loader_html_ab12e7e4d5f33ade6dd73d7a30873c032 .ttc}
::: {.ttname}
[tensorflow::serving::Loader::\~Loader](classtensorflow_1_1serving_1_1Loader.html#ab12e7e4d5f33ade6dd73d7a30873c032)
:::

::: {.ttdeci}
virtual \~Loader()=default
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

::: {#aclasstensorflow_1_1serving_1_1ResourceUnsafeLoader_html .ttc}
::: {.ttname}
[tensorflow::serving::ResourceUnsafeLoader](classtensorflow_1_1serving_1_1ResourceUnsafeLoader.html)
:::

::: {.ttdef}
**Definition:** loader.h:155
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ResourceUnsafeLoader_html_a1a0c1398af9af54032ba16a79a9ecac4 .ttc}
::: {.ttname}
[tensorflow::serving::ResourceUnsafeLoader::EstimateResources](classtensorflow_1_1serving_1_1ResourceUnsafeLoader.html#a1a0c1398af9af54032ba16a79a9ecac4)
:::

::: {.ttdeci}
Status EstimateResources(ResourceAllocation \*estimate) const final
:::

::: {.ttdef}
**Definition:** loader.h:157
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

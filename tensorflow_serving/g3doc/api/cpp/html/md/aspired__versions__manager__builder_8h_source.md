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
aspired\_versions\_manager\_builder.h
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
TENSORFLOW\_SERVING\_CORE\_ASPIRED\_VERSIONS\_MANAGER\_BUILDER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_ASPIRED\_VERSIONS\_MANAGER\_BUILDER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow\_serving/core/aspired\_versions\_manager.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow\_serving/core/loader.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow\_serving/core/source.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/core/source\_adapter.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/util/unique\_ptr\_with\_deps.h\"]{.preprocessor}
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
[]{#l00031}[ 31]{.lineno} [// TODO(b/64163389): revisit the escaped HTML
characters in c2devsite toolchain]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} 
:::

::: {.line}
[]{#l00059}[
[59](classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder.html){.line}]{.lineno} [class
]{.keyword}[AspiredVersionsManagerBuilder](classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder.html){.code}
{
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [using]{.keyword}
[Options](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html){.code}
=
[AspiredVersionsManager::Options](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html){.code};
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [static]{.keyword} Status
Create([Options](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html){.code}
options,
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} 
std::unique\_ptr\<AspiredVersionsManagerBuilder\>\* builder);
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} 
\~[AspiredVersionsManagerBuilder](classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} 
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
S\>
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [void]{.keywordtype}
[AddSource](classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder.html#abd6f745193c54f7887119ed886dda0ed){.code}(std::unique\_ptr\<S\>
source);
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} 
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
S, [typename]{.keyword} SA, [typename]{.keyword}\... Args\>
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  [void]{.keywordtype}
[AddSourceChain](classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder.html#a4b8c4eda9ac206ecc69b7464b6e42a44){.code}(std::unique\_ptr\<S\>
source,
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  std::unique\_ptr\<SA\>
first\_source\_adapter,
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  std::unique\_ptr\<Args\>\...
remaining\_source\_adapters);
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} 
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  std::unique\_ptr\<Manager\>
[Build](classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder.html#a9a95dc4a19029c2bc28fdc6caa274656){.code}();
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} 
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  [explicit]{.keyword}
[AspiredVersionsManagerBuilder](classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder.html){.code}(
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  std::unique\_ptr\<AspiredVersionsManager\>
manager);
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} 
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
S, [typename]{.keyword} SA, [typename]{.keyword}\... Args\>
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  [void]{.keywordtype}
AddSourceChainImpl(std::unique\_ptr\<S\> source,
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  std::unique\_ptr\<SA\>
first\_source\_adapter,
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  std::unique\_ptr\<Args\>\...
remaining\_source\_adapters);
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} 
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
S\>
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  [void]{.keywordtype}
AddSourceChainImpl(std::unique\_ptr\<S\> source);
:::

::: {.line}
[]{#l00104}[ 104]{.lineno} 
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} 
[AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.code}\*
[const]{.keyword} aspired\_versions\_manager\_;
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} 
[UniquePtrWithDeps\<Manager\>](classtensorflow_1_1serving_1_1UniquePtrWithDeps.html){.code}
manager\_with\_sources\_;
:::

::: {.line}
[]{#l00107}[ 107]{.lineno} };
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} 
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} [// Implementation details follow. API
readers may skip.]{.comment}
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} []{.comment}
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} [template]{.keyword} \<[typename]{.keyword}
S\>
:::

::: {.line}
[]{#l00114}[
[114](classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder.html#abd6f745193c54f7887119ed886dda0ed){.line}]{.lineno} [void]{.keywordtype}
[AspiredVersionsManagerBuilder::AddSource](classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder.html#abd6f745193c54f7887119ed886dda0ed){.code}(std::unique\_ptr\<S\>
source) {
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  static\_assert(
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  std::is\_convertible\<S\*,
[Source](classtensorflow_1_1serving_1_1Source.html){.code}\<std::unique\_ptr\<Loader\>\>\*\>::value,
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  [\"Source type should be convertible to
Source\<std::unique\_ptr\<Loader\>\>.\"]{.stringliteral});
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  ConnectSourceToTarget(source.get(),
aspired\_versions\_manager\_);
:::

::: {.line}
[]{#l00119}[ 119]{.lineno} 
manager\_with\_sources\_.AddDependency(std::move(source));
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} }
:::

::: {.line}
[]{#l00121}[ 121]{.lineno} 
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} [template]{.keyword} \<[typename]{.keyword}
S, [typename]{.keyword} SA, [typename]{.keyword}\... Args\>
:::

::: {.line}
[]{#l00123}[
[123](classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder.html#a4b8c4eda9ac206ecc69b7464b6e42a44){.line}]{.lineno} [void]{.keywordtype}
[AspiredVersionsManagerBuilder::AddSourceChain](classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder.html#a4b8c4eda9ac206ecc69b7464b6e42a44){.code}(
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  std::unique\_ptr\<S\> source,
std::unique\_ptr\<SA\> first\_source\_adapter,
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  std::unique\_ptr\<Args\>\...
remaining\_source\_adapters) {
:::

::: {.line}
[]{#l00126}[ 126]{.lineno}  AddSourceChainImpl(std::move(source),
std::move(first\_source\_adapter),
:::

::: {.line}
[]{#l00127}[ 127]{.lineno}  std::move(remaining\_source\_adapters)\...);
:::

::: {.line}
[]{#l00128}[ 128]{.lineno} }
:::

::: {.line}
[]{#l00129}[ 129]{.lineno} 
:::

::: {.line}
[]{#l00130}[ 130]{.lineno} [template]{.keyword} \<[typename]{.keyword}
S, [typename]{.keyword} SA, [typename]{.keyword}\... Args\>
:::

::: {.line}
[]{#l00131}[ 131]{.lineno} [void]{.keywordtype}
AspiredVersionsManagerBuilder::AddSourceChainImpl(
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  std::unique\_ptr\<S\> source,
std::unique\_ptr\<SA\> first\_source\_adapter,
:::

::: {.line}
[]{#l00133}[ 133]{.lineno}  std::unique\_ptr\<Args\>\...
remaining\_source\_adapters) {
:::

::: {.line}
[]{#l00134}[ 134]{.lineno}  [auto]{.keyword}\* [const]{.keyword} target
= first\_source\_adapter.get();
:::

::: {.line}
[]{#l00135}[ 135]{.lineno} 
AddSourceChainImpl(std::move(first\_source\_adapter),
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  std::move(remaining\_source\_adapters)\...);
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  ConnectSourceToTarget(source.get(), target);
:::

::: {.line}
[]{#l00138}[ 138]{.lineno}  [// We add them in this order because
UniquePtrWithDeps will delete them in]{.comment}
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  [// the inverse order of entry.]{.comment}
:::

::: {.line}
[]{#l00140}[ 140]{.lineno} 
manager\_with\_sources\_.AddDependency(std::move(source));
:::

::: {.line}
[]{#l00141}[ 141]{.lineno} }
:::

::: {.line}
[]{#l00142}[ 142]{.lineno} 
:::

::: {.line}
[]{#l00143}[ 143]{.lineno} [template]{.keyword} \<[typename]{.keyword}
S\>
:::

::: {.line}
[]{#l00144}[ 144]{.lineno} [void]{.keywordtype}
AspiredVersionsManagerBuilder::AddSourceChainImpl(
:::

::: {.line}
[]{#l00145}[ 145]{.lineno}  std::unique\_ptr\<S\> source) {
:::

::: {.line}
[]{#l00146}[ 146]{.lineno} 
[AddSource](classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder.html#abd6f745193c54f7887119ed886dda0ed){.code}(std::move(source));
:::

::: {.line}
[]{#l00147}[ 147]{.lineno} }
:::

::: {.line}
[]{#l00148}[ 148]{.lineno} 
:::

::: {.line}
[]{#l00149}[ 149]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00150}[ 150]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00151}[ 151]{.lineno} 
:::

::: {.line}
[]{#l00152}[ 152]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_ASPIRED\_VERSIONS\_MANAGER\_BUILDER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1AspiredVersionsManagerBuilder_html .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManagerBuilder](classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder.html)
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager\_builder.h:59
:::
:::

::: {#aclasstensorflow_1_1serving_1_1AspiredVersionsManagerBuilder_html_a4b8c4eda9ac206ecc69b7464b6e42a44 .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManagerBuilder::AddSourceChain](classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder.html#a4b8c4eda9ac206ecc69b7464b6e42a44)
:::

::: {.ttdeci}
void AddSourceChain(std::unique\_ptr\< S \> source, std::unique\_ptr\<
SA \> first\_source\_adapter, std::unique\_ptr\< Args \>\...
remaining\_source\_adapters)
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager\_builder.h:123
:::
:::

::: {#aclasstensorflow_1_1serving_1_1AspiredVersionsManagerBuilder_html_a9a95dc4a19029c2bc28fdc6caa274656 .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManagerBuilder::Build](classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder.html#a9a95dc4a19029c2bc28fdc6caa274656)
:::

::: {.ttdeci}
std::unique\_ptr\< Manager \> Build()
:::

::: {.ttdoc}
Builds the AspiredVersionsManager and returns it as the Manager
interface.
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager\_builder.cc:42
:::
:::

::: {#aclasstensorflow_1_1serving_1_1AspiredVersionsManagerBuilder_html_abd6f745193c54f7887119ed886dda0ed .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManagerBuilder::AddSource](classtensorflow_1_1serving_1_1AspiredVersionsManagerBuilder.html#abd6f745193c54f7887119ed886dda0ed)
:::

::: {.ttdeci}
void AddSource(std::unique\_ptr\< S \> source)
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager\_builder.h:114
:::
:::

::: {#aclasstensorflow_1_1serving_1_1AspiredVersionsManager_html .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html)
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager.h:86
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Source_html .ttc}
::: {.ttname}
[tensorflow::serving::Source](classtensorflow_1_1serving_1_1Source.html)
:::

::: {.ttdef}
**Definition:** source.h:65
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

::: {#astructtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_html .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManager::Options](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html)
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager.h:96
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

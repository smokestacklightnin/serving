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
loader\_harness.h
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
TENSORFLOW\_SERVING\_CORE\_LOADER\_HARNESS\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_LOADER\_HARNESS\_H\_]{.preprocessor}
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
\"absl/status/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"absl/types/optional.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/platform/mutex.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/platform/thread\_annotations.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow/core/platform/types.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow\_serving/core/loader.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_id.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} 
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} 
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// START\_SKIP\_DOXYGEN]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [// Forward-declaration for the use in
LoaderHarness.]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [struct ]{.keyword}ServableStateSnapshot;
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [// END\_SKIP\_DOXYGEN]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} 
:::

::: {.line}
[]{#l00049}[
[49](classtensorflow_1_1serving_1_1LoaderHarness.html){.line}]{.lineno} [class
]{.keyword}[LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.code}
final {
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00059}[
[59](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8){.line}]{.lineno} 
[enum class]{.keyword}
[State](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8){.code}
{
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} 
[kNew](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8aaf1adf7ec3673b4f5765cfbc5d43b7dc){.code},
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} 
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
[kLoadRequested](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8a20bc321c13f15e2546c39d9e0f296dd3){.code},
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} 
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} 
[kLoadApproved](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8a80697002f1c98b1828669ae672654ff5){.code},
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} 
[kLoading](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8aa2c94488cf2076543584c6a3f78556d1){.code},
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} 
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} 
[kReady](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8a25d5606fe07425ea73f245c48612c039){.code},
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} 
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} 
[kUnloadRequested](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8a723f4d66c7dcb881700bf57200e52e7d){.code},
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} 
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} 
[kQuiescing](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8ab872a4b4ff718537f0aee3d06c9f914f){.code},
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} 
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} 
[kQuiesced](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8aa468d1e1bd9ad8243b7c9d31ac711ed6){.code},
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} 
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} 
[kUnloading](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8ae4e34ef3f2680339459b2a77aa84fdb8){.code},
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} 
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} 
[kDisabled](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8a7b04d8795f5fd03c761ce70dab985fee){.code},
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} 
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} 
[kError](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8ae3587c730cc1aa530fa4ddc9c4204e97){.code}
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  };
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} 
:::

::: {.line}
[]{#l00097}[
[97](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html){.line}]{.lineno} 
[struct
]{.keyword}[Options](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html){.code}
{
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} 
[Options](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html){.code}()
{}
:::

::: {.line}
[]{#l00099}[ 99]{.lineno} 
:::

::: {.line}
[]{#l00102}[
[102](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html#a4774535a566aad29ab5bc0c7b3e0dc3e){.line}]{.lineno} 
uint32
[max\_num\_load\_retries](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html#a4774535a566aad29ab5bc0c7b3e0dc3e){.code}
= 0;
:::

::: {.line}
[]{#l00103}[ 103]{.lineno} 
:::

::: {.line}
[]{#l00105}[
[105](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html#acbf10fe52eba4bee54882e25a62386e7){.line}]{.lineno} 
uint64\_t
[load\_retry\_interval\_micros](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html#acbf10fe52eba4bee54882e25a62386e7){.code}
= 0;
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} 
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  std::function\<void([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
[id]{.keywordtype}, [const]{.keyword} Status& error)\>
:::

::: {.line}
[]{#l00109}[
[109](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html#a5f9d2107c294a1e6b0e9865ed9d34ec4){.line}]{.lineno} 
[error\_callback](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html#a5f9d2107c294a1e6b0e9865ed9d34ec4){.code};
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  };
:::

::: {.line}
[]{#l00111}[ 111]{.lineno} 
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} 
[LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.code}([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
[id]{.keywordtype}, std::unique\_ptr\<Loader\>
[loader](classtensorflow_1_1serving_1_1LoaderHarness.html#ae0be696227d934efdfc91bd13de4e48a){.code},
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  [const]{.keyword}
[Options](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html){.code}&
options =
[Options](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html){.code}());
:::

::: {.line}
[]{#l00114}[ 114]{.lineno} 
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00118}[
[118](classtensorflow_1_1serving_1_1LoaderHarness.html#a7f7ab209922600ef1d95e6be35dec8fd){.line}]{.lineno} 
[LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html#a7f7ab209922600ef1d95e6be35dec8fd){.code}([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
[id]{.keywordtype}, std::unique\_ptr\<Loader\>
[loader](classtensorflow_1_1serving_1_1LoaderHarness.html#ae0be696227d934efdfc91bd13de4e48a){.code},
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  std::unique\_ptr\<T\>
[additional\_state](classtensorflow_1_1serving_1_1LoaderHarness.html#a2a5bfd26e4b27de0e59a9dea68315a84){.code},
:::

::: {.line}
[]{#l00120}[ 120]{.lineno}  [const]{.keyword}
[Options](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html){.code}&
options =
[Options](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html){.code}())
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  :
id\_([id](classtensorflow_1_1serving_1_1LoaderHarness.html#ac6581aa3aa10002465c0ffab0b83ab95){.code}),
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} 
loader\_(std::move([loader](classtensorflow_1_1serving_1_1LoaderHarness.html#ae0be696227d934efdfc91bd13de4e48a){.code})),
:::

::: {.line}
[]{#l00123}[ 123]{.lineno} 
additional\_state\_(std::move([additional\_state](classtensorflow_1_1serving_1_1LoaderHarness.html#a2a5bfd26e4b27de0e59a9dea68315a84){.code})),
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  options\_(options),
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  should\_retry\_(\[&\](absl::Status
[status](classtensorflow_1_1serving_1_1LoaderHarness.html#afb34eca424243aacbf71f466d4ec99ef){.code})
{ [return]{.keywordflow} [true]{.keyword}; }) {}
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} 
:::

::: {.line}
[]{#l00129}[ 129]{.lineno} 
[\~LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html#a60facd158c858dbdcaaae74a18a4edd9){.code}();
:::

::: {.line}
[]{#l00130}[ 130]{.lineno} 
:::

::: {.line}
[]{#l00132}[
[132](classtensorflow_1_1serving_1_1LoaderHarness.html#ac6581aa3aa10002465c0ffab0b83ab95){.line}]{.lineno} 
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}
[id](classtensorflow_1_1serving_1_1LoaderHarness.html#ac6581aa3aa10002465c0ffab0b83ab95){.code}()[
const ]{.keyword}{ [return]{.keywordflow} id\_; }
:::

::: {.line}
[]{#l00133}[ 133]{.lineno} 
:::

::: {.line}
[]{#l00135}[ 135]{.lineno} 
[State](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8){.code}
[state](classtensorflow_1_1serving_1_1LoaderHarness.html#a5ba7d4fb6a28bbfeb94d42cfa81bd95f){.code}()
const TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00136}[ 136]{.lineno} 
:::

::: {.line}
[]{#l00139}[
[139](classtensorflow_1_1serving_1_1LoaderHarness.html#ae0be696227d934efdfc91bd13de4e48a){.line}]{.lineno} 
[Loader](classtensorflow_1_1serving_1_1Loader.html){.code}\*
[loader](classtensorflow_1_1serving_1_1LoaderHarness.html#ae0be696227d934efdfc91bd13de4e48a){.code}()[
const ]{.keyword}{ [return]{.keywordflow} loader\_.get(); }
:::

::: {.line}
[]{#l00140}[ 140]{.lineno} 
:::

::: {.line}
[]{#l00142}[ 142]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
T = std::[nullptr]{.keywordtype}\_t\>
:::

::: {.line}
[]{#l00143}[ 143]{.lineno} 
[ServableStateSnapshot\<T\>](structtensorflow_1_1serving_1_1ServableStateSnapshot.html){.code}
[loader\_state\_snapshot](classtensorflow_1_1serving_1_1LoaderHarness.html#af4ed9d7690c7bd8907cc35f8f0343fd5){.code}()
const TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00144}[ 144]{.lineno} 
:::

::: {.line}
[]{#l00148}[ 148]{.lineno}  Status
[LoadRequested](classtensorflow_1_1serving_1_1LoaderHarness.html#af38723eb75813331dad2f0d910466f57){.code}()
TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00149}[ 149]{.lineno} 
:::

::: {.line}
[]{#l00154}[ 154]{.lineno}  Status
[LoadApproved](classtensorflow_1_1serving_1_1LoaderHarness.html#aab4e0158cc9fccd7539df5a9fa312e8c){.code}()
TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00155}[ 155]{.lineno} 
:::

::: {.line}
[]{#l00166}[ 166]{.lineno}  Status
[Load](classtensorflow_1_1serving_1_1LoaderHarness.html#af7e5a0ecbec71342dcb2aa9764d0604e){.code}()
TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00167}[ 167]{.lineno} 
:::

::: {.line}
[]{#l00171}[ 171]{.lineno}  Status
[UnloadRequested](classtensorflow_1_1serving_1_1LoaderHarness.html#a6451e73c25ba30b0c78a560deba29e03){.code}()
TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00172}[ 172]{.lineno} 
:::

::: {.line}
[]{#l00181}[ 181]{.lineno}  [void]{.keywordtype}
[set\_should\_retry](classtensorflow_1_1serving_1_1LoaderHarness.html#a001ec617f6fd186d27cc911f9a952f00){.code}(std::function\<[bool]{.keywordtype}(absl::Status)\>
[should\_retry](classtensorflow_1_1serving_1_1LoaderHarness.html#ae344a05f0ae81c0f589daaa737223435){.code})
:::

::: {.line}
[]{#l00182}[ 182]{.lineno}  TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00183}[ 183]{.lineno} 
:::

::: {.line}
[]{#l00185}[ 185]{.lineno}  [bool]{.keywordtype}
[should\_retry](classtensorflow_1_1serving_1_1LoaderHarness.html#ae344a05f0ae81c0f589daaa737223435){.code}(absl::Status
[status](classtensorflow_1_1serving_1_1LoaderHarness.html#afb34eca424243aacbf71f466d4ec99ef){.code})
TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00186}[ 186]{.lineno} 
:::

::: {.line}
[]{#l00192}[ 192]{.lineno}  Status
[Unload](classtensorflow_1_1serving_1_1LoaderHarness.html#a5c131cef32324cd2ec6b22fc4dd92942){.code}()
TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00193}[ 193]{.lineno} 
:::

::: {.line}
[]{#l00199}[ 199]{.lineno}  Status
[StartQuiescing](classtensorflow_1_1serving_1_1LoaderHarness.html#a811f9dbe7ab8fb5df0c35916ec57aad8){.code}()
TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00200}[ 200]{.lineno} 
:::

::: {.line}
[]{#l00207}[ 207]{.lineno}  Status
[DoneQuiescing](classtensorflow_1_1serving_1_1LoaderHarness.html#a11b81e561e55c5b21907f8fc2eafe6e9){.code}()
TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00208}[ 208]{.lineno} 
:::

::: {.line}
[]{#l00210}[ 210]{.lineno}  [void]{.keywordtype}
[Error](classtensorflow_1_1serving_1_1LoaderHarness.html#a9833ae8f23545a9975901d8a3508d30a){.code}(const
Status&
[status](classtensorflow_1_1serving_1_1LoaderHarness.html#afb34eca424243aacbf71f466d4ec99ef){.code})
TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00211}[ 211]{.lineno} 
:::

::: {.line}
[]{#l00217}[ 217]{.lineno}  Status
[status](classtensorflow_1_1serving_1_1LoaderHarness.html#afb34eca424243aacbf71f466d4ec99ef){.code}()
const TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00218}[ 218]{.lineno} 
:::

::: {.line}
[]{#l00221}[ 221]{.lineno}  template \<typename T\>
:::

::: {.line}
[]{#l00222}[
[222](classtensorflow_1_1serving_1_1LoaderHarness.html#a2a5bfd26e4b27de0e59a9dea68315a84){.line}]{.lineno} 
T\*
[additional\_state](classtensorflow_1_1serving_1_1LoaderHarness.html#a2a5bfd26e4b27de0e59a9dea68315a84){.code}()
{
:::

::: {.line}
[]{#l00223}[ 223]{.lineno}  [return]{.keywordflow}
additional\_state\_.[get](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#acb57a78f3357bd37e85a25ca707d692b){.code}\<T\>();
:::

::: {.line}
[]{#l00224}[ 224]{.lineno}  }
:::

::: {.line}
[]{#l00225}[ 225]{.lineno} 
:::

::: {.line}
[]{#l00226}[ 226]{.lineno}  [static]{.keyword} [string]{.keywordtype}
StateDebugString([State](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8){.code}
[state](classtensorflow_1_1serving_1_1LoaderHarness.html#a5ba7d4fb6a28bbfeb94d42cfa81bd95f){.code});
:::

::: {.line}
[]{#l00227}[ 227]{.lineno} 
:::

::: {.line}
[]{#l00228}[ 228]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00229}[ 229]{.lineno}  [// Transitions the state to kError and
invokes \'options\_.error\_callback\'.]{.comment}
:::

::: {.line}
[]{#l00230}[ 230]{.lineno}  [// Private method to be used when we want
to set an error from another method]{.comment}
:::

::: {.line}
[]{#l00231}[ 231]{.lineno}  [// in this class, where mu\_ is already
held.]{.comment}
:::

::: {.line}
[]{#l00232}[ 232]{.lineno}  [void]{.keywordtype}
ErrorInternal([const]{.keyword} Status&
[status](classtensorflow_1_1serving_1_1LoaderHarness.html#afb34eca424243aacbf71f466d4ec99ef){.code})
TF\_EXCLUSIVE\_LOCKS\_REQUIRED(mu\_);
:::

::: {.line}
[]{#l00233}[ 233]{.lineno} 
:::

::: {.line}
[]{#l00234}[ 234]{.lineno}  [// Expects \'state\_\' to equal \'from\',
and if so transitions it to \'to\'. If not,]{.comment}
:::

::: {.line}
[]{#l00235}[ 235]{.lineno}  [// DCHECK-fails, calls ErrorInternal() with
a suitable error and returns the]{.comment}
:::

::: {.line}
[]{#l00236}[ 236]{.lineno}  [// same error.]{.comment}
:::

::: {.line}
[]{#l00237}[ 237]{.lineno}  Status
TransitionState([State](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8){.code}
from,
[State](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8){.code}
to) TF\_EXCLUSIVE\_LOCKS\_REQUIRED(mu\_);
:::

::: {.line}
[]{#l00238}[ 238]{.lineno} 
:::

::: {.line}
[]{#l00239}[ 239]{.lineno}  Status
UnloadInternal([State](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8){.code}
from\_state) TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00240}[ 240]{.lineno}  Status UnloadDueToCancelledLoad()
TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00241}[ 241]{.lineno} 
:::

::: {.line}
[]{#l00242}[ 242]{.lineno}  const
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}
id\_;
:::

::: {.line}
[]{#l00243}[ 243]{.lineno}  const
std::unique\_ptr\<[Loader](classtensorflow_1_1serving_1_1Loader.html){.code}\>
loader\_;
:::

::: {.line}
[]{#l00244}[ 244]{.lineno}  [// Additional state that the manager
uses.]{.comment}
:::

::: {.line}
[]{#l00245}[ 245]{.lineno}  const
[UniqueAnyPtr](classtensorflow_1_1serving_1_1UniqueAnyPtr.html){.code}
additional\_state\_;
:::

::: {.line}
[]{#l00246}[ 246]{.lineno}  const Options options\_;
:::

::: {.line}
[]{#l00247}[ 247]{.lineno}  mutable mutex mu\_;
:::

::: {.line}
[]{#l00248}[ 248]{.lineno} 
[State](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8){.code}
state\_ TF\_GUARDED\_BY(mu\_) =
[State](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8){.code}::kNew;
:::

::: {.line}
[]{#l00249}[ 249]{.lineno}  [// If state\_ is kError, this will be
non-OK.]{.comment}
:::

::: {.line}
[]{#l00250}[ 250]{.lineno}  Status status\_ TF\_GUARDED\_BY(mu\_);
:::

::: {.line}
[]{#l00251}[ 251]{.lineno}  [// The retry policy for the servable. If
the function returns false, we cancel]{.comment}
:::

::: {.line}
[]{#l00252}[ 252]{.lineno}  [// the next retry. This does not affect the
current load action already]{.comment}
:::

::: {.line}
[]{#l00253}[ 253]{.lineno}  [// running.]{.comment}
:::

::: {.line}
[]{#l00254}[ 254]{.lineno}  [// There is no retry if the last action was
successful.]{.comment}
:::

::: {.line}
[]{#l00255}[ 255]{.lineno} 
std::function\<[bool]{.keywordtype}(absl::Status)\> should\_retry\_
TF\_GUARDED\_BY(mu\_);
:::

::: {.line}
[]{#l00256}[ 256]{.lineno} 
:::

::: {.line}
[]{#l00257}[ 257]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.code});
:::

::: {.line}
[]{#l00258}[ 258]{.lineno} };
:::

::: {.line}
[]{#l00259}[ 259]{.lineno} 
:::

::: {.line}
[]{#l00260}[ 260]{.lineno} [// START\_SKIP\_DOXYGEN]{.comment}
:::

::: {.line}
[]{#l00261}[ 261]{.lineno} 
:::

::: {.line}
[]{#l00262}[ 262]{.lineno} [// A snapshot of a servable\'s state and
aspiredness, from the LoaderHarness\'s]{.comment}
:::

::: {.line}
[]{#l00263}[ 263]{.lineno} [// perspective.]{.comment}
:::

::: {.line}
[]{#l00264}[ 264]{.lineno} template \<typename T = std::nullptr\_t\>
:::

::: {.line}
[]{#l00265}[
[265](structtensorflow_1_1serving_1_1ServableStateSnapshot.html){.line}]{.lineno} struct
[ServableStateSnapshot](structtensorflow_1_1serving_1_1ServableStateSnapshot.html){.code}
final {
:::

::: {.line}
[]{#l00266}[ 266]{.lineno} 
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}
[id](classtensorflow_1_1serving_1_1LoaderHarness.html#ac6581aa3aa10002465c0ffab0b83ab95){.code};
:::

::: {.line}
[]{#l00267}[ 267]{.lineno} 
[LoaderHarness::State](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8){.code}
[state](classtensorflow_1_1serving_1_1LoaderHarness.html#a5ba7d4fb6a28bbfeb94d42cfa81bd95f){.code};
:::

::: {.line}
[]{#l00268}[ 268]{.lineno}  absl::optional\<T\>
[additional\_state](classtensorflow_1_1serving_1_1LoaderHarness.html#a2a5bfd26e4b27de0e59a9dea68315a84){.code};
:::

::: {.line}
[]{#l00269}[ 269]{.lineno} };
:::

::: {.line}
[]{#l00270}[ 270]{.lineno} 
:::

::: {.line}
[]{#l00271}[ 271]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00272}[ 272]{.lineno} [inline]{.keyword} [bool]{.keywordtype}
operator==([const]{.keyword}
[ServableStateSnapshot\<T\>](structtensorflow_1_1serving_1_1ServableStateSnapshot.html){.code}&
a,
:::

::: {.line}
[]{#l00273}[ 273]{.lineno}  [const]{.keyword}
[ServableStateSnapshot\<T\>](structtensorflow_1_1serving_1_1ServableStateSnapshot.html){.code}&
b) {
:::

::: {.line}
[]{#l00274}[ 274]{.lineno}  [return]{.keywordflow} a.id == b.id &&
a.state == b.state &&
:::

::: {.line}
[]{#l00275}[ 275]{.lineno}  a.additional\_state == b.additional\_state;
:::

::: {.line}
[]{#l00276}[ 276]{.lineno} }
:::

::: {.line}
[]{#l00277}[ 277]{.lineno} 
:::

::: {.line}
[]{#l00278}[ 278]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00279}[ 279]{.lineno} [inline]{.keyword} [bool]{.keywordtype}
operator!=([const]{.keyword} ServableStateSnapshot\<T\>& a,
:::

::: {.line}
[]{#l00280}[ 280]{.lineno}  [const]{.keyword}
ServableStateSnapshot\<T\>& b) {
:::

::: {.line}
[]{#l00281}[ 281]{.lineno}  [return]{.keywordflow} !(a == b);
:::

::: {.line}
[]{#l00282}[ 282]{.lineno} }
:::

::: {.line}
[]{#l00283}[ 283]{.lineno} 
:::

::: {.line}
[]{#l00284}[ 284]{.lineno} [inline]{.keyword} std::ostream&
operator\<\<(std::ostream& os,
[LoaderHarness::State](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8){.code}
[state](classtensorflow_1_1serving_1_1LoaderHarness.html#a5ba7d4fb6a28bbfeb94d42cfa81bd95f){.code})
{
:::

::: {.line}
[]{#l00285}[ 285]{.lineno}  os \<\<
LoaderHarness::StateDebugString([state](classtensorflow_1_1serving_1_1LoaderHarness.html#a5ba7d4fb6a28bbfeb94d42cfa81bd95f){.code});
:::

::: {.line}
[]{#l00286}[ 286]{.lineno}  [return]{.keywordflow} os;
:::

::: {.line}
[]{#l00287}[ 287]{.lineno} }
:::

::: {.line}
[]{#l00288}[ 288]{.lineno} 
:::

::: {.line}
[]{#l00290}[ 290]{.lineno} [// Implementation details. API readers may
skip.]{.comment}
:::

::: {.line}
[]{#l00292}[ 292]{.lineno} []{.comment}
:::

::: {.line}
[]{#l00293}[ 293]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00294}[
[294](classtensorflow_1_1serving_1_1LoaderHarness.html#af4ed9d7690c7bd8907cc35f8f0343fd5){.line}]{.lineno} [ServableStateSnapshot\<T\>](structtensorflow_1_1serving_1_1ServableStateSnapshot.html){.code}
[LoaderHarness::loader\_state\_snapshot](classtensorflow_1_1serving_1_1LoaderHarness.html#af4ed9d7690c7bd8907cc35f8f0343fd5){.code}()[
const ]{.keyword}{
:::

::: {.line}
[]{#l00295}[ 295]{.lineno}  mutex\_lock l(mu\_);
:::

::: {.line}
[]{#l00296}[ 296]{.lineno}  [if]{.keywordflow}
(additional\_state\_.[get](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#acb57a78f3357bd37e85a25ca707d692b){.code}\<T\>()
== [nullptr]{.keyword}) {
:::

::: {.line}
[]{#l00297}[ 297]{.lineno}  [return]{.keywordflow} {id\_, state\_, {}};
:::

::: {.line}
[]{#l00298}[ 298]{.lineno}  } [else]{.keywordflow} {
:::

::: {.line}
[]{#l00299}[ 299]{.lineno}  [return]{.keywordflow} {id\_, state\_,
{\*additional\_state\_.[get](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#acb57a78f3357bd37e85a25ca707d692b){.code}\<T\>()}};
:::

::: {.line}
[]{#l00300}[ 300]{.lineno}  }
:::

::: {.line}
[]{#l00301}[ 301]{.lineno} }
:::

::: {.line}
[]{#l00302}[ 302]{.lineno} 
:::

::: {.line}
[]{#l00303}[ 303]{.lineno} [// Specialization for
std::nullptr\_t.]{.comment}
:::

::: {.line}
[]{#l00304}[ 304]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00305}[ 305]{.lineno} [// We mark this inline to follow
ODR.]{.comment}
:::

::: {.line}
[]{#l00306}[ 306]{.lineno} [template]{.keyword} \<\>
:::

::: {.line}
[]{#l00307}[ 307]{.lineno} [inline]{.keyword}
[ServableStateSnapshot\<std::nullptr\_t\>](structtensorflow_1_1serving_1_1ServableStateSnapshot.html){.code}
:::

::: {.line}
[]{#l00308}[
308]{.lineno} [LoaderHarness::loader\_state\_snapshot](classtensorflow_1_1serving_1_1LoaderHarness.html#af4ed9d7690c7bd8907cc35f8f0343fd5){.code}()[
const ]{.keyword}{
:::

::: {.line}
[]{#l00309}[ 309]{.lineno}  mutex\_lock l(mu\_);
:::

::: {.line}
[]{#l00310}[ 310]{.lineno}  [return]{.keywordflow} {id\_, state\_, {}};
:::

::: {.line}
[]{#l00311}[ 311]{.lineno} }
:::

::: {.line}
[]{#l00312}[ 312]{.lineno} 
:::

::: {.line}
[]{#l00313}[ 313]{.lineno} [// END\_SKIP\_DOXYGEN]{.comment}
:::

::: {.line}
[]{#l00314}[ 314]{.lineno} 
:::

::: {.line}
[]{#l00315}[ 315]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00316}[ 316]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00317}[ 317]{.lineno} 
:::

::: {.line}
[]{#l00318}[ 318]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_LOADER\_HARNESS\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html)
:::

::: {.ttdef}
**Definition:** loader\_harness.h:49
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_a001ec617f6fd186d27cc911f9a952f00 .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::set\_should\_retry](classtensorflow_1_1serving_1_1LoaderHarness.html#a001ec617f6fd186d27cc911f9a952f00)
:::

::: {.ttdeci}
void set\_should\_retry(std::function\< bool(absl::Status)\>
should\_retry) TF\_LOCKS\_EXCLUDED(mu\_)
:::

::: {.ttdef}
**Definition:** loader\_harness.cc:141
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_a11b81e561e55c5b21907f8fc2eafe6e9 .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::DoneQuiescing](classtensorflow_1_1serving_1_1LoaderHarness.html#a11b81e561e55c5b21907f8fc2eafe6e9)
:::

::: {.ttdeci}
Status DoneQuiescing() TF\_LOCKS\_EXCLUDED(mu\_)
:::

::: {.ttdef}
**Definition:** loader\_harness.cc:162
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_a2a5bfd26e4b27de0e59a9dea68315a84 .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::additional\_state](classtensorflow_1_1serving_1_1LoaderHarness.html#a2a5bfd26e4b27de0e59a9dea68315a84)
:::

::: {.ttdeci}
T \* additional\_state()
:::

::: {.ttdef}
**Definition:** loader\_harness.h:222
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_a5ba7d4fb6a28bbfeb94d42cfa81bd95f .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::state](classtensorflow_1_1serving_1_1LoaderHarness.html#a5ba7d4fb6a28bbfeb94d42cfa81bd95f)
:::

::: {.ttdeci}
State state() const TF\_LOCKS\_EXCLUDED(mu\_)
:::

::: {.ttdoc}
Returns the current state of underlying Servable.
:::

::: {.ttdef}
**Definition:** loader\_harness.cc:50
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_a5c131cef32324cd2ec6b22fc4dd92942 .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::Unload](classtensorflow_1_1serving_1_1LoaderHarness.html#a5c131cef32324cd2ec6b22fc4dd92942)
:::

::: {.ttdeci}
Status Unload() TF\_LOCKS\_EXCLUDED(mu\_)
:::

::: {.ttdef}
**Definition:** loader\_harness.cc:152
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_a60facd158c858dbdcaaae74a18a4edd9 .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::\~LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html#a60facd158c858dbdcaaae74a18a4edd9)
:::

::: {.ttdeci}
\~LoaderHarness()
:::

::: {.ttdef}
**Definition:** loader\_harness.cc:43
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_a6451e73c25ba30b0c78a560deba29e03 .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::UnloadRequested](classtensorflow_1_1serving_1_1LoaderHarness.html#a6451e73c25ba30b0c78a560deba29e03)
:::

::: {.ttdeci}
Status UnloadRequested() TF\_LOCKS\_EXCLUDED(mu\_)
:::

::: {.ttdef}
**Definition:** loader\_harness.cc:110
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_a7f7ab209922600ef1d95e6be35dec8fd .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html#a7f7ab209922600ef1d95e6be35dec8fd)
:::

::: {.ttdeci}
LoaderHarness(const ServableId &id, std::unique\_ptr\< Loader \> loader,
std::unique\_ptr\< T \> additional\_state, const Options
&options=Options())
:::

::: {.ttdef}
**Definition:** loader\_harness.h:118
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_a811f9dbe7ab8fb5df0c35916ec57aad8 .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::StartQuiescing](classtensorflow_1_1serving_1_1LoaderHarness.html#a811f9dbe7ab8fb5df0c35916ec57aad8)
:::

::: {.ttdeci}
Status StartQuiescing() TF\_LOCKS\_EXCLUDED(mu\_)
:::

::: {.ttdef}
**Definition:** loader\_harness.cc:154
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_a9552eba3f9f1ca631c218befd9e686f8 .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::State](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8)
:::

::: {.ttdeci}
State
:::

::: {.ttdef}
**Definition:** loader\_harness.h:59
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_a9552eba3f9f1ca631c218befd9e686f8a20bc321c13f15e2546c39d9e0f296dd3 .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::State::kLoadRequested](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8a20bc321c13f15e2546c39d9e0f296dd3)
:::

::: {.ttdeci}
@ kLoadRequested
:::

::: {.ttdoc}
The manager has been requested to load this servable.
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_a9552eba3f9f1ca631c218befd9e686f8a25d5606fe07425ea73f245c48612c039 .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::State::kReady](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8a25d5606fe07425ea73f245c48612c039)
:::

::: {.ttdeci}
@ kReady
:::

::: {.ttdoc}
\'loader\_-\>Load()\' has succeeded.
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_a9552eba3f9f1ca631c218befd9e686f8a723f4d66c7dcb881700bf57200e52e7d .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::State::kUnloadRequested](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8a723f4d66c7dcb881700bf57200e52e7d)
:::

::: {.ttdeci}
@ kUnloadRequested
:::

::: {.ttdoc}
The manager has been requested to unload this servable.
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_a9552eba3f9f1ca631c218befd9e686f8a7b04d8795f5fd03c761ce70dab985fee .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::State::kDisabled](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8a7b04d8795f5fd03c761ce70dab985fee)
:::

::: {.ttdeci}
@ kDisabled
:::

::: {.ttdoc}
\'loader\_-\>Unload()\' has finished.
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_a9552eba3f9f1ca631c218befd9e686f8a80697002f1c98b1828669ae672654ff5 .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::State::kLoadApproved](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8a80697002f1c98b1828669ae672654ff5)
:::

::: {.ttdeci}
@ kLoadApproved
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_a9552eba3f9f1ca631c218befd9e686f8aa2c94488cf2076543584c6a3f78556d1 .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::State::kLoading](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8aa2c94488cf2076543584c6a3f78556d1)
:::

::: {.ttdeci}
@ kLoading
:::

::: {.ttdoc}
\'loader\_-\>Load()\' has been called.
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_a9552eba3f9f1ca631c218befd9e686f8aa468d1e1bd9ad8243b7c9d31ac711ed6 .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::State::kQuiesced](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8aa468d1e1bd9ad8243b7c9d31ac711ed6)
:::

::: {.ttdeci}
@ kQuiesced
:::

::: {.ttdoc}
The servable has been made unavailable for serving.
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_a9552eba3f9f1ca631c218befd9e686f8aaf1adf7ec3673b4f5765cfbc5d43b7dc .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::State::kNew](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8aaf1adf7ec3673b4f5765cfbc5d43b7dc)
:::

::: {.ttdeci}
@ kNew
:::

::: {.ttdoc}
Initial state.
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_a9552eba3f9f1ca631c218befd9e686f8ab872a4b4ff718537f0aee3d06c9f914f .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::State::kQuiescing](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8ab872a4b4ff718537f0aee3d06c9f914f)
:::

::: {.ttdeci}
@ kQuiescing
:::

::: {.ttdoc}
The servable is going to be made unavailable for serving.
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_a9552eba3f9f1ca631c218befd9e686f8ae3587c730cc1aa530fa4ddc9c4204e97 .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::State::kError](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8ae3587c730cc1aa530fa4ddc9c4204e97)
:::

::: {.ttdeci}
@ kError
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_a9552eba3f9f1ca631c218befd9e686f8ae4e34ef3f2680339459b2a77aa84fdb8 .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::State::kUnloading](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8ae4e34ef3f2680339459b2a77aa84fdb8)
:::

::: {.ttdeci}
@ kUnloading
:::

::: {.ttdoc}
\'loader\_-\>Unload()\' has been called.
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_a9833ae8f23545a9975901d8a3508d30a .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::Error](classtensorflow_1_1serving_1_1LoaderHarness.html#a9833ae8f23545a9975901d8a3508d30a)
:::

::: {.ttdeci}
void Error(const Status &status) TF\_LOCKS\_EXCLUDED(mu\_)
:::

::: {.ttdoc}
Transitions the state to kError and invokes
\'options\_.error\_callback\'.
:::

::: {.ttdef}
**Definition:** loader\_harness.cc:179
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_aab4e0158cc9fccd7539df5a9fa312e8c .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::LoadApproved](classtensorflow_1_1serving_1_1LoaderHarness.html#aab4e0158cc9fccd7539df5a9fa312e8c)
:::

::: {.ttdeci}
Status LoadApproved() TF\_LOCKS\_EXCLUDED(mu\_)
:::

::: {.ttdef}
**Definition:** loader\_harness.cc:67
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_ac6581aa3aa10002465c0ffab0b83ab95 .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::id](classtensorflow_1_1serving_1_1LoaderHarness.html#ac6581aa3aa10002465c0ffab0b83ab95)
:::

::: {.ttdeci}
ServableId id() const
:::

::: {.ttdoc}
Returns the identifier of underlying Servable.
:::

::: {.ttdef}
**Definition:** loader\_harness.h:132
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_ae0be696227d934efdfc91bd13de4e48a .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::loader](classtensorflow_1_1serving_1_1LoaderHarness.html#ae0be696227d934efdfc91bd13de4e48a)
:::

::: {.ttdeci}
Loader \* loader() const
:::

::: {.ttdef}
**Definition:** loader\_harness.h:139
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_ae344a05f0ae81c0f589daaa737223435 .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::should\_retry](classtensorflow_1_1serving_1_1LoaderHarness.html#ae344a05f0ae81c0f589daaa737223435)
:::

::: {.ttdeci}
bool should\_retry(absl::Status status) TF\_LOCKS\_EXCLUDED(mu\_)
:::

::: {.ttdoc}
Returns true if the servable should be retried.
:::

::: {.ttdef}
**Definition:** loader\_harness.cc:147
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_af38723eb75813331dad2f0d910466f57 .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::LoadRequested](classtensorflow_1_1serving_1_1LoaderHarness.html#af38723eb75813331dad2f0d910466f57)
:::

::: {.ttdeci}
Status LoadRequested() TF\_LOCKS\_EXCLUDED(mu\_)
:::

::: {.ttdef}
**Definition:** loader\_harness.cc:55
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_af4ed9d7690c7bd8907cc35f8f0343fd5 .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::loader\_state\_snapshot](classtensorflow_1_1serving_1_1LoaderHarness.html#af4ed9d7690c7bd8907cc35f8f0343fd5)
:::

::: {.ttdeci}
ServableStateSnapshot\< T \> loader\_state\_snapshot() const
TF\_LOCKS\_EXCLUDED(mu\_)
:::

::: {.ttdoc}
Returns the current overall state snapshot of the underlying Servable.
:::

::: {.ttdef}
**Definition:** loader\_harness.h:294
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_af7e5a0ecbec71342dcb2aa9764d0604e .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::Load](classtensorflow_1_1serving_1_1LoaderHarness.html#af7e5a0ecbec71342dcb2aa9764d0604e)
:::

::: {.ttdeci}
Status Load() TF\_LOCKS\_EXCLUDED(mu\_)
:::

::: {.ttdef}
**Definition:** loader\_harness.cc:75
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html_afb34eca424243aacbf71f466d4ec99ef .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::status](classtensorflow_1_1serving_1_1LoaderHarness.html#afb34eca424243aacbf71f466d4ec99ef)
:::

::: {.ttdeci}
Status status() const TF\_LOCKS\_EXCLUDED(mu\_)
:::

::: {.ttdef}
**Definition:** loader\_harness.cc:200
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

::: {#aclasstensorflow_1_1serving_1_1UniqueAnyPtr_html .ttc}
::: {.ttname}
[tensorflow::serving::UniqueAnyPtr](classtensorflow_1_1serving_1_1UniqueAnyPtr.html)
:::

::: {.ttdef}
**Definition:** any\_ptr.h:109
:::
:::

::: {#aclasstensorflow_1_1serving_1_1UniqueAnyPtr_html_acb57a78f3357bd37e85a25ca707d692b .ttc}
::: {.ttname}
[tensorflow::serving::UniqueAnyPtr::get](classtensorflow_1_1serving_1_1UniqueAnyPtr.html#acb57a78f3357bd37e85a25ca707d692b)
:::

::: {.ttdeci}
T \* get() const
:::

::: {.ttdoc}
Accessor for the underlying pointer if it is of type T, otherwise null.
:::

::: {.ttdef}
**Definition:** any\_ptr.h:136
:::
:::

::: {#astructtensorflow_1_1serving_1_1LoaderHarness_1_1Options_html .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::Options](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html)
:::

::: {.ttdoc}
Options to configure a LoaderHarness.
:::

::: {.ttdef}
**Definition:** loader\_harness.h:97
:::
:::

::: {#astructtensorflow_1_1serving_1_1LoaderHarness_1_1Options_html_a4774535a566aad29ab5bc0c7b3e0dc3e .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::Options::max\_num\_load\_retries](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html#a4774535a566aad29ab5bc0c7b3e0dc3e)
:::

::: {.ttdeci}
uint32 max\_num\_load\_retries
:::

::: {.ttdef}
**Definition:** loader\_harness.h:102
:::
:::

::: {#astructtensorflow_1_1serving_1_1LoaderHarness_1_1Options_html_a5f9d2107c294a1e6b0e9865ed9d34ec4 .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::Options::error\_callback](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html#a5f9d2107c294a1e6b0e9865ed9d34ec4)
:::

::: {.ttdeci}
std::function\< void(const ServableId &id, const Status &error)\>
error\_callback
:::

::: {.ttdoc}
An (optional) function to call upon transitioning to state kError.
:::

::: {.ttdef}
**Definition:** loader\_harness.h:109
:::
:::

::: {#astructtensorflow_1_1serving_1_1LoaderHarness_1_1Options_html_acbf10fe52eba4bee54882e25a62386e7 .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness::Options::load\_retry\_interval\_micros](structtensorflow_1_1serving_1_1LoaderHarness_1_1Options.html#acbf10fe52eba4bee54882e25a62386e7)
:::

::: {.ttdeci}
uint64\_t load\_retry\_interval\_micros
:::

::: {.ttdoc}
The interval, in microseconds, between each servable load retry.
:::

::: {.ttdef}
**Definition:** loader\_harness.h:105
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

::: {#astructtensorflow_1_1serving_1_1ServableStateSnapshot_html .ttc}
::: {.ttname}
[tensorflow::serving::ServableStateSnapshot](structtensorflow_1_1serving_1_1ServableStateSnapshot.html)
:::

::: {.ttdef}
**Definition:** loader\_harness.h:265
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

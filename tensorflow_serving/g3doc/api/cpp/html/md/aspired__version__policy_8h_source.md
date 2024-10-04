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
aspired\_version\_policy.h
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
TENSORFLOW\_SERVING\_CORE\_ASPIRED\_VERSION\_POLICY\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_ASPIRED\_VERSION\_POLICY\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} 
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"absl/types/optional.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow/core/lib/strings/strcat.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow/core/platform/types.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/core/loader\_harness.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_id.h\"]{.preprocessor}
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
[]{#l00031}[
[31](structtensorflow_1_1serving_1_1AspiredServableStateSnapshot.html){.line}]{.lineno} [struct
]{.keyword}[AspiredServableStateSnapshot](structtensorflow_1_1serving_1_1AspiredServableStateSnapshot.html){.code}
final {
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} 
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code} id;
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} 
[LoaderHarness::State](classtensorflow_1_1serving_1_1LoaderHarness.html#a9552eba3f9f1ca631c218befd9e686f8){.code}
state;
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  [bool]{.keywordtype} is\_aspired;
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} };
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
:::

::: {.line}
[]{#l00048}[
[48](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html){.line}]{.lineno} [class
]{.keyword}[AspiredVersionPolicy](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html){.code}
{
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00051}[
[51](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a5681f3f1c6c14f088084b29438e6fa85){.line}]{.lineno} 
[enum class]{.keyword}
[Action](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a5681f3f1c6c14f088084b29438e6fa85){.code}
: int {
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} 
[kLoad](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a5681f3f1c6c14f088084b29438e6fa85ae40d6c82a1a5f5a163aca43efa5e444a){.code},
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} 
[kUnload](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a5681f3f1c6c14f088084b29438e6fa85a2941108d29908fe92ae8627b1d2ec0a1){.code},
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  };
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} 
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [virtual]{.keyword}
\~[AspiredVersionPolicy](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} 
:::

::: {.line}
[]{#l00061}[
[61](structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction.html){.line}]{.lineno} 
[struct
]{.keyword}[ServableAction](structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction.html){.code}
final {
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} 
[Action](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a5681f3f1c6c14f088084b29438e6fa85){.code}
action;
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} 
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code} id;
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [string]{.keywordtype} DebugString()[ const
]{.keyword}{
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [return]{.keywordflow} strings::StrCat([\"{
action: \"]{.stringliteral},
[static\_cast\<]{.keyword}[int]{.keywordtype}[\>]{.keyword}(action),
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [\" id: \"]{.stringliteral},
[id]{.keywordtype}.DebugString(), [\" }\"]{.stringliteral});
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  }
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  };
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} 
:::

::: {.line}
[]{#l00077}[
[77](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a86135f0f3225cd2999033da63e013214){.line}]{.lineno} 
[virtual]{.keyword} absl::optional\<ServableAction\>
[GetNextAction](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a86135f0f3225cd2999033da63e013214){.code}(
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [const]{.keyword}
std::vector\<AspiredServableStateSnapshot\>& all\_versions)
[const]{.keyword} = 0;
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} 
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [protected]{.keyword}:
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  [static]{.keyword}
absl::optional\<ServableId\>
[GetHighestAspiredNewServableId](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a71bde7aea4c6116cede2714758688857){.code}(
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [const]{.keyword}
std::vector\<AspiredServableStateSnapshot\>& all\_versions);
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} 
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  [friend]{.keyword} [class
]{.keyword}[AspiredVersionPolicyTest](classtensorflow_1_1serving_1_1AspiredVersionPolicyTest.html){.code};
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} };
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} 
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} [inline]{.keyword} [bool]{.keywordtype}
operator==([const]{.keyword}
[AspiredVersionPolicy::ServableAction](structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction.html){.code}&
lhs,
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  [const]{.keyword}
[AspiredVersionPolicy::ServableAction](structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction.html){.code}&
rhs) {
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [return]{.keywordflow} lhs.action ==
rhs.action && lhs.id == rhs.id;
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} }
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} 
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} 
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_ASPIRED\_VERSION\_POLICY\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1AspiredVersionPolicyTest_html .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionPolicyTest](classtensorflow_1_1serving_1_1AspiredVersionPolicyTest.html)
:::

::: {.ttdef}
**Definition:** aspired\_version\_policy\_test.cc:27
:::
:::

::: {#aclasstensorflow_1_1serving_1_1AspiredVersionPolicy_html .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionPolicy](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html)
:::

::: {.ttdef}
**Definition:** aspired\_version\_policy.h:48
:::
:::

::: {#aclasstensorflow_1_1serving_1_1AspiredVersionPolicy_html_a5681f3f1c6c14f088084b29438e6fa85 .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionPolicy::Action](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a5681f3f1c6c14f088084b29438e6fa85)
:::

::: {.ttdeci}
Action
:::

::: {.ttdoc}
The different actions that could be recommended by a policy.
:::

::: {.ttdef}
**Definition:** aspired\_version\_policy.h:51
:::
:::

::: {#aclasstensorflow_1_1serving_1_1AspiredVersionPolicy_html_a5681f3f1c6c14f088084b29438e6fa85a2941108d29908fe92ae8627b1d2ec0a1 .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionPolicy::Action::kUnload](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a5681f3f1c6c14f088084b29438e6fa85a2941108d29908fe92ae8627b1d2ec0a1)
:::

::: {.ttdeci}
@ kUnload
:::

::: {.ttdoc}
Call unload on the servable.
:::
:::

::: {#aclasstensorflow_1_1serving_1_1AspiredVersionPolicy_html_a5681f3f1c6c14f088084b29438e6fa85ae40d6c82a1a5f5a163aca43efa5e444a .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionPolicy::Action::kLoad](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a5681f3f1c6c14f088084b29438e6fa85ae40d6c82a1a5f5a163aca43efa5e444a)
:::

::: {.ttdeci}
@ kLoad
:::

::: {.ttdoc}
Call load on the servable.
:::
:::

::: {#aclasstensorflow_1_1serving_1_1AspiredVersionPolicy_html_a71bde7aea4c6116cede2714758688857 .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionPolicy::GetHighestAspiredNewServableId](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a71bde7aea4c6116cede2714758688857)
:::

::: {.ttdeci}
static absl::optional\< ServableId \>
GetHighestAspiredNewServableId(const std::vector\<
AspiredServableStateSnapshot \> &all\_versions)
:::

::: {.ttdef}
**Definition:** aspired\_version\_policy.cc:23
:::
:::

::: {#aclasstensorflow_1_1serving_1_1AspiredVersionPolicy_html_a86135f0f3225cd2999033da63e013214 .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionPolicy::GetNextAction](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html#a86135f0f3225cd2999033da63e013214)
:::

::: {.ttdeci}
virtual absl::optional\< ServableAction \> GetNextAction(const
std::vector\< AspiredServableStateSnapshot \> &all\_versions) const =0
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

::: {#astructtensorflow_1_1serving_1_1AspiredServableStateSnapshot_html .ttc}
::: {.ttname}
[tensorflow::serving::AspiredServableStateSnapshot](structtensorflow_1_1serving_1_1AspiredServableStateSnapshot.html)
:::

::: {.ttdoc}
A snapshot of a servable\'s state and aspiredness.
:::

::: {.ttdef}
**Definition:** aspired\_version\_policy.h:31
:::
:::

::: {#astructtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction_html .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionPolicy::ServableAction](structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction.html)
:::

::: {.ttdoc}
Action and the id of the servable associated with it.
:::

::: {.ttdef}
**Definition:** aspired\_version\_policy.h:61
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

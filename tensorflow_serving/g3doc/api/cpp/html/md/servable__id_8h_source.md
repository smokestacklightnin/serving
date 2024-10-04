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
servable\_id.h
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
TENSORFLOW\_SERVING\_CORE\_SERVABLE\_ID\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_SERVABLE\_ID\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<iosfwd\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<unordered\_map\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} 
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
\"tensorflow\_serving/util/hash.h\"]{.preprocessor}
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
[]{#l00030}[ 30]{.lineno} [// An identifier for a Servable. Two Servable
objects with the]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [// same identifier are considered
semantically equivalent (modulo its loaded-]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// ness state).]{.comment}
:::

::: {.line}
[]{#l00033}[
[33](structtensorflow_1_1serving_1_1ServableId.html){.line}]{.lineno} [struct
]{.keyword}[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}
{
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  [// The name of the servable stream to which
this servable object belongs.]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  [string]{.keywordtype} name;
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [// The sequence number of this servable
object in its stream. The primary]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  [// purpose of \'version\' is to uniquely
identify a servable object. A]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [// secondary purpose is to support inbound
requests that identify just a]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [// servable stream name but not a specific
version; those are routed to the]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [// active servable with the largest version
number.]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [// Must be non-negative.]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  int64\_t version;
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [// Returns a string representation of this
object. Useful in logging.]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [string]{.keywordtype} DebugString()[ const
]{.keyword}{
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [return]{.keywordflow}
strings::StrCat([\"{name: \"]{.stringliteral}, name, [\" version:
\"]{.stringliteral}, version, [\"}\"]{.stringliteral});
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  }
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} };
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
:::

::: {.line}
[]{#l00052}[
[52](structtensorflow_1_1serving_1_1HashServableId.html){.line}]{.lineno} [struct
]{.keyword}[HashServableId](structtensorflow_1_1serving_1_1HashServableId.html){.code}
{
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  uint64\_t operator()([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
[id]{.keywordtype})[ const ]{.keyword}{
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [// Hash codes for many common types are
remarkably bad, often clustering]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [// around the same values of the low and/or
high bits for linear]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [// sequences of inputs such as 1, 2, 3; or
addresses of consecutively]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [// allocated objects. For these cases the
default hash function is the]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [// identity function on the bit
patterns.]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [// So we apply a one-to-one mapping to the
resulting bit patterns to]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [// make the high bits contain more entropy
from the entire hash code.]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [// It\'s based on Fibonacci hashing from
Knuth\'s Art of Computer]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [// Programming volume 3, section
6.4.]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  [const]{.keyword} uint64\_t version\_hash =
\[&\]() -\> uint64\_t {
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [if]{.keywordflow}
([id]{.keywordtype}.version \>= 0) {
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [return]{.keywordflow}
std::hash\<int64\_t\>()([id]{.keywordtype}.version) \*
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  0x9E3779B97F4A7C13; [// (sqrt(5) - 1)/2 as a
binary fraction.]{.comment}
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  } [else]{.keywordflow} {
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [return]{.keywordflow} 0xDECAFCAFFE;
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  }
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  }();
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [// Using version\_hash as the seed here to
combine the hashes.]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [return]{.keywordflow}
HashCombine(version\_hash,
std::hash\<string\>()([id]{.keywordtype}.name));
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  }
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} };
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} 
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} [inline]{.keyword} [bool]{.keywordtype}
operator==([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}& a,
[const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}& b)
{
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [return]{.keywordflow} a.version == b.version
&& a.name == b.name;
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} }
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} 
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} [inline]{.keyword} [bool]{.keywordtype}
operator!=([const]{.keyword} ServableId& a, [const]{.keyword}
ServableId& b) {
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  [return]{.keywordflow} !(a == b);
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} }
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} 
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} [inline]{.keyword} [bool]{.keywordtype}
operator\<([const]{.keyword} ServableId& a, [const]{.keyword}
ServableId& b) {
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  [const]{.keyword} [int]{.keywordtype}
strcmp\_result = a.name.compare(b.name);
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  [if]{.keywordflow} (strcmp\_result != 0) {
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  [return]{.keywordflow} strcmp\_result \< 0;
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  }
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  [return]{.keywordflow} a.version \<
b.version;
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} }
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} 
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} [inline]{.keyword} std::ostream&
operator\<\<(std::ostream& out, [const]{.keyword} ServableId&
[id]{.keywordtype}) {
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  [return]{.keywordflow} out \<\<
[id]{.keywordtype}.DebugString();
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} }
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} 
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00099}[ 99]{.lineno} 
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_SERVABLE\_ID\_H\_]{.comment}
:::

::: {#astructtensorflow_1_1serving_1_1HashServableId_html .ttc}
::: {.ttname}
[tensorflow::serving::HashServableId](structtensorflow_1_1serving_1_1HashServableId.html)
:::

::: {.ttdef}
**Definition:** servable\_id.h:52
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

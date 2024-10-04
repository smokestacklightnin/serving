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
source.h
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
TENSORFLOW\_SERVING\_CORE\_SOURCE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_SOURCE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<functional\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} 
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow/core/lib/core/stringpiece.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow/core/lib/io/path.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow/core/lib/strings/str\_util.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/lib/strings/strcat.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_data.h\"]{.preprocessor}
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
[]{#l00064}[ 64]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00065}[
[65](classtensorflow_1_1serving_1_1Source.html){.line}]{.lineno} [class
]{.keyword}[Source](classtensorflow_1_1serving_1_1Source.html){.code} {
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [virtual]{.keyword}
\~[Source](classtensorflow_1_1serving_1_1Source.html){.code}() =
[default]{.keywordflow};
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} 
:::

::: {.line}
[]{#l00087}[
[87](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f){.line}]{.lineno} 
[using]{.keyword}
[AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f){.code}
= std::function\<void(
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  [const]{.keyword} StringPiece servable\_name,
std::vector\<[ServableData\<T\>](classtensorflow_1_1serving_1_1ServableData.html){.code}\>
versions)\>;
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} 
:::

::: {.line}
[]{#l00091}[
[91](classtensorflow_1_1serving_1_1Source.html#a70d7f3b3ab429deb777d4672c0cec447){.line}]{.lineno} 
[virtual]{.keyword} [void]{.keywordtype}
[SetAspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#a70d7f3b3ab429deb777d4672c0cec447){.code}([AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f){.code}
callback) = 0;
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} };
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} 
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} 
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_SOURCE\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1ServableData_html .ttc}
::: {.ttname}
[tensorflow::serving::ServableData](classtensorflow_1_1serving_1_1ServableData.html)
:::

::: {.ttdef}
**Definition:** servable\_data.h:32
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

::: {#aclasstensorflow_1_1serving_1_1Source_html_a70d7f3b3ab429deb777d4672c0cec447 .ttc}
::: {.ttname}
[tensorflow::serving::Source::SetAspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#a70d7f3b3ab429deb777d4672c0cec447)
:::

::: {.ttdeci}
virtual void SetAspiredVersionsCallback(AspiredVersionsCallback
callback)=0
:::

::: {.ttdoc}
Supplies an AspiredVersionsCallback to use. Can be called at most once.
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Source_html_aeb281087e1478b0ff4a74e3f60496c6f .ttc}
::: {.ttname}
[tensorflow::serving::Source::AspiredVersionsCallback](classtensorflow_1_1serving_1_1Source.html#aeb281087e1478b0ff4a74e3f60496c6f)
:::

::: {.ttdeci}
std::function\< void(const StringPiece servable\_name, std::vector\<
ServableData\< T \> \> versions)\> AspiredVersionsCallback
:::

::: {.ttdef}
**Definition:** source.h:88
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

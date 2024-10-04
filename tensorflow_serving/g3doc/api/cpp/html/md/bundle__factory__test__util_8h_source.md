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
bundle\_factory\_test\_util.h
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
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_BUNDLE\_FACTORY\_TEST\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_BUNDLE\_FACTORY\_TEST\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<gtest/gtest.h\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include
\"tensorflow/core/protobuf/meta\_graph.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow/core/public/session.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow\_serving/resources/resources.pb.h\"]{.preprocessor}
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
[]{#l00028}[ 28]{.lineno} [// Returns the path of the Saved Model (the
pb version) for the half plus two]{.comment}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [// model.]{.comment}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [string]{.keywordtype}
GetTestSavedModelPath();
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [string]{.keywordtype}
GetTestMLMetadataSavedModelPath();
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} 
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// Returns the Session Bundle export path for
the half plus two model.]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [string]{.keywordtype}
GetTestSessionBundleExportPath();
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} 
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [// Returns the path of TensorFlow Lite model
for the half plus two model.]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [string]{.keywordtype}
GetTestTfLiteModelPath();
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [// Returns the paths of the files of the
Session Bundle export for the half plus]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [// two model.]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} std::vector\<string\>
GetTestSessionBundleExportFiles();
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [// Returns the paths of the files of the
SavedModel Bundle export for the half]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [// plus two model.]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} std::vector\<string\>
GetTestSavedModelBundleExportFiles();
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} 
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [// Returns the total size of the given files.
Requires the files to exist.]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} uint64\_t GetTotalFileSize([const]{.keyword}
std::vector\<string\>& files);
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [// Returns a signature for the half plus two
model.]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} SignatureDef GetTestSessionSignature();
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} 
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} [// Test that a Session handles a single
request for the half plus two]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [// model properly. Each request contains
\`input\_batch\_size\` sized input.]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} [void]{.keywordtype}
TestSingleRequest(Session\* session, [int]{.keywordtype}
input\_batch\_size = 2);
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} 
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} [// Test that a Session handles multiple
concurrent requests for the half plus]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} [// two model properly. Send \`num\_requests\`
request, with each request containing]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} [// \`input\_batch\_size\` sized
input.]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} [void]{.keywordtype}
TestMultipleRequests(Session\* session, [int]{.keywordtype}
num\_requests,
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [int]{.keywordtype} input\_batch\_size);
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} 
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} [// Returns the expected resource estimate for
the given total file size.]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} ResourceAllocation
GetExpectedResourceEstimate([double]{.keywordtype} total\_file\_size);
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} 
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} [// Copy (recursively) directory from \`src\`
to \`dst\`. If \`dst\` directory exists]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} [// it will be removed before copying.
CHECK-fail on errors.]{.comment}
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} [void]{.keywordtype}
CopyDirOrDie([const]{.keyword} [string]{.keywordtype}& src\_dir,
[const]{.keyword} [string]{.keywordtype}& dst\_dir);
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} } [// namespace test\_util]{.comment}
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} 
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_BUNDLE\_FACTORY\_TEST\_UTIL\_H\_]{.comment}
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

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
-   [util](dir_1303efdc8de326749a332c6a57186055.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
file\_probing\_env.h
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
TENSORFLOW\_SERVING\_UTIL\_FILE\_PROBING\_ENV\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_UTIL\_FILE\_PROBING\_ENV\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include
\"tensorflow/core/platform/env.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} 
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} 
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [// An interface used to probe the contents of
a file system. This allows file]{.comment}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [// systems other than those supported by
tensorflow::Env to be used.]{.comment}
:::

::: {.line}
[]{#l00027}[
[27](classtensorflow_1_1serving_1_1FileProbingEnv.html){.line}]{.lineno} [class
]{.keyword}[FileProbingEnv](classtensorflow_1_1serving_1_1FileProbingEnv.html){.code}
{
:::

::: {.line}
[]{#l00028}[ 28]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00029}[ 29]{.lineno}  [virtual]{.keyword}
\~[FileProbingEnv](classtensorflow_1_1serving_1_1FileProbingEnv.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} 
:::

::: {.line}
[]{#l00031}[ 31]{.lineno}  [// Returns OK if the named path exists and
NOT\_FOUND otherwise.]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno}  [virtual]{.keyword} Status
FileExists([const]{.keyword} [string]{.keywordtype}& fname) = 0;
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} 
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  [// Stores in \*children the names of the
children of the specified]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  [// directory. The names are relative to
\"dir\".]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  [// Original contents of \*children are
dropped.]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [virtual]{.keyword} Status
GetChildren([const]{.keyword} [string]{.keywordtype}& dir,
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  std::vector\<string\>\* children) = 0;
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} 
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [// Returns whether the given path is a
directory or not.]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [// See tensorflow::Env::IsDirectory() for
possible status code.]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [virtual]{.keyword} Status
IsDirectory([const]{.keyword} [string]{.keywordtype}& fname) = 0;
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} 
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [// Stores the size of \`fname\` in
\`\*file\_size\`.]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [virtual]{.keyword} Status
GetFileSize([const]{.keyword} [string]{.keywordtype}& fname, uint64\_t\*
file\_size) = 0;
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} };
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [// An implementation of FileProbingEnv which
delegates the calls to]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [// tensorflow::Env.]{.comment}
:::

::: {.line}
[]{#l00050}[
[50](classtensorflow_1_1serving_1_1TensorflowFileProbingEnv.html){.line}]{.lineno} [class
]{.keyword}[TensorflowFileProbingEnv](classtensorflow_1_1serving_1_1TensorflowFileProbingEnv.html){.code}
: [public]{.keyword}
[FileProbingEnv](classtensorflow_1_1serving_1_1FileProbingEnv.html){.code}
{
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [// \'env\' is owned by the
caller.]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} 
[TensorflowFileProbingEnv](classtensorflow_1_1serving_1_1TensorflowFileProbingEnv.html){.code}(tensorflow::Env\*
env) : env\_(env) {}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} 
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} 
\~[TensorflowFileProbingEnv](classtensorflow_1_1serving_1_1TensorflowFileProbingEnv.html){.code}()
[override]{.keyword} = [default]{.keywordflow};
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} 
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  Status FileExists([const]{.keyword}
[string]{.keywordtype}& fname) [override]{.keyword};
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} 
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  Status GetChildren([const]{.keyword}
[string]{.keywordtype}& dir, std::vector\<string\>\* children)
[override]{.keyword};
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  Status IsDirectory([const]{.keyword}
[string]{.keywordtype}& fname) [override]{.keyword};
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} 
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  Status GetFileSize([const]{.keyword}
[string]{.keywordtype}& fname, uint64\_t\* file\_size)
[override]{.keyword};
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [// Not owned.]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  tensorflow::Env\* env\_;
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} };
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} 
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_UTIL\_FILE\_PROBING\_ENV\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1FileProbingEnv_html .ttc}
::: {.ttname}
[tensorflow::serving::FileProbingEnv](classtensorflow_1_1serving_1_1FileProbingEnv.html)
:::

::: {.ttdef}
**Definition:** file\_probing\_env.h:27
:::
:::

::: {#aclasstensorflow_1_1serving_1_1TensorflowFileProbingEnv_html .ttc}
::: {.ttname}
[tensorflow::serving::TensorflowFileProbingEnv](classtensorflow_1_1serving_1_1TensorflowFileProbingEnv.html)
:::

::: {.ttdef}
**Definition:** file\_probing\_env.h:50
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

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
-   [net\_http](dir_3615685a5307a228eaa5ec677f0aeb77.html){.el}
-   [internal](dir_0b5bf4ec89be083080e2df7576ab401e.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
net\_logging.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2019 Google Inc. All Rights
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
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_INTERNAL\_NET\_LOGGING\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_INTERNAL\_NET\_LOGGING\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"absl/base/attributes.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"absl/base/log\_severity.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"absl/base/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"absl/base/port.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} 
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [// This initial version is a minimum fork
from absl/base/internal/raw\_logging.h]{.comment}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [// Hooks are not supported.]{.comment}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [// TODO(wenboz): finalize the log support for
net\_http]{.comment}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [// \* make logging pluggable (by TF serving
or by adapting external libraries]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} 
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [\#define NET\_LOG(severity, \...)
\\]{.preprocessor}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [ do { \\]{.preprocessor}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [ constexpr const char\*
net\_logging\_internal\_basename = \\]{.preprocessor}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [
::tensorflow::serving::net\_http::Basename(\_\_FILE\_\_,
\\]{.preprocessor}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [ sizeof(\_\_FILE\_\_) - 1);
\\]{.preprocessor}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [
::tensorflow::serving::net\_http::NetLog(NET\_LOGGING\_INTERNAL\_\#\#severity,
\\]{.preprocessor}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [ net\_logging\_internal\_basename,
\\]{.preprocessor}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [ \_\_LINE\_\_, \_\_VA\_ARGS\_\_);
\\]{.preprocessor}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [ } while (0)]{.preprocessor}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} 
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [\#define NET\_CHECK(condition, message)
\\]{.preprocessor}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [ do { \\]{.preprocessor}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [ if (ABSL\_PREDICT\_FALSE(!(condition))) {
\\]{.preprocessor}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [ NET\_LOG(FATAL, \"Check %s failed:
%s\"]{.preprocessor}, \#condition, message); \\
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  } \\
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  } while (0)
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} 
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [\#define NET\_LOGGING\_INTERNAL\_INFO
::absl::LogSeverity::kInfo]{.preprocessor}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [\#define NET\_LOGGING\_INTERNAL\_WARNING
::absl::LogSeverity::kWarning]{.preprocessor}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} [\#define NET\_LOGGING\_INTERNAL\_ERROR
::absl::LogSeverity::kError]{.preprocessor}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [\#define NET\_LOGGING\_INTERNAL\_FATAL
::absl::LogSeverity::kFatal]{.preprocessor}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} [\#define
NET\_LOGGING\_INTERNAL\_LEVEL(severity) \\]{.preprocessor}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [
::absl::NormalizeLogSeverity(severity)]{.preprocessor}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} 
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} [namespace ]{.keyword}net\_http {
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} 
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} [void]{.keywordtype} NetLog(absl::LogSeverity
severity, [const]{.keyword} [char]{.keywordtype}\* file,
[int]{.keywordtype} line,
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [const]{.keyword} [char]{.keywordtype}\*
format, \...) ABSL\_PRINTF\_ATTRIBUTE(4, 5);
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} 
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} [void]{.keywordtype} SafeWriteToStderr(const
[char]{.keywordtype}\* s, [size\_t]{.keywordtype} len);
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} constexpr const [char]{.keywordtype}\*
Basename(const [char]{.keywordtype}\* fname, [int]{.keywordtype} offset)
{
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [return]{.keywordflow} offset == 0 \|\|
fname\[offset - 1\] == [\'/\']{.charliteral} \|\| fname\[offset - 1\] ==
[\'\\\\\']{.charliteral}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  ? fname + offset
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  : Basename(fname, offset - 1);
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} }
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} 
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} } [// namespace net\_http]{.comment}
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} 
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_INTERNAL\_NET\_LOGGING\_H\_]{.comment}
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

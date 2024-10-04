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
mock\_request\_logger.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2017 Google Inc. All Rights
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
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_MOCK\_REQUEST\_LOGGER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_MOCK\_REQUEST\_LOGGER\_H\_]{.preprocessor}
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
\"google/protobuf/message.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<gmock/gmock.h\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow\_serving/apis/logging.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/config/logging\_config.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/core/log\_collector.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow\_serving/core/request\_logger.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} 
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} 
:::

::: {.line}
[]{#l00032}[
[32](classtensorflow_1_1serving_1_1MockRequestLogger.html){.line}]{.lineno} [class
]{.keyword}[MockRequestLogger](classtensorflow_1_1serving_1_1MockRequestLogger.html){.code}
: [public]{.keyword}
[RequestLogger](classtensorflow_1_1serving_1_1RequestLogger.html){.code}
{
:::

::: {.line}
[]{#l00033}[ 33]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  [// Unfortunately NiceMock doesn\'t support
ctors with move-only types, so we]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  [// have to do this workaround.]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
[MockRequestLogger](classtensorflow_1_1serving_1_1MockRequestLogger.html){.code}([const]{.keyword}
LoggingConfig& logging\_config,
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [const]{.keyword} std::vector\<string\>&
saved\_model\_tags,
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
[LogCollector](classtensorflow_1_1serving_1_1LogCollector.html){.code}\*
log\_collector,
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} 
std::function\<[void]{.keywordtype}([void]{.keywordtype})\>
notify\_destruction =
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
std::function\<[void]{.keywordtype}([void]{.keywordtype})\>())
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  :
[RequestLogger](classtensorflow_1_1serving_1_1RequestLogger.html){.code}(logging\_config,
saved\_model\_tags,
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
std::unique\_ptr\<LogCollector\>(log\_collector)),
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} 
notify\_destruction\_(std::move(notify\_destruction)) {}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [virtual]{.keyword}
\~[MockRequestLogger](classtensorflow_1_1serving_1_1MockRequestLogger.html){.code}()
{
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [if]{.keywordflow} (notify\_destruction\_) {
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  notify\_destruction\_();
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  }
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  }
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} 
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  MOCK\_METHOD(Status, CreateLogMessage,
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  ([const]{.keyword} google::protobuf::Message&
request, [const]{.keyword} google::protobuf::Message& response,
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [const]{.keyword} LogMetadata& log\_metadata,
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} 
std::unique\_ptr\<google::protobuf::Message\>\* log),
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  ([override]{.keyword}));
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} 
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  MOCK\_METHOD(LogMetadata, FillLogMetadata,
([const]{.keyword} LogMetadata&), ([override]{.keyword}));
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} 
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  std::function\<void([void]{.keywordtype})\>
notify\_destruction\_;
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} };
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} 
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} 
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_TEST\_UTIL\_MOCK\_REQUEST\_LOGGER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1LogCollector_html .ttc}
::: {.ttname}
[tensorflow::serving::LogCollector](classtensorflow_1_1serving_1_1LogCollector.html)
:::

::: {.ttdef}
**Definition:** log\_collector.h:35
:::
:::

::: {#aclasstensorflow_1_1serving_1_1MockRequestLogger_html .ttc}
::: {.ttname}
[tensorflow::serving::MockRequestLogger](classtensorflow_1_1serving_1_1MockRequestLogger.html)
:::

::: {.ttdef}
**Definition:** mock\_request\_logger.h:32
:::
:::

::: {#aclasstensorflow_1_1serving_1_1RequestLogger_html .ttc}
::: {.ttname}
[tensorflow::serving::RequestLogger](classtensorflow_1_1serving_1_1RequestLogger.html)
:::

::: {.ttdef}
**Definition:** request\_logger.h:36
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

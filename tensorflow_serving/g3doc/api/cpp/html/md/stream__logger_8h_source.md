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
stream\_logger.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2023 Google Inc. All Rights
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
THIRD\_PARTY\_TENSORFLOW\_SERVING\_CORE\_STREAM\_LOGGER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
THIRD\_PARTY\_TENSORFLOW\_SERVING\_CORE\_STREAM\_LOGGER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<functional\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<type\_traits\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<utility\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} 
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"absl/status/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/lib/core/errors.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow\_serving/apis/logging.pb.h\"]{.preprocessor}
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
[]{#l00032}[ 32]{.lineno} [// Simple logger for a stream of requests and
responses. In practice, the]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// lifetime of this class should be attached
to the lifetime of a stream.]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [// The class being templated on requests and
responses is to avoid RTTI in the]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [// subclasses.]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [// Not thread-safe.]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [template]{.keyword} \<[typename]{.keyword}
Request, [typename]{.keyword} Response\>
:::

::: {.line}
[]{#l00039}[
[39](classtensorflow_1_1serving_1_1StreamLogger.html){.line}]{.lineno} [class
]{.keyword}[StreamLogger](classtensorflow_1_1serving_1_1StreamLogger.html){.code}
{
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} 
[StreamLogger](classtensorflow_1_1serving_1_1StreamLogger.html){.code}()
{
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
static\_assert((std::is\_base\_of\<google::protobuf::Message,
Request\>::value),
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [\"Request must be a proto
type.\"]{.stringliteral});
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
static\_assert((std::is\_base\_of\<google::protobuf::Message,
Response\>::value),
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [\"Response must be a proto
type.\"]{.stringliteral});
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  }
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [virtual]{.keyword}
\~[StreamLogger](classtensorflow_1_1serving_1_1StreamLogger.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [virtual]{.keyword} [void]{.keywordtype}
LogStreamRequest(Request request) = 0;
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [virtual]{.keyword} [void]{.keywordtype}
LogStreamResponse(Response response) = 0;
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} 
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [using]{.keyword} LogMessageFn =
std::function\<absl::Status([const]{.keyword}
google::protobuf::Message&)\>;
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [// Registers a log callback to be invoked
when calling LogMessage();]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [void]{.keywordtype}
AddLogCallback([const]{.keyword} LogMetadata& log\_metadata,
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  LogMessageFn log\_message\_fn);
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} 
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [// Logs the message with all requests and
responses accumulated so far, and]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [// invokes all log callbacks sequentially.
Upon return, any subsequent calls]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [// to any other methods of this class will
result in undefined behavior. On]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [// multiple callbacks, we return error from
the first failed one (and continue]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [// attempting the rest).]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  absl::Status LogMessage();
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [virtual]{.keyword} absl::Status
CreateLogMessage(
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [const]{.keyword} LogMetadata& log\_metadata,
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} 
std::unique\_ptr\<google::protobuf::Message\>\* log) = 0;
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [struct ]{.keyword}StreamLogCallback {
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  LogMetadata log\_metadata;
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  LogMessageFn log\_message\_fn;
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  };
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} 
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  std::vector\<StreamLogCallback\> callbacks\_;
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} };
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} 
:::

::: {.line}
[]{#l00078}[
78]{.lineno} [/\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*Implementation
Details\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*/]{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} 
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} [template]{.keyword} \<[typename]{.keyword}
Request, [typename]{.keyword} Response\>
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} absl::Status [StreamLogger\<Request,
Response\>::LogMessage](classtensorflow_1_1serving_1_1StreamLogger.html){.code}()
{
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  absl::Status status;
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  [for]{.keywordflow} ([const]{.keyword}
[auto]{.keyword}& callback : callbacks\_) {
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  std::unique\_ptr\<google::protobuf::Message\>
log;
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  absl::Status create\_status =
CreateLogMessage(callback.log\_metadata, &log);
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  [if]{.keywordflow} (create\_status.ok()) {
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} 
status.Update(callback.log\_message\_fn(\*log));
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  } [else]{.keywordflow} {
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  LOG\_EVERY\_N\_SEC(ERROR, 30)
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  \<\< [\"Failed creating log message for
streaming request. Log metadata: \"]{.stringliteral}
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  \<\< callback.log\_metadata.DebugString()
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  \<\< [\", error: \"]{.stringliteral} \<\<
create\_status;
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  status.Update(create\_status);
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  }
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  }
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  [return]{.keywordflow} status;
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} }
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} 
:::

::: {.line}
[]{#l00099}[ 99]{.lineno} [template]{.keyword} \<[typename]{.keyword}
Request, [typename]{.keyword} Response\>
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} [void]{.keywordtype} StreamLogger\<Request,
Response\>::AddLogCallback(
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  [const]{.keyword} LogMetadata&
log\_metadata, LogMessageFn log\_message\_fn) {
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  StreamLogCallback callback;
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  callback.log\_metadata = log\_metadata;
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  callback.log\_message\_fn =
std::move(log\_message\_fn);
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  callbacks\_.push\_back(std::move(callback));
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} }
:::

::: {.line}
[]{#l00107}[ 107]{.lineno} 
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} 
:::

::: {.line}
[]{#l00111}[ 111]{.lineno} [\#endif ]{.preprocessor}[//
THIRD\_PARTY\_TENSORFLOW\_SERVING\_CORE\_STREAM\_LOGGER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1StreamLogger_html .ttc}
::: {.ttname}
[tensorflow::serving::StreamLogger](classtensorflow_1_1serving_1_1StreamLogger.html)
:::

::: {.ttdef}
**Definition:** stream\_logger.h:39
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

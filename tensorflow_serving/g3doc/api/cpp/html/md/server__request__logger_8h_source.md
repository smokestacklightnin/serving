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
server\_request\_logger.h
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
TENSORFLOW\_SERVING\_CORE\_SERVER\_REQUEST\_LOGGER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_SERVER\_REQUEST\_LOGGER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<functional\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<map\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include \<unordered\_map\>]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} 
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"google/protobuf/message.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow\_serving/apis/logging.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow\_serving/config/logging\_config.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow\_serving/core/request\_logger.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include
\"tensorflow\_serving/util/fast\_read\_dynamic\_ptr.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} 
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} 
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [// Logs a sample of requests hitting all the
models in the server.]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [// Constructed based on the logging config
for the server, which contains the]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [// sampling config.]{.comment}
:::

::: {.line}
[]{#l00040}[
[40](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.line}]{.lineno} [class
]{.keyword}[ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.code}
{
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [using]{.keyword} LoggerCreator =
std::function\<Status(
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [const]{.keyword} LoggingConfig&
logging\_config, std::shared\_ptr\<RequestLogger\>\*)\>;
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [// Creates the ServerRequestLogger based on
a custom request\_logger\_creator]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [// method.]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [// You can create an empty
ServerRequestLogger with an empty]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [// request\_logger\_creator.]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [static]{.keyword} Status Create(
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  LoggerCreator request\_logger\_creator,
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  std::unique\_ptr\<ServerRequestLogger\>\*
server\_request\_logger);
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} 
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [virtual]{.keyword}
\~[ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} 
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [// Updates the logger with the new
\'logging\_config\_map\'.]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [// If the ServerRequestLogger was created
using an empty]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [// request\_logger\_creator, this will
return an error if a non-empty]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [// logging\_config\_map is passed
in.]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [virtual]{.keyword} Status Update(
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [const]{.keyword}
std::map\<[string]{.keywordtype}, std::vector\<LoggingConfig\>\>&
logging\_config\_map);
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} 
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [// Similar to
RequestLogger::Log().]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [// If request is logged/written to multiple
sinks, we return error from]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [// the first failed write (and continue
attempting to write to all).]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [virtual]{.keyword} Status
Log([const]{.keyword} google::protobuf::Message& request,
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [const]{.keyword} google::protobuf::Message&
response,
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [const]{.keyword} LogMetadata&
log\_metadata);
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} 
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  [// Starts logging a stream. Returns a
StreamLogger created through]{.comment}
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [// \`create\_stream\_logger\_fn\`. Returns
NULL if the stream should not be logged.]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  [// Even if the stream is logged/written to
multiple sinks, we return a single]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [// stream logger but register multiple
callbacks, one for each sink.]{.comment}
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
Request, [typename]{.keyword} Response\>
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [using]{.keyword} CreateStreamLoggerFn =
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} 
std::function\<std::unique\_ptr\<StreamLogger\<Request,
Response\>\>()\>;
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
Request, [typename]{.keyword} Response\>
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  std::unique\_ptr\<StreamLogger\<Request,
Response\>\> StartLoggingStream(
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  [const]{.keyword} LogMetadata& log\_metadata,
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  CreateStreamLoggerFn\<Request, Response\>
create\_stream\_logger\_fn);
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} 
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [protected]{.keyword}:
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  [explicit]{.keyword}
[ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.code}(LoggerCreator
request\_logger\_creator);
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} 
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  [using]{.keyword} StringToRequestLoggersMap =
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  std::unordered\_map\<string,
std::vector\<std::shared\_ptr\<RequestLogger\>\>\>;
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  [using]{.keyword}
StringToUniqueRequestLoggerMap =
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  std::unordered\_map\<string,
std::shared\_ptr\<RequestLogger\>\>;
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} 
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  [// Find a logger for config in either
config\_to\_logger\_map\_ or]{.comment}
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  [// new\_config\_to\_logger\_map. If the
logger was found in]{.comment}
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  [// config\_to\_logger\_map\_ move it to
new\_config\_to\_logger\_map and erase the]{.comment}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  [// entry from config\_to\_logger\_map\_. If
such a logger does not exist,]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  [// create a new logger and insert it into
new\_config\_to\_logger\_map. Return the]{.comment}
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  [// logger in result.]{.comment}
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  Status FindOrCreateLogger(
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  [const]{.keyword} LoggingConfig& config,
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  StringToUniqueRequestLoggerMap\*
new\_config\_to\_logger\_map,
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  std::shared\_ptr\<RequestLogger\>\* result);
:::

::: {.line}
[]{#l00103}[ 103]{.lineno} 
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  [// Invokes \`fn\` with all loggers for the
corresponding model.]{.comment}
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  [void]{.keywordtype} InvokeLoggerForModel(
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  [const]{.keyword} LogMetadata&
log\_metadata,
:::

::: {.line}
[]{#l00107}[ 107]{.lineno} 
std::function\<[void]{.keywordtype}([const]{.keyword}
std::shared\_ptr\<RequestLogger\>&)\> fn);
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} 
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  [// Mutex to ensure concurrent calls to
Update() are serialized.]{.comment}
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  [mutable]{.keyword} mutex update\_mu\_;
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  [// A map from serialized model logging
config to its corresponding]{.comment}
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  [// RequestLogger. If two models have the
same logging config, they]{.comment}
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  [// will share the RequestLogger.]{.comment}
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [// This is only used during calls to
Update().]{.comment}
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  StringToUniqueRequestLoggerMap
config\_to\_logger\_map\_;
:::

::: {.line}
[]{#l00116}[ 116]{.lineno} 
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  [// A map from model\_name to its
corresponding RequestLoggers.]{.comment}
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  [// The RequestLoggers are owned by
config\_to\_logger\_map\_.]{.comment}
:::

::: {.line}
[]{#l00119}[ 119]{.lineno} 
[FastReadDynamicPtr\<StringToRequestLoggersMap\>](classtensorflow_1_1serving_1_1FastReadDynamicPtr.html){.code}
model\_to\_loggers\_map\_;
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} 
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  LoggerCreator request\_logger\_creator\_;
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} };
:::

::: {.line}
[]{#l00123}[ 123]{.lineno} 
:::

::: {.line}
[]{#l00124}[
124]{.lineno} [/\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*Implementation
Details\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*/]{.comment}
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} [template]{.keyword} \<[typename]{.keyword}
Request, [typename]{.keyword} Response\>
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} std::unique\_ptr\<StreamLogger\<Request,
Response\>\>
:::

::: {.line}
[]{#l00127}[ 127]{.lineno} ServerRequestLogger::StartLoggingStream(
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  [const]{.keyword} LogMetadata&
log\_metadata,
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  CreateStreamLoggerFn\<Request, Response\>
create\_stream\_logger\_fn) {
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  [StreamLogger\<Request,
Response\>](classtensorflow_1_1serving_1_1StreamLogger.html){.code}\*
stream\_logger = [nullptr]{.keyword};
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  InvokeLoggerForModel(
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  log\_metadata, \[create\_stream\_logger\_fn,
&stream\_logger, &log\_metadata\](
:::

::: {.line}
[]{#l00133}[ 133]{.lineno}  [const]{.keyword}
std::shared\_ptr\<RequestLogger\>& request\_logger) {
:::

::: {.line}
[]{#l00134}[ 134]{.lineno}  RequestLogger::GetStreamLoggerFn\<Request,
Response\> create\_logger =
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  \[&create\_stream\_logger\_fn,
&stream\_logger\]() {
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  stream\_logger =
create\_stream\_logger\_fn().release();
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  [return]{.keywordflow} stream\_logger;
:::

::: {.line}
[]{#l00138}[ 138]{.lineno}  };
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  RequestLogger::GetStreamLoggerFn\<Request,
Response\> get\_logger =
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  \[stream\_logger\]() {
[return]{.keywordflow} stream\_logger; };
:::

::: {.line}
[]{#l00141}[ 141]{.lineno}  request\_logger-\>MaybeStartLoggingStream(
:::

::: {.line}
[]{#l00142}[ 142]{.lineno}  log\_metadata, stream\_logger ==
[nullptr]{.keyword} ? std::move(create\_logger)
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  : std::move(get\_logger));
:::

::: {.line}
[]{#l00144}[ 144]{.lineno}  [// If the stream logger has been created,
reuse it.]{.comment}
:::

::: {.line}
[]{#l00145}[ 145]{.lineno}  });
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  [return]{.keywordflow}
absl::WrapUnique(stream\_logger);
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
TENSORFLOW\_SERVING\_CORE\_SERVER\_REQUEST\_LOGGER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1FastReadDynamicPtr_html .ttc}
::: {.ttname}
[tensorflow::serving::FastReadDynamicPtr\< StringToRequestLoggersMap
\>](classtensorflow_1_1serving_1_1FastReadDynamicPtr.html)
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServerRequestLogger_html .ttc}
::: {.ttname}
[tensorflow::serving::ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html)
:::

::: {.ttdef}
**Definition:** server\_request\_logger.h:40
:::
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

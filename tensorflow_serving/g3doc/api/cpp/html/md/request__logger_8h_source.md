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
request\_logger.h
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
TENSORFLOW\_SERVING\_CORE\_REQUEST\_LOGGER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_REQUEST\_LOGGER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<random\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} 
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"google/protobuf/message.h\"]{.preprocessor}
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
\"tensorflow\_serving/core/stream\_logger.h\"]{.preprocessor}
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
[]{#l00032}[ 32]{.lineno} [// Abstraction to log requests and responses
hitting a server. The log storage]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// is handled by the log-collector. We sample
requests based on the config.]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// All subclasses must only implement a
factory method that returns a]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [// shared\_ptr.]{.comment}
:::

::: {.line}
[]{#l00036}[
[36](classtensorflow_1_1serving_1_1RequestLogger.html){.line}]{.lineno} [class
]{.keyword}[RequestLogger](classtensorflow_1_1serving_1_1RequestLogger.html){.code}
: [public]{.keyword} std::enable\_shared\_from\_this\<RequestLogger\> {
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
[RequestLogger](classtensorflow_1_1serving_1_1RequestLogger.html){.code}([const]{.keyword}
LoggingConfig& logging\_config,
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [const]{.keyword} std::vector\<string\>&
saved\_model\_tags,
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  std::unique\_ptr\<LogCollector\>
log\_collector);
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} 
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [virtual]{.keyword}
\~[RequestLogger](classtensorflow_1_1serving_1_1RequestLogger.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} 
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [// Writes the log for the particular
request, response and metadata, if we]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [// decide to sample it.]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  Status Log([const]{.keyword}
google::protobuf::Message& request, [const]{.keyword}
google::protobuf::Message& response,
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [const]{.keyword} LogMetadata&
log\_metadata);
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} 
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [// Starts logging a stream through returning
a StreamLogger through]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [// \`get\_stream\_logger\_fn\` and registers
a log callback. Returns NULL if the]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [// stream should not be logged.]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
Request, [typename]{.keyword} Response\>
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [using]{.keyword} GetStreamLoggerFn =
std::function\<StreamLogger\<Request, Response\>\*()\>;
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
Request, [typename]{.keyword} Response\>
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [void]{.keywordtype} MaybeStartLoggingStream(
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [const]{.keyword} LogMetadata& log\_metadata,
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  GetStreamLoggerFn\<Request, Response\>
get\_stream\_logger\_fn);
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} 
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [const]{.keyword} LoggingConfig&
logging\_config()[ const ]{.keyword}{ [return]{.keywordflow}
logging\_config\_; }
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [// Creates the log message given the
request, response and metadata.]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [// Implementations override it to create the
particular message that they want]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  [// to be logged.]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [virtual]{.keyword} Status
CreateLogMessage([const]{.keyword} google::protobuf::Message& request,
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [const]{.keyword} google::protobuf::Message&
response,
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
[]{#l00070}[ 70]{.lineno}  [// Implementations can fill up additional
information to LogMetadata.]{.comment}
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  [virtual]{.keyword} LogMetadata
FillLogMetadata([const]{.keyword} LogMetadata& lm\_in) = 0;
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} 
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [// Writes the log.]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  Status Log([const]{.keyword}
google::protobuf::Message& log);
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} 
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [// A sampler which samples uniformly at
random.]{.comment}
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [class ]{.keyword}UniformSampler {
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  UniformSampler() : rd\_(), gen\_(rd\_()),
dist\_(0, 1) {}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} 
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  [// Returns true if the sampler decides to
sample it with a probability]{.comment}
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  [// \'rate\'.]{.comment}
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  [bool]{.keywordtype} Sample([const]{.keyword}
[double]{.keywordtype} rate) { [return]{.keywordflow} dist\_(gen\_) \<
rate; }
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} 
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  std::random\_device rd\_;
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  std::mt19937 gen\_;
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  std::uniform\_real\_distribution\<double\>
dist\_;
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  };
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} 
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  [const]{.keyword} LoggingConfig
logging\_config\_;
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [const]{.keyword} std::vector\<string\>
saved\_model\_tags\_;
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  std::unique\_ptr\<LogCollector\>
log\_collector\_;
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  UniformSampler uniform\_sampler\_;
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} };
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} 
:::

::: {.line}
[]{#l00097}[
97]{.lineno} [/\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*Implementation
Detail\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*/]{.comment}
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} [template]{.keyword} \<[typename]{.keyword}
Request, [typename]{.keyword} Response\>
:::

::: {.line}
[]{#l00099}[ 99]{.lineno} [void]{.keywordtype}
RequestLogger::MaybeStartLoggingStream(
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  [const]{.keyword} LogMetadata&
log\_metadata,
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  GetStreamLoggerFn\<Request, Response\>
get\_stream\_logger\_fn) {
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [// Sampling happens at the beginning of
logging to avoid logging overhead.]{.comment}
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  [// if request logger goes away during a
stream which could happen due to]{.comment}
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  [// loggin config update, the stream won\'t
be logged.]{.comment}
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  [if]{.keywordflow}
(!uniform\_sampler\_.Sample(
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} 
logging\_config\_.sampling\_config().sampling\_rate())) {
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [return]{.keywordflow};
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  }
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} 
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  [auto]{.keyword}\* stream\_logger =
get\_stream\_logger\_fn();
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  [if]{.keywordflow} (stream\_logger ==
[nullptr]{.keyword}) [return]{.keywordflow};
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} 
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  LogMetadata lm\_out =
FillLogMetadata(log\_metadata);
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  std::weak\_ptr\<RequestLogger\>
logger\_ref(shared\_from\_this());
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  stream\_logger-\>AddLogCallback(
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  lm\_out, \[logger\_ref =
std::move(logger\_ref)\]([const]{.keyword} google::protobuf::Message&
log) {
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  [// The callback refers back to the request
logger. If the]{.comment}
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  [// request logger goes away after creation
but before stream]{.comment}
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  [// ends, we simply skip this
sink.]{.comment}
:::

::: {.line}
[]{#l00120}[ 120]{.lineno}  [if]{.keywordflow} ([auto]{.keyword} logger
= logger\_ref.lock(); logger != [nullptr]{.keyword}) {
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  TF\_RETURN\_IF\_ERROR(logger-\>Log(log));
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  }
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  [return]{.keywordflow} OkStatus();
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  });
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} }
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} 
:::

::: {.line}
[]{#l00127}[ 127]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00128}[ 128]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00129}[ 129]{.lineno} 
:::

::: {.line}
[]{#l00130}[ 130]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_REQUEST\_LOGGER\_H\_]{.comment}
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

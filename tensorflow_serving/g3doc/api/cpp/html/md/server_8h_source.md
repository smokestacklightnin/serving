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
-   [model\_servers](dir_5bce3ff2a459f05fa975e832b2676e62.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
server.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2018 Google Inc. All Rights
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
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_SERVER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_SERVER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \"grpcpp/server.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow/core/kernels/batching\_util/periodic\_function.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow/core/platform/cpu\_info.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/platform/types.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/profiler/rpc/profiler\_service\_impl.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow\_serving/model\_servers/http\_server.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow\_serving/model\_servers/model\_service\_impl.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow\_serving/model\_servers/prediction\_service\_impl.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow\_serving/model\_servers/server\_core.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/thread\_pool\_factory.h\"]{.preprocessor}
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
[]{#l00035}[ 35]{.lineno} [namespace ]{.keyword}main {
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
:::

::: {.line}
[]{#l00037}[
[37](classtensorflow_1_1serving_1_1main_1_1Server.html){.line}]{.lineno} [class
]{.keyword}[Server](classtensorflow_1_1serving_1_1main_1_1Server.html){.code}
{
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00039}[
[39](structtensorflow_1_1serving_1_1main_1_1Server_1_1Options.html){.line}]{.lineno} 
[struct
]{.keyword}[Options](structtensorflow_1_1serving_1_1main_1_1Server_1_1Options.html){.code}
{
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [// gRPC Server options]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  tensorflow::int32 grpc\_port = 8500;
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  tensorflow::string grpc\_channel\_arguments;
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  tensorflow::string grpc\_socket\_path;
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  tensorflow::int32 grpc\_max\_threads = 4.0 \*
port::NumSchedulableCPUs();
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [// HTTP Server options.]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  tensorflow::int32 http\_port = 0;
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  tensorflow::int32 http\_num\_threads = 4.0 \*
port::NumSchedulableCPUs();
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  tensorflow::int32 http\_timeout\_in\_ms =
30000; [// 30 seconds.]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [bool]{.keywordtype} enable\_cors\_support =
[false]{.keyword};
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} 
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [// Model Server options.]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [bool]{.keywordtype} enable\_batching =
[false]{.keyword};
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [bool]{.keywordtype}
enable\_per\_model\_batching\_params = [false]{.keyword};
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [bool]{.keywordtype}
allow\_version\_labels\_for\_unavailable\_models = [false]{.keyword};
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [bool]{.keywordtype}
force\_allow\_any\_version\_labels\_for\_unavailable\_models =
[false]{.keyword};
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [float]{.keywordtype}
per\_process\_gpu\_memory\_fraction = 0;
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  tensorflow::string
batching\_parameters\_file;
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  tensorflow::string model\_name;
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  tensorflow::int32 num\_load\_threads = 0;
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  tensorflow::int32 num\_unload\_threads = 0;
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  tensorflow::int32 max\_num\_load\_retries =
5;
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  int64\_t load\_retry\_interval\_micros = 1LL
\* 60 \* 1000 \* 1000;
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  tensorflow::int32
file\_system\_poll\_wait\_seconds = 1;
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  [bool]{.keywordtype}
flush\_filesystem\_caches = [true]{.keyword};
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  tensorflow::string model\_base\_path;
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  tensorflow::string saved\_model\_tags;
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  [// Tensorflow session parallelism of zero
means that both inter and intra op]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [// thread pools will be auto
configured.]{.comment}
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  int64\_t tensorflow\_session\_parallelism =
0;
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} 
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [// Zero means that the thread pools will be
auto configured.]{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  int64\_t tensorflow\_intra\_op\_parallelism =
0;
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  int64\_t tensorflow\_inter\_op\_parallelism =
0;
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  tensorflow::string platform\_config\_file;
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  [// Only one of ALTS or SSl can be specified.
I.e. either]{.comment}
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  [// use\_alts\_credentials must be false or
ssl\_config\_file must be empty.]{.comment}
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [bool]{.keywordtype} use\_alts\_credentials =
[false]{.keyword};
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  tensorflow::string ssl\_config\_file;
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  [string]{.keywordtype} model\_config\_file;
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  [// Text proto file for TensorFlow Session
ConfigProto.]{.comment}
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  [string]{.keywordtype}
tensorflow\_session\_config\_file;
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [// Zero means server will not poll FS for
model config file after start-up.]{.comment}
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  tensorflow::int32
fs\_model\_config\_poll\_wait\_seconds = 0;
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  [bool]{.keywordtype} enable\_model\_warmup =
[true]{.keyword};
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [// This value is used only if \>
0.]{.comment}
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  tensorflow::int32
num\_request\_iterations\_for\_warmup = 0;
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  tensorflow::string monitoring\_config\_file;
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  [// Tensorflow session run
options.]{.comment}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  [bool]{.keywordtype}
enforce\_session\_run\_timeout = [true]{.keyword};
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  [bool]{.keywordtype}
remove\_unused\_fields\_from\_bundle\_metagraph = [true]{.keyword};
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  [bool]{.keywordtype} prefer\_tflite\_model =
[false]{.keyword};
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  tensorflow::int32 num\_tflite\_pools =
port::NumSchedulableCPUs();
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  tensorflow::int32
num\_tflite\_interpreters\_per\_pool = 1;
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  tensorflow::string
thread\_pool\_factory\_config\_file;
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [bool]{.keywordtype}
enable\_signature\_method\_name\_check = [false]{.keyword};
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  [bool]{.keywordtype} enable\_profiler =
[true]{.keyword};
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  tensorflow::string mixed\_precision;
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  [bool]{.keywordtype} skip\_initialize\_tpu =
[false]{.keyword};
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  [// Misc GRPC features]{.comment}
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [bool]{.keywordtype}
enable\_grpc\_healthcheck\_service = [false]{.keyword};
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} 
[Options](structtensorflow_1_1serving_1_1main_1_1Server_1_1Options.html){.code}();
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  };
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} 
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  [// Blocks the current thread waiting for
servers (if any)]{.comment}
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  [// started as part of BuildAndStart()
call.]{.comment}
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} 
\~[Server](classtensorflow_1_1serving_1_1main_1_1Server.html){.code}();
:::

::: {.line}
[]{#l00114}[ 114]{.lineno} 
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  [// Build and start gRPC (and optionally
HTTP) server, to be ready to]{.comment}
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  [// accept and process new requests over
gRPC (and optionally HTTP/REST).]{.comment}
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  Status BuildAndStart([const]{.keyword}
[Options](structtensorflow_1_1serving_1_1main_1_1Server_1_1Options.html){.code}&
server\_options);
:::

::: {.line}
[]{#l00118}[ 118]{.lineno} 
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  [// Wait for servers started in
BuildAndStart() above to terminate.]{.comment}
:::

::: {.line}
[]{#l00120}[ 120]{.lineno}  [// This will block the current thread until
termination is successful.]{.comment}
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  [void]{.keywordtype} WaitForTermination();
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} 
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  [// Polls the filesystem, parses config at
specified path, and calls]{.comment}
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  [// ServerCore::ReloadConfig with the
captured model config.]{.comment}
:::

::: {.line}
[]{#l00126}[ 126]{.lineno}  [void]{.keywordtype}
PollFilesystemAndReloadConfig([const]{.keyword} [string]{.keywordtype}&
config\_file\_path);
:::

::: {.line}
[]{#l00127}[ 127]{.lineno} 
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  std::unique\_ptr\<ServerCore\>
server\_core\_;
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  std::unique\_ptr\<ModelServiceImpl\>
model\_service\_;
:::

::: {.line}
[]{#l00130}[ 130]{.lineno} 
std::unique\_ptr\<PredictionService::Service\> prediction\_service\_;
:::

::: {.line}
[]{#l00131}[ 131]{.lineno} 
std::unique\_ptr\<tensorflow::grpc::ProfilerService::Service\>
profiler\_service\_;
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  std::unique\_ptr\<::grpc::Server\>
grpc\_server\_;
:::

::: {.line}
[]{#l00133}[ 133]{.lineno} 
std::unique\_ptr\<net\_http::HTTPServerInterface\> http\_server\_;
:::

::: {.line}
[]{#l00134}[ 134]{.lineno}  [// A thread that calls
PollFilesystemAndReloadConfig() periodically if]{.comment}
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  [// fs\_model\_config\_poll\_wait\_seconds
\> 0.]{.comment}
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  std::unique\_ptr\<PeriodicFunction\>
fs\_config\_polling\_thread\_;
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  std::unique\_ptr\<ThreadPoolFactory\>
thread\_pool\_factory\_;
:::

::: {.line}
[]{#l00138}[ 138]{.lineno} };
:::

::: {.line}
[]{#l00139}[ 139]{.lineno} 
:::

::: {.line}
[]{#l00140}[ 140]{.lineno} } [// namespace main]{.comment}
:::

::: {.line}
[]{#l00141}[ 141]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00142}[ 142]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00143}[ 143]{.lineno} 
:::

::: {.line}
[]{#l00144}[ 144]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_SERVER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1main_1_1Server_html .ttc}
::: {.ttname}
[tensorflow::serving::main::Server](classtensorflow_1_1serving_1_1main_1_1Server.html)
:::

::: {.ttdef}
**Definition:** server.h:37
:::
:::

::: {#astructtensorflow_1_1serving_1_1main_1_1Server_1_1Options_html .ttc}
::: {.ttname}
[tensorflow::serving::main::Server::Options](structtensorflow_1_1serving_1_1main_1_1Server_1_1Options.html)
:::

::: {.ttdef}
**Definition:** server.h:39
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

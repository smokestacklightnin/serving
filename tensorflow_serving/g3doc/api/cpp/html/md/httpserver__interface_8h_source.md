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
-   [server](dir_8888e4e61b8af1df5068a6bf52638e77.html){.el}
-   [public](dir_f270ff06e372d77ace79fc5b2d9d4fbc.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
httpserver\_interface.h
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
[]{#l00016}[ 16]{.lineno} [// APIs for the HTTP server.]{.comment}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} 
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_SERVER\_PUBLIC\_HTTPSERVER\_INTERFACE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#define
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_SERVER\_PUBLIC\_HTTPSERVER\_INTERFACE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<cassert\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} 
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include \<functional\>]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} 
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"absl/strings/string\_view.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"absl/time/time.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} 
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow\_serving/util/net\_http/server/public/server\_request\_interface.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} 
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [namespace ]{.keyword}net\_http {
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} 
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [// A non-blocking executor for processing I/O
polling or callback events.]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [// TODO: move EventExecutor into
ServerOptions]{.comment}
:::

::: {.line}
[]{#l00038}[
[38](classtensorflow_1_1serving_1_1net__http_1_1EventExecutor.html){.line}]{.lineno} [class
]{.keyword}[EventExecutor](classtensorflow_1_1serving_1_1net__http_1_1EventExecutor.html){.code}
{
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [virtual]{.keyword}
\~[EventExecutor](classtensorflow_1_1serving_1_1net__http_1_1EventExecutor.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} 
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
[EventExecutor](classtensorflow_1_1serving_1_1net__http_1_1EventExecutor.html){.code}([const]{.keyword}
[EventExecutor](classtensorflow_1_1serving_1_1net__http_1_1EventExecutor.html){.code}&
other) = [delete]{.keyword};
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} 
[EventExecutor](classtensorflow_1_1serving_1_1net__http_1_1EventExecutor.html){.code}&
operator=([const]{.keyword}
[EventExecutor](classtensorflow_1_1serving_1_1net__http_1_1EventExecutor.html){.code}&
other) = [delete]{.keyword};
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [// Schedule the specified \'fn\' for
execution in this executor.]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [// Must be non-blocking]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [virtual]{.keyword} [void]{.keywordtype}
Schedule(std::function\<[void]{.keywordtype}()\> fn) = 0;
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} 
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [protected]{.keyword}:
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} 
[EventExecutor](classtensorflow_1_1serving_1_1net__http_1_1EventExecutor.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} };
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} 
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} [// Options to specify when a server instance
is created.]{.comment}
:::

::: {.line}
[]{#l00054}[
[54](classtensorflow_1_1serving_1_1net__http_1_1ServerOptions.html){.line}]{.lineno} [class
]{.keyword}[ServerOptions](classtensorflow_1_1serving_1_1net__http_1_1ServerOptions.html){.code}
{
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} 
[ServerOptions](classtensorflow_1_1serving_1_1net__http_1_1ServerOptions.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} 
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [// At least one port has to be
configured.]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [// Port 0 will start the server using an
ephemeral port.]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [void]{.keywordtype}
AddPort([int]{.keywordtype} port) {
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  assert(port \>= 0);
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  ports\_.emplace\_back(port);
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  }
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [// The default executor for running I/O
event polling.]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [// This is a mandatory option.]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [void]{.keywordtype}
SetExecutor(std::unique\_ptr\<EventExecutor\> executor) {
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  executor\_ = std::move(executor);
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  }
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} 
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  [const]{.keyword} std::vector\<int\>&
ports()[ const ]{.keyword}{ [return]{.keywordflow} ports\_; }
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} 
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} 
[EventExecutor](classtensorflow_1_1serving_1_1net__http_1_1EventExecutor.html){.code}\*
executor()[ const ]{.keyword}{ [return]{.keywordflow} executor\_.get();
}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} 
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  std::vector\<int\> ports\_;
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  std::unique\_ptr\<EventExecutor\> executor\_;
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} };
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} 
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} [// Options to specify when registering a
handler (given a uri pattern).]{.comment}
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} [// This should be a value type.]{.comment}
:::

::: {.line}
[]{#l00082}[
[82](classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions.html){.line}]{.lineno} [class
]{.keyword}[RequestHandlerOptions](classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions.html){.code}
{
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} 
[RequestHandlerOptions](classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} 
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} 
[RequestHandlerOptions](classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions.html){.code}([const]{.keyword}
[RequestHandlerOptions](classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions.html){.code}&)
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} 
[RequestHandlerOptions](classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions.html){.code}&
operator=([const]{.keyword}
[RequestHandlerOptions](classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions.html){.code}&)
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} 
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [// Sets the max length of uncompressed data
when uncompressing a request body]{.comment}
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  [inline]{.keyword}
[RequestHandlerOptions](classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions.html){.code}&
set\_auto\_uncompress\_max\_size(int64\_t size) {
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  auto\_uncompress\_max\_size\_ = size;
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [return]{.keywordflow} \*[this]{.keyword};
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  }
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} 
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  [// The max length of uncompressed data when
doing uncompress. Returns 0 if]{.comment}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  [// not set. See Zlib::kMaxUncompressedBytes
for the default config.]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  [inline]{.keyword} int64\_t
auto\_uncompress\_max\_size()[ const ]{.keyword}{
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  [return]{.keywordflow}
auto\_uncompress\_max\_size\_;
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  }
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} 
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  [// The auto\_uncompress\_input option
specifies whether the request]{.comment}
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [// input data should be uncompressed if the
request has the]{.comment}
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  [// Content-Encoding: .\*gzip.\* header. The
option defaults to true.]{.comment}
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  [inline]{.keyword}
[RequestHandlerOptions](classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions.html){.code}&
set\_auto\_uncompress\_input(
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  [bool]{.keywordtype} should\_uncompress) {
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  auto\_uncompress\_input\_ =
should\_uncompress;
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [return]{.keywordflow} \*[this]{.keyword};
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  }
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} 
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  [inline]{.keyword} [bool]{.keywordtype}
auto\_uncompress\_input()[ const ]{.keyword}{ [return]{.keywordflow}
auto\_uncompress\_input\_; }
:::

::: {.line}
[]{#l00111}[ 111]{.lineno} 
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  [// To be added: compression, CORS rules,
streaming control]{.comment}
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [// thread executor, admission control,
limits \...]{.comment}
:::

::: {.line}
[]{#l00115}[ 115]{.lineno} 
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  [bool]{.keywordtype}
auto\_uncompress\_input\_ = [true]{.keyword};
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} 
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  int64\_t auto\_uncompress\_max\_size\_ = 0;
:::

::: {.line}
[]{#l00119}[ 119]{.lineno} };
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} 
:::

::: {.line}
[]{#l00121}[ 121]{.lineno} [// A request handler is registered by the
application to handle a request]{.comment}
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} [// based on the request Uri path, available
via ServerRequestInterface.]{.comment}
:::

::: {.line}
[]{#l00123}[ 123]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00124}[ 124]{.lineno} [// Request handlers need be completely
non-blocking. And handlers may add]{.comment}
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} [// callbacks to a thread-pool that is
managed by the application itself.]{.comment}
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} [typedef]{.keyword}
std::function\<void([ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.code}\*)\>
RequestHandler;
:::

::: {.line}
[]{#l00127}[ 127]{.lineno} 
:::

::: {.line}
[]{#l00128}[ 128]{.lineno} [// Returns a nullptr if the request is not
handled by this dispatcher.]{.comment}
:::

::: {.line}
[]{#l00129}[ 129]{.lineno} [typedef]{.keyword}
std::function\<RequestHandler([ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.code}\*)\>
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  RequestDispatcher;
:::

::: {.line}
[]{#l00131}[ 131]{.lineno} 
:::

::: {.line}
[]{#l00132}[ 132]{.lineno} [// This interface class specifies the API
contract for the HTTP server.]{.comment}
:::

::: {.line}
[]{#l00133}[ 133]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00134}[ 134]{.lineno} [// Requirements for
implementations:]{.comment}
:::

::: {.line}
[]{#l00135}[ 135]{.lineno} [// - must be thread-safe]{.comment}
:::

::: {.line}
[]{#l00136}[ 136]{.lineno} [// - multiple HTTP server instances need be
supported in a single process]{.comment}
:::

::: {.line}
[]{#l00137}[ 137]{.lineno} [// - for a basic implementation, the
application needs provide a dedicated]{.comment}
:::

::: {.line}
[]{#l00138}[ 138]{.lineno} [// thread to handle all I/O events, i.e. the
thread that calls]{.comment}
:::

::: {.line}
[]{#l00139}[ 139]{.lineno} [// StartAcceptingRequests().]{.comment}
:::

::: {.line}
[]{#l00140}[ 140]{.lineno} [// - the arrival order of concurrent
requests is insignificant because the]{.comment}
:::

::: {.line}
[]{#l00141}[ 141]{.lineno} [// server runtime and I/O are completely
event-driven.]{.comment}
:::

::: {.line}
[]{#l00142}[
[142](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.line}]{.lineno} [class
]{.keyword}[HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.code}
{
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00144}[ 144]{.lineno}  [virtual]{.keyword}
\~[HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00145}[ 145]{.lineno} 
:::

::: {.line}
[]{#l00146}[ 146]{.lineno} 
[HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.code}([const]{.keyword}
[HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.code}&
other) = [delete]{.keyword};
:::

::: {.line}
[]{#l00147}[ 147]{.lineno} 
[HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.code}&
operator=([const]{.keyword}
[HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.code}&
other) = [delete]{.keyword};
:::

::: {.line}
[]{#l00148}[ 148]{.lineno} 
:::

::: {.line}
[]{#l00149}[ 149]{.lineno}  [// Starts to accept requests arrived on the
network.]{.comment}
:::

::: {.line}
[]{#l00150}[ 150]{.lineno}  [// Returns false if the server runtime
fails to initialize properly.]{.comment}
:::

::: {.line}
[]{#l00151}[ 151]{.lineno}  [virtual]{.keyword} [bool]{.keywordtype}
StartAcceptingRequests() = 0;
:::

::: {.line}
[]{#l00152}[ 152]{.lineno} 
:::

::: {.line}
[]{#l00153}[ 153]{.lineno}  [// Returns true if StartAcceptingRequests()
has been called.]{.comment}
:::

::: {.line}
[]{#l00154}[ 154]{.lineno}  [virtual]{.keyword} [bool]{.keywordtype}
is\_accepting\_requests() [const]{.keyword} = 0;
:::

::: {.line}
[]{#l00155}[ 155]{.lineno} 
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  [// Returns the server listener port if any,
or else returns 0.]{.comment}
:::

::: {.line}
[]{#l00157}[ 157]{.lineno}  [virtual]{.keyword} [int]{.keywordtype}
listen\_port() [const]{.keyword} = 0;
:::

::: {.line}
[]{#l00158}[ 158]{.lineno} 
:::

::: {.line}
[]{#l00159}[ 159]{.lineno}  [// Starts the server termination, and
returns immediately.]{.comment}
:::

::: {.line}
[]{#l00160}[ 160]{.lineno}  [virtual]{.keyword} [void]{.keywordtype}
Terminate() = 0;
:::

::: {.line}
[]{#l00161}[ 161]{.lineno} 
:::

::: {.line}
[]{#l00162}[ 162]{.lineno}  [// Returns true if Terminate() has been
called.]{.comment}
:::

::: {.line}
[]{#l00163}[ 163]{.lineno}  [virtual]{.keyword} [bool]{.keywordtype}
is\_terminating() [const]{.keyword} = 0;
:::

::: {.line}
[]{#l00164}[ 164]{.lineno} 
:::

::: {.line}
[]{#l00165}[ 165]{.lineno}  [// Blocks the calling thread until the
server is terminated and safe]{.comment}
:::

::: {.line}
[]{#l00166}[ 166]{.lineno}  [// to destroy.]{.comment}
:::

::: {.line}
[]{#l00167}[ 167]{.lineno}  [virtual]{.keyword} [void]{.keywordtype}
WaitForTermination() = 0;
:::

::: {.line}
[]{#l00168}[ 168]{.lineno} 
:::

::: {.line}
[]{#l00169}[ 169]{.lineno}  [// Blocks the calling thread until the
server is terminated and safe]{.comment}
:::

::: {.line}
[]{#l00170}[ 170]{.lineno}  [// to destroy, or until the specified
timeout elapses. Returns true]{.comment}
:::

::: {.line}
[]{#l00171}[ 171]{.lineno}  [// if safe termination completed within the
timeout, and false otherwise.]{.comment}
:::

::: {.line}
[]{#l00172}[ 172]{.lineno}  [virtual]{.keyword} [bool]{.keywordtype}
WaitForTerminationWithTimeout(absl::Duration timeout) = 0;
:::

::: {.line}
[]{#l00173}[ 173]{.lineno} 
:::

::: {.line}
[]{#l00174}[ 174]{.lineno}  [// To be specified: lameduck]{.comment}
:::

::: {.line}
[]{#l00175}[ 175]{.lineno} 
:::

::: {.line}
[]{#l00176}[ 176]{.lineno}  [// Registers a request handler with exact
URI path matching.]{.comment}
:::

::: {.line}
[]{#l00177}[ 177]{.lineno}  [// Any existing handler under the same uri
will be overwritten.]{.comment}
:::

::: {.line}
[]{#l00178}[ 178]{.lineno}  [// The server owns the handler after
registration.]{.comment}
:::

::: {.line}
[]{#l00179}[ 179]{.lineno}  [// Handlers may be registered after the
server has been started.]{.comment}
:::

::: {.line}
[]{#l00180}[ 180]{.lineno}  [virtual]{.keyword} [void]{.keywordtype}
RegisterRequestHandler(absl::string\_view uri,
:::

::: {.line}
[]{#l00181}[ 181]{.lineno}  RequestHandler handler,
:::

::: {.line}
[]{#l00182}[ 182]{.lineno}  [const]{.keyword}
[RequestHandlerOptions](classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions.html){.code}&
options) = 0;
:::

::: {.line}
[]{#l00183}[ 183]{.lineno} 
:::

::: {.line}
[]{#l00184}[ 184]{.lineno}  [// Registers a request dispatcher, i.e.
application-provided URI dispatching]{.comment}
:::

::: {.line}
[]{#l00185}[ 185]{.lineno}  [// logic, e.g. a regexp based
one.]{.comment}
:::

::: {.line}
[]{#l00186}[ 186]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00187}[ 187]{.lineno}  [// For a given request, dispatchers are
only invoked if there is no exact URI]{.comment}
:::

::: {.line}
[]{#l00188}[ 188]{.lineno}  [// path matching to any registered request
handler.]{.comment}
:::

::: {.line}
[]{#l00189}[ 189]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00190}[ 190]{.lineno}  [// Dispatchers are invoked in order of
registration, i.e. first registered]{.comment}
:::

::: {.line}
[]{#l00191}[ 191]{.lineno}  [// gets first pick. The server owns the
dispatcher after registration.]{.comment}
:::

::: {.line}
[]{#l00192}[ 192]{.lineno}  [// Dispatchers may be registered after the
server has been started.]{.comment}
:::

::: {.line}
[]{#l00193}[ 193]{.lineno}  [virtual]{.keyword} [void]{.keywordtype}
RegisterRequestDispatcher(
:::

::: {.line}
[]{#l00194}[ 194]{.lineno}  RequestDispatcher dispatcher,
[const]{.keyword}
[RequestHandlerOptions](classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions.html){.code}&
options) = 0;
:::

::: {.line}
[]{#l00195}[ 195]{.lineno} 
:::

::: {.line}
[]{#l00196}[ 196]{.lineno}  [// To be added: unregister (if
needed)]{.comment}
:::

::: {.line}
[]{#l00197}[ 197]{.lineno} 
:::

::: {.line}
[]{#l00198}[ 198]{.lineno}  [protected]{.keyword}:
:::

::: {.line}
[]{#l00199}[ 199]{.lineno} 
[HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00200}[ 200]{.lineno} };
:::

::: {.line}
[]{#l00201}[ 201]{.lineno} 
:::

::: {.line}
[]{#l00202}[ 202]{.lineno} } [// namespace net\_http]{.comment}
:::

::: {.line}
[]{#l00203}[ 203]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00204}[ 204]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00205}[ 205]{.lineno} 
:::

::: {.line}
[]{#l00206}[ 206]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_SERVER\_PUBLIC\_HTTPSERVER\_INTERFACE\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1net__http_1_1EventExecutor_html .ttc}
::: {.ttname}
[tensorflow::serving::net\_http::EventExecutor](classtensorflow_1_1serving_1_1net__http_1_1EventExecutor.html)
:::

::: {.ttdef}
**Definition:** httpserver\_interface.h:38
:::
:::

::: {#aclasstensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface_html .ttc}
::: {.ttname}
[tensorflow::serving::net\_http::HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html)
:::

::: {.ttdef}
**Definition:** httpserver\_interface.h:142
:::
:::

::: {#aclasstensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions_html .ttc}
::: {.ttname}
[tensorflow::serving::net\_http::RequestHandlerOptions](classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions.html)
:::

::: {.ttdef}
**Definition:** httpserver\_interface.h:82
:::
:::

::: {#aclasstensorflow_1_1serving_1_1net__http_1_1ServerOptions_html .ttc}
::: {.ttname}
[tensorflow::serving::net\_http::ServerOptions](classtensorflow_1_1serving_1_1net__http_1_1ServerOptions.html)
:::

::: {.ttdef}
**Definition:** httpserver\_interface.h:54
:::
:::

::: {#aclasstensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_html .ttc}
::: {.ttname}
[tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html)
:::

::: {.ttdef}
**Definition:** server\_request\_interface.h:42
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

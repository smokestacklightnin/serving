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
-   [internal](dir_7ca4e85f5b3c9affb60e28a6024c2ea6.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
evhttp\_server.h
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
[]{#l00016}[ 16]{.lineno} [// libevent based server
implementation]{.comment}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} 
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_SERVER\_INTERNAL\_EVHTTP\_SERVER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#define
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_SERVER\_INTERNAL\_EVHTTP\_SERVER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<cstdint\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<ctime\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include \<unordered\_map\>]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} 
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"absl/base/thread\_annotations.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"absl/synchronization/mutex.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} 
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"absl/synchronization/notification.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} 
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [\#include
\"tensorflow\_serving/util/net\_http/server/internal/evhttp\_request.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [\#include
\"tensorflow\_serving/util/net\_http/server/internal/server\_support.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [\#include
\"tensorflow\_serving/util/net\_http/server/public/httpserver\_interface.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} 
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [struct ]{.keyword}event\_base;
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [struct ]{.keyword}evhttp;
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [struct ]{.keyword}evhttp\_bound\_socket;
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [struct ]{.keyword}evhttp\_request;
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} 
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [namespace ]{.keyword}net\_http {
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
:::

::: {.line}
[]{#l00045}[
[45](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.line}]{.lineno} [class
]{.keyword}[EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.code}
final : [public]{.keyword}
[HTTPServerInterface](classtensorflow_1_1serving_1_1net__http_1_1HTTPServerInterface.html){.code},
[ServerSupport](classtensorflow_1_1serving_1_1net__http_1_1ServerSupport.html){.code}
{
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [virtual]{.keyword}
\~[EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.code}();
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} 
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
[EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.code}([const]{.keyword}
[EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.code}&
other) = [delete]{.keyword};
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} 
[EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.code}&
operator=([const]{.keyword}
[EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.code}&
other) = [delete]{.keyword};
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [explicit]{.keyword}
[EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html){.code}(std::unique\_ptr\<ServerOptions\>
options);
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} 
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [bool]{.keywordtype} Initialize();
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} 
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [bool]{.keywordtype} StartAcceptingRequests()
[override]{.keyword};
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} 
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [bool]{.keywordtype}
is\_accepting\_requests() [const override]{.keyword};
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} 
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [int]{.keywordtype} listen\_port() [const
override]{.keyword};
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} 
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [void]{.keywordtype} Terminate()
[override]{.keyword};
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} 
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  [bool]{.keywordtype} is\_terminating() [const
override]{.keyword};
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} 
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [void]{.keywordtype} WaitForTermination()
[override]{.keyword};
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [bool]{.keywordtype}
WaitForTerminationWithTimeout(absl::Duration timeout)
[override]{.keyword};
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [void]{.keywordtype}
RegisterRequestHandler(absl::string\_view uri, RequestHandler handler,
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  [const]{.keyword}
[RequestHandlerOptions](classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions.html){.code}&
options) [override]{.keyword};
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} 
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [void]{.keywordtype}
RegisterRequestDispatcher(RequestDispatcher dispatcher,
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  [const]{.keyword}
[RequestHandlerOptions](classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions.html){.code}&
options) [override]{.keyword};
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} 
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [void]{.keywordtype} IncOps()
[override]{.keyword};
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [void]{.keywordtype} DecOps()
[override]{.keyword};
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} 
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  [bool]{.keywordtype}
EventLoopSchedule(std::function\<[void]{.keywordtype}()\> fn)
[override]{.keyword};
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} 
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  [static]{.keyword} [void]{.keywordtype}
DispatchEvRequestFn([struct]{.keyword} evhttp\_request\* req,
[void]{.keywordtype}\* server);
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} 
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [void]{.keywordtype}
DispatchEvRequest([struct]{.keyword} evhttp\_request\* req);
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} 
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  [void]{.keywordtype}
ScheduleHandlerReference([const]{.keyword} RequestHandler& handler,
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} 
[EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.code}\*
ev\_request)
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} 
ABSL\_EXCLUSIVE\_LOCKS\_REQUIRED(request\_mu\_);
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [void]{.keywordtype}
ScheduleHandler(RequestHandler&& handler,
[EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.code}\*
ev\_request)
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} 
ABSL\_EXCLUSIVE\_LOCKS\_REQUIRED(request\_mu\_);
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} 
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [struct ]{.keyword}UriHandlerInfo {
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  UriHandlerInfo(absl::string\_view uri\_in,
RequestHandler handler\_in,
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  [const]{.keyword}
[RequestHandlerOptions](classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions.html){.code}&
options\_in);
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  [const]{.keyword} std::string uri;
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  [const]{.keyword} RequestHandler handler;
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  [const]{.keyword}
[RequestHandlerOptions](classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions.html){.code}
options;
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  };
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} 
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  [struct ]{.keyword}DispatcherInfo {
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  DispatcherInfo(RequestDispatcher
dispatcher\_in,
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  [const]{.keyword}
[RequestHandlerOptions](classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions.html){.code}&
options\_in);
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} 
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  [const]{.keyword} RequestDispatcher
dispatcher;
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [const]{.keyword}
[RequestHandlerOptions](classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions.html){.code}
options;
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  };
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} 
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  std::unique\_ptr\<ServerOptions\>
server\_options\_;
:::

::: {.line}
[]{#l00111}[ 111]{.lineno} 
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  [// Started accepting requests.]{.comment}
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  absl::Notification accepting\_requests\_;
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [// Listener port]{.comment}
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  [int]{.keywordtype} port\_ = 0;
:::

::: {.line}
[]{#l00116}[ 116]{.lineno} 
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  [// Started terminating the server, i.e.
Terminate() has been called]{.comment}
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  absl::Notification terminating\_;
:::

::: {.line}
[]{#l00119}[ 119]{.lineno} 
:::

::: {.line}
[]{#l00120}[ 120]{.lineno}  [// Tracks the \# of pending
operations]{.comment}
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  [mutable]{.keyword} absl::Mutex ops\_mu\_;
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  int64\_t num\_pending\_ops\_
ABSL\_GUARDED\_BY(ops\_mu\_) = 0;
:::

::: {.line}
[]{#l00123}[ 123]{.lineno} 
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  [mutable]{.keyword} absl::Mutex
request\_mu\_;
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  std::unordered\_map\<std::string,
UriHandlerInfo\> uri\_handlers\_
:::

::: {.line}
[]{#l00126}[ 126]{.lineno}  ABSL\_GUARDED\_BY(request\_mu\_);
:::

::: {.line}
[]{#l00127}[ 127]{.lineno}  std::vector\<DispatcherInfo\> dispatchers\_
ABSL\_GUARDED\_BY(request\_mu\_);
:::

::: {.line}
[]{#l00128}[ 128]{.lineno} 
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  [// ev instances]{.comment}
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  event\_base\* ev\_base\_ =
[nullptr]{.keyword};
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  evhttp\* ev\_http\_ = [nullptr]{.keyword};
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  evhttp\_bound\_socket\* ev\_listener\_ =
[nullptr]{.keyword};
:::

::: {.line}
[]{#l00133}[ 133]{.lineno} 
:::

::: {.line}
[]{#l00134}[ 134]{.lineno}  [// Timeval used to register immediate
callbacks, which are called]{.comment}
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  [// in the order that they are
registered.]{.comment}
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  [const]{.keyword} timeval\* immediate\_;
:::

::: {.line}
[]{#l00137}[ 137]{.lineno} };
:::

::: {.line}
[]{#l00138}[ 138]{.lineno} 
:::

::: {.line}
[]{#l00139}[ 139]{.lineno} } [// namespace net\_http]{.comment}
:::

::: {.line}
[]{#l00140}[ 140]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00141}[ 141]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00142}[ 142]{.lineno} 
:::

::: {.line}
[]{#l00143}[ 143]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_SERVER\_INTERNAL\_EVHTTP\_SERVER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_html .ttc}
::: {.ttname}
[tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html)
:::

::: {.ttdef}
**Definition:** evhttp\_request.h:65
:::
:::

::: {#aclasstensorflow_1_1serving_1_1net__http_1_1EvHTTPServer_html .ttc}
::: {.ttname}
[tensorflow::serving::net\_http::EvHTTPServer](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPServer.html)
:::

::: {.ttdef}
**Definition:** evhttp\_server.h:45
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

::: {#aclasstensorflow_1_1serving_1_1net__http_1_1ServerSupport_html .ttc}
::: {.ttname}
[tensorflow::serving::net\_http::ServerSupport](classtensorflow_1_1serving_1_1net__http_1_1ServerSupport.html)
:::

::: {.ttdef}
**Definition:** server\_support.h:31
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

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
-   [client](dir_d1f4c45ba788687d66f9beca8a90b565.html){.el}
-   [test\_client](dir_c5608d91c5c2f8da3a0afcdf2e4d91fb.html){.el}
-   [internal](dir_d82273ebfb3c8254d0e91238f16dccf3.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
evhttp\_connection.h
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
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_CLIENT\_TEST\_CLIENT\_INTERNAL\_EVHTTP\_CONNECTION\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_CLIENT\_TEST\_CLIENT\_INTERNAL\_EVHTTP\_CONNECTION\_H\_]{.preprocessor}
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
[]{#l00021}[ 21]{.lineno} [\#include \<string\>]{.preprocessor}
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
\"absl/strings/string\_view.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"absl/synchronization/notification.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"libevent/include/event2/buffer.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"libevent/include/event2/bufferevent.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"libevent/include/event2/event.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"libevent/include/event2/http.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include
\"libevent/include/event2/keyvalq\_struct.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [\#include
\"libevent/include/event2/util.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} 
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// TODO(wenboz): move EventExecutor to
net\_http/common]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [\#include
\"tensorflow\_serving/util/net\_http/client/test\_client/public/httpclient\_interface.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [\#include
\"tensorflow\_serving/util/net\_http/server/public/httpserver\_interface.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} 
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [namespace ]{.keyword}net\_http {
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} 
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [// The following types may be moved to an API
interface in future.]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} 
:::

::: {.line}
[]{#l00044}[
[44](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.line}]{.lineno} [class
]{.keyword}[TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.code}
final : [public]{.keyword}
[TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.code}
{
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} 
[TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} 
\~[TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} 
[TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.code}([const]{.keyword}
[TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.code}&
other) = [delete]{.keyword};
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
[TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.code}&
operator=([const]{.keyword}
[TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html){.code}&
other) = [delete]{.keyword};
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} 
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [// Terminates the connection.]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [void]{.keywordtype} Terminate()
[override]{.keyword};
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} 
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [// Returns a new connection given an
absolute URL.]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [// Always treat the URL scheme as \"http\"
for now.]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [// Returns nullptr if any error]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [static]{.keyword}
std::unique\_ptr\<TestEvHTTPConnection\> Connect(absl::string\_view
url);
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [// Returns a new connection to the specified
host:port.]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [// Returns nullptr if any error]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [static]{.keyword}
std::unique\_ptr\<TestEvHTTPConnection\> Connect(absl::string\_view
host,
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  [int]{.keywordtype} port);
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} 
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [// Returns a new connection to the specified
port of localhost.]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [// Returns nullptr if any error]{.comment}
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [static]{.keyword}
std::unique\_ptr\<TestEvHTTPConnection\>
ConnectLocal([int]{.keywordtype} port) {
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [return]{.keywordflow}
Connect([\"localhost\"]{.stringliteral}, port);
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  }
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} 
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [// Sends a request and blocks the caller
till a response is received]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [// or any error has happened.]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  [// Returns false if any error.]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [bool]{.keywordtype}
BlockingSendRequest([const]{.keyword}
[TestClientRequest](structtensorflow_1_1serving_1_1net__http_1_1TestClientRequest.html){.code}&
request,
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} 
[TestClientResponse](structtensorflow_1_1serving_1_1net__http_1_1TestClientResponse.html){.code}\*
response) [override]{.keyword};
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} 
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [// Sends a request and returns immediately.
The response will be handled]{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  [// asynchronously via the response-\>done
callback.]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [// Returns false if any error in sending the
request, or if the executor]{.comment}
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  [// has not been configured.]{.comment}
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  [bool]{.keywordtype}
SendRequest([const]{.keyword}
[TestClientRequest](structtensorflow_1_1serving_1_1net__http_1_1TestClientRequest.html){.code}&
request,
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} 
[TestClientResponse](structtensorflow_1_1serving_1_1net__http_1_1TestClientResponse.html){.code}\*
response) [override]{.keyword};
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} 
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  [// Sets the executor for processing requests
asynchronously.]{.comment}
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  [void]{.keywordtype}
SetExecutor(std::unique\_ptr\<EventExecutor\> executor)
[override]{.keyword};
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} 
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [struct ]{.keyword}event\_base\* ev\_base\_;
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  [struct ]{.keyword}evhttp\_uri\* http\_uri\_;
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  [struct ]{.keyword}evhttp\_connection\*
evcon\_;
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} 
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  std::unique\_ptr\<EventExecutor\> executor\_;
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} 
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  std::unique\_ptr\<absl::Notification\>
loop\_exit\_;
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} };
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} 
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} } [// namespace net\_http]{.comment}
:::

::: {.line}
[]{#l00099}[ 99]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} 
:::

::: {.line}
[]{#l00102}[ 102]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_CLIENT\_TEST\_CLIENT\_INTERNAL\_EVHTTP\_CONNECTION\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection_html .ttc}
::: {.ttname}
[tensorflow::serving::net\_http::TestEvHTTPConnection](classtensorflow_1_1serving_1_1net__http_1_1TestEvHTTPConnection.html)
:::

::: {.ttdef}
**Definition:** evhttp\_connection.h:44
:::
:::

::: {#aclasstensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface_html .ttc}
::: {.ttname}
[tensorflow::serving::net\_http::TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html)
:::

::: {.ttdef}
**Definition:** httpclient\_interface.h:51
:::
:::

::: {#astructtensorflow_1_1serving_1_1net__http_1_1TestClientRequest_html .ttc}
::: {.ttname}
[tensorflow::serving::net\_http::TestClientRequest](structtensorflow_1_1serving_1_1net__http_1_1TestClientRequest.html)
:::

::: {.ttdef}
**Definition:** httpclient\_interface.h:30
:::
:::

::: {#astructtensorflow_1_1serving_1_1net__http_1_1TestClientResponse_html .ttc}
::: {.ttname}
[tensorflow::serving::net\_http::TestClientResponse](structtensorflow_1_1serving_1_1net__http_1_1TestClientResponse.html)
:::

::: {.ttdef}
**Definition:** httpclient\_interface.h:40
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

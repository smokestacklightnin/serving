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
-   [public](dir_a9fbe37892c0cf542a0391af6887d78b.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
httpclient\_interface.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2020 Google Inc. All Rights
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
THIRD\_PARTY\_TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_CLIENT\_TEST\_CLIENT\_PUBLIC\_HTTPCLIENT\_INTERFACE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
THIRD\_PARTY\_TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_CLIENT\_TEST\_CLIENT\_PUBLIC\_HTTPCLIENT\_INTERFACE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include
\"tensorflow\_serving/util/net\_http/public/response\_code\_enum.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include
\"tensorflow\_serving/util/net\_http/server/public/httpserver\_interface.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} 
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [// API for the HTTP Client]{.comment}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [// NOTE: This API is not yet finalized, and
should be considered experimental.]{.comment}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} 
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [namespace ]{.keyword}net\_http {
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} 
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [// Data to be copied]{.comment}
:::

::: {.line}
[]{#l00030}[
[30](structtensorflow_1_1serving_1_1net__http_1_1TestClientRequest.html){.line}]{.lineno} [struct
]{.keyword}[TestClientRequest](structtensorflow_1_1serving_1_1net__http_1_1TestClientRequest.html){.code}
{
:::

::: {.line}
[]{#l00031}[ 31]{.lineno}  [typedef]{.keyword}
std::pair\<absl::string\_view, absl::string\_view\> HeaderKeyValue;
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} 
:::

::: {.line}
[]{#l00033}[ 33]{.lineno}  absl::string\_view uri\_path;
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  absl::string\_view method; [// must be in
upper-case]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  std::vector\<HeaderKeyValue\> headers;
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  absl::string\_view body;
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} };
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [// Caller allocates the data for
output]{.comment}
:::

::: {.line}
[]{#l00040}[
[40](structtensorflow_1_1serving_1_1net__http_1_1TestClientResponse.html){.line}]{.lineno} [struct
]{.keyword}[TestClientResponse](structtensorflow_1_1serving_1_1net__http_1_1TestClientResponse.html){.code}
{
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [typedef]{.keyword} std::pair\<std::string,
std::string\> HeaderKeyValue;
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} 
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  HTTPStatusCode status =
HTTPStatusCode::UNDEFINED;
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  std::vector\<HeaderKeyValue\> headers;
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  std::string body;
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} 
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  std::function\<void()\> done; [//
callback]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} };
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [// This interface class specifies the API
contract for the HTTP client.]{.comment}
:::

::: {.line}
[]{#l00051}[
[51](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.line}]{.lineno} [class
]{.keyword}[TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.code}
{
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} 
[TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.code}([const]{.keyword}
[TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.code}&
other) = [delete]{.keyword};
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} 
[TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.code}&
operator=([const]{.keyword}
[TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.code}&
other) =
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [delete]{.keyword};
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} 
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [virtual]{.keyword}
\~[TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} 
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [// Terminates the connection.]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [virtual]{.keyword} [void]{.keywordtype}
Terminate() = 0;
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} 
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [// Sends a request and blocks the caller
till a response is received]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [// or any error has happened.]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  [// Returns false if any error.]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [virtual]{.keyword} [bool]{.keywordtype}
BlockingSendRequest([const]{.keyword}
[TestClientRequest](structtensorflow_1_1serving_1_1net__http_1_1TestClientRequest.html){.code}&
request,
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} 
[TestClientResponse](structtensorflow_1_1serving_1_1net__http_1_1TestClientResponse.html){.code}\*
response) = 0;
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [// Sends a request and returns immediately.
The response will be handled]{.comment}
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [// asynchronously via the response-\>done
callback.]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [// Returns false if any error in sending the
request, or if the executor]{.comment}
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  [// has not been configured.]{.comment}
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [virtual]{.keyword} [bool]{.keywordtype}
SendRequest([const]{.keyword}
[TestClientRequest](structtensorflow_1_1serving_1_1net__http_1_1TestClientRequest.html){.code}&
request,
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} 
[TestClientResponse](structtensorflow_1_1serving_1_1net__http_1_1TestClientResponse.html){.code}\*
response) = 0;
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} 
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [// Sets the executor for processing requests
asynchronously.]{.comment}
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [virtual]{.keyword} [void]{.keywordtype}
SetExecutor(std::unique\_ptr\<EventExecutor\> executor) = 0;
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} 
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [protected]{.keyword}:
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} 
[TestHTTPClientInterface](classtensorflow_1_1serving_1_1net__http_1_1TestHTTPClientInterface.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} };
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} 
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} } [// namespace net\_http]{.comment}
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} 
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} [\#endif ]{.preprocessor}[//
THIRD\_PARTY\_TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_CLIENT\_TEST\_CLIENT\_PUBLIC\_HTTPCLIENT\_INTERFACE\_H\_]{.comment}
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

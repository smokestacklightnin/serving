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
evhttp\_request.h
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
[]{#l00016}[ 16]{.lineno} [// libevent based request
implementation]{.comment}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} 
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_SERVER\_INTERNAL\_EVHTTP\_REQUEST\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#define
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_SERVER\_INTERNAL\_EVHTTP\_REQUEST\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<cstdint\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} 
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/util/net\_http/server/internal/server\_support.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/util/net\_http/server/public/httpserver\_interface.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow\_serving/util/net\_http/server/public/server\_request\_interface.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} 
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [struct ]{.keyword}evbuffer;
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [struct ]{.keyword}evhttp\_request;
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [struct ]{.keyword}evhttp\_uri;
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [struct ]{.keyword}evkeyvalq;
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} 
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [namespace ]{.keyword}net\_http {
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} 
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [// Headers only]{.comment}
:::

::: {.line}
[]{#l00039}[
[39](structtensorflow_1_1serving_1_1net__http_1_1ParsedEvRequest.html){.line}]{.lineno} [struct
]{.keyword}[ParsedEvRequest](structtensorflow_1_1serving_1_1net__http_1_1ParsedEvRequest.html){.code}
{
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [// Doesn\'t take the ownership]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [explicit]{.keyword}
[ParsedEvRequest](structtensorflow_1_1serving_1_1net__http_1_1ParsedEvRequest.html){.code}(evhttp\_request\*
request\_in);
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} 
\~[ParsedEvRequest](structtensorflow_1_1serving_1_1net__http_1_1ParsedEvRequest.html){.code}();
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [// Decode and cache the result; or return
false if any parsing error]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [bool]{.keywordtype} decode();
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  evhttp\_request\* request; [// raw
request]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [const]{.keyword} [char]{.keywordtype}\*
method; [// from enum]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [const]{.keyword} [char]{.keywordtype}\* uri
= [nullptr]{.keyword}; [// from raw request]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  evhttp\_uri\* decoded\_uri =
[nullptr]{.keyword}; [// owned by this]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} 
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [// TODO(wenboz): do we need escaped path for
dispatching requests?]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [// evhttp\_uridecode(path)]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [const]{.keyword} [char]{.keywordtype}\* path
= [nullptr]{.keyword}; [// owned by uri]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  std::string path\_and\_query;
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} 
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  evkeyvalq\* headers = [nullptr]{.keyword};
[// owned by raw request]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} };
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} 
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} [// Thread-compatible. See
ServerRequestInterface on the exact contract]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} [// between the server runtime and application
handlers.]{.comment}
:::

::: {.line}
[]{#l00065}[
[65](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.line}]{.lineno} [class
]{.keyword}[EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.code}
final : [public]{.keyword}
[ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.code}
{
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [virtual]{.keyword}
\~[EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.code}();
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} 
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
[EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.code}([const]{.keyword}
[EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.code}&
other) = [delete]{.keyword};
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} 
[EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.code}&
operator=([const]{.keyword}
[EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.code}&
other) = [delete]{.keyword};
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} 
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [// Doesn\'t own the server]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} 
[EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html){.code}(std::unique\_ptr\<ParsedEvRequest\>
request,
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} 
[ServerSupport](classtensorflow_1_1serving_1_1net__http_1_1ServerSupport.html){.code}\*
server);
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} 
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  absl::string\_view uri\_path() [const
override]{.keyword};
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} 
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  absl::string\_view http\_method() [const
override]{.keyword};
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} 
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [void]{.keywordtype}
WriteResponseBytes([const]{.keyword} [char]{.keywordtype}\* data,
int64\_t size) [override]{.keyword};
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} 
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  [void]{.keywordtype}
WriteResponseString(absl::string\_view data) [override]{.keyword};
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} 
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  std::unique\_ptr\<char\[\],
ServerRequestInterface::BlockDeleter\>
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  ReadRequestBytes(int64\_t\* size)
[override]{.keyword};
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} 
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  absl::string\_view
GetRequestHeader(absl::string\_view header) [const override]{.keyword};
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} 
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  std::vector\<absl::string\_view\>
request\_headers() [const override]{.keyword};
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} 
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  [void]{.keywordtype}
OverwriteResponseHeader(absl::string\_view header,
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  absl::string\_view value)
[override]{.keyword};
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  [void]{.keywordtype}
AppendResponseHeader(absl::string\_view header,
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  absl::string\_view value)
[override]{.keyword};
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} 
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  [void]{.keywordtype}
PartialReplyWithStatus(HTTPStatusCode status) [override]{.keyword};
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  [void]{.keywordtype} PartialReply()
[override]{.keyword};
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} 
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  CallbackStatus PartialReplyWithFlushCallback(
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  std::function\<[void]{.keywordtype}()\>
callback) [override]{.keyword};
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} 
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [void]{.keywordtype}
ReplyWithStatus(HTTPStatusCode status) [override]{.keyword};
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  [void]{.keywordtype} Reply()
[override]{.keyword};
:::

::: {.line}
[]{#l00104}[ 104]{.lineno} 
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  [void]{.keywordtype} Abort()
[override]{.keyword};
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} 
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [// Initializes the resource and returns
false if any error.]{.comment}
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  [bool]{.keywordtype} Initialize();
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} 
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  [// Keeps a reference to the registered
RequestHandlerOptions]{.comment}
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  [void]{.keywordtype}
SetHandlerOptions([const]{.keyword}
[RequestHandlerOptions](classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions.html){.code}&
handler\_options) {
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  this-\>handler\_options\_ =
&handler\_options;
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  }
:::

::: {.line}
[]{#l00114}[ 114]{.lineno} 
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  [void]{.keywordtype}
EvSendReply(HTTPStatusCode status);
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} 
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  [// Returns true if the data needs be
uncompressed]{.comment}
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  [bool]{.keywordtype}
NeedUncompressGzipContent();
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} 
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  [// Must set uncompressed\_input to nullptr
if uncompression is failed]{.comment}
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  [void]{.keywordtype}
UncompressGzipBody([void]{.keywordtype}\* input, [size\_t]{.keywordtype}
input\_size,
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  [void]{.keywordtype}\*\*
uncompressed\_input,
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  [size\_t]{.keywordtype}\*
uncompressed\_input\_size);
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} 
:::

::: {.line}
[]{#l00126}[ 126]{.lineno}  std::unique\_ptr\<char\[\],
ServerRequestInterface::BlockDeleter\>
:::

::: {.line}
[]{#l00127}[ 127]{.lineno}  ReadRequestGzipBytes(evbuffer\* input\_buf,
int64\_t\* size);
:::

::: {.line}
[]{#l00128}[ 128]{.lineno} 
:::

::: {.line}
[]{#l00129}[ 129]{.lineno} 
[ServerSupport](classtensorflow_1_1serving_1_1net__http_1_1ServerSupport.html){.code}\*
server\_;
:::

::: {.line}
[]{#l00130}[ 130]{.lineno} 
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  [const]{.keyword}
[RequestHandlerOptions](classtensorflow_1_1serving_1_1net__http_1_1RequestHandlerOptions.html){.code}\*
handler\_options\_;
:::

::: {.line}
[]{#l00132}[ 132]{.lineno} 
:::

::: {.line}
[]{#l00133}[ 133]{.lineno}  std::unique\_ptr\<ParsedEvRequest\>
parsed\_request\_;
:::

::: {.line}
[]{#l00134}[ 134]{.lineno} 
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  evbuffer\* output\_buf; [// owned by
this]{.comment}
:::

::: {.line}
[]{#l00136}[ 136]{.lineno} };
:::

::: {.line}
[]{#l00137}[ 137]{.lineno} 
:::

::: {.line}
[]{#l00138}[ 138]{.lineno} } [// namespace net\_http]{.comment}
:::

::: {.line}
[]{#l00139}[ 139]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00140}[ 140]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00141}[ 141]{.lineno} 
:::

::: {.line}
[]{#l00142}[ 142]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_SERVER\_INTERNAL\_EVHTTP\_REQUEST\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest_html .ttc}
::: {.ttname}
[tensorflow::serving::net\_http::EvHTTPRequest](classtensorflow_1_1serving_1_1net__http_1_1EvHTTPRequest.html)
:::

::: {.ttdef}
**Definition:** evhttp\_request.h:65
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

::: {#aclasstensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_html .ttc}
::: {.ttname}
[tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html)
:::

::: {.ttdef}
**Definition:** server\_request\_interface.h:42
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

::: {#astructtensorflow_1_1serving_1_1net__http_1_1ParsedEvRequest_html .ttc}
::: {.ttname}
[tensorflow::serving::net\_http::ParsedEvRequest](structtensorflow_1_1serving_1_1net__http_1_1ParsedEvRequest.html)
:::

::: {.ttdef}
**Definition:** evhttp\_request.h:39
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

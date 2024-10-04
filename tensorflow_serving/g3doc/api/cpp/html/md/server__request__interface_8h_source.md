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
server\_request\_interface.h
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
[]{#l00016}[ 16]{.lineno} [// net\_http::ServerRequestInterface defines
a pure interface class for handling]{.comment}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [// an HTTP request on the server-side. It is
designed as a minimum API]{.comment}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} [// to ensure reusability and to work with
different HTTP implementations.]{.comment}
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [// ServerRequestInterface is
thread-compatible. Once the request object]{.comment}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [// has been dispatched to the
application-specified handler, the HTTP server]{.comment}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [// runtime will not access the request object
till Reply() is called.]{.comment}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [// Streamed request/response APIs are to be
added, which will introduce]{.comment}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [// additional API contract wrt the threading
semantics.]{.comment}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} 
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_SERVER\_PUBLIC\_SERVER\_REQUEST\_INTERFACE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#define
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_SERVER\_PUBLIC\_SERVER\_REQUEST\_INTERFACE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} 
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include \<cstdlib\>]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include \<functional\>]{.preprocessor}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} 
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [\#include
\"absl/strings/string\_view.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [\#include
\"tensorflow\_serving/util/net\_http/public/response\_code\_enum.h\"]{.preprocessor}
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
[]{#l00042}[
[42](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.line}]{.lineno} [class
]{.keyword}[ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.code}
{
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [// To be used with memory blocks returned
via std::unique\_ptr\<char\[\]\>]{.comment}
:::

::: {.line}
[]{#l00045}[
[45](structtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_1_1BlockDeleter.html){.line}]{.lineno} 
[struct
]{.keyword}[BlockDeleter](structtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_1_1BlockDeleter.html){.code}
{
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
[BlockDeleter](structtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_1_1BlockDeleter.html){.code}()
: size\_(0) {} [// nullptr]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [explicit]{.keyword}
[BlockDeleter](structtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_1_1BlockDeleter.html){.code}(int64\_t
size) : size\_(size) {}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [inline]{.keyword} [void]{.keywordtype}
operator()([char]{.keywordtype}\* ptr)[ const ]{.keyword}{
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [// TODO: c++14 ::operator delete\[\](ptr,
size\_t)]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  std::allocator\<char\>().deallocate(ptr,
[static\_cast\<]{.keyword}std::size\_t[\>]{.keyword}(size\_));
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  }
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} 
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  int64\_t size\_;
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  };
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} 
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [virtual]{.keyword}
\~[ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} 
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
[ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.code}([const]{.keyword}
[ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.code}&
other) = [delete]{.keyword};
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} 
[ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.code}&
operator=([const]{.keyword}
[ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html){.code}&
other) =
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [delete]{.keyword};
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} 
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  [// The portion of the request URI after the
host and port.]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [// E.g.
\"/path/to/resource?param=value&param=value\#fragment\".]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [// Doesn\'t unescape the contents; returns
\"/\" at least.]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [virtual]{.keyword} absl::string\_view
uri\_path() [const]{.keyword} = 0;
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} 
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [// HTTP request method.]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [// Must be in Upper Case.]{.comment}
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  [virtual]{.keyword} absl::string\_view
http\_method() [const]{.keyword} = 0;
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} 
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [// Input/output byte-buffer types are
subject to change!]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  [// I/O buffer choices:]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [// - absl::ByteStream would work but it is
not yet open-sourced]{.comment}
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [// - iovec doesn\'t add much value and may
limit portability; but otherwise]{.comment}
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [// the current API is compatible with
iovec]{.comment}
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [// - absl::Span is open-sourced, but
string\_view is simpler to use for writing]{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  [// to an HTTP response.]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} 
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  [// Appends the data block of the specified
size to the response body.]{.comment}
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  [// This request object takes the ownership
of the data block.]{.comment}
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [// Note this is not a streaming write API.
See PartialReply() below.]{.comment}
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  [virtual]{.keyword} [void]{.keywordtype}
WriteResponseBytes([const]{.keyword} [char]{.keywordtype}\* data,
int64\_t size) = 0;
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} 
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  [// Appends (by coping) the data of
string\_view to the end of]{.comment}
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  [// the response body.]{.comment}
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [virtual]{.keyword} [void]{.keywordtype}
WriteResponseString(absl::string\_view data) = 0;
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} 
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  [// Reads from the request body.]{.comment}
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [// Returns the number bytes of data read,
whose ownership will be transferred]{.comment}
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  [// to the caller. Returns nullptr when EOF
is reached or when there]{.comment}
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  [// is no request body.]{.comment}
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  [// The returned memory will be \"free-ed\"
via the custom Deleter. Do not]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  [// release the memory manually as its
allocator is subject to change.]{.comment}
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  [// Note this is not a streaming read API in
that the complete request body]{.comment}
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  [// should have already been
received.]{.comment}
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  [virtual]{.keyword}
std::unique\_ptr\<char\[\], ServerRequestInterface::BlockDeleter\>
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  ReadRequestBytes(int64\_t\* size) = 0;
:::

::: {.line}
[]{#l00103}[ 103]{.lineno} 
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  [// Returns the first value, including \"\",
associated with a request]{.comment}
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  [// header name. The header name argument is
case-insensitive.]{.comment}
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  [// Returns nullptr if the specified header
doesn\'t exist.]{.comment}
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [virtual]{.keyword} absl::string\_view
GetRequestHeader(
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  absl::string\_view header) [const]{.keyword}
= 0;
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} 
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  [// To be added: multi-value
headers.]{.comment}
:::

::: {.line}
[]{#l00111}[ 111]{.lineno} 
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  [// Returns all the request header
names.]{.comment}
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  [// This is not an efficient way to access
headers, mainly for debugging uses.]{.comment}
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [virtual]{.keyword}
std::vector\<absl::string\_view\> request\_headers() [const]{.keyword} =
0;
:::

::: {.line}
[]{#l00115}[ 115]{.lineno} 
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  [virtual]{.keyword} [void]{.keywordtype}
OverwriteResponseHeader(absl::string\_view header,
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  absl::string\_view value) = 0;
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  [virtual]{.keyword} [void]{.keywordtype}
AppendResponseHeader(absl::string\_view header,
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  absl::string\_view value) = 0;
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} 
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  [// The IO status of a request or response
body.]{.comment}
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  [enum class]{.keyword} BodyStatus {
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  [// The body hasn\'t been completely read or
written.]{.comment}
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  PENDING = 0,
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  [// The body has been completely read or
written or when there is no body.]{.comment}
:::

::: {.line}
[]{#l00126}[ 126]{.lineno}  COMPLETE = 1,
:::

::: {.line}
[]{#l00127}[ 127]{.lineno}  [// The transport has reported a failure and
the request should be aborted.]{.comment}
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  FAILED = 2,
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  };
:::

::: {.line}
[]{#l00130}[ 130]{.lineno} 
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  [// This serves as the return value type for
callbacks that may be]{.comment}
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  [// skipped for optimization
reasons]{.comment}
:::

::: {.line}
[]{#l00133}[ 133]{.lineno}  [enum class]{.keyword} CallbackStatus {
:::

::: {.line}
[]{#l00134}[ 134]{.lineno}  NOT\_SCHEDULED = 0,
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  SCHEDULED = 1,
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  };
:::

::: {.line}
[]{#l00137}[ 137]{.lineno} 
:::

::: {.line}
[]{#l00138}[ 138]{.lineno}  [// Sends headers and/or any buffered
response body data to the client.]{.comment}
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  [// Assumes 200 if status is not
specified.]{.comment}
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  [// If called for the first time, all the
response headers will be sent]{.comment}
:::

::: {.line}
[]{#l00141}[ 141]{.lineno}  [// together including headers specified by
the application and]{.comment}
:::

::: {.line}
[]{#l00142}[ 142]{.lineno}  [// headers generated by the
server.]{.comment}
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  [// Trying to modify headers or specifying a
status after the first]{.comment}
:::

::: {.line}
[]{#l00144}[ 144]{.lineno}  [// PartialReply() is called is considered a
programming error and]{.comment}
:::

::: {.line}
[]{#l00145}[ 145]{.lineno}  [// the underlying behavior is
undefined.]{.comment}
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  [virtual]{.keyword} [void]{.keywordtype}
PartialReplyWithStatus(HTTPStatusCode status) = 0;
:::

::: {.line}
[]{#l00147}[ 147]{.lineno}  [virtual]{.keyword} [void]{.keywordtype}
PartialReply() = 0;
:::

::: {.line}
[]{#l00148}[ 148]{.lineno} 
:::

::: {.line}
[]{#l00149}[ 149]{.lineno}  [// Similar to PartialReply() but with an
on\_flush callback which will be]{.comment}
:::

::: {.line}
[]{#l00150}[ 150]{.lineno}  [// invoked when the response data has been
completely flushed by the]{.comment}
:::

::: {.line}
[]{#l00151}[ 151]{.lineno}  [// transport. This allows the handler to
apply transport-provided flow-control]{.comment}
:::

::: {.line}
[]{#l00152}[ 152]{.lineno}  [// in writing data to the peer.]{.comment}
:::

::: {.line}
[]{#l00153}[ 153]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00154}[ 154]{.lineno}  [// Returns SCHEDULED if the callback will
be invoked asynchronously after]{.comment}
:::

::: {.line}
[]{#l00155}[ 155]{.lineno}  [// this method returns. Until the callback
is invoked, the request object]{.comment}
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  [// should not be accessed by the
handler.]{.comment}
:::

::: {.line}
[]{#l00157}[ 157]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00158}[ 158]{.lineno}  [// Returns NOT\_SCHEDULED if data is
already flushed when this method returns]{.comment}
:::

::: {.line}
[]{#l00159}[ 159]{.lineno}  [// or when the request should be aborted
due to transport failures.]{.comment}
:::

::: {.line}
[]{#l00160}[ 160]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00161}[ 161]{.lineno}  [// The handler should check
response\_body\_status() after this method returns]{.comment}
:::

::: {.line}
[]{#l00162}[ 162]{.lineno}  [// or from the callback to decide if the
request should be aborted due to]{.comment}
:::

::: {.line}
[]{#l00163}[ 163]{.lineno}  [// transport failures.]{.comment}
:::

::: {.line}
[]{#l00164}[ 164]{.lineno}  [virtual]{.keyword} CallbackStatus
PartialReplyWithFlushCallback(
:::

::: {.line}
[]{#l00165}[ 165]{.lineno}  std::function\<[void]{.keywordtype}()\>
callback) = 0;
:::

::: {.line}
[]{#l00166}[ 166]{.lineno}  [virtual]{.keyword} BodyStatus
response\_body\_status() { [return]{.keywordflow} BodyStatus::PENDING; }
:::

::: {.line}
[]{#l00167}[ 167]{.lineno} 
:::

::: {.line}
[]{#l00168}[ 168]{.lineno}  [// Request streaming is disabled by
default]{.comment}
:::

::: {.line}
[]{#l00169}[ 169]{.lineno}  [virtual]{.keyword} BodyStatus
request\_body\_status() { [return]{.keywordflow} BodyStatus::COMPLETE; }
:::

::: {.line}
[]{#l00170}[ 170]{.lineno} 
:::

::: {.line}
[]{#l00171}[ 171]{.lineno}  [// Completes the response and sends any
buffered response body]{.comment}
:::

::: {.line}
[]{#l00172}[ 172]{.lineno}  [// to the client. Headers will be generated
and sent first if PartialReply()]{.comment}
:::

::: {.line}
[]{#l00173}[ 173]{.lineno}  [// has never be called.]{.comment}
:::

::: {.line}
[]{#l00174}[ 174]{.lineno}  [// Assumes 200 if status is not
specified.]{.comment}
:::

::: {.line}
[]{#l00175}[ 175]{.lineno}  [// Once Reply() is called, the request
object will be owned and destructed]{.comment}
:::

::: {.line}
[]{#l00176}[ 176]{.lineno}  [// by the server runtime.]{.comment}
:::

::: {.line}
[]{#l00177}[ 177]{.lineno}  [virtual]{.keyword} [void]{.keywordtype}
ReplyWithStatus(HTTPStatusCode status) = 0;
:::

::: {.line}
[]{#l00178}[ 178]{.lineno}  [virtual]{.keyword} [void]{.keywordtype}
Reply() = 0;
:::

::: {.line}
[]{#l00179}[ 179]{.lineno} 
:::

::: {.line}
[]{#l00180}[ 180]{.lineno}  [// Aborts the current request
forcibly.]{.comment}
:::

::: {.line}
[]{#l00181}[ 181]{.lineno}  [// Once Abort() is called, the request
object will be owned and destructed]{.comment}
:::

::: {.line}
[]{#l00182}[ 182]{.lineno}  [// by the server runtime.]{.comment}
:::

::: {.line}
[]{#l00183}[ 183]{.lineno}  [virtual]{.keyword} [void]{.keywordtype}
Abort() = 0;
:::

::: {.line}
[]{#l00184}[ 184]{.lineno} 
:::

::: {.line}
[]{#l00185}[ 185]{.lineno}  [protected]{.keyword}:
:::

::: {.line}
[]{#l00186}[ 186]{.lineno}  ServerRequestInterface() =
[default]{.keywordflow};
:::

::: {.line}
[]{#l00187}[ 187]{.lineno} 
:::

::: {.line}
[]{#l00188}[ 188]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00189}[ 189]{.lineno}  [// Do not add any data members to this
class.]{.comment}
:::

::: {.line}
[]{#l00190}[ 190]{.lineno} };
:::

::: {.line}
[]{#l00191}[ 191]{.lineno} 
:::

::: {.line}
[]{#l00192}[ 192]{.lineno} [// Helper methods.]{.comment}
:::

::: {.line}
[]{#l00193}[ 193]{.lineno} 
:::

::: {.line}
[]{#l00194}[ 194]{.lineno} [inline]{.keyword} [void]{.keywordtype}
SetContentType(ServerRequestInterface\* request,
:::

::: {.line}
[]{#l00195}[ 195]{.lineno}  absl::string\_view type) {
:::

::: {.line}
[]{#l00196}[ 196]{.lineno} 
request-\>OverwriteResponseHeader([\"Content-Type\"]{.stringliteral},
type);
:::

::: {.line}
[]{#l00197}[ 197]{.lineno} }
:::

::: {.line}
[]{#l00198}[ 198]{.lineno} 
:::

::: {.line}
[]{#l00199}[ 199]{.lineno} [inline]{.keyword} [void]{.keywordtype}
SetContentTypeHTML(ServerRequestInterface\* request) {
:::

::: {.line}
[]{#l00200}[ 200]{.lineno}  SetContentType(request,
[\"text/html\"]{.stringliteral});
:::

::: {.line}
[]{#l00201}[ 201]{.lineno} }
:::

::: {.line}
[]{#l00202}[ 202]{.lineno} 
:::

::: {.line}
[]{#l00203}[ 203]{.lineno} [inline]{.keyword} [void]{.keywordtype}
SetContentTypeTEXT(ServerRequestInterface\* request) {
:::

::: {.line}
[]{#l00204}[ 204]{.lineno}  SetContentType(request,
[\"text/plain\"]{.stringliteral});
:::

::: {.line}
[]{#l00205}[ 205]{.lineno} }
:::

::: {.line}
[]{#l00206}[ 206]{.lineno} 
:::

::: {.line}
[]{#l00207}[ 207]{.lineno} } [// namespace net\_http]{.comment}
:::

::: {.line}
[]{#l00208}[ 208]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00209}[ 209]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00210}[ 210]{.lineno} 
:::

::: {.line}
[]{#l00211}[ 211]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_SERVER\_PUBLIC\_SERVER\_REQUEST\_INTERFACE\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_html .ttc}
::: {.ttname}
[tensorflow::serving::net\_http::ServerRequestInterface](classtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface.html)
:::

::: {.ttdef}
**Definition:** server\_request\_interface.h:42
:::
:::

::: {#astructtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_1_1BlockDeleter_html .ttc}
::: {.ttname}
[tensorflow::serving::net\_http::ServerRequestInterface::BlockDeleter](structtensorflow_1_1serving_1_1net__http_1_1ServerRequestInterface_1_1BlockDeleter.html)
:::

::: {.ttdef}
**Definition:** server\_request\_interface.h:45
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

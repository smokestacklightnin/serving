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
-   [public](dir_1db290addf700e6fb9661329f10bb0cb.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
response\_code\_enum.h
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
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_PUBLIC\_RESPONSE\_CODE\_ENUM\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_PUBLIC\_RESPONSE\_CODE\_ENUM\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [namespace ]{.keyword}net\_http {
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} 
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [enum class]{.keyword} HTTPStatusCode {
:::

::: {.line}
[]{#l00024}[ 24]{.lineno}  [// These are the status codes we can give
back to the client.]{.comment}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno}  [//
http://www.iana.org/assignments/http-status-codes/http-status-codes.xhtml\#http-status-codes-1]{.comment}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno}  UNDEFINED = 0, [// Illegal value for
initialization]{.comment}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno}  FIRST\_CODE = 100,
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} 
:::

::: {.line}
[]{#l00029}[ 29]{.lineno}  [// Informational]{.comment}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno}  CONTINUE = 100, [// Continue]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno}  SWITCHING = 101, [// Switching
Protocols]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno}  PROCESSING = 102, [// Processing (RFC 2518,
sec 10.1)]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} 
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  [// Success]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  OK = 200, [// OK]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  CREATED = 201, [// Created]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  ACCEPTED = 202, [// Accepted]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  PROVISIONAL = 203, [// Non-Authoritative
Information]{.comment}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  NO\_CONTENT = 204, [// No Content]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  RESET\_CONTENT = 205, [// Reset
Content]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  PART\_CONTENT = 206, [// Partial
Content]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  MULTI\_STATUS = 207, [// Multi-Status (RFC
2518, sec 10.2)]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  ALREADY\_REPORTED = 208, [// Already Reported
(RFC 5842)]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  IM\_USED = 226, [// IM Used (RFC
3229)]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} 
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [// Redirect]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  MULTIPLE = 300, [// Multiple
Choices]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  MOVED\_PERM = 301, [// Moved
Permanently]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  MOVED\_TEMP = 302, [// Found. For historical
reasons,]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [// a user agent MAY change the
method]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [// from POST to GET for the
subsequent]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [// request (RFC 7231, sec 6.4.3).]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  SEE\_OTHER = 303, [// See Other]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  NOT\_MODIFIED = 304, [// Not
Modified]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  USE\_PROXY = 305, [// Use Proxy]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  TEMP\_REDIRECT = 307, [// Similar to 302,
except that user]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [// agents MUST NOT change the
request]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [// method (RFC 7231, sec 6.4.7)]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  RESUME\_INCOMPLETE = 308, [// Resume
Incomplete]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [// Client Error]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  BAD\_REQUEST = 400, [// Bad
Request]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  UNAUTHORIZED = 401, [//
Unauthorized]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  PAYMENT = 402, [// Payment
Required]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  FORBIDDEN = 403, [// Forbidden]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  NOT\_FOUND = 404, [// Not Found]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  METHOD\_NA = 405, [// Method Not
Allowed]{.comment}
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  NONE\_ACC = 406, [// Not
Acceptable]{.comment}
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  PROXY = 407, [// Proxy Authentication
Required]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  REQUEST\_TO = 408, [// Request
Time-out]{.comment}
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  CONFLICT = 409, [// Conflict]{.comment}
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  GONE = 410, [// Gone]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  LEN\_REQUIRED = 411, [// Length
Required]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  PRECOND\_FAILED = 412, [// Precondition
Failed]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  ENTITY\_TOO\_BIG = 413, [// Request Entity
Too Large]{.comment}
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  URI\_TOO\_BIG = 414, [// Request-URI Too
Large]{.comment}
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  UNKNOWN\_MEDIA = 415, [// Unsupported Media
Type]{.comment}
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  BAD\_RANGE = 416, [// Requested range not
satisfiable]{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  BAD\_EXPECTATION = 417, [// Expectation
Failed]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  IM\_A\_TEAPOT = 418, [// I\'m a Teapot (RFC
2324, 7168)]{.comment}
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  MISDIRECTED\_REQUEST = 421, [// Misdirected
Request (RFC 7540)]{.comment}
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  UNPROC\_ENTITY = 422, [// Unprocessable
Entity (RFC 2518, sec 10.3)]{.comment}
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  LOCKED = 423, [// Locked (RFC 2518, sec
10.4)]{.comment}
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  FAILED\_DEP = 424, [// Failed Dependency (RFC
2518, sec 10.5)]{.comment}
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  UPGRADE\_REQUIRED = 426, [// Upgrade Required
(RFC 7231, sec 6.5.14)]{.comment}
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  PRECOND\_REQUIRED = 428, [// Precondition
Required (RFC 6585, sec 3)]{.comment}
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  TOO\_MANY\_REQUESTS = 429, [// Too Many
Requests (RFC 6585, sec 4)]{.comment}
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  HEADER\_TOO\_LARGE = 431, [// Request Header
Fields Too Large]{.comment}
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [// (RFC 6585, sec 5)]{.comment}
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  UNAVAILABLE\_LEGAL = 451, [// Unavailable For
Legal Reasons (RFC 7725)]{.comment}
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  CLIENT\_CLOSED\_REQUEST = 499, [// Client
Closed Request (Nginx)]{.comment}
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} 
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  [// Server Error]{.comment}
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  ERROR = 500, [// Internal Server
Error]{.comment}
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  NOT\_IMP = 501, [// Not
Implemented]{.comment}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  BAD\_GATEWAY = 502, [// Bad
Gateway]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  SERVICE\_UNAV = 503, [// Service
Unavailable]{.comment}
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  GATEWAY\_TO = 504, [// Gateway
Time-out]{.comment}
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  BAD\_VERSION = 505, [// HTTP Version not
supported]{.comment}
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  VARIANT\_NEGOTIATES = 506, [// Variant Also
Negotiates (RFC 2295)]{.comment}
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  INSUF\_STORAGE = 507, [// Insufficient
Storage (RFC 2518, sec 10.6)]{.comment}
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  LOOP\_DETECTED = 508, [// Loop Detected (RFC
5842)]{.comment}
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  NOT\_EXTENDED = 510, [// Not Extended (RFC
2774)]{.comment}
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  NETAUTH\_REQUIRED = 511, [// Network
Authentication Required]{.comment}
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  [// (RFC 6585, sec 6)]{.comment}
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  LAST\_CODE = 599,
:::

::: {.line}
[]{#l00107}[ 107]{.lineno} };
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} 
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} } [// namespace net\_http]{.comment}
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00111}[ 111]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} 
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_PUBLIC\_RESPONSE\_CODE\_ENUM\_H\_]{.comment}
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

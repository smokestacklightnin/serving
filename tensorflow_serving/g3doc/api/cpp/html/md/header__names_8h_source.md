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
header\_names.h
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
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_PUBLIC\_HEADER\_NAMES\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_PUBLIC\_HEADER\_NAMES\_H\_]{.preprocessor}
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
[]{#l00023}[ 23]{.lineno} [// Standard HTTP Header Names]{.comment}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [//
http://www.iana.org/assignments/message-headers]{.comment}
:::

::: {.line}
[]{#l00026}[
[26](classtensorflow_1_1serving_1_1net__http_1_1HTTPHeaders.html){.line}]{.lineno} [class
]{.keyword}[HTTPHeaders](classtensorflow_1_1serving_1_1net__http_1_1HTTPHeaders.html){.code}
{
:::

::: {.line}
[]{#l00027}[ 27]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} 
[HTTPHeaders](classtensorflow_1_1serving_1_1net__http_1_1HTTPHeaders.html){.code}()
= [delete]{.keyword};
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} 
:::

::: {.line}
[]{#l00030}[ 30]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} ACCEPT\[\];
:::

::: {.line}
[]{#l00031}[ 31]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} ACCEPT\_CHARSET\[\];
:::

::: {.line}
[]{#l00032}[ 32]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} ACCEPT\_ENCODING\[\];
:::

::: {.line}
[]{#l00033}[ 33]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} ACCEPT\_LANGUAGE\[\];
:::

::: {.line}
[]{#l00034}[ 34]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} ACCEPT\_RANGES\[\];
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} ACCESS\_CONTROL\_ALLOW\_CREDENTIALS\[\];
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} ACCESS\_CONTROL\_ALLOW\_HEADERS\[\];
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} ACCESS\_CONTROL\_ALLOW\_METHODS\[\];
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} ACCESS\_CONTROL\_ALLOW\_ORIGIN\[\];
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} ACCESS\_CONTROL\_EXPOSE\_HEADERS\[\];
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} ACCESS\_CONTROL\_MAX\_AGE\[\];
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} ACCESS\_CONTROL\_REQUEST\_HEADERS\[\];
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} ACCESS\_CONTROL\_REQUEST\_METHOD\[\];
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} AGE\[\];
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} ALLOW\[\];
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} AUTHORIZATION\[\];
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} CACHE\_CONTROL\[\];
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} CONNECTION\[\];
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} CONTENT\_DISPOSITION\[\];
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} CONTENT\_ENCODING\[\];
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} CONTENT\_LANGUAGE\[\];
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} CONTENT\_LENGTH\[\];
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} CONTENT\_LOCATION\[\];
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} CONTENT\_RANGE\[\];
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [//
http://w3.org/TR/CSP/\#content-security-policy-header-field]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} CONTENT\_SECURITY\_POLICY\[\];
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [//
http://w3.org/TR/CSP/\#content-security-policy-report-only-header-field]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} CONTENT\_SECURITY\_POLICY\_REPORT\_ONLY\[\];
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [// A nonstandard CSP header that was
introduced for CSP v.1]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [//
https://www.w3.org/TR/2011/WD-CSP-20111129/ and used by the Firefox
until]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [// version 23 and the Internet Explorer
version 10.]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [// Please, use CONTENT\_SECURITY\_POLICY to
pass the CSP.]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} X\_CONTENT\_SECURITY\_POLICY\[\];
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [// A nonstandard CSP header that was
introduced for CSP v.1]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  [//
https://www.w3.org/TR/2011/WD-CSP-20111129/ and used by the Firefox
until]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [// version 23 and Internet Explorer version
10.]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [// Please, use
CONTENT\_SECURITY\_POLICY\_REPORT\_ONLY to pass the CSP.]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} X\_CONTENT\_SECURITY\_POLICY\_REPORT\_ONLY\[\];
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [// A nonstandard CSP header that was
introduced for CSP v.1]{.comment}
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [//
https://www.w3.org/TR/2011/WD-CSP-20111129/ and used by the Chrome
until]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [// version 25. Please, use
CONTENT\_SECURITY\_POLICY to pass the CSP.]{.comment}
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} X\_WEBKIT\_CSP\[\];
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [// A nonstandard CSP header that was
introduced for CSP v.1]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [//
https://www.w3.org/TR/2011/WD-CSP-20111129/ and used by the Chrome
until]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  [// version 25.]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [// Please, use
CONTENT\_SECURITY\_POLICY\_REPORT\_ONLY to pass the CSP.]{.comment}
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} X\_WEBKIT\_CSP\_REPORT\_ONLY\[\];
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} CONTENT\_TYPE\[\];
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} CONTENT\_MD5\[\];
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  [// A header, introduced by Microsoft, to
modify how browsers]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [// interpret Content-Type:]{.comment}
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  [//
http://blogs.msdn.com/ie/archive/2008/09/02/ie8-security-part-vi-beta-2-update.aspx]{.comment}
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} X\_CONTENT\_TYPE\_OPTIONS\[\];
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} COOKIE\[\];
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} COOKIE2\[\];
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} DATE\[\];
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} DAV\[\];
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} DEPTH\[\];
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} DESTINATION\[\];
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} DNT\[\];
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  [//
https://tools.ietf.org/html/rfc8470]{.comment}
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} EARLY\_DATA\[\];
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} ETAG\[\];
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} EXPECT\[\];
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} EXPIRES\[\];
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} FOLLOW\_ONLY\_WHEN\_PRERENDER\_SHOWN\[\];
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  [// Supersedes X-Forwarded-For
(https://tools.ietf.org/html/rfc7239).]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} FORWARDED\[\];
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} FROM\[\];
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} HOST\[\];
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  [//
http://httpwg.org/specs/rfc7540.html\#Http2SettingsHeader]{.comment}
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} HTTP2\_SETTINGS\[\];
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} IF\[\];
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} IF\_MATCH\[\];
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} IF\_MODIFIED\_SINCE\[\];
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} IF\_NONE\_MATCH\[\];
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} IF\_RANGE\[\];
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} IF\_UNMODIFIED\_SINCE\[\];
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} KEEP\_ALIVE\[\];
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} LABEL\[\];
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} LAST\_MODIFIED\[\];
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} LINK\[\];
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} LOCATION\[\];
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} LOCK\_TOKEN\[\];
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} MAX\_FORWARDS\[\];
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} MS\_AUTHOR\_VIA\[\];
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} ORIGIN\[\];
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} OVERWRITE\_HDR\[\];
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} P3P\[\];
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  [//
http://html.spec.whatwg.org/multipage/semantics.html\#hyperlink-auditing]{.comment}
:::

::: {.line}
[]{#l00120}[ 120]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} PING\_FROM\[\];
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  [//
http://html.spec.whatwg.org/multipage/semantics.html\#hyperlink-auditing]{.comment}
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} PING\_TO\[\];
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} PRAGMA\[\];
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} PROXY\_CONNECTION\[\];
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} PROXY\_AUTHENTICATE\[\];
:::

::: {.line}
[]{#l00126}[ 126]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} PROXY\_AUTHORIZATION\[\];
:::

::: {.line}
[]{#l00127}[ 127]{.lineno}  [//
http://tools.ietf.org/html/draft-ietf-websec-key-pinning]{.comment}
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} PUBLIC\_KEY\_PINS\[\];
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} PUBLIC\_KEY\_PINS\_REPORT\_ONLY\[\];
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} RANGE\[\];
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} REFERER\[\];
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  [//
https://www.w3.org/TR/referrer-policy/]{.comment}
:::

::: {.line}
[]{#l00133}[ 133]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} REFERRER\_POLICY\[\];
:::

::: {.line}
[]{#l00134}[ 134]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} REFERRER\_POLICY\_NO\_REFERRER\[\];
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype}
REFERRER\_POLICY\_NO\_REFFERER\_WHEN\_DOWNGRADE\[\];
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} REFERRER\_POLICY\_SAME\_ORIGIN\[\];
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} REFERRER\_POLICY\_ORIGIN\[\];
:::

::: {.line}
[]{#l00138}[ 138]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} REFERRER\_POLICY\_STRICT\_ORIGIN\[\];
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} REFERRER\_POLICY\_ORIGIN\_WHEN\_CROSS\_ORIGIN\[\];
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype}
REFERRER\_POLICY\_STRICT\_ORIGIN\_WHEN\_CROSS\_ORIGIN\[\];
:::

::: {.line}
[]{#l00141}[ 141]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} REFERRER\_POLICY\_UNSAFE\_URL\[\];
:::

::: {.line}
[]{#l00142}[ 142]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} REFRESH\[\];
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} RETRY\_AFTER\[\];
:::

::: {.line}
[]{#l00144}[ 144]{.lineno}  [//
https://github.com/mikewest/sec-metadata]{.comment}
:::

::: {.line}
[]{#l00145}[ 145]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} SEC\_METADATA\[\];
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  [//
https://tools.ietf.org/html/draft-ietf-tokbind-https]{.comment}
:::

::: {.line}
[]{#l00147}[ 147]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} SEC\_TOKEN\_BINDING\[\];
:::

::: {.line}
[]{#l00148}[ 148]{.lineno}  [//
https://tools.ietf.org/html/draft-ietf-tokbind-ttrp]{.comment}
:::

::: {.line}
[]{#l00149}[ 149]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} SEC\_PROVIDED\_TOKEN\_BINDING\_ID\[\];
:::

::: {.line}
[]{#l00150}[ 150]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} SEC\_REFERRED\_TOKEN\_BINDING\_ID\[\];
:::

::: {.line}
[]{#l00151}[ 151]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} SERVER\[\];
:::

::: {.line}
[]{#l00152}[ 152]{.lineno}  [//
https://www.w3.org/TR/server-timing/]{.comment}
:::

::: {.line}
[]{#l00153}[ 153]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} SERVER\_TIMING\[\];
:::

::: {.line}
[]{#l00154}[ 154]{.lineno}  [//
https://www.w3.org/TR/service-workers/\#update-algorithm]{.comment}
:::

::: {.line}
[]{#l00155}[ 155]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} SERVICE\_WORKER\[\];
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} SERVICE\_WORKER\_ALLOWED\[\];
:::

::: {.line}
[]{#l00157}[ 157]{.lineno}  [//
https://developers.google.com/web/updates/2017/02/navigation-preload]{.comment}
:::

::: {.line}
[]{#l00158}[ 158]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} SERVICE\_WORKER\_NAVIGATION\_PRELOAD\[\];
:::

::: {.line}
[]{#l00159}[ 159]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} SET\_COOKIE\[\];
:::

::: {.line}
[]{#l00160}[ 160]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} SET\_COOKIE2\[\];
:::

::: {.line}
[]{#l00161}[ 161]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} STATUS\_URI\[\];
:::

::: {.line}
[]{#l00162}[ 162]{.lineno}  [// HSTS
http://tools.ietf.org/html/draft-ietf-websec-strict-transport-sec]{.comment}
:::

::: {.line}
[]{#l00163}[ 163]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} STRICT\_TRANSPORT\_SECURITY\[\];
:::

::: {.line}
[]{#l00164}[ 164]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} TIMEOUT\[\];
:::

::: {.line}
[]{#l00165}[ 165]{.lineno}  [//
http://www.w3.org/TR/2011/WD-resource-timing-20110524/\#cross-origin-resources]{.comment}
:::

::: {.line}
[]{#l00166}[ 166]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} TIMING\_ALLOW\_ORIGIN\[\];
:::

::: {.line}
[]{#l00167}[ 167]{.lineno}  [//
http://www.w3.org/2011/tracking-protection/drafts/tracking-dnt.html\#response-header-field]{.comment}
:::

::: {.line}
[]{#l00168}[ 168]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} TK\[\];
:::

::: {.line}
[]{#l00169}[ 169]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} TRAILER\[\];
:::

::: {.line}
[]{#l00170}[ 170]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} TRAILERS\[\];
:::

::: {.line}
[]{#l00171}[ 171]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} TRANSFER\_ENCODING\[\];
:::

::: {.line}
[]{#l00172}[ 172]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} TRANSFER\_ENCODING\_ABBRV\[\];
:::

::: {.line}
[]{#l00173}[ 173]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} UPGRADE\[\];
:::

::: {.line}
[]{#l00174}[ 174]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} USER\_AGENT\[\];
:::

::: {.line}
[]{#l00175}[ 175]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} VARY\[\];
:::

::: {.line}
[]{#l00176}[ 176]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} VIA\[\];
:::

::: {.line}
[]{#l00177}[ 177]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} WARNING\[\];
:::

::: {.line}
[]{#l00178}[ 178]{.lineno}  [static]{.keyword} [const]{.keyword}
[char]{.keywordtype} WWW\_AUTHENTICATE\[\];
:::

::: {.line}
[]{#l00179}[ 179]{.lineno} };
:::

::: {.line}
[]{#l00180}[ 180]{.lineno} 
:::

::: {.line}
[]{#l00181}[ 181]{.lineno} } [// namespace net\_http]{.comment}
:::

::: {.line}
[]{#l00182}[ 182]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00183}[ 183]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00184}[ 184]{.lineno} 
:::

::: {.line}
[]{#l00185}[ 185]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_PUBLIC\_HEADER\_NAMES\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1net__http_1_1HTTPHeaders_html .ttc}
::: {.ttname}
[tensorflow::serving::net\_http::HTTPHeaders](classtensorflow_1_1serving_1_1net__http_1_1HTTPHeaders.html)
:::

::: {.ttdef}
**Definition:** header\_names.h:26
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

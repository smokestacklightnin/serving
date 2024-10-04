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
httpserver.h
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
[]{#l00016}[ 16]{.lineno} [// The entry point to access different HTTP
server implementations.]{.comment}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} 
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_SERVER\_PUBLIC\_HTTPSERVER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#define
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_SERVER\_PUBLIC\_HTTPSERVER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} 
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"absl/memory/memory.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} 
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/util/net\_http/server/internal/evhttp\_server.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/util/net\_http/server/public/httpserver\_interface.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} 
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [namespace ]{.keyword}net\_http {
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} 
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// Creates a server implemented based on the
libevents library.]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// Returns nullptr if there is any
error.]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [// Must call WaitForTermination() or
WaitForTerminationWithTimeout() before]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [// the server is to be destructed.]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [inline]{.keyword}
std::unique\_ptr\<HTTPServerInterface\> CreateEvHTTPServer(
:::

::: {.line}
[]{#l00038}[ 38]{.lineno}  std::unique\_ptr\<ServerOptions\> options) {
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [auto]{.keyword} server =
absl::make\_unique\<EvHTTPServer\>(std::move(options));
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [bool]{.keywordtype} result =
server-\>Initialize();
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [if]{.keywordflow} (!result) {
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [return]{.keywordflow} [nullptr]{.keyword};
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  }
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [return]{.keywordflow} std::move(server);
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} }
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} } [// namespace net\_http]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_UTIL\_NET\_HTTP\_SERVER\_PUBLIC\_HTTPSERVER\_H\_]{.comment}
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

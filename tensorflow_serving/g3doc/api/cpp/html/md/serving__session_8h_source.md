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
-   [servables](dir_e240d895a087fc4ce46e8f4c52318018.html){.el}
-   [tensorflow](dir_143c99ffaf6c8b3b63b06c22e49d7998.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
serving\_session.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2016 Google Inc. All Rights
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
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_SERVING\_SESSION\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_SERVING\_SESSION\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<utility\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} 
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow/core/platform/logging.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/platform/threadpool\_options.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/public/session.h\"]{.preprocessor}
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
[]{#l00030}[ 30]{.lineno} 
:::

::: {.line}
[]{#l00034}[
[34](classtensorflow_1_1serving_1_1ServingSession.html){.line}]{.lineno} [class
]{.keyword}[ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.code}
: [public]{.keyword} Session {
:::

::: {.line}
[]{#l00035}[ 35]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
[ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} 
\~[ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.code}()
[override]{.keyword} = [default]{.keywordflow};
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [// Methods that return errors.]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  Status Create([const]{.keyword} GraphDef&
graph) [final]{.keyword};
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  Status Extend([const]{.keyword} GraphDef&
graph) [final]{.keyword};
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  Status Close() [final]{.keyword};
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} 
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [// (Subclasses just implement
Run().)]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} };
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} 
:::

::: {.line}
[]{#l00049}[
[49](classtensorflow_1_1serving_1_1ServingSessionWrapper.html){.line}]{.lineno} [class
]{.keyword}[ServingSessionWrapper](classtensorflow_1_1serving_1_1ServingSessionWrapper.html){.code}
: [public]{.keyword}
[ServingSession](classtensorflow_1_1serving_1_1ServingSession.html){.code}
{
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [explicit]{.keyword}
[ServingSessionWrapper](classtensorflow_1_1serving_1_1ServingSessionWrapper.html){.code}(std::unique\_ptr\<Session\>
wrapped)
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  : wrapped\_(std::move(wrapped)) {
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  VLOG(2) \<\< [\"Created the
ServingSessionWrapper around the Session.\"]{.stringliteral};
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  }
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} 
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} 
\~[ServingSessionWrapper](classtensorflow_1_1serving_1_1ServingSessionWrapper.html){.code}()
[override]{.keyword} = [default]{.keywordflow};
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} 
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  Status Run([const]{.keyword}
std::vector\<std::pair\<string, Tensor\>\>& inputs,
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [const]{.keyword} std::vector\<string\>&
output\_tensor\_names,
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [const]{.keyword} std::vector\<string\>&
target\_node\_names,
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  std::vector\<Tensor\>\* outputs)[ override
]{.keyword}{
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [return]{.keywordflow}
wrapped\_-\>Run(inputs, output\_tensor\_names, target\_node\_names,
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  outputs);
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  }
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} 
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  Status Run([const]{.keyword} RunOptions&
run\_options,
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [const]{.keyword}
std::vector\<std::pair\<string, Tensor\>\>& inputs,
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [const]{.keyword} std::vector\<string\>&
output\_tensor\_names,
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [const]{.keyword} std::vector\<string\>&
target\_node\_names,
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  std::vector\<Tensor\>\* outputs,
RunMetadata\* run\_metadata)[ override ]{.keyword}{
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  [return]{.keywordflow}
wrapped\_-\>Run(run\_options, inputs, output\_tensor\_names,
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  target\_node\_names, outputs, run\_metadata);
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  }
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} 
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  Status Run([const]{.keyword} RunOptions&
run\_options,
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [const]{.keyword}
std::vector\<std::pair\<string, Tensor\>\>& inputs,
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [const]{.keyword} std::vector\<string\>&
output\_tensor\_names,
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [const]{.keyword} std::vector\<string\>&
target\_node\_names,
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  std::vector\<Tensor\>\* outputs,
RunMetadata\* run\_metadata,
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [const]{.keyword} thread::ThreadPoolOptions&
thread\_pool\_options)[ override ]{.keyword}{
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  [return]{.keywordflow}
wrapped\_-\>Run(run\_options, inputs, output\_tensor\_names,
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  target\_node\_names, outputs, run\_metadata,
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  thread\_pool\_options);
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  }
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} 
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  Status
ListDevices(std::vector\<DeviceAttributes\>\* response)[ override
]{.keyword}{
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  [return]{.keywordflow}
wrapped\_-\>ListDevices(response);
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  }
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} 
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  std::unique\_ptr\<Session\> wrapped\_;
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} 
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([ServingSessionWrapper](classtensorflow_1_1serving_1_1ServingSessionWrapper.html){.code});
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} };
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} 
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} [// Subclass of SessionWrapper which reroutes
Run() calls with]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} [// thread\_pool\_options to Run() without
those options. This is to provide]{.comment}
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} [// support for RemoteSession::Run which does
not implement the overloaded Run()]{.comment}
:::

::: {.line}
[]{#l00099}[ 99]{.lineno} [// method with thread pool
options.]{.comment}
:::

::: {.line}
[]{#l00100}[
[100](classtensorflow_1_1serving_1_1SessionWrapperIgnoreThreadPoolOptions.html){.line}]{.lineno} [class
]{.keyword}[SessionWrapperIgnoreThreadPoolOptions](classtensorflow_1_1serving_1_1SessionWrapperIgnoreThreadPoolOptions.html){.code}
: [public]{.keyword}
[ServingSessionWrapper](classtensorflow_1_1serving_1_1ServingSessionWrapper.html){.code}
{
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [explicit]{.keyword}
[SessionWrapperIgnoreThreadPoolOptions](classtensorflow_1_1serving_1_1SessionWrapperIgnoreThreadPoolOptions.html){.code}(
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  std::unique\_ptr\<Session\> wrapped)
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  :
[ServingSessionWrapper](classtensorflow_1_1serving_1_1ServingSessionWrapper.html){.code}(std::move(wrapped))
{
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  VLOG(2) \<\< [\"Created the
SessionWrapperIgnoreThreadPoolOptions around the \"]{.stringliteral}
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  [\"Session.\"]{.stringliteral};
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  }
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} 
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  Status Run([const]{.keyword} RunOptions&
run\_options,
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  [const]{.keyword}
std::vector\<std::pair\<string, Tensor\>\>& inputs,
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  [const]{.keyword} std::vector\<string\>&
output\_tensor\_names,
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  [const]{.keyword} std::vector\<string\>&
target\_node\_names,
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  std::vector\<Tensor\>\* outputs,
RunMetadata\* run\_metadata,
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [const]{.keyword} thread::ThreadPoolOptions&
thread\_pool\_options)[ override ]{.keyword}{
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  [return]{.keywordflow}
ServingSessionWrapper::Run(run\_options, inputs, output\_tensor\_names,
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  target\_node\_names, outputs,
run\_metadata);
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  }
:::

::: {.line}
[]{#l00118}[ 118]{.lineno} 
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([SessionWrapperIgnoreThreadPoolOptions](classtensorflow_1_1serving_1_1SessionWrapperIgnoreThreadPoolOptions.html){.code});
:::

::: {.line}
[]{#l00121}[ 121]{.lineno} };
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} 
:::

::: {.line}
[]{#l00123}[ 123]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00124}[ 124]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} 
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_SERVING\_SESSION\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1ServingSessionWrapper_html .ttc}
::: {.ttname}
[tensorflow::serving::ServingSessionWrapper](classtensorflow_1_1serving_1_1ServingSessionWrapper.html)
:::

::: {.ttdef}
**Definition:** serving\_session.h:49
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServingSession_html .ttc}
::: {.ttname}
[tensorflow::serving::ServingSession](classtensorflow_1_1serving_1_1ServingSession.html)
:::

::: {.ttdef}
**Definition:** serving\_session.h:34
:::
:::

::: {#aclasstensorflow_1_1serving_1_1SessionWrapperIgnoreThreadPoolOptions_html .ttc}
::: {.ttname}
[tensorflow::serving::SessionWrapperIgnoreThreadPoolOptions](classtensorflow_1_1serving_1_1SessionWrapperIgnoreThreadPoolOptions.html)
:::

::: {.ttdef}
**Definition:** serving\_session.h:100
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

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
-   [core](dir_517df0ab1daf8f221f60ae5135602a49.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
log\_collector.h
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
TENSORFLOW\_SERVING\_CORE\_LOG\_COLLECTOR\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_LOG\_COLLECTOR\_H\_]{.preprocessor}
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
[]{#l00022}[ 22]{.lineno} 
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"google/protobuf/message.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/config/log\_collector\_config.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} 
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} 
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [// LogCollector defines an abstract interface
to use for collecting logs.]{.comment}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [// Each LogCollector implementation is
registered along with a \'type\', and if a]{.comment}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [// LogCollector is created using this API, we
create the LogCollector]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [// corresponding to the \'type\'
specified.]{.comment}
:::

::: {.line}
[]{#l00035}[
[35](classtensorflow_1_1serving_1_1LogCollector.html){.line}]{.lineno} [class
]{.keyword}[LogCollector](classtensorflow_1_1serving_1_1LogCollector.html){.code}
{
:::

::: {.line}
[]{#l00036}[ 36]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00037}[ 37]{.lineno}  [virtual]{.keyword}
\~[LogCollector](classtensorflow_1_1serving_1_1LogCollector.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
:::

::: {.line}
[]{#l00039}[ 39]{.lineno}  [// Creates a log-collector for a given
\'log\_collector\_config\' and \'id\'. The]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno}  [// factory registered for the type,
mentioned in the config, can then be used]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno}  [// to create the log-collector. The \'id\'
argument helps in disambiguating logs]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno}  [// from replicated servers (processes), so
it could be a combination of]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno}  [// task-id and replica-id or process-id and
timestamp, etc.]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno}  [static]{.keyword} Status
Create([const]{.keyword} LogCollectorConfig& log\_collector\_config,
:::

::: {.line}
[]{#l00045}[ 45]{.lineno}  [const]{.keyword} uint32 [id]{.keywordtype},
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  std::unique\_ptr\<LogCollector\>\*
log\_collector);
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [using]{.keyword} Factory =
std::function\<decltype(Create)\>;
:::

::: {.line}
[]{#l00049}[ 49]{.lineno}  [// Registers a factory for creating
log-collectors for a particular \'type\'.]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [// Returns an error status if a factory is
already registered for the]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [// particular \'type\'.]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [static]{.keyword} Status
RegisterFactory([const]{.keyword} [string]{.keywordtype}& type,
[const]{.keyword} Factory& factory);
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} 
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [// Collects the log as a protocol
buffer.]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [virtual]{.keyword} Status
CollectMessage([const]{.keyword} google::protobuf::Message& message) =
0;
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} 
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  [// Flushes buffered data so that the data
can survive an application crash]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno}  [// (but not an OS crash).]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [virtual]{.keyword} Status Flush() = 0;
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [protected]{.keyword}:
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} 
[LogCollector](classtensorflow_1_1serving_1_1LogCollector.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} };
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} [namespace ]{.keyword}register\_log\_collector
{
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} 
:::

::: {.line}
[]{#l00067}[
[67](structtensorflow_1_1serving_1_1register__log__collector_1_1RegisterFactory.html){.line}]{.lineno} [struct
]{.keyword}[RegisterFactory](structtensorflow_1_1serving_1_1register__log__collector_1_1RegisterFactory.html){.code}
{
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} 
[RegisterFactory](structtensorflow_1_1serving_1_1register__log__collector_1_1RegisterFactory.html){.code}([const]{.keyword}
[string]{.keywordtype}& type, [const]{.keyword} LogCollector::Factory&
factory) {
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [// This check happens during global object
construction time, even before]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [// control reaches main(), so we are ok with
the crash.]{.comment}
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} 
TF\_CHECK\_OK(LogCollector::RegisterFactory(type, factory)); [// Crash
ok.]{.comment}
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  }
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} };
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} 
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} } [// namespace
register\_log\_collector]{.comment}
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} 
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} 
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} [\#define
REGISTER\_LOG\_COLLECTOR\_UNIQ\_HELPER(ctr, type, factory)
\\]{.preprocessor}
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} [ REGISTER\_LOG\_COLLECTOR\_UNIQ(ctr, type,
factory)]{.preprocessor}
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} [\#define REGISTER\_LOG\_COLLECTOR\_UNIQ(ctr,
type, factory) \\]{.preprocessor}
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} [ static
::tensorflow::serving::register\_log\_collector::RegisterFactory
\\]{.preprocessor}
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} [ register\_lgc\#\#ctr TF\_ATTRIBUTE\_UNUSED =
\\]{.preprocessor}
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} [
::tensorflow::serving::register\_log\_collector::RegisterFactory(
\\]{.preprocessor}
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} [ type, factory)]{.preprocessor}
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} 
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} [// Registers a LogCollector factory
implementation for a type.]{.comment}
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} [\#define REGISTER\_LOG\_COLLECTOR(type,
factory) \\]{.preprocessor}
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} [
REGISTER\_LOG\_COLLECTOR\_UNIQ\_HELPER(\_\_COUNTER\_\_, type,
factory)]{.preprocessor}
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} 
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_LOG\_COLLECTOR\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1LogCollector_html .ttc}
::: {.ttname}
[tensorflow::serving::LogCollector](classtensorflow_1_1serving_1_1LogCollector.html)
:::

::: {.ttdef}
**Definition:** log\_collector.h:35
:::
:::

::: {#astructtensorflow_1_1serving_1_1register__log__collector_1_1RegisterFactory_html .ttc}
::: {.ttname}
[tensorflow::serving::register\_log\_collector::RegisterFactory](structtensorflow_1_1serving_1_1register__log__collector_1_1RegisterFactory.html)
:::

::: {.ttdef}
**Definition:** log\_collector.h:67
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

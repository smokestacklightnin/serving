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
-   [model\_servers](dir_5bce3ff2a459f05fa975e832b2676e62.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
server\_core.h
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
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_SERVER\_CORE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_SERVER\_CORE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<functional\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<limits\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<map\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include \<utility\>]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} 
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"google/protobuf/any.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"absl/base/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"absl/status/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"absl/time/time.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"absl/types/optional.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [\#include
\"tensorflow/core/platform/cpu\_info.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [\#include
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [\#include
\"tensorflow/core/platform/mutex.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [\#include
\"tensorflow/core/platform/types.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [\#include
\"tensorflow\_serving/apis/model.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [\#include
\"tensorflow\_serving/config/logging\_config.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [\#include
\"tensorflow\_serving/config/model\_server\_config.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [\#include
\"tensorflow\_serving/config/platform\_config.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [\#include
\"tensorflow\_serving/core/aspired\_versions\_manager.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [\#include
\"tensorflow\_serving/core/dynamic\_source\_router.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [\#include
\"tensorflow\_serving/core/prefix\_storage\_path\_source\_adapter.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_state\_monitor.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [\#include
\"tensorflow\_serving/core/server\_request\_logger.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [\#include
\"tensorflow\_serving/core/source.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [\#include
\"tensorflow\_serving/core/source\_adapter.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [\#include
\"tensorflow\_serving/core/storage\_path.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [\#include
\"tensorflow\_serving/core/stream\_logger.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/predict\_util.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/servable.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} [\#include
\"tensorflow\_serving/sources/storage\_path/file\_system\_storage\_path\_source.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [\#include
\"tensorflow\_serving/util/event\_bus.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} [\#include
\"tensorflow\_serving/util/unique\_ptr\_with\_deps.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} 
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} 
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} [namespace ]{.keyword}test\_util {
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} [class ]{.keyword}ServerCoreTestAccess;
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} } [// namespace test\_util]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} 
:::

::: {.line}
[]{#l00074}[
[74](classtensorflow_1_1serving_1_1ServerCore.html){.line}]{.lineno} [class
]{.keyword}[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.code}
: [public]{.keyword}
[Manager](classtensorflow_1_1serving_1_1Manager.html){.code} {
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [using]{.keyword} PreLoadHook =
AspiredVersionsManager::PreLoadHook;
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} 
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [using]{.keyword} ServableStateMonitorCreator
=
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} 
std::function\<Status([EventBus\<ServableState\>](classtensorflow_1_1serving_1_1EventBus.html){.code}\*
event\_bus,
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  std::unique\_ptr\<ServableStateMonitor\>\*
monitor)\>;
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} 
:::

::: {.line}
[]{#l00087}[
[87](classtensorflow_1_1serving_1_1ServerCore.html#aded4a259be715e96c76f6d239ea68a80){.line}]{.lineno} 
[using]{.keyword}
[CustomModelConfigLoader](classtensorflow_1_1serving_1_1ServerCore.html#aded4a259be715e96c76f6d239ea68a80){.code}
= std::function\<Status(
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  const ::google::protobuf::Any& any,
[EventBus\<ServableState\>](classtensorflow_1_1serving_1_1EventBus.html){.code}\*
event\_bus,
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} 
[UniquePtrWithDeps\<AspiredVersionsManager\>](classtensorflow_1_1serving_1_1UniquePtrWithDeps.html){.code}\*
manager)\>;
:::

::: {.line}
[]{#l00090}[ 90]{.lineno} 
:::

::: {.line}
[]{#l00092}[
[92](classtensorflow_1_1serving_1_1ServerCore.html#a1112df0a65160902633dcc7590aa5a7c){.line}]{.lineno} 
[using]{.keyword}
[ServerRequestLoggerUpdater](classtensorflow_1_1serving_1_1ServerCore.html#a1112df0a65160902633dcc7590aa5a7c){.code}
=
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  std::function\<Status([const]{.keyword}
ModelServerConfig&,
[ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html){.code}\*)\>;
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} 
:::

::: {.line}
[]{#l00096}[
[96](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html){.line}]{.lineno} 
[struct
]{.keyword}[Options](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html){.code}
{
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  [// ModelServer configuration.]{.comment}
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  ModelServerConfig model\_server\_config;
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  [// Relative (non-absolute) base-paths in
model\_server\_config will]{.comment}
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  [// be prepended with
model\_config\_list\_root\_dir.]{.comment}
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  absl::optional\<string\>
model\_config\_list\_root\_dir;
:::

::: {.line}
[]{#l00102}[ 102]{.lineno} 
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  [// The AspiredVersionPolicy to use for the
manager. Must be non-null.]{.comment}
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  std::unique\_ptr\<AspiredVersionPolicy\>
aspired\_version\_policy;
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} 
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  [// See
AspiredVersionsManager::Options::custom\_sort\_actions]{.comment}
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  AspiredVersionsManager::CustomSortActionsFn
custom\_sort\_actions;
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} 
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  [// The number of threads used to load
models. If set to 0, then no thread]{.comment}
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  [// pool is used and loads are performed
serially in the manager thread.]{.comment}
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  int32 num\_load\_threads = 0;
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} 
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  [// The number of load threads used to load
the initial set of models at]{.comment}
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [// server startup. This is set high to load
up the initial set of models]{.comment}
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  [// fast, after this the server uses
num\_load\_threads.]{.comment}
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  int32 num\_initial\_load\_threads = 4.0 \*
port::NumSchedulableCPUs();
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} 
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  [// The number of threads used to unload
models. If set to 0, then no thread]{.comment}
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  [// pool is used and unloads are performed
serially in the manager thread.]{.comment}
:::

::: {.line}
[]{#l00120}[ 120]{.lineno}  int32 num\_unload\_threads = 0;
:::

::: {.line}
[]{#l00121}[ 121]{.lineno} 
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  [// Total model size limit, in terms of main
memory, in bytes.]{.comment}
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  uint64\_t total\_model\_memory\_limit\_bytes
=
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  std::numeric\_limits\<uint64\_t\>::max();
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} 
:::

::: {.line}
[]{#l00126}[ 126]{.lineno}  [// Maximum number of times we retry loading
a model, after the first]{.comment}
:::

::: {.line}
[]{#l00127}[ 127]{.lineno}  [// failure, before we give up.]{.comment}
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  [// If set to 0, a load is attempted only
once.]{.comment}
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  int32 max\_num\_load\_retries = 5;
:::

::: {.line}
[]{#l00131}[ 131]{.lineno} 
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  [// The interval, in microseconds, between
each servable load retry. If set]{.comment}
:::

::: {.line}
[]{#l00133}[ 133]{.lineno}  [// negative, we don\'t wait.]{.comment}
:::

::: {.line}
[]{#l00134}[ 134]{.lineno}  [// Default: 1 minute.]{.comment}
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  int64\_t load\_retry\_interval\_micros = 1LL
\* 60 \* 1000 \* 1000;
:::

::: {.line}
[]{#l00136}[ 136]{.lineno} 
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  [// Time interval between file-system polls,
in seconds.]{.comment}
:::

::: {.line}
[]{#l00138}[ 138]{.lineno}  int32 file\_system\_poll\_wait\_seconds =
30;
:::

::: {.line}
[]{#l00139}[ 139]{.lineno} 
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  [// If true, filesystem caches are flushed
in the following cases:]{.comment}
:::

::: {.line}
[]{#l00141}[ 141]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00142}[ 142]{.lineno}  [// 1) After the initial models are
loaded.]{.comment}
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  [// 2) After a new config is supplied and a
changed set of models are loaded.]{.comment}
:::

::: {.line}
[]{#l00144}[ 144]{.lineno}  [// 3) After each new model version is
loaded, if num\_load\_threads == 1.]{.comment}
:::

::: {.line}
[]{#l00145}[ 145]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  [// In the common scenario where the number
of load threads is set to 1 after]{.comment}
:::

::: {.line}
[]{#l00147}[ 147]{.lineno}  [// the initial load, this will take care of
flushing the cache once after]{.comment}
:::

::: {.line}
[]{#l00148}[ 148]{.lineno}  [// the initial load, and after every
subsequent load of every model version.]{.comment}
:::

::: {.line}
[]{#l00149}[ 149]{.lineno}  [bool]{.keywordtype}
flush\_filesystem\_caches = [false]{.keyword};
:::

::: {.line}
[]{#l00150}[ 150]{.lineno} 
:::

::: {.line}
[]{#l00151}[ 151]{.lineno}  [// Configuration for the supported
platforms.]{.comment}
:::

::: {.line}
[]{#l00152}[ 152]{.lineno}  PlatformConfigMap platform\_config\_map;
:::

::: {.line}
[]{#l00153}[ 153]{.lineno} 
:::

::: {.line}
[]{#l00154}[ 154]{.lineno}  [// A function for creating
ServableStateMonitor. If not specified, a default]{.comment}
:::

::: {.line}
[]{#l00155}[ 155]{.lineno}  [// creator that creates
ServableStateMonitor will be used.]{.comment}
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  ServableStateMonitorCreator
servable\_state\_monitor\_creator;
:::

::: {.line}
[]{#l00157}[ 157]{.lineno} 
:::

::: {.line}
[]{#l00158}[ 158]{.lineno}  [// A function for instantiating and
connecting custom sources and source]{.comment}
:::

::: {.line}
[]{#l00159}[ 159]{.lineno}  [// adapters to the manager.]{.comment}
:::

::: {.line}
[]{#l00160}[ 160]{.lineno} 
[CustomModelConfigLoader](classtensorflow_1_1serving_1_1ServerCore.html#aded4a259be715e96c76f6d239ea68a80){.code}
custom\_model\_config\_loader;
:::

::: {.line}
[]{#l00161}[ 161]{.lineno} 
:::

::: {.line}
[]{#l00162}[ 162]{.lineno}  [// Whether to permit incoming ModelSpec
requests to use the \'version\_label\']{.comment}
:::

::: {.line}
[]{#l00163}[ 163]{.lineno}  [// field.]{.comment}
:::

::: {.line}
[]{#l00164}[ 164]{.lineno}  [bool]{.keywordtype} allow\_version\_labels
= [true]{.keyword};
:::

::: {.line}
[]{#l00165}[ 165]{.lineno} 
:::

::: {.line}
[]{#l00166}[ 166]{.lineno}  [// If set to true, the server will fail to
start up (or fail a config]{.comment}
:::

::: {.line}
[]{#l00167}[ 167]{.lineno}  [// reload) if, for any configured model, no
versions of the model are found]{.comment}
:::

::: {.line}
[]{#l00168}[ 168]{.lineno}  [// in the filesystem under the model\'s
base path.]{.comment}
:::

::: {.line}
[]{#l00169}[ 169]{.lineno}  ABSL\_DEPRECATED([\"Use
servable\_versions\_always\_present.\"]{.stringliteral})
:::

::: {.line}
[]{#l00170}[ 170]{.lineno}  [bool]{.keywordtype}
fail\_if\_no\_model\_versions\_found = [false]{.keyword};
:::

::: {.line}
[]{#l00171}[ 171]{.lineno} 
:::

::: {.line}
[]{#l00172}[ 172]{.lineno}  [// For servables which end with
LoaderHarness::State::kError, enable]{.comment}
:::

::: {.line}
[]{#l00173}[ 173]{.lineno}  [// future attempts at reload to
progress.]{.comment}
:::

::: {.line}
[]{#l00174}[ 174]{.lineno}  [bool]{.keywordtype}
enable\_reload\_servables\_with\_error = [false]{.keyword};
:::

::: {.line}
[]{#l00175}[ 175]{.lineno} 
:::

::: {.line}
[]{#l00176}[ 176]{.lineno}  [// If set to true, the server will fail to
start up (or fail a config]{.comment}
:::

::: {.line}
[]{#l00177}[ 177]{.lineno}  [// reload) if, for any configured model, no
versions of the model are found]{.comment}
:::

::: {.line}
[]{#l00178}[ 178]{.lineno}  [// in the filesystem under the model\'s
base path. In addition, if the]{.comment}
:::

::: {.line}
[]{#l00179}[ 179]{.lineno}  [// filesystem polling finds no servables
under the base path for a]{.comment}
:::

::: {.line}
[]{#l00180}[ 180]{.lineno}  [// configured model, it will do nothing,
rather than unloading all versions.]{.comment}
:::

::: {.line}
[]{#l00181}[ 181]{.lineno}  [bool]{.keywordtype}
servable\_versions\_always\_present = [false]{.keyword};
:::

::: {.line}
[]{#l00182}[ 182]{.lineno} 
:::

::: {.line}
[]{#l00183}[ 183]{.lineno}  [// Logger used for logging requests hitting
the server.]{.comment}
:::

::: {.line}
[]{#l00184}[ 184]{.lineno}  std::unique\_ptr\<ServerRequestLogger\>
server\_request\_logger;
:::

::: {.line}
[]{#l00185}[ 185]{.lineno} 
:::

::: {.line}
[]{#l00186}[ 186]{.lineno}  [// If set, we use this function to update
the server\_request\_logger.]{.comment}
:::

::: {.line}
[]{#l00187}[ 187]{.lineno} 
[ServerRequestLoggerUpdater](classtensorflow_1_1serving_1_1ServerCore.html#a1112df0a65160902633dcc7590aa5a7c){.code}
server\_request\_logger\_updater;
:::

::: {.line}
[]{#l00188}[ 188]{.lineno} 
:::

::: {.line}
[]{#l00189}[ 189]{.lineno}  [// Callback to be called just before a
servable is to be loaded. This will]{.comment}
:::

::: {.line}
[]{#l00190}[ 190]{.lineno}  [// called on the same manager load thread
which starts the load.]{.comment}
:::

::: {.line}
[]{#l00191}[ 191]{.lineno}  PreLoadHook pre\_load\_hook;
:::

::: {.line}
[]{#l00192}[ 192]{.lineno} 
:::

::: {.line}
[]{#l00193}[ 193]{.lineno}  [// Whether to allow assigning unused
version labels to models that are not]{.comment}
:::

::: {.line}
[]{#l00194}[ 194]{.lineno}  [// available yet.]{.comment}
:::

::: {.line}
[]{#l00195}[ 195]{.lineno}  [bool]{.keywordtype}
allow\_version\_labels\_for\_unavailable\_models = [false]{.keyword};
:::

::: {.line}
[]{#l00196}[ 196]{.lineno} 
:::

::: {.line}
[]{#l00197}[ 197]{.lineno}  [// Whether to force-allow assigning any
version labels to models that are]{.comment}
:::

::: {.line}
[]{#l00198}[ 198]{.lineno}  [// not available yet.]{.comment}
:::

::: {.line}
[]{#l00199}[ 199]{.lineno}  [bool]{.keywordtype}
force\_allow\_any\_version\_labels\_for\_unavailable\_models =
[false]{.keyword};
:::

::: {.line}
[]{#l00200}[ 200]{.lineno} 
:::

::: {.line}
[]{#l00201}[ 201]{.lineno}  [// In a predict handler, this option
specifies how to serialize tensors]{.comment}
:::

::: {.line}
[]{#l00202}[ 202]{.lineno}  [// (e.g: as proto fields or as proto
content).]{.comment}
:::

::: {.line}
[]{#l00203}[ 203]{.lineno}  [// Serialize as proto fields by default,
for backward compatibility.]{.comment}
:::

::: {.line}
[]{#l00204}[ 204]{.lineno} 
internal::PredictResponseTensorSerializationOption
:::

::: {.line}
[]{#l00205}[ 205]{.lineno} 
predict\_response\_tensor\_serialization\_option =
:::

::: {.line}
[]{#l00206}[ 206]{.lineno} 
internal::PredictResponseTensorSerializationOption::kAsProtoField;
:::

::: {.line}
[]{#l00207}[ 207]{.lineno} 
:::

::: {.line}
[]{#l00208}[ 208]{.lineno}  [// The prefix to append to the file system
storage paths.]{.comment}
:::

::: {.line}
[]{#l00209}[ 209]{.lineno}  std::string storage\_path\_prefix;
:::

::: {.line}
[]{#l00210}[ 210]{.lineno} 
:::

::: {.line}
[]{#l00211}[ 211]{.lineno}  [bool]{.keywordtype} enable\_cors\_support =
[false]{.keyword};
:::

::: {.line}
[]{#l00212}[ 212]{.lineno} 
:::

::: {.line}
[]{#l00213}[ 213]{.lineno}  [// If true, propagate current context to
children threads (periodic]{.comment}
:::

::: {.line}
[]{#l00214}[ 214]{.lineno}  [// functions) in
AspiredVersionsManager.]{.comment}
:::

::: {.line}
[]{#l00215}[ 215]{.lineno}  [bool]{.keywordtype} with\_current\_context
= [false]{.keyword};
:::

::: {.line}
[]{#l00216}[ 216]{.lineno} 
:::

::: {.line}
[]{#l00217}[ 217]{.lineno}  [// How long to wait for servables to reach
a given state.]{.comment}
:::

::: {.line}
[]{#l00218}[ 218]{.lineno}  absl::Duration
servable\_state\_waiter\_timeout = absl::InfiniteDuration();
:::

::: {.line}
[]{#l00219}[ 219]{.lineno} 
:::

::: {.line}
[]{#l00220}[ 220]{.lineno}  [// Defines how we want to retry when model
loading fails.]{.comment}
:::

::: {.line}
[]{#l00221}[ 221]{.lineno}  std::function\<bool(absl::Status)\>
should\_retry\_model\_load;
:::

::: {.line}
[]{#l00222}[ 222]{.lineno}  };
:::

::: {.line}
[]{#l00223}[ 223]{.lineno} 
:::

::: {.line}
[]{#l00224}[ 224]{.lineno}  [virtual]{.keyword}
\~[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.code}() =
[default]{.keywordflow};
:::

::: {.line}
[]{#l00225}[ 225]{.lineno} 
:::

::: {.line}
[]{#l00232}[ 232]{.lineno}  [static]{.keyword} Status
[Create](classtensorflow_1_1serving_1_1ServerCore.html#a538a0253233bd77da1051a985e3c2642){.code}([Options](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html){.code}
options, std::unique\_ptr\<ServerCore\>\* core);
:::

::: {.line}
[]{#l00233}[ 233]{.lineno} 
:::

::: {.line}
[]{#l00234}[
[234](classtensorflow_1_1serving_1_1ServerCore.html#ac88da0268e401fa99bcd074e692ee709){.line}]{.lineno} 
std::vector\<ServableId\>
[ListAvailableServableIds](classtensorflow_1_1serving_1_1ServerCore.html#ac88da0268e401fa99bcd074e692ee709){.code}()[
const override ]{.keyword}{
:::

::: {.line}
[]{#l00235}[ 235]{.lineno}  [return]{.keywordflow}
manager\_-\>ListAvailableServableIds();
:::

::: {.line}
[]{#l00236}[ 236]{.lineno}  }
:::

::: {.line}
[]{#l00237}[ 237]{.lineno} 
:::

::: {.line}
[]{#l00247}[ 247]{.lineno}  [virtual]{.keyword} Status
[ReloadConfig](classtensorflow_1_1serving_1_1ServerCore.html#ac3fbf30a022d978159532c2c68384669){.code}([const]{.keyword}
ModelServerConfig& config)
:::

::: {.line}
[]{#l00248}[ 248]{.lineno}  TF\_LOCKS\_EXCLUDED(config\_mu\_);
:::

::: {.line}
[]{#l00249}[ 249]{.lineno} 
:::

::: {.line}
[]{#l00251}[
[251](classtensorflow_1_1serving_1_1ServerCore.html#ac435225d6ad57889e29d524b32b84c46){.line}]{.lineno} 
[virtual]{.keyword}
[ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.code}\*
[servable\_state\_monitor](classtensorflow_1_1serving_1_1ServerCore.html#ac435225d6ad57889e29d524b32b84c46){.code}()[
const ]{.keyword}{
:::

::: {.line}
[]{#l00252}[ 252]{.lineno}  [return]{.keywordflow}
servable\_state\_monitor\_.get();
:::

::: {.line}
[]{#l00253}[ 253]{.lineno}  }
:::

::: {.line}
[]{#l00254}[ 254]{.lineno} 
:::

::: {.line}
[]{#l00266}[ 266]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00267}[
[267](classtensorflow_1_1serving_1_1ServerCore.html#adbe7fed540950b47bf889d3414239dbf){.line}]{.lineno} 
Status
[GetServableHandle](classtensorflow_1_1serving_1_1ServerCore.html#adbe7fed540950b47bf889d3414239dbf){.code}([const]{.keyword}
ModelSpec& model\_spec,
:::

::: {.line}
[]{#l00268}[ 268]{.lineno} 
[ServableHandle\<T\>](classtensorflow_1_1serving_1_1ServableHandle.html){.code}\*
[const]{.keyword} handle) {
:::

::: {.line}
[]{#l00269}[ 269]{.lineno} 
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.code}
servable\_request;
:::

::: {.line}
[]{#l00270}[ 270]{.lineno}  tensorflow::Status status =
:::

::: {.line}
[]{#l00271}[ 271]{.lineno}  ServableRequestFromModelSpec(model\_spec,
&servable\_request);
:::

::: {.line}
[]{#l00272}[ 272]{.lineno}  [if]{.keywordflow} (!status.ok()) {
:::

::: {.line}
[]{#l00273}[ 273]{.lineno}  VLOG(1) \<\< [\"Unable to get servable
handle due to: \"]{.stringliteral} \<\< status;
:::

::: {.line}
[]{#l00274}[ 274]{.lineno}  [return]{.keywordflow} status;
:::

::: {.line}
[]{#l00275}[ 275]{.lineno}  }
:::

::: {.line}
[]{#l00276}[ 276]{.lineno}  status =
manager\_-\>GetServableHandle(servable\_request, handle);
:::

::: {.line}
[]{#l00277}[ 277]{.lineno}  [if]{.keywordflow} (!status.ok()) {
:::

::: {.line}
[]{#l00278}[ 278]{.lineno}  VLOG(1) \<\< [\"Unable to get servable
handle due to: \"]{.stringliteral} \<\< status;
:::

::: {.line}
[]{#l00279}[ 279]{.lineno}  [return]{.keywordflow} status;
:::

::: {.line}
[]{#l00280}[ 280]{.lineno}  }
:::

::: {.line}
[]{#l00281}[ 281]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00282}[ 282]{.lineno}  }
:::

::: {.line}
[]{#l00283}[ 283]{.lineno} 
:::

::: {.line}
[]{#l00284}[ 284]{.lineno}  [// This specialized version allows us to
override GetServableHandle for]{.comment}
:::

::: {.line}
[]{#l00285}[ 285]{.lineno}  [// Servables in sub-classes. Useful for
testing.]{.comment}
:::

::: {.line}
[]{#l00286}[ 286]{.lineno}  [virtual]{.keyword} Status
[GetServableHandle](classtensorflow_1_1serving_1_1ServerCore.html#adbe7fed540950b47bf889d3414239dbf){.code}([const]{.keyword}
ModelSpec& model\_spec,
:::

::: {.line}
[]{#l00287}[ 287]{.lineno} 
[ServableHandle\<Servable\>](classtensorflow_1_1serving_1_1ServableHandle.html){.code}\*
[const]{.keyword} handle) {
:::

::: {.line}
[]{#l00288}[ 288]{.lineno}  [return]{.keywordflow}
GetServableHandle\<Servable\>(model\_spec, handle);
:::

::: {.line}
[]{#l00289}[ 289]{.lineno}  }
:::

::: {.line}
[]{#l00290}[ 290]{.lineno} 
:::

::: {.line}
[]{#l00291}[ 291]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00292}[ 292]{.lineno}  std::map\<ServableId, ServableHandle\<T\>\>
GetAvailableServableHandles()[ const ]{.keyword}{
:::

::: {.line}
[]{#l00293}[ 293]{.lineno}  [return]{.keywordflow}
manager\_-\>GetAvailableServableHandles\<T\>();
:::

::: {.line}
[]{#l00294}[ 294]{.lineno}  }
:::

::: {.line}
[]{#l00295}[ 295]{.lineno} 
:::

::: {.line}
[]{#l00299}[
[299](classtensorflow_1_1serving_1_1ServerCore.html#a7eec47dca427a8fcf5e345572bf818e4){.line}]{.lineno} 
[virtual]{.keyword} Status
[Log](classtensorflow_1_1serving_1_1ServerCore.html#a7eec47dca427a8fcf5e345572bf818e4){.code}([const]{.keyword}
google::protobuf::Message& request,
:::

::: {.line}
[]{#l00300}[ 300]{.lineno}  [const]{.keyword} google::protobuf::Message&
response,
:::

::: {.line}
[]{#l00301}[ 301]{.lineno}  [const]{.keyword} LogMetadata&
log\_metadata) {
:::

::: {.line}
[]{#l00302}[ 302]{.lineno}  [return]{.keywordflow}
options\_.server\_request\_logger-\>Log(request, response,
log\_metadata);
:::

::: {.line}
[]{#l00303}[ 303]{.lineno}  }
:::

::: {.line}
[]{#l00304}[ 304]{.lineno} 
:::

::: {.line}
[]{#l00305}[ 305]{.lineno}  [// Starts logging a stream through
returning a StreamLogger created through]{.comment}
:::

::: {.line}
[]{#l00306}[ 306]{.lineno}  [// \`create\_stream\_logger\_fn\`. Returns
NULL if the stream should not be logged.]{.comment}
:::

::: {.line}
[]{#l00307}[ 307]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
Request, [typename]{.keyword} Response\>
:::

::: {.line}
[]{#l00308}[ 308]{.lineno}  std::unique\_ptr\<StreamLogger\<Request,
Response\>\> StartLoggingStream(
:::

::: {.line}
[]{#l00309}[ 309]{.lineno}  [const]{.keyword} LogMetadata&
log\_metadata,
:::

::: {.line}
[]{#l00310}[ 310]{.lineno} 
ServerRequestLogger::CreateStreamLoggerFn\<Request, Response\>
:::

::: {.line}
[]{#l00311}[ 311]{.lineno}  create\_stream\_logger\_fn) {
:::

::: {.line}
[]{#l00312}[ 312]{.lineno}  [return]{.keywordflow}
options\_.server\_request\_logger-\>StartLoggingStream(
:::

::: {.line}
[]{#l00313}[ 313]{.lineno}  log\_metadata,
std::move(create\_stream\_logger\_fn));
:::

::: {.line}
[]{#l00314}[ 314]{.lineno}  }
:::

::: {.line}
[]{#l00315}[ 315]{.lineno} 
:::

::: {.line}
[]{#l00316}[ 316]{.lineno} 
internal::PredictResponseTensorSerializationOption
:::

::: {.line}
[]{#l00317}[ 317]{.lineno} 
predict\_response\_tensor\_serialization\_option()[ const ]{.keyword}{
:::

::: {.line}
[]{#l00318}[ 318]{.lineno}  [return]{.keywordflow}
options\_.predict\_response\_tensor\_serialization\_option;
:::

::: {.line}
[]{#l00319}[ 319]{.lineno}  }
:::

::: {.line}
[]{#l00320}[ 320]{.lineno} 
:::

::: {.line}
[]{#l00321}[ 321]{.lineno}  [bool]{.keywordtype}
enable\_cors\_support()[ const ]{.keyword}{ [return]{.keywordflow}
options\_.enable\_cors\_support; }
:::

::: {.line}
[]{#l00322}[ 322]{.lineno} 
:::

::: {.line}
[]{#l00323}[ 323]{.lineno}  [protected]{.keyword}:
:::

::: {.line}
[]{#l00324}[ 324]{.lineno}  ServerCore(Options options);
:::

::: {.line}
[]{#l00325}[ 325]{.lineno} 
:::

::: {.line}
[]{#l00326}[ 326]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00327}[ 327]{.lineno}  [friend]{.keyword} [class
]{.keyword}test\_util::ServerCoreTestAccess;
:::

::: {.line}
[]{#l00328}[ 328]{.lineno} 
:::

::: {.line}
[]{#l00329}[ 329]{.lineno}  [//
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*]{.comment}
:::

::: {.line}
[]{#l00330}[ 330]{.lineno}  [// Server Setup and
Initialization.]{.comment}
:::

::: {.line}
[]{#l00331}[ 331]{.lineno}  [//
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*]{.comment}
:::

::: {.line}
[]{#l00332}[ 332]{.lineno} 
:::

::: {.line}
[]{#l00333}[ 333]{.lineno}  [// Initializes server core.]{.comment}
:::

::: {.line}
[]{#l00334}[ 334]{.lineno}  [// Must be run once and only once per
ServerCore instance.]{.comment}
:::

::: {.line}
[]{#l00335}[ 335]{.lineno}  Status Initialize(
:::

::: {.line}
[]{#l00336}[ 336]{.lineno}  std::unique\_ptr\<AspiredVersionPolicy\>
aspired\_version\_policy,
:::

::: {.line}
[]{#l00337}[ 337]{.lineno}  AspiredVersionsManager::CustomSortActionsFn
custom\_sort\_actions);
:::

::: {.line}
[]{#l00338}[ 338]{.lineno} 
:::

::: {.line}
[]{#l00339}[ 339]{.lineno}  [// Creates a AspiredVersionsManager with
the specified policy.]{.comment}
:::

::: {.line}
[]{#l00340}[ 340]{.lineno}  Status CreateAspiredVersionsManager(
:::

::: {.line}
[]{#l00341}[ 341]{.lineno}  std::unique\_ptr\<AspiredVersionPolicy\>
policy,
:::

::: {.line}
[]{#l00342}[ 342]{.lineno}  AspiredVersionsManager::CustomSortActionsFn
custom\_sort\_actions,
:::

::: {.line}
[]{#l00343}[ 343]{.lineno}  std::unique\_ptr\<AspiredVersionsManager\>\*
manager);
:::

::: {.line}
[]{#l00344}[ 344]{.lineno} 
:::

::: {.line}
[]{#l00345}[ 345]{.lineno}  [// Creates a ResourceTracker.]{.comment}
:::

::: {.line}
[]{#l00346}[ 346]{.lineno}  Status CreateResourceTracker(
:::

::: {.line}
[]{#l00347}[ 347]{.lineno}  std::unique\_ptr\<ResourceTracker\>\*
resource\_tracker);
:::

::: {.line}
[]{#l00348}[ 348]{.lineno} 
:::

::: {.line}
[]{#l00349}[ 349]{.lineno}  [// Creates a platform-specific source
adapter.]{.comment}
:::

::: {.line}
[]{#l00350}[ 350]{.lineno}  Status CreateAdapter(
:::

::: {.line}
[]{#l00351}[ 351]{.lineno}  [const]{.keyword} [string]{.keywordtype}&
model\_platform,
:::

::: {.line}
[]{#l00352}[ 352]{.lineno} 
std::unique\_ptr\<StoragePathSourceAdapter\>\* adapter)
[const]{.keyword};
:::

::: {.line}
[]{#l00353}[ 353]{.lineno} 
:::

::: {.line}
[]{#l00354}[ 354]{.lineno}  [// Creates a
FileSystemStoragePathSourceConfig from the ModelConfigList of]{.comment}
:::

::: {.line}
[]{#l00355}[ 355]{.lineno}  [// \'config\'.]{.comment}
:::

::: {.line}
[]{#l00356}[ 356]{.lineno}  FileSystemStoragePathSourceConfig
CreateStoragePathSourceConfig(
:::

::: {.line}
[]{#l00357}[ 357]{.lineno}  [const]{.keyword} ModelServerConfig& config)
[const]{.keyword};
:::

::: {.line}
[]{#l00358}[ 358]{.lineno} 
:::

::: {.line}
[]{#l00359}[ 359]{.lineno}  [// Creates routes for a DynamicSourceRouter
from the ModelConfigList of]{.comment}
:::

::: {.line}
[]{#l00360}[ 360]{.lineno}  [// \'config\'.]{.comment}
:::

::: {.line}
[]{#l00361}[ 361]{.lineno}  Status CreateStoragePathRoutes(
:::

::: {.line}
[]{#l00362}[ 362]{.lineno}  [const]{.keyword} ModelServerConfig& config,
:::

::: {.line}
[]{#l00363}[ 363]{.lineno}  DynamicSourceRouter\<StoragePath\>::Routes\*
routes) [const]{.keyword};
:::

::: {.line}
[]{#l00364}[ 364]{.lineno} 
:::

::: {.line}
[]{#l00365}[ 365]{.lineno}  [// Waits until all entries in \'models\'
have been loaded, according to]{.comment}
:::

::: {.line}
[]{#l00366}[ 366]{.lineno}  [// \'monitor\'. Returns an error if any
model fails to load.]{.comment}
:::

::: {.line}
[]{#l00367}[ 367]{.lineno}  Status
WaitUntilModelsAvailable([const]{.keyword} std::set\<string\>& models,
:::

::: {.line}
[]{#l00368}[ 368]{.lineno}  ServableStateMonitor\* monitor);
:::

::: {.line}
[]{#l00369}[ 369]{.lineno} 
:::

::: {.line}
[]{#l00370}[ 370]{.lineno}  [// Creates a FileSystemStoragePathSource
and an optional]{.comment}
:::

::: {.line}
[]{#l00371}[ 371]{.lineno}  [// PrefixStoragePathSourceAdapter, and
connects them to the supplied target.]{.comment}
:::

::: {.line}
[]{#l00372}[ 372]{.lineno}  Status CreateStoragePathSource(
:::

::: {.line}
[]{#l00373}[ 373]{.lineno}  [const]{.keyword}
FileSystemStoragePathSourceConfig& config,
:::

::: {.line}
[]{#l00374}[ 374]{.lineno}  Target\<StoragePath\>\* target,
:::

::: {.line}
[]{#l00375}[ 375]{.lineno} 
std::unique\_ptr\<FileSystemStoragePathSource\>\* source,
:::

::: {.line}
[]{#l00376}[ 376]{.lineno} 
std::unique\_ptr\<PrefixStoragePathSourceAdapter\>\*
prefix\_source\_adapter)
:::

::: {.line}
[]{#l00377}[ 377]{.lineno} 
TF\_EXCLUSIVE\_LOCKS\_REQUIRED(config\_mu\_);
:::

::: {.line}
[]{#l00378}[ 378]{.lineno} 
:::

::: {.line}
[]{#l00379}[ 379]{.lineno}  [// The source adapters to deploy, to handle
the configured platforms as well]{.comment}
:::

::: {.line}
[]{#l00380}[ 380]{.lineno}  [// as models whose platform is unknown
(errors).]{.comment}
:::

::: {.line}
[]{#l00381}[ 381]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00382}[ 382]{.lineno}  [// Importantly, we deploy one source
adapter per platform, not one per model,]{.comment}
:::

::: {.line}
[]{#l00383}[ 383]{.lineno}  [// to handle cross-model optimizations that
some platforms/adapters may employ]{.comment}
:::

::: {.line}
[]{#l00384}[ 384]{.lineno}  [// e.g. cross-model batch
scheduling.]{.comment}
:::

::: {.line}
[]{#l00385}[ 385]{.lineno}  [struct ]{.keyword}SourceAdapters {
:::

::: {.line}
[]{#l00386}[ 386]{.lineno}  [// One adapter for each
platform.]{.comment}
:::

::: {.line}
[]{#l00387}[ 387]{.lineno}  std::map\<string,
std::unique\_ptr\<StoragePathSourceAdapter\>\>
:::

::: {.line}
[]{#l00388}[ 388]{.lineno}  platform\_adapters;
:::

::: {.line}
[]{#l00389}[ 389]{.lineno} 
:::

::: {.line}
[]{#l00390}[ 390]{.lineno}  [// An extra adapter to report errors for
models with no configured platform.]{.comment}
:::

::: {.line}
[]{#l00391}[ 391]{.lineno}  std::unique\_ptr\<StoragePathSourceAdapter\>
error\_adapter;
:::

::: {.line}
[]{#l00392}[ 392]{.lineno}  };
:::

::: {.line}
[]{#l00393}[ 393]{.lineno} 
:::

::: {.line}
[]{#l00394}[ 394]{.lineno}  [// Creates a source router and connects it
to the supplied adapter targets.]{.comment}
:::

::: {.line}
[]{#l00395}[ 395]{.lineno}  Status CreateRouter(
:::

::: {.line}
[]{#l00396}[ 396]{.lineno}  [const]{.keyword}
DynamicSourceRouter\<StoragePath\>::Routes& routes,
:::

::: {.line}
[]{#l00397}[ 397]{.lineno}  SourceAdapters\* targets,
:::

::: {.line}
[]{#l00398}[ 398]{.lineno} 
std::unique\_ptr\<DynamicSourceRouter\<StoragePath\>\>\* router)
[const]{.keyword};
:::

::: {.line}
[]{#l00399}[ 399]{.lineno} 
:::

::: {.line}
[]{#l00400}[ 400]{.lineno}  [// Creates a set of source adapters based
on options\_.platform\_config\_map.]{.comment}
:::

::: {.line}
[]{#l00401}[ 401]{.lineno}  Status CreateAdapters(SourceAdapters\*
adapters) [const]{.keyword};
:::

::: {.line}
[]{#l00402}[ 402]{.lineno} 
:::

::: {.line}
[]{#l00403}[ 403]{.lineno}  [// Connects the source adapters to the
manager and waits it to load all]{.comment}
:::

::: {.line}
[]{#l00404}[ 404]{.lineno}  [// configured models.]{.comment}
:::

::: {.line}
[]{#l00405}[ 405]{.lineno}  Status
ConnectAdaptersToManagerAndAwaitModelLoads(SourceAdapters\* adapters)
:::

::: {.line}
[]{#l00406}[ 406]{.lineno} 
TF\_EXCLUSIVE\_LOCKS\_REQUIRED(config\_mu\_);
:::

::: {.line}
[]{#l00407}[ 407]{.lineno} 
:::

::: {.line}
[]{#l00408}[ 408]{.lineno}  [// Updates the config of
\'storage\_path\_source\_and\_router\_-\>source\'.]{.comment}
:::

::: {.line}
[]{#l00409}[ 409]{.lineno}  Status ReloadStoragePathSourceConfig(
:::

::: {.line}
[]{#l00410}[ 410]{.lineno}  [const]{.keyword}
FileSystemStoragePathSourceConfig& source\_config)
:::

::: {.line}
[]{#l00411}[ 411]{.lineno} 
TF\_EXCLUSIVE\_LOCKS\_REQUIRED(config\_mu\_);
:::

::: {.line}
[]{#l00412}[ 412]{.lineno} 
:::

::: {.line}
[]{#l00413}[ 413]{.lineno}  [// Updates the configured routes of
\'storage\_path\_source\_and\_router\_-\>router\'.]{.comment}
:::

::: {.line}
[]{#l00414}[ 414]{.lineno}  Status ReloadRoutes([const]{.keyword}
DynamicSourceRouter\<StoragePath\>::Routes& routes)
:::

::: {.line}
[]{#l00415}[ 415]{.lineno} 
TF\_EXCLUSIVE\_LOCKS\_REQUIRED(config\_mu\_);
:::

::: {.line}
[]{#l00416}[ 416]{.lineno} 
:::

::: {.line}
[]{#l00417}[ 417]{.lineno}  [// Adds/reloads models through
ModelConfigList of \'config\_\'.]{.comment}
:::

::: {.line}
[]{#l00418}[ 418]{.lineno}  Status AddModelsViaModelConfigList()
TF\_EXCLUSIVE\_LOCKS\_REQUIRED(config\_mu\_);
:::

::: {.line}
[]{#l00419}[ 419]{.lineno} 
:::

::: {.line}
[]{#l00420}[ 420]{.lineno}  [// Adds/reloads models through custom model
config of \'config\_\'.]{.comment}
:::

::: {.line}
[]{#l00421}[ 421]{.lineno}  Status AddModelsViaCustomModelConfig()
:::

::: {.line}
[]{#l00422}[ 422]{.lineno} 
TF\_EXCLUSIVE\_LOCKS\_REQUIRED(config\_mu\_);
:::

::: {.line}
[]{#l00423}[ 423]{.lineno} 
:::

::: {.line}
[]{#l00424}[ 424]{.lineno}  [// Updates the ServerRequestLogger based on
the ModelConfigList.]{.comment}
:::

::: {.line}
[]{#l00425}[ 425]{.lineno}  Status MaybeUpdateServerRequestLogger(
:::

::: {.line}
[]{#l00426}[ 426]{.lineno}  ModelServerConfig::ConfigCase config\_case)
:::

::: {.line}
[]{#l00427}[ 427]{.lineno} 
TF\_EXCLUSIVE\_LOCKS\_REQUIRED(config\_mu\_);
:::

::: {.line}
[]{#l00428}[ 428]{.lineno} 
:::

::: {.line}
[]{#l00429}[ 429]{.lineno}  [// Updates
\'model\_labels\_to\_versions\_\' based on \'config\_\'. Throws an error
if]{.comment}
:::

::: {.line}
[]{#l00430}[ 430]{.lineno}  [// requesting to assign an existing label
to a version not in state]{.comment}
:::

::: {.line}
[]{#l00431}[ 431]{.lineno}  [// kAvailable. For a new version label, it
can be assigned to a version that]{.comment}
:::

::: {.line}
[]{#l00432}[ 432]{.lineno}  [// is not in state kAvailable yet
if]{.comment}
:::

::: {.line}
[]{#l00433}[ 433]{.lineno}  [//
allow\_version\_labels\_for\_unavailable\_models is true.]{.comment}
:::

::: {.line}
[]{#l00434}[ 434]{.lineno}  Status UpdateModelVersionLabelMap()
TF\_EXCLUSIVE\_LOCKS\_REQUIRED(config\_mu\_)
:::

::: {.line}
[]{#l00435}[ 435]{.lineno} 
TF\_LOCKS\_EXCLUDED(model\_labels\_to\_versions\_mu\_);
:::

::: {.line}
[]{#l00436}[ 436]{.lineno} 
:::

::: {.line}
[]{#l00437}[ 437]{.lineno}  [//
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*]{.comment}
:::

::: {.line}
[]{#l00438}[ 438]{.lineno}  [// Request Processing.]{.comment}
:::

::: {.line}
[]{#l00439}[ 439]{.lineno}  [//
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*]{.comment}
:::

::: {.line}
[]{#l00440}[ 440]{.lineno} 
:::

::: {.line}
[]{#l00441}[ 441]{.lineno}  [// Extracts a ServableRequest from the
given ModelSpec.]{.comment}
:::

::: {.line}
[]{#l00442}[ 442]{.lineno}  Status ServableRequestFromModelSpec(const
ModelSpec& model\_spec,
:::

::: {.line}
[]{#l00443}[ 443]{.lineno}  ServableRequest\* servable\_request) const;
:::

::: {.line}
[]{#l00444}[ 444]{.lineno} 
:::

::: {.line}
[]{#l00445}[ 445]{.lineno}  [// Gets the version associated with
\'label\', for the given model name.]{.comment}
:::

::: {.line}
[]{#l00446}[ 446]{.lineno}  Status GetModelVersionForLabel(const
[string]{.keywordtype}& model\_name, const [string]{.keywordtype}&
label,
:::

::: {.line}
[]{#l00447}[ 447]{.lineno}  int64\_t\* version) const
:::

::: {.line}
[]{#l00448}[ 448]{.lineno} 
TF\_LOCKS\_EXCLUDED(model\_labels\_to\_versions\_mu\_);
:::

::: {.line}
[]{#l00449}[ 449]{.lineno} 
:::

::: {.line}
[]{#l00450}[ 450]{.lineno}  Status GetUntypedServableHandle(
:::

::: {.line}
[]{#l00451}[ 451]{.lineno}  const ServableRequest& request,
:::

::: {.line}
[]{#l00452}[ 452]{.lineno}  std::unique\_ptr\<UntypedServableHandle\>\*
untyped\_handle)[ override ]{.keyword}{
:::

::: {.line}
[]{#l00453}[ 453]{.lineno}  [return]{.keywordflow}
manager\_-\>GetUntypedServableHandle(request, untyped\_handle);
:::

::: {.line}
[]{#l00454}[ 454]{.lineno}  }
:::

::: {.line}
[]{#l00455}[ 455]{.lineno} 
:::

::: {.line}
[]{#l00456}[ 456]{.lineno}  std::map\<ServableId,
std::unique\_ptr\<UntypedServableHandle\>\>
:::

::: {.line}
[]{#l00457}[ 457]{.lineno}  GetAvailableUntypedServableHandles()[ const
override ]{.keyword}{
:::

::: {.line}
[]{#l00458}[ 458]{.lineno}  [return]{.keywordflow}
manager\_-\>GetAvailableUntypedServableHandles();
:::

::: {.line}
[]{#l00459}[ 459]{.lineno}  }
:::

::: {.line}
[]{#l00460}[ 460]{.lineno} 
:::

::: {.line}
[]{#l00461}[ 461]{.lineno}  [// The options passed to the ctor, minus
the AspiredVersionPolicy.]{.comment}
:::

::: {.line}
[]{#l00462}[ 462]{.lineno}  Options options\_;
:::

::: {.line}
[]{#l00463}[ 463]{.lineno} 
:::

::: {.line}
[]{#l00464}[ 464]{.lineno}  [// All of the supported platforms (i.e. the
ones given in]{.comment}
:::

::: {.line}
[]{#l00465}[ 465]{.lineno}  [// \'options\_.platform\_config\_map\'),
and a router output port number for each.]{.comment}
:::

::: {.line}
[]{#l00466}[ 466]{.lineno}  [// Used to deterministically associate a
platform with a source adapter.]{.comment}
:::

::: {.line}
[]{#l00467}[ 467]{.lineno}  std::map\<string, int\>
platform\_to\_router\_port\_;
:::

::: {.line}
[]{#l00468}[ 468]{.lineno} 
:::

::: {.line}
[]{#l00469}[ 469]{.lineno} 
std::shared\_ptr\<EventBus\<ServableState\>\> servable\_event\_bus\_;
:::

::: {.line}
[]{#l00470}[ 470]{.lineno}  std::shared\_ptr\<ServableStateMonitor\>
servable\_state\_monitor\_;
:::

::: {.line}
[]{#l00471}[ 471]{.lineno}  UniquePtrWithDeps\<AspiredVersionsManager\>
manager\_;
:::

::: {.line}
[]{#l00472}[ 472]{.lineno} 
:::

::: {.line}
[]{#l00473}[ 473]{.lineno}  [// The most recent config supplied to
ReloadConfig().]{.comment}
:::

::: {.line}
[]{#l00474}[ 474]{.lineno}  ModelServerConfig config\_
TF\_GUARDED\_BY(config\_mu\_);
:::

::: {.line}
[]{#l00475}[ 475]{.lineno} 
:::

::: {.line}
[]{#l00476}[ 476]{.lineno}  [// A model\_name-\>label-\>version\#
map.]{.comment}
:::

::: {.line}
[]{#l00477}[ 477]{.lineno}  std::unique\_ptr\<std::map\<string,
std::map\<string, int64\_t\>\>\>
:::

::: {.line}
[]{#l00478}[ 478]{.lineno}  model\_labels\_to\_versions\_
TF\_GUARDED\_BY(model\_labels\_to\_versions\_mu\_);
:::

::: {.line}
[]{#l00479}[ 479]{.lineno} 
:::

::: {.line}
[]{#l00480}[ 480]{.lineno}  [struct
]{.keyword}StoragePathSourceAndRouter {
:::

::: {.line}
[]{#l00481}[ 481]{.lineno}  FileSystemStoragePathSource\* source;
:::

::: {.line}
[]{#l00482}[ 482]{.lineno}  DynamicSourceRouter\<StoragePath\>\* router;
:::

::: {.line}
[]{#l00483}[ 483]{.lineno}  };
:::

::: {.line}
[]{#l00484}[ 484]{.lineno} 
:::

::: {.line}
[]{#l00485}[ 485]{.lineno}  [// If the configuration uses a file-system
source, this is populated with]{.comment}
:::

::: {.line}
[]{#l00486}[ 486]{.lineno}  [// pointers to the source and router (to
enable reconfiguration later). Both]{.comment}
:::

::: {.line}
[]{#l00487}[ 487]{.lineno}  [// are owned by \'manager\_\'.]{.comment}
:::

::: {.line}
[]{#l00488}[ 488]{.lineno}  absl::optional\<StoragePathSourceAndRouter\>
storage\_path\_source\_and\_router\_
:::

::: {.line}
[]{#l00489}[ 489]{.lineno}  TF\_GUARDED\_BY(config\_mu\_);
:::

::: {.line}
[]{#l00490}[ 490]{.lineno} 
:::

::: {.line}
[]{#l00491}[ 491]{.lineno}  [// A mutex for reconfiguration, used by
ReloadConfig().]{.comment}
:::

::: {.line}
[]{#l00492}[ 492]{.lineno}  [mutable]{.keyword} mutex config\_mu\_;
:::

::: {.line}
[]{#l00493}[ 493]{.lineno} 
:::

::: {.line}
[]{#l00494}[ 494]{.lineno}  [// A mutex for swapping the model version
label map. Should only be held for]{.comment}
:::

::: {.line}
[]{#l00495}[ 495]{.lineno}  [// a short time (i.e. pointer swap) to
avoid holding up inference requests.]{.comment}
:::

::: {.line}
[]{#l00496}[ 496]{.lineno}  [mutable]{.keyword} mutex
model\_labels\_to\_versions\_mu\_;
:::

::: {.line}
[]{#l00497}[ 497]{.lineno} };
:::

::: {.line}
[]{#l00498}[ 498]{.lineno} 
:::

::: {.line}
[]{#l00499}[ 499]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00500}[ 500]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00501}[ 501]{.lineno} 
:::

::: {.line}
[]{#l00502}[ 502]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_SERVER\_CORE\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1EventBus_html .ttc}
::: {.ttname}
[tensorflow::serving::EventBus](classtensorflow_1_1serving_1_1EventBus.html)
:::

::: {.ttdef}
**Definition:** event\_bus.h:63
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Manager_html .ttc}
::: {.ttname}
[tensorflow::serving::Manager](classtensorflow_1_1serving_1_1Manager.html)
:::

::: {.ttdef}
**Definition:** manager.h:77
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServableHandle_html .ttc}
::: {.ttname}
[tensorflow::serving::ServableHandle](classtensorflow_1_1serving_1_1ServableHandle.html)
:::

::: {.ttdef}
**Definition:** servable\_handle.h:75
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServableStateMonitor_html .ttc}
::: {.ttname}
[tensorflow::serving::ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html)
:::

::: {.ttdef}
**Definition:** servable\_state\_monitor.h:46
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServerCore_html .ttc}
::: {.ttname}
[tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html)
:::

::: {.ttdef}
**Definition:** server\_core.h:74
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServerCore_html_a1112df0a65160902633dcc7590aa5a7c .ttc}
::: {.ttname}
[tensorflow::serving::ServerCore::ServerRequestLoggerUpdater](classtensorflow_1_1serving_1_1ServerCore.html#a1112df0a65160902633dcc7590aa5a7c)
:::

::: {.ttdeci}
std::function\< Status(const ModelServerConfig &, ServerRequestLogger
\*)\> ServerRequestLoggerUpdater
:::

::: {.ttdoc}
Function signature used to update the server\_request\_logger.
:::

::: {.ttdef}
**Definition:** server\_core.h:93
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServerCore_html_a538a0253233bd77da1051a985e3c2642 .ttc}
::: {.ttname}
[tensorflow::serving::ServerCore::Create](classtensorflow_1_1serving_1_1ServerCore.html#a538a0253233bd77da1051a985e3c2642)
:::

::: {.ttdeci}
static Status Create(Options options, std::unique\_ptr\< ServerCore \>
\*core)
:::

::: {.ttdef}
**Definition:** server\_core.cc:231
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServerCore_html_a7eec47dca427a8fcf5e345572bf818e4 .ttc}
::: {.ttname}
[tensorflow::serving::ServerCore::Log](classtensorflow_1_1serving_1_1ServerCore.html#a7eec47dca427a8fcf5e345572bf818e4)
:::

::: {.ttdeci}
virtual Status Log(const google::protobuf::Message &request, const
google::protobuf::Message &response, const LogMetadata &log\_metadata)
:::

::: {.ttdef}
**Definition:** server\_core.h:299
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServerCore_html_ac3fbf30a022d978159532c2c68384669 .ttc}
::: {.ttname}
[tensorflow::serving::ServerCore::ReloadConfig](classtensorflow_1_1serving_1_1ServerCore.html#ac3fbf30a022d978159532c2c68384669)
:::

::: {.ttdeci}
virtual Status ReloadConfig(const ModelServerConfig &config)
TF\_LOCKS\_EXCLUDED(config\_mu\_)
:::

::: {.ttdef}
**Definition:** server\_core.cc:447
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServerCore_html_ac435225d6ad57889e29d524b32b84c46 .ttc}
::: {.ttname}
[tensorflow::serving::ServerCore::servable\_state\_monitor](classtensorflow_1_1serving_1_1ServerCore.html#ac435225d6ad57889e29d524b32b84c46)
:::

::: {.ttdeci}
virtual ServableStateMonitor \* servable\_state\_monitor() const
:::

::: {.ttdoc}
Returns ServableStateMonitor that can be used to query servable states.
:::

::: {.ttdef}
**Definition:** server\_core.h:251
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServerCore_html_ac88da0268e401fa99bcd074e692ee709 .ttc}
::: {.ttname}
[tensorflow::serving::ServerCore::ListAvailableServableIds](classtensorflow_1_1serving_1_1ServerCore.html#ac88da0268e401fa99bcd074e692ee709)
:::

::: {.ttdeci}
std::vector\< ServableId \> ListAvailableServableIds() const override
:::

::: {.ttdef}
**Definition:** server\_core.h:234
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServerCore_html_adbe7fed540950b47bf889d3414239dbf .ttc}
::: {.ttname}
[tensorflow::serving::ServerCore::GetServableHandle](classtensorflow_1_1serving_1_1ServerCore.html#adbe7fed540950b47bf889d3414239dbf)
:::

::: {.ttdeci}
Status GetServableHandle(const ModelSpec &model\_spec, ServableHandle\<
T \> \*const handle)
:::

::: {.ttdef}
**Definition:** server\_core.h:267
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServerCore_html_aded4a259be715e96c76f6d239ea68a80 .ttc}
::: {.ttname}
[tensorflow::serving::ServerCore::CustomModelConfigLoader](classtensorflow_1_1serving_1_1ServerCore.html#aded4a259be715e96c76f6d239ea68a80)
:::

::: {.ttdeci}
std::function\< Status(const ::google::protobuf::Any &any, EventBus\<
ServableState \> \*event\_bus, UniquePtrWithDeps\<
AspiredVersionsManager \> \*manager)\> CustomModelConfigLoader
:::

::: {.ttdef}
**Definition:** server\_core.h:89
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServerRequestLogger_html .ttc}
::: {.ttname}
[tensorflow::serving::ServerRequestLogger](classtensorflow_1_1serving_1_1ServerRequestLogger.html)
:::

::: {.ttdef}
**Definition:** server\_request\_logger.h:40
:::
:::

::: {#aclasstensorflow_1_1serving_1_1UniquePtrWithDeps_html .ttc}
::: {.ttname}
[tensorflow::serving::UniquePtrWithDeps](classtensorflow_1_1serving_1_1UniquePtrWithDeps.html)
:::

::: {.ttdef}
**Definition:** unique\_ptr\_with\_deps.h:40
:::
:::

::: {#astructtensorflow_1_1serving_1_1ServableRequest_html .ttc}
::: {.ttname}
[tensorflow::serving::ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html)
:::

::: {.ttdef}
**Definition:** manager.h:39
:::
:::

::: {#astructtensorflow_1_1serving_1_1ServerCore_1_1Options_html .ttc}
::: {.ttname}
[tensorflow::serving::ServerCore::Options](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html)
:::

::: {.ttdoc}
Options for configuring a ServerCore object.
:::

::: {.ttdef}
**Definition:** server\_core.h:96
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

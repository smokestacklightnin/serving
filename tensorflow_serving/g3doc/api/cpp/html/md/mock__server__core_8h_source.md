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
-   [test\_util](dir_36785626a2bf25c917a1b24ac423d44f.html){.el}
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
mock\_server\_core.h
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
[]{#l00016}[ 16]{.lineno} [// GMock implementation of
ServerCore.]{.comment}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_TEST\_UTIL\_MOCK\_SERVER\_CORE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} [\#define
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_TEST\_UTIL\_MOCK\_SERVER\_CORE\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} 
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
[]{#l00023}[ 23]{.lineno} 
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"google/protobuf/any.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"google/protobuf/map.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include \<gmock/gmock.h\>]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"absl/status/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow/core/platform/logging.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow\_serving/apis/logging.proto.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include
\"tensorflow\_serving/apis/model.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [\#include
\"tensorflow\_serving/config/model\_server\_config.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [\#include
\"tensorflow\_serving/config/platform\_config.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [\#include
\"tensorflow\_serving/core/aspired\_versions\_manager.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_handle.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_id.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_state.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_state\_monitor.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [\#include
\"tensorflow\_serving/core/server\_request\_logger.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [\#include
\"tensorflow\_serving/core/test\_util/fake\_loader\_source\_adapter.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [\#include
\"tensorflow\_serving/core/test\_util/servable\_handle\_test\_util.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [\#include
\"tensorflow\_serving/model\_servers/server\_core.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/servable.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [\#include
\"tensorflow\_serving/util/event\_bus.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [\#include
\"tensorflow\_serving/util/unique\_ptr\_with\_deps.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} 
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [namespace ]{.keyword}test\_util {
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} 
:::

::: {.line}
[]{#l00051}[
[51](classtensorflow_1_1serving_1_1test__util_1_1MockServerCore.html){.line}]{.lineno} [class
]{.keyword}[MockServerCore](classtensorflow_1_1serving_1_1test__util_1_1MockServerCore.html){.code}
: [public]{.keyword}
[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.code} {
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [// Creates a PlatformConfigMap with a
FakeLoaderSourceAdapterConfig.]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [static]{.keyword} PlatformConfigMap
CreateFakeLoaderPlatformConfigMap() {
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  ::google::protobuf::Any
source\_adapter\_config;
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} 
source\_adapter\_config.PackFrom(test\_util::FakeLoaderSourceAdapterConfig());
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  PlatformConfigMap platform\_config\_map;
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} 
(\*(\*platform\_config\_map.mutable\_platform\_configs())\[[\"fake\_servable\"]{.stringliteral}\]
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  .mutable\_source\_adapter\_config()) =
source\_adapter\_config;
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [return]{.keywordflow} platform\_config\_map;
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  }
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} 
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [static]{.keyword}
[Options](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html){.code}
GetOptions(
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  [const]{.keyword} PlatformConfigMap&
platform\_config\_map,
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  std::unique\_ptr\<ServerRequestLogger\>
server\_request\_logger) {
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} 
[Options](structtensorflow_1_1serving_1_1ServerCore_1_1Options.html){.code}
options;
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  options.platform\_config\_map =
platform\_config\_map;
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  options.servable\_state\_monitor\_creator =
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
\[\]([EventBus\<ServableState\>](classtensorflow_1_1serving_1_1EventBus.html){.code}\*
event\_bus,
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  std::unique\_ptr\<ServableStateMonitor\>\*
monitor) -\> Status {
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  monitor-\>reset([new]{.keyword}
[ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.code}(event\_bus));
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  };
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  options.custom\_model\_config\_loader =
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  \[\](const ::google::protobuf::Any& any,
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} 
[EventBus\<ServableState\>](classtensorflow_1_1serving_1_1EventBus.html){.code}\*
event\_bus,
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} 
[UniquePtrWithDeps\<AspiredVersionsManager\>](classtensorflow_1_1serving_1_1UniquePtrWithDeps.html){.code}\*
manager) -\> Status {
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  };
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [if]{.keywordflow} (server\_request\_logger
!= [nullptr]{.keyword}) {
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  options.server\_request\_logger =
std::move(server\_request\_logger);
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  } [else]{.keywordflow} {
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  TF\_CHECK\_OK(
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} 
ServerRequestLogger::Create([nullptr]{.keyword},
&options.server\_request\_logger));
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  }
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  [return]{.keywordflow} options;
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  }
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} 
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [explicit]{.keyword}
[MockServerCore](classtensorflow_1_1serving_1_1test__util_1_1MockServerCore.html){.code}([const]{.keyword}
PlatformConfigMap& platform\_config\_map)
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  :
[MockServerCore](classtensorflow_1_1serving_1_1test__util_1_1MockServerCore.html){.code}(platform\_config\_map,
[nullptr]{.keyword}) {}
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} 
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} 
[MockServerCore](classtensorflow_1_1serving_1_1test__util_1_1MockServerCore.html){.code}([const]{.keyword}
PlatformConfigMap& platform\_config\_map,
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  std::unique\_ptr\<ServerRequestLogger\>
server\_request\_logger)
:::

::: {.line}
[]{#l00094}[ 94]{.lineno}  :
[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.code}(GetOptions(platform\_config\_map,
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  std::move(server\_request\_logger))) {}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} 
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} 
MOCK\_METHOD([ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.code}\*,
[servable\_state\_monitor](classtensorflow_1_1serving_1_1ServerCore.html#ac435225d6ad57889e29d524b32b84c46){.code},
(),
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  ([const]{.keyword}, [override]{.keyword}));
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  MOCK\_METHOD(Status,
[ReloadConfig](classtensorflow_1_1serving_1_1ServerCore.html#ac3fbf30a022d978159532c2c68384669){.code},
([const]{.keyword} ModelServerConfig&), ([override]{.keyword}));
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  MOCK\_METHOD(Status,
[Log](classtensorflow_1_1serving_1_1ServerCore.html#a7eec47dca427a8fcf5e345572bf818e4){.code},
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  ([const]{.keyword}
google::protobuf::Message& request, [const]{.keyword}
google::protobuf::Message& response,
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [const]{.keyword} LogMetadata&
log\_metadata),
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  ([override]{.keyword}));
:::

::: {.line}
[]{#l00104}[ 104]{.lineno} 
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  [// Sets the Servable used by
GetServableHandle]{.comment}
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  [void]{.keywordtype}
SetServable(std::unique\_ptr\<Servable\> servable) {
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  servable\_ = std::move(servable);
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  }
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} 
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  Status GetServableHandle([const]{.keyword}
ModelSpec& model\_spec,
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} 
[ServableHandle\<T\>](classtensorflow_1_1serving_1_1ServableHandle.html){.code}\*
[const]{.keyword} handle) {
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  LOG(FATAL) \<\< [\"Not
implemented.\"]{.stringliteral};
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  }
:::

::: {.line}
[]{#l00115}[ 115]{.lineno} 
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  [// Implement GetServable for type Servable.
Will return the Servable]{.comment}
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  [// set by SetServable, otherwise forwards
to base class.]{.comment}
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  [virtual]{.keyword} Status
GetServableHandle(
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  [const]{.keyword} ModelSpec& model\_spec,
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} 
[ServableHandle\<Servable\>](classtensorflow_1_1serving_1_1ServableHandle.html){.code}\*
[const]{.keyword} handle)[ override ]{.keyword}{
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  [if]{.keywordflow} (servable\_) {
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  [const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}
[id]{.keywordtype} = {[\"servable\"]{.stringliteral}, 0};
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  \*handle =
WrapAsHandle\<Servable\>([id]{.keywordtype}, servable\_.get());
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  [return]{.keywordflow} absl::OkStatus();
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  } [else]{.keywordflow} {
:::

::: {.line}
[]{#l00126}[ 126]{.lineno}  [return]{.keywordflow}
ServerCore::GetServableHandle\<Servable\>(model\_spec, handle);
:::

::: {.line}
[]{#l00127}[ 127]{.lineno}  }
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  }
:::

::: {.line}
[]{#l00129}[ 129]{.lineno} 
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  std::unique\_ptr\<Servable\> servable\_;
:::

::: {.line}
[]{#l00131}[ 131]{.lineno} };
:::

::: {.line}
[]{#l00132}[ 132]{.lineno} 
:::

::: {.line}
[]{#l00133}[ 133]{.lineno} } [// namespace test\_util]{.comment}
:::

::: {.line}
[]{#l00134}[ 134]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00135}[ 135]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00136}[ 136]{.lineno} 
:::

::: {.line}
[]{#l00137}[ 137]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_MODEL\_SERVERS\_TEST\_UTIL\_MOCK\_SERVER\_CORE\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1EventBus_html .ttc}
::: {.ttname}
[tensorflow::serving::EventBus](classtensorflow_1_1serving_1_1EventBus.html)
:::

::: {.ttdef}
**Definition:** event\_bus.h:63
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

::: {#aclasstensorflow_1_1serving_1_1UniquePtrWithDeps_html .ttc}
::: {.ttname}
[tensorflow::serving::UniquePtrWithDeps](classtensorflow_1_1serving_1_1UniquePtrWithDeps.html)
:::

::: {.ttdef}
**Definition:** unique\_ptr\_with\_deps.h:40
:::
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1MockServerCore_html .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::MockServerCore](classtensorflow_1_1serving_1_1test__util_1_1MockServerCore.html)
:::

::: {.ttdef}
**Definition:** mock\_server\_core.h:51
:::
:::

::: {#astructtensorflow_1_1serving_1_1ServableId_html .ttc}
::: {.ttname}
[tensorflow::serving::ServableId](structtensorflow_1_1serving_1_1ServableId.html)
:::

::: {.ttdef}
**Definition:** servable\_id.h:33
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

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
basic\_manager.h
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
TENSORFLOW\_SERVING\_CORE\_BASIC\_MANAGER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_BASIC\_MANAGER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<atomic\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<unordered\_map\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} 
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"absl/types/optional.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow/core/lib/core/stringpiece.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow/core/lib/hash/hash.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow/core/platform/env.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow/core/platform/mutex.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include
\"tensorflow/core/platform/thread\_annotations.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [\#include
\"tensorflow/core/platform/types.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [\#include
\"tensorflow\_serving/core/loader.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [\#include
\"tensorflow\_serving/core/loader\_harness.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [\#include
\"tensorflow\_serving/core/manager.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_data.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_handle.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_id.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_state.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [\#include
\"tensorflow\_serving/resources/resource\_tracker.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [\#include
\"tensorflow\_serving/util/event\_bus.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [\#include
\"tensorflow\_serving/util/executor.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [\#include
\"tensorflow\_serving/util/fast\_read\_dynamic\_ptr.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} 
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [namespace ]{.keyword}test\_util {
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [class ]{.keyword}BasicManagerTestAccess;
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} } [// namespace test\_util]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
:::

::: {.line}
[]{#l00106}[
[106](classtensorflow_1_1serving_1_1BasicManager.html){.line}]{.lineno} [class
]{.keyword}[BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.code}
: [public]{.keyword}
[Manager](classtensorflow_1_1serving_1_1Manager.html){.code} {
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  [// Type of the callback to be called just
before a servable is to be loaded.]{.comment}
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  [using]{.keyword} PreLoadHook =
std::function\<void([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&)\>;
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} 
:::

::: {.line}
[]{#l00113}[
[113](structtensorflow_1_1serving_1_1BasicManager_1_1Options.html){.line}]{.lineno} 
[struct
]{.keyword}[Options](structtensorflow_1_1serving_1_1BasicManager_1_1Options.html){.code}
{
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [// The resource tracker to use while
managing servable resources. Optional.]{.comment}
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  [// If left as nullptr, we do not validate
servable resource usage.]{.comment}
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  std::unique\_ptr\<ResourceTracker\>
resource\_tracker;
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} 
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  [// The number of threads in the thread-pool
used to load servables.]{.comment}
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00120}[ 120]{.lineno}  [// If set as 0, we don\'t use a
thread-pool, and LoadServable() blocks.]{.comment}
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  uint32 num\_load\_threads = 0;
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} 
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  [// The number of threads in the thread-pool
used to unload servables.]{.comment}
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  [// If set as 0, we don\'t use a
thread-pool, and UnloadServable() blocks.]{.comment}
:::

::: {.line}
[]{#l00126}[ 126]{.lineno}  uint32 num\_unload\_threads = 0;
:::

::: {.line}
[]{#l00127}[ 127]{.lineno} 
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  [// Defines how we want to retry when model
loading fails.]{.comment}
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  std::function\<bool(absl::Status)\>
should\_retry\_model\_load;
:::

::: {.line}
[]{#l00130}[ 130]{.lineno} 
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  [// EventBus to publish servable state
changes. This is optional, if unset,]{.comment}
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  [// we don\'t publish.]{.comment}
:::

::: {.line}
[]{#l00133}[ 133]{.lineno} 
[EventBus\<ServableState\>](classtensorflow_1_1serving_1_1EventBus.html){.code}\*
servable\_event\_bus = [nullptr]{.keyword};
:::

::: {.line}
[]{#l00134}[ 134]{.lineno} 
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  [// Maximum number of times we retry loading
a servable, after the first]{.comment}
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  [// failure, before we give up.]{.comment}
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00138}[ 138]{.lineno}  [// If set to 0, a load is attempted only
once.]{.comment}
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  uint32 max\_num\_load\_retries = 5;
:::

::: {.line}
[]{#l00140}[ 140]{.lineno} 
:::

::: {.line}
[]{#l00141}[ 141]{.lineno}  [// The interval, in microseconds, between
each servable load retry. If set]{.comment}
:::

::: {.line}
[]{#l00142}[ 142]{.lineno}  [// negative, we don\'t wait.]{.comment}
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  [// Default: 1 minute.]{.comment}
:::

::: {.line}
[]{#l00144}[ 144]{.lineno}  int64\_t load\_retry\_interval\_micros = 1LL
\* 60 \* 1000 \* 1000;
:::

::: {.line}
[]{#l00145}[ 145]{.lineno} 
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  [// If true, and there are not multiple load
threads, filesystem caches will]{.comment}
:::

::: {.line}
[]{#l00147}[ 147]{.lineno}  [// be flushed after each servable is
loaded. (Cache flush is skipped when]{.comment}
:::

::: {.line}
[]{#l00148}[ 148]{.lineno}  [// multiple load threads are active, in
order to avoid setting back a]{.comment}
:::

::: {.line}
[]{#l00149}[ 149]{.lineno}  [// concurrent load on another
thread.)]{.comment}
:::

::: {.line}
[]{#l00150}[ 150]{.lineno}  [bool]{.keywordtype}
flush\_filesystem\_caches = [false]{.keyword};
:::

::: {.line}
[]{#l00151}[ 151]{.lineno} 
:::

::: {.line}
[]{#l00152}[ 152]{.lineno}  [// The environment to use for starting
threads in the thread-pool.]{.comment}
:::

::: {.line}
[]{#l00153}[ 153]{.lineno}  Env\* env = Env::Default();
:::

::: {.line}
[]{#l00154}[ 154]{.lineno} 
:::

::: {.line}
[]{#l00155}[ 155]{.lineno}  [// Callback to be called just before a
servable is to be loaded. This will]{.comment}
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  [// called on the same manager load thread
which starts the load.]{.comment}
:::

::: {.line}
[]{#l00157}[ 157]{.lineno}  PreLoadHook pre\_load\_hook;
:::

::: {.line}
[]{#l00158}[ 158]{.lineno}  };
:::

::: {.line}
[]{#l00159}[ 159]{.lineno}  [static]{.keyword} Status
Create([Options](structtensorflow_1_1serving_1_1BasicManager_1_1Options.html){.code}
options, std::unique\_ptr\<BasicManager\>\* manager);
:::

::: {.line}
[]{#l00160}[ 160]{.lineno} 
:::

::: {.line}
[]{#l00163}[ 163]{.lineno} 
[\~BasicManager](classtensorflow_1_1serving_1_1BasicManager.html#a492123b8bb97709184ddb57772e3ccf3){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00164}[ 164]{.lineno} 
:::

::: {.line}
[]{#l00165}[ 165]{.lineno}  std::vector\<ServableId\>
[ListAvailableServableIds](classtensorflow_1_1serving_1_1BasicManager.html#a3c004d32952596c1f5759b1cfcc3c639){.code}()
[const override]{.keyword};
:::

::: {.line}
[]{#l00166}[ 166]{.lineno} 
:::

::: {.line}
[]{#l00167}[ 167]{.lineno}  Status GetUntypedServableHandle(
:::

::: {.line}
[]{#l00168}[ 168]{.lineno}  [const]{.keyword}
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.code}&
request,
:::

::: {.line}
[]{#l00169}[ 169]{.lineno}  std::unique\_ptr\<UntypedServableHandle\>\*
untyped\_handle) [override]{.keyword};
:::

::: {.line}
[]{#l00170}[ 170]{.lineno} 
:::

::: {.line}
[]{#l00171}[ 171]{.lineno}  std::map\<ServableId,
std::unique\_ptr\<UntypedServableHandle\>\>
:::

::: {.line}
[]{#l00172}[ 172]{.lineno}  GetAvailableUntypedServableHandles() [const
override]{.keyword};
:::

::: {.line}
[]{#l00173}[ 173]{.lineno} 
:::

::: {.line}
[]{#l00184}[ 184]{.lineno}  Status
[ManageServable](classtensorflow_1_1serving_1_1BasicManager.html#ac2759caea67d3d37b9dba31589f9ef1d){.code}([ServableData](classtensorflow_1_1serving_1_1ServableData.html){.code}\<std::unique\_ptr\<Loader\>\>
servable);
:::

::: {.line}
[]{#l00185}[ 185]{.lineno} 
:::

::: {.line}
[]{#l00190}[ 190]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00191}[ 191]{.lineno}  Status
[ManageServableWithAdditionalState](classtensorflow_1_1serving_1_1BasicManager.html#a72406e3aedfa0084e24f2bd8ec7efdcc){.code}(
:::

::: {.line}
[]{#l00192}[ 192]{.lineno} 
[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.code}\<std::unique\_ptr\<Loader\>\>
servable,
:::

::: {.line}
[]{#l00193}[ 193]{.lineno}  std::unique\_ptr\<T\> additional\_state);
:::

::: {.line}
[]{#l00194}[ 194]{.lineno} 
:::

::: {.line}
[]{#l00198}[ 198]{.lineno}  Status
[StopManagingServable](classtensorflow_1_1serving_1_1BasicManager.html#a3209cd82cbb5eac79bc3238b3c6bec43){.code}([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
[id]{.keywordtype});
:::

::: {.line}
[]{#l00199}[ 199]{.lineno} 
:::

::: {.line}
[]{#l00202}[ 202]{.lineno}  std::vector\<string\>
[GetManagedServableNames](classtensorflow_1_1serving_1_1BasicManager.html#afbdc3d0ed83559c7d8b3b0092194ead6){.code}()
[const]{.keyword};
:::

::: {.line}
[]{#l00203}[ 203]{.lineno} 
:::

::: {.line}
[]{#l00208}[ 208]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
T = std::[nullptr]{.keywordtype}\_t\>
:::

::: {.line}
[]{#l00209}[ 209]{.lineno}  std::vector\<ServableStateSnapshot\<T\>\>
[GetManagedServableStateSnapshots](classtensorflow_1_1serving_1_1BasicManager.html#a31716665d8df8451d379363309dac826){.code}(
:::

::: {.line}
[]{#l00210}[ 210]{.lineno}  [const]{.keyword} [string]{.keywordtype}&
servable\_name) [const]{.keyword};
:::

::: {.line}
[]{#l00211}[ 211]{.lineno} 
:::

::: {.line}
[]{#l00217}[ 217]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
T = std::[nullptr]{.keywordtype}\_t\>
:::

::: {.line}
[]{#l00218}[ 218]{.lineno}  absl::optional\<ServableStateSnapshot\<T\>\>
[GetManagedServableStateSnapshot](classtensorflow_1_1serving_1_1BasicManager.html#af681f56bbef07ab201f25c0097f73e75){.code}(
:::

::: {.line}
[]{#l00219}[ 219]{.lineno}  [const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
[id]{.keywordtype});
:::

::: {.line}
[]{#l00220}[ 220]{.lineno} 
:::

::: {.line}
[]{#l00227}[ 227]{.lineno}  [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00228}[ 228]{.lineno}  T\*
[GetAdditionalServableState](classtensorflow_1_1serving_1_1BasicManager.html#a99dbea960f6d47461dbfca5bfa149335){.code}([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
[id]{.keywordtype});
:::

::: {.line}
[]{#l00229}[ 229]{.lineno} 
:::

::: {.line}
[]{#l00232}[
[232](classtensorflow_1_1serving_1_1BasicManager.html#a8ee7a19d059b362c0702686d981bf5fc){.line}]{.lineno} 
[using]{.keyword}
[DoneCallback](classtensorflow_1_1serving_1_1BasicManager.html#a8ee7a19d059b362c0702686d981bf5fc){.code}
= std::function\<void([const]{.keyword} Status& status)\>;
:::

::: {.line}
[]{#l00233}[ 233]{.lineno} 
:::

::: {.line}
[]{#l00246}[ 246]{.lineno}  [void]{.keywordtype}
[LoadServable](classtensorflow_1_1serving_1_1BasicManager.html#a09e87e3b0bc3410a78db3439ff0fb9bb){.code}([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
[id]{.keywordtype},
[DoneCallback](classtensorflow_1_1serving_1_1BasicManager.html#a8ee7a19d059b362c0702686d981bf5fc){.code}
done\_callback);
:::

::: {.line}
[]{#l00247}[ 247]{.lineno} 
:::

::: {.line}
[]{#l00255}[ 255]{.lineno}  [void]{.keywordtype}
[CancelLoadServableRetry](classtensorflow_1_1serving_1_1BasicManager.html#a84dca5ec1ecc28421d5ab020beac2ee3){.code}([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
[id]{.keywordtype});
:::

::: {.line}
[]{#l00256}[ 256]{.lineno} 
:::

::: {.line}
[]{#l00269}[ 269]{.lineno}  [void]{.keywordtype}
[UnloadServable](classtensorflow_1_1serving_1_1BasicManager.html#a97af7156e38c29225534bacdeefe9408){.code}([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
[id]{.keywordtype},
[DoneCallback](classtensorflow_1_1serving_1_1BasicManager.html#a8ee7a19d059b362c0702686d981bf5fc){.code}
done\_callback);
:::

::: {.line}
[]{#l00270}[ 270]{.lineno} 
:::

::: {.line}
[]{#l00271}[ 271]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00272}[ 272]{.lineno}  [friend]{.keyword} [class
]{.keyword}[AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.code};
:::

::: {.line}
[]{#l00273}[ 273]{.lineno}  [friend]{.keyword} [class
]{.keyword}[test\_util::BasicManagerTestAccess](classtensorflow_1_1serving_1_1test__util_1_1BasicManagerTestAccess.html){.code};
:::

::: {.line}
[]{#l00274}[ 274]{.lineno} 
:::

::: {.line}
[]{#l00275}[ 275]{.lineno} 
[BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.code}(Env\*
env, uint32 num\_load\_threads, uint32 num\_unload\_threads,
:::

::: {.line}
[]{#l00276}[ 276]{.lineno}  uint32 max\_num\_load\_retries,
:::

::: {.line}
[]{#l00277}[ 277]{.lineno} 
std::function\<[bool]{.keywordtype}(absl::Status)\>
should\_retry\_model\_load,
:::

::: {.line}
[]{#l00278}[ 278]{.lineno}  int64\_t load\_retry\_interval\_micros,
[bool]{.keywordtype} flush\_filesystem\_caches,
:::

::: {.line}
[]{#l00279}[ 279]{.lineno}  std::unique\_ptr\<ResourceTracker\>
resource\_tracker,
:::

::: {.line}
[]{#l00280}[ 280]{.lineno} 
[EventBus\<ServableState\>](classtensorflow_1_1serving_1_1EventBus.html){.code}\*
servable\_event\_bus,
:::

::: {.line}
[]{#l00281}[ 281]{.lineno}  PreLoadHook pre\_load\_hook);
:::

::: {.line}
[]{#l00282}[ 282]{.lineno} 
:::

::: {.line}
[]{#l00283}[ 283]{.lineno}  [// Starts managing the servable.]{.comment}
:::

::: {.line}
[]{#l00284}[ 284]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00285}[ 285]{.lineno}  [// If called multiple times with the same
servable id, all of them are]{.comment}
:::

::: {.line}
[]{#l00286}[ 286]{.lineno}  [// accepted, but only the first one is
used. We accept the servable even if]{.comment}
:::

::: {.line}
[]{#l00287}[ 287]{.lineno}  [// called with erroneous
ServableData.]{.comment}
:::

::: {.line}
[]{#l00288}[ 288]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00289}[ 289]{.lineno}  [// Also accepts a closure to create the
harness as a shared\_ptr. The harness]{.comment}
:::

::: {.line}
[]{#l00290}[ 290]{.lineno}  [// has a different constructors for
creating it with or without]{.comment}
:::

::: {.line}
[]{#l00291}[ 291]{.lineno}  [// additional\_state.]{.comment}
:::

::: {.line}
[]{#l00292}[ 292]{.lineno}  Status
ManageServableInternal([ServableData](classtensorflow_1_1serving_1_1ServableData.html){.code}\<std::unique\_ptr\<Loader\>\>
servable,
:::

::: {.line}
[]{#l00293}[ 293]{.lineno} 
std::function\<std::shared\_ptr\<LoaderHarness\>(
:::

::: {.line}
[]{#l00294}[ 294]{.lineno}  [const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&,
std::unique\_ptr\<Loader\>)\>
:::

::: {.line}
[]{#l00295}[ 295]{.lineno}  harness\_creator);
:::

::: {.line}
[]{#l00296}[ 296]{.lineno} 
:::

::: {.line}
[]{#l00297}[ 297]{.lineno}  [// Obtains the harness associated with the
given servable id. Returns an ok]{.comment}
:::

::: {.line}
[]{#l00298}[ 298]{.lineno}  [// status if a corresponding harness was
found, else an error status.]{.comment}
:::

::: {.line}
[]{#l00299}[ 299]{.lineno}  Status GetHealthyHarness([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
servable\_id,
:::

::: {.line}
[]{#l00300}[ 300]{.lineno} 
[LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html){.code}\*\*
harness)
:::

::: {.line}
[]{#l00301}[ 301]{.lineno}  TF\_EXCLUSIVE\_LOCKS\_REQUIRED(mu\_);
:::

::: {.line}
[]{#l00302}[ 302]{.lineno} 
:::

::: {.line}
[]{#l00303}[ 303]{.lineno}  [// Obtains a pointer to every managed
loader that is currently holding]{.comment}
:::

::: {.line}
[]{#l00304}[ 304]{.lineno}  [// resources, i.e. whose state is one of
kApprovedForLoading, kLoading,]{.comment}
:::

::: {.line}
[]{#l00305}[ 305]{.lineno}  [// kReady, kUnloadRequested, kQuiescing,
kQuiesced or kUnloading.]{.comment}
:::

::: {.line}
[]{#l00306}[ 306]{.lineno}  std::vector\<const Loader\*\>
GetLoadersCurrentlyUsingResources() const
:::

::: {.line}
[]{#l00307}[ 307]{.lineno}  TF\_EXCLUSIVE\_LOCKS\_REQUIRED(mu\_);
:::

::: {.line}
[]{#l00308}[ 308]{.lineno} 
:::

::: {.line}
[]{#l00309}[ 309]{.lineno}  [// A load or unload request for a
particular servable. Facilitates code]{.comment}
:::

::: {.line}
[]{#l00310}[ 310]{.lineno}  [// sharing across the two cases.]{.comment}
:::

::: {.line}
[]{#l00311}[ 311]{.lineno}  struct LoadOrUnloadRequest {
:::

::: {.line}
[]{#l00312}[ 312]{.lineno}  [enum class]{.keyword} Kind { kLoad, kUnload
};
:::

::: {.line}
[]{#l00313}[ 313]{.lineno}  Kind kind;
:::

::: {.line}
[]{#l00314}[ 314]{.lineno} 
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}
servable\_id;
:::

::: {.line}
[]{#l00315}[ 315]{.lineno}  };
:::

::: {.line}
[]{#l00316}[ 316]{.lineno} 
:::

::: {.line}
[]{#l00317}[ 317]{.lineno}  [// A unification of LoadServable() and
UnloadServable().]{.comment}
:::

::: {.line}
[]{#l00318}[ 318]{.lineno}  [void]{.keywordtype}
LoadOrUnloadServable([const]{.keyword} LoadOrUnloadRequest& request,
:::

::: {.line}
[]{#l00319}[ 319]{.lineno} 
[DoneCallback](classtensorflow_1_1serving_1_1BasicManager.html#a8ee7a19d059b362c0702686d981bf5fc){.code}
done\_callback) TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00320}[ 320]{.lineno} 
:::

::: {.line}
[]{#l00321}[ 321]{.lineno}  [// The synchronous logic for handling a
load/unload request, including both]{.comment}
:::

::: {.line}
[]{#l00322}[ 322]{.lineno}  [// the decision and execution phases. This
is the method run in the executor.]{.comment}
:::

::: {.line}
[]{#l00323}[ 323]{.lineno}  [void]{.keywordtype}
HandleLoadOrUnloadRequest([const]{.keyword} LoadOrUnloadRequest&
request,
:::

::: {.line}
[]{#l00324}[ 324]{.lineno} 
[DoneCallback](classtensorflow_1_1serving_1_1BasicManager.html#a8ee7a19d059b362c0702686d981bf5fc){.code}
done\_callback)
:::

::: {.line}
[]{#l00325}[ 325]{.lineno}  TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00326}[ 326]{.lineno} 
:::

::: {.line}
[]{#l00327}[ 327]{.lineno}  [// The decision phase of whether to approve
a load/unload request. Delegates]{.comment}
:::

::: {.line}
[]{#l00328}[ 328]{.lineno}  [// to one of ApproveLoad() or
ApproveUnload() \-- see those methods\' comments]{.comment}
:::

::: {.line}
[]{#l00329}[ 329]{.lineno}  [// for details.]{.comment}
:::

::: {.line}
[]{#l00330}[ 330]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00331}[ 331]{.lineno}  [// Upon approving the request, signals
entrance to the execution phase by]{.comment}
:::

::: {.line}
[]{#l00332}[ 332]{.lineno}  [// incrementing
\'num\_ongoing\_load\_unload\_executions\_\'.]{.comment}
:::

::: {.line}
[]{#l00333}[ 333]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00334}[ 334]{.lineno}  [// If returning \"ok\", populates
\'harness\' with the harness for the request\'s]{.comment}
:::

::: {.line}
[]{#l00335}[ 335]{.lineno}  [// servable. (Note that \'harness\' is
guaranteed to remain live for the]{.comment}
:::

::: {.line}
[]{#l00336}[ 336]{.lineno}  [// subsequent execution phase of the
request because approval of this request]{.comment}
:::

::: {.line}
[]{#l00337}[ 337]{.lineno}  [// precludes concurrent execution of
another request that could delete the]{.comment}
:::

::: {.line}
[]{#l00338}[ 338]{.lineno}  [// harness.)]{.comment}
:::

::: {.line}
[]{#l00339}[ 339]{.lineno}  Status ApproveLoadOrUnload([const]{.keyword}
LoadOrUnloadRequest& request,
:::

::: {.line}
[]{#l00340}[ 340]{.lineno}  LoaderHarness\*\* harness)
TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00341}[ 341]{.lineno} 
:::

::: {.line}
[]{#l00342}[ 342]{.lineno}  [// The decision phase of whether to approve
a load request.]{.comment}
:::

::: {.line}
[]{#l00343}[ 343]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00344}[ 344]{.lineno}  [// If it succeeds, places the servable into
state kApprovedForLoad. Among]{.comment}
:::

::: {.line}
[]{#l00345}[ 345]{.lineno}  [// other things, that prevents a subsequent
load request from proceeding]{.comment}
:::

::: {.line}
[]{#l00346}[ 346]{.lineno}  [// concurrently.]{.comment}
:::

::: {.line}
[]{#l00347}[ 347]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00348}[ 348]{.lineno}  [// Argument \'mu\_lock\' is a lock held on
\'mu\_\'. It is released temporarily via]{.comment}
:::

::: {.line}
[]{#l00349}[ 349]{.lineno}  [//
\'num\_ongoing\_load\_unload\_executions\_cv\_\'.]{.comment}
:::

::: {.line}
[]{#l00350}[ 350]{.lineno}  Status ApproveLoad(LoaderHarness\* harness,
mutex\_lock\* mu\_lock)
:::

::: {.line}
[]{#l00351}[ 351]{.lineno}  TF\_EXCLUSIVE\_LOCKS\_REQUIRED(mu\_);
:::

::: {.line}
[]{#l00352}[ 352]{.lineno} 
:::

::: {.line}
[]{#l00353}[ 353]{.lineno}  [// The decision phase of whether to approve
an unload request. If it succeeds,]{.comment}
:::

::: {.line}
[]{#l00354}[ 354]{.lineno}  [// places the servable into state
kQuiescing. Among other things, that]{.comment}
:::

::: {.line}
[]{#l00355}[ 355]{.lineno}  [// prevents a subsequent unload request
from proceeding concurrently.]{.comment}
:::

::: {.line}
[]{#l00356}[ 356]{.lineno}  Status ApproveUnload(LoaderHarness\*
harness) TF\_EXCLUSIVE\_LOCKS\_REQUIRED(mu\_);
:::

::: {.line}
[]{#l00357}[ 357]{.lineno} 
:::

::: {.line}
[]{#l00358}[ 358]{.lineno}  [// Attempts to reserve the resources
required to load the servable in]{.comment}
:::

::: {.line}
[]{#l00359}[ 359]{.lineno}  [// \'harness\'. Does not make any state
transitions on \'harness\' \-- merely]{.comment}
:::

::: {.line}
[]{#l00360}[ 360]{.lineno}  [// reserves the resources in
\'resource\_tracker\_\' (upon success) or returns an]{.comment}
:::

::: {.line}
[]{#l00361}[ 361]{.lineno}  [// error.]{.comment}
:::

::: {.line}
[]{#l00362}[ 362]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00363}[ 363]{.lineno}  [// Argument \'mu\_lock\' is a lock held on
\'mu\_\'. It is released temporarily via]{.comment}
:::

::: {.line}
[]{#l00364}[ 364]{.lineno}  [//
\'num\_ongoing\_load\_unload\_executions\_cv\_\'.]{.comment}
:::

::: {.line}
[]{#l00365}[ 365]{.lineno}  Status ReserveResources(LoaderHarness\*
harness, mutex\_lock\* mu\_lock)
:::

::: {.line}
[]{#l00366}[ 366]{.lineno}  TF\_EXCLUSIVE\_LOCKS\_REQUIRED(mu\_);
:::

::: {.line}
[]{#l00367}[ 367]{.lineno} 
:::

::: {.line}
[]{#l00368}[ 368]{.lineno}  [// The execution phase of loading/unloading
a servable. Delegates to either]{.comment}
:::

::: {.line}
[]{#l00369}[ 369]{.lineno}  [// ExecuteLoad() or
ExecuteUnload().]{.comment}
:::

::: {.line}
[]{#l00370}[ 370]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00371}[ 371]{.lineno}  [// Upon completion (and regardless of the
outcome), signals exit of the]{.comment}
:::

::: {.line}
[]{#l00372}[ 372]{.lineno}  [// execution phase by decrementing
\'num\_ongoing\_load\_unload\_executions\_\'.]{.comment}
:::

::: {.line}
[]{#l00373}[ 373]{.lineno}  Status ExecuteLoadOrUnload([const]{.keyword}
LoadOrUnloadRequest& request,
:::

::: {.line}
[]{#l00374}[ 374]{.lineno}  LoaderHarness\* harness);
:::

::: {.line}
[]{#l00375}[ 375]{.lineno} 
:::

::: {.line}
[]{#l00376}[ 376]{.lineno}  [// The execution phase of loading a
servable.]{.comment}
:::

::: {.line}
[]{#l00377}[ 377]{.lineno}  Status ExecuteLoad(LoaderHarness\* harness)
TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00378}[ 378]{.lineno} 
:::

::: {.line}
[]{#l00379}[ 379]{.lineno}  [// The execution phase of loading a
unservable.]{.comment}
:::

::: {.line}
[]{#l00380}[ 380]{.lineno}  Status ExecuteUnload(LoaderHarness\*
harness) TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00381}[ 381]{.lineno} 
:::

::: {.line}
[]{#l00382}[ 382]{.lineno}  [// Unloads all the managed
servables.]{.comment}
:::

::: {.line}
[]{#l00383}[ 383]{.lineno}  Status UnloadAllServables()
TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00384}[ 384]{.lineno} 
:::

::: {.line}
[]{#l00385}[ 385]{.lineno}  [// Updates the serving map by copying
servables from the managed map, which]{.comment}
:::

::: {.line}
[]{#l00386}[ 386]{.lineno}  [// are ready to be served.]{.comment}
:::

::: {.line}
[]{#l00387}[ 387]{.lineno}  [void]{.keywordtype} UpdateServingMap()
TF\_EXCLUSIVE\_LOCKS\_REQUIRED(mu\_);
:::

::: {.line}
[]{#l00388}[ 388]{.lineno} 
:::

::: {.line}
[]{#l00389}[ 389]{.lineno}  [// Sets the number of load
threads.]{.comment}
:::

::: {.line}
[]{#l00390}[ 390]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00391}[ 391]{.lineno}  [// When either existing or target
num\_load\_threads means single thread, we]{.comment}
:::

::: {.line}
[]{#l00392}[ 392]{.lineno}  [// block all new load requests while the
old thread pool is destructed, a new]{.comment}
:::

::: {.line}
[]{#l00393}[ 393]{.lineno}  [// one is created and then swapped with the
old one. Note that destructing]{.comment}
:::

::: {.line}
[]{#l00394}[ 394]{.lineno}  [// the old thread pool blocks until all
threads are done, so it could block]{.comment}
:::

::: {.line}
[]{#l00395}[ 395]{.lineno}  [// for a long time.]{.comment}
:::

::: {.line}
[]{#l00396}[ 396]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00397}[ 397]{.lineno}  [// When both existing and target
num\_load\_threads are multi-threaded, this]{.comment}
:::

::: {.line}
[]{#l00398}[ 398]{.lineno}  [// call still blocks until the old thread
pool is destructed, but other loads]{.comment}
:::

::: {.line}
[]{#l00399}[ 399]{.lineno}  [// can happen concurrently, potentially
increasing the number of running load]{.comment}
:::

::: {.line}
[]{#l00400}[ 400]{.lineno}  [// threads, up to the sum of existing and
target num\_load\_threads.]{.comment}
:::

::: {.line}
[]{#l00401}[ 401]{.lineno}  [void]{.keywordtype}
SetNumLoadThreads(uint32 num\_load\_threads)
:::

::: {.line}
[]{#l00402}[ 402]{.lineno}  TF\_LOCKS\_EXCLUDED(load\_executor\_mu\_);
:::

::: {.line}
[]{#l00403}[ 403]{.lineno}  uint32 num\_load\_threads() const;
:::

::: {.line}
[]{#l00404}[ 404]{.lineno} 
:::

::: {.line}
[]{#l00405}[ 405]{.lineno}  [// Keys are the servable names.]{.comment}
:::

::: {.line}
[]{#l00406}[ 406]{.lineno}  [// Values are the harnesses for each
servable version. The values when]{.comment}
:::

::: {.line}
[]{#l00407}[ 407]{.lineno}  [// fetched, are unordered.]{.comment}
:::

::: {.line}
[]{#l00408}[ 408]{.lineno}  using ManagedMap =
:::

::: {.line}
[]{#l00409}[ 409]{.lineno} 
std::unordered\_multimap\<[string]{.keywordtype},
std::shared\_ptr\<LoaderHarness\>\>;
:::

::: {.line}
[]{#l00410}[ 410]{.lineno} 
:::

::: {.line}
[]{#l00411}[ 411]{.lineno}  [// Fetches the harness with this id from
the harness\_map\_. Returns]{.comment}
:::

::: {.line}
[]{#l00412}[ 412]{.lineno}  [// harness\_map\_.end(), if the harness is
not found.]{.comment}
:::

::: {.line}
[]{#l00413}[ 413]{.lineno}  ManagedMap::iterator FindHarnessInMap(const
ServableId& [id]{.keywordtype})
:::

::: {.line}
[]{#l00414}[ 414]{.lineno}  TF\_EXCLUSIVE\_LOCKS\_REQUIRED(mu\_);
:::

::: {.line}
[]{#l00415}[ 415]{.lineno} 
:::

::: {.line}
[]{#l00416}[ 416]{.lineno}  [// Publishes the state on the event bus, if
an event bus was part of the]{.comment}
:::

::: {.line}
[]{#l00417}[ 417]{.lineno}  [// options, if not we ignore it.]{.comment}
:::

::: {.line}
[]{#l00418}[ 418]{.lineno}  [void]{.keywordtype} PublishOnEventBus(const
ServableState& state);
:::

::: {.line}
[]{#l00419}[ 419]{.lineno} 
:::

::: {.line}
[]{#l00420}[ 420]{.lineno}  LoaderHarness::Options harness\_options\_;
:::

::: {.line}
[]{#l00421}[ 421]{.lineno} 
:::

::: {.line}
[]{#l00422}[ 422]{.lineno}  [// The event bus to which to publish
servable state change events, or nullptr]{.comment}
:::

::: {.line}
[]{#l00423}[ 423]{.lineno}  [// if no bus has been
configured.]{.comment}
:::

::: {.line}
[]{#l00424}[ 424]{.lineno}  EventBus\<ServableState\>\*
servable\_event\_bus\_;
:::

::: {.line}
[]{#l00425}[ 425]{.lineno} 
:::

::: {.line}
[]{#l00426}[ 426]{.lineno}  [// Defines how we want to retry when model
loading fails.]{.comment}
:::

::: {.line}
[]{#l00427}[ 427]{.lineno} 
std::function\<[bool]{.keywordtype}(absl::Status)\>
should\_retry\_model\_load\_;
:::

::: {.line}
[]{#l00428}[ 428]{.lineno} 
:::

::: {.line}
[]{#l00429}[ 429]{.lineno}  [// Used to protect access to
\'managed\_map\_\', \'resource\_tracker\_\' and other]{.comment}
:::

::: {.line}
[]{#l00430}[ 430]{.lineno}  [// core state elements.]{.comment}
:::

::: {.line}
[]{#l00431}[ 431]{.lineno}  mutable mutex mu\_;
:::

::: {.line}
[]{#l00432}[ 432]{.lineno} 
:::

::: {.line}
[]{#l00433}[ 433]{.lineno}  [// ManagedMap contains all the servables
managed by this manager, in different]{.comment}
:::

::: {.line}
[]{#l00434}[ 434]{.lineno}  [// states.]{.comment}
:::

::: {.line}
[]{#l00435}[ 435]{.lineno}  ManagedMap managed\_map\_
TF\_GUARDED\_BY(mu\_);
:::

::: {.line}
[]{#l00436}[ 436]{.lineno} 
:::

::: {.line}
[]{#l00437}[ 437]{.lineno}  [// ServingMap contains all the servables
which are ready to be served, which]{.comment}
:::

::: {.line}
[]{#l00438}[ 438]{.lineno}  [// is a subset of those in the managed
map.]{.comment}
:::

::: {.line}
[]{#l00439}[ 439]{.lineno}  [// This map is updated occasionally from
the main manager loop thread while]{.comment}
:::

::: {.line}
[]{#l00440}[ 440]{.lineno}  [// being accessed from multiple threads to
get ServableHandles.]{.comment}
:::

::: {.line}
[]{#l00441}[ 441]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00442}[ 442]{.lineno}  [// This class is thread-safe.]{.comment}
:::

::: {.line}
[]{#l00443}[ 443]{.lineno}  class ServingMap {
:::

::: {.line}
[]{#l00444}[ 444]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00445}[ 445]{.lineno}  ServingMap();
:::

::: {.line}
[]{#l00446}[ 446]{.lineno} 
:::

::: {.line}
[]{#l00447}[ 447]{.lineno}  [// Gets a list of all servable
ids.]{.comment}
:::

::: {.line}
[]{#l00448}[ 448]{.lineno}  std::vector\<ServableId\>
[ListAvailableServableIds](classtensorflow_1_1serving_1_1BasicManager.html#a3c004d32952596c1f5759b1cfcc3c639){.code}()
[const]{.keyword};
:::

::: {.line}
[]{#l00449}[ 449]{.lineno} 
:::

::: {.line}
[]{#l00450}[ 450]{.lineno}  [// Returns an UntypedServableHandle given a
ServableRequest.]{.comment}
:::

::: {.line}
[]{#l00451}[ 451]{.lineno}  [// Returns error if no such Servable is
available \-- e.g. not yet loaded,]{.comment}
:::

::: {.line}
[]{#l00452}[ 452]{.lineno}  [// has been quiesced/unloaded,
etc.]{.comment}
:::

::: {.line}
[]{#l00453}[ 453]{.lineno}  Status GetUntypedServableHandle(
:::

::: {.line}
[]{#l00454}[ 454]{.lineno}  [const]{.keyword} ServableRequest& request,
:::

::: {.line}
[]{#l00455}[ 455]{.lineno}  std::unique\_ptr\<UntypedServableHandle\>\*
untyped\_handle);
:::

::: {.line}
[]{#l00456}[ 456]{.lineno} 
:::

::: {.line}
[]{#l00457}[ 457]{.lineno}  [// Returns a map of all the currently
available servable\_ids to their]{.comment}
:::

::: {.line}
[]{#l00458}[ 458]{.lineno}  [// corresponding
UntypedServableHandles.]{.comment}
:::

::: {.line}
[]{#l00459}[ 459]{.lineno}  std::map\<ServableId,
std::unique\_ptr\<UntypedServableHandle\>\>
:::

::: {.line}
[]{#l00460}[ 460]{.lineno}  GetAvailableUntypedServableHandles()
[const]{.keyword};
:::

::: {.line}
[]{#l00461}[ 461]{.lineno} 
:::

::: {.line}
[]{#l00462}[ 462]{.lineno}  [// Updates the serving map by copying
servables from the managed map, which]{.comment}
:::

::: {.line}
[]{#l00463}[ 463]{.lineno}  [// are ready to be served.]{.comment}
:::

::: {.line}
[]{#l00464}[ 464]{.lineno}  [void]{.keywordtype}
Update([const]{.keyword} ManagedMap& managed\_map);
:::

::: {.line}
[]{#l00465}[ 465]{.lineno} 
:::

::: {.line}
[]{#l00466}[ 466]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00467}[ 467]{.lineno}  [struct ]{.keyword}EqRequest;
:::

::: {.line}
[]{#l00468}[ 468]{.lineno}  [// Hash and equality functors for
ServableRequest.]{.comment}
:::

::: {.line}
[]{#l00469}[ 469]{.lineno}  [// Forward-declared here and defined in the
cc file.]{.comment}
:::

::: {.line}
[]{#l00470}[ 470]{.lineno}  [struct ]{.keyword}HashRequest;
:::

::: {.line}
[]{#l00471}[ 471]{.lineno} 
:::

::: {.line}
[]{#l00472}[ 472]{.lineno}  [// Map from ServableRequest to
corresponding harness. For the latest version]{.comment}
:::

::: {.line}
[]{#l00473}[ 473]{.lineno}  [// of a servable stream, we add an extra
entry for it, where key is the]{.comment}
:::

::: {.line}
[]{#l00474}[ 474]{.lineno}  [// ServableRequest without the version set,
so that requests for the latest,]{.comment}
:::

::: {.line}
[]{#l00475}[ 475]{.lineno}  [// can be directly queried on this
map.]{.comment}
:::

::: {.line}
[]{#l00476}[ 476]{.lineno}  [using]{.keyword} HandlesMap =
:::

::: {.line}
[]{#l00477}[ 477]{.lineno}  std::unordered\_multimap\<ServableRequest,
:::

::: {.line}
[]{#l00478}[ 478]{.lineno}  std::shared\_ptr\<const LoaderHarness\>,
:::

::: {.line}
[]{#l00479}[ 479]{.lineno}  HashRequest, EqRequest\>;
:::

::: {.line}
[]{#l00480}[ 480]{.lineno}  FastReadDynamicPtr\<HandlesMap\>
handles\_map\_;
:::

::: {.line}
[]{#l00481}[ 481]{.lineno}  };
:::

::: {.line}
[]{#l00482}[ 482]{.lineno}  ServingMap serving\_map\_;
:::

::: {.line}
[]{#l00483}[ 483]{.lineno} 
:::

::: {.line}
[]{#l00485}[ 485]{.lineno}  [// State associated with loading/unloading
servables, and tracking their]{.comment}
:::

::: {.line}
[]{#l00486}[ 486]{.lineno}  [// resources.]{.comment}
:::

::: {.line}
[]{#l00487}[ 487]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00488}[ 488]{.lineno}  [// Load/unload requests have two phases: a
decision phase and an execution]{.comment}
:::

::: {.line}
[]{#l00489}[ 489]{.lineno}  [// phase. The decision phase either accepts
or rejects the request; if]{.comment}
:::

::: {.line}
[]{#l00490}[ 490]{.lineno}  [// accepted the execution phase executes
the request (i.e. invokes Load() or]{.comment}
:::

::: {.line}
[]{#l00491}[ 491]{.lineno}  [// Unload() on the servable\'s
loader).]{.comment}
:::

::: {.line}
[]{#l00492}[ 492]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00493}[ 493]{.lineno}  [// Given a stream of load/unload requests,
we execute the decision phases]{.comment}
:::

::: {.line}
[]{#l00494}[ 494]{.lineno}  [// serially, which guarantees that request
i's decision phase can complete]{.comment}
:::

::: {.line}
[]{#l00495}[ 495]{.lineno}  [// before considering request i+1\'s so
there's no starvation.]{.comment}
:::

::: {.line}
[]{#l00496}[ 496]{.lineno} 
:::

::: {.line}
[]{#l00497}[ 497]{.lineno}  Env\* [const]{.keyword} env\_;
:::

::: {.line}
[]{#l00498}[ 498]{.lineno} 
:::

::: {.line}
[]{#l00499}[ 499]{.lineno}  [// The number of load threads. Can be
changed after instantiation of the]{.comment}
:::

::: {.line}
[]{#l00500}[ 500]{.lineno}  [// manager via
SetNumLoadThreads().]{.comment}
:::

::: {.line}
[]{#l00501}[ 501]{.lineno}  std::atomic\<uint32\> num\_load\_threads\_;
:::

::: {.line}
[]{#l00502}[ 502]{.lineno}  [// Whether to flush filesystem caches (if
num\_load\_threads\_ == 1)]{.comment}
:::

::: {.line}
[]{#l00503}[ 503]{.lineno}  [const]{.keyword} [bool]{.keywordtype}
flush\_filesystem\_caches\_ = [false]{.keyword};
:::

::: {.line}
[]{#l00504}[ 504]{.lineno}  [// The executor (and associated mutex) used
for executing loads of servables.]{.comment}
:::

::: {.line}
[]{#l00505}[ 505]{.lineno}  [mutable]{.keyword} mutex
load\_executor\_mu\_;
:::

::: {.line}
[]{#l00506}[ 506]{.lineno}  std::unique\_ptr\<Executor\>
load\_executor\_ TF\_GUARDED\_BY(load\_executor\_mu\_);
:::

::: {.line}
[]{#l00507}[ 507]{.lineno} 
:::

::: {.line}
[]{#l00508}[ 508]{.lineno}  [// The executor used for executing unloads
of servables. (Unlike for loads,]{.comment}
:::

::: {.line}
[]{#l00509}[ 509]{.lineno}  [// the unload executor is fixed for the
lifetime of the manager.)]{.comment}
:::

::: {.line}
[]{#l00510}[ 510]{.lineno}  std::unique\_ptr\<Executor\>
unload\_executor\_;
:::

::: {.line}
[]{#l00511}[ 511]{.lineno} 
:::

::: {.line}
[]{#l00512}[ 512]{.lineno}  [// Used to serialize the decision phases of
the load/unload requests.]{.comment}
:::

::: {.line}
[]{#l00513}[ 513]{.lineno}  [mutable]{.keyword} mutex
load\_unload\_decision\_phase\_mu\_;
:::

::: {.line}
[]{#l00514}[ 514]{.lineno} 
:::

::: {.line}
[]{#l00515}[ 515]{.lineno}  [// A module that keeps track of available,
used and reserved servable]{.comment}
:::

::: {.line}
[]{#l00516}[ 516]{.lineno}  [// resources (e.g. RAM).]{.comment}
:::

::: {.line}
[]{#l00517}[ 517]{.lineno}  std::unique\_ptr\<ResourceTracker\>
resource\_tracker\_ TF\_GUARDED\_BY(mu\_);
:::

::: {.line}
[]{#l00518}[ 518]{.lineno} 
:::

::: {.line}
[]{#l00519}[ 519]{.lineno}  [// The number of load/unload requests
currently in their execution phase.]{.comment}
:::

::: {.line}
[]{#l00520}[ 520]{.lineno}  [int]{.keywordtype}
num\_ongoing\_load\_unload\_executions\_ TF\_GUARDED\_BY(mu\_) = 0;
:::

::: {.line}
[]{#l00521}[ 521]{.lineno} 
:::

::: {.line}
[]{#l00522}[ 522]{.lineno}  [// Used to wake up threads that are waiting
for \'num\_ongoing\_executions\' to]{.comment}
:::

::: {.line}
[]{#l00523}[ 523]{.lineno}  [// decrease.]{.comment}
:::

::: {.line}
[]{#l00524}[ 524]{.lineno}  condition\_variable
num\_ongoing\_load\_unload\_executions\_cv\_;
:::

::: {.line}
[]{#l00525}[ 525]{.lineno} 
:::

::: {.line}
[]{#l00526}[ 526]{.lineno}  PreLoadHook pre\_load\_hook\_;
:::

::: {.line}
[]{#l00527}[ 527]{.lineno} 
:::

::: {.line}
[]{#l00528}[ 528]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN(BasicManager);
:::

::: {.line}
[]{#l00529}[ 529]{.lineno} };
:::

::: {.line}
[]{#l00530}[ 530]{.lineno} 
:::

::: {.line}
[]{#l00532}[ 532]{.lineno} [// Implementation details. API readers may
skip.]{.comment}
:::

::: {.line}
[]{#l00534}[ 534]{.lineno} []{.comment}
:::

::: {.line}
[]{#l00535}[ 535]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00536}[
[536](classtensorflow_1_1serving_1_1BasicManager.html#a72406e3aedfa0084e24f2bd8ec7efdcc){.line}]{.lineno} Status
[BasicManager::ManageServableWithAdditionalState](classtensorflow_1_1serving_1_1BasicManager.html#a72406e3aedfa0084e24f2bd8ec7efdcc){.code}(
:::

::: {.line}
[]{#l00537}[ 537]{.lineno} 
[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.code}\<std::unique\_ptr\<Loader\>\>
servable,
:::

::: {.line}
[]{#l00538}[ 538]{.lineno}  std::unique\_ptr\<T\> additional\_state) {
:::

::: {.line}
[]{#l00539}[ 539]{.lineno}  [return]{.keywordflow}
ManageServableInternal(
:::

::: {.line}
[]{#l00540}[ 540]{.lineno}  std::move(servable),
:::

::: {.line}
[]{#l00541}[ 541]{.lineno}  \[[this]{.keyword},
&additional\_state\]([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
[id]{.keywordtype},
:::

::: {.line}
[]{#l00542}[ 542]{.lineno}  std::unique\_ptr\<Loader\> loader) {
:::

::: {.line}
[]{#l00543}[ 543]{.lineno}  [return]{.keywordflow}
std::make\_shared\<LoaderHarness\>([id]{.keywordtype},
std::move(loader),
:::

::: {.line}
[]{#l00544}[ 544]{.lineno}  std::move(additional\_state),
:::

::: {.line}
[]{#l00545}[ 545]{.lineno}  harness\_options\_);
:::

::: {.line}
[]{#l00546}[ 546]{.lineno}  });
:::

::: {.line}
[]{#l00547}[ 547]{.lineno} }
:::

::: {.line}
[]{#l00548}[ 548]{.lineno} 
:::

::: {.line}
[]{#l00549}[ 549]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00550}[ 550]{.lineno} std::vector\<ServableStateSnapshot\<T\>\>
:::

::: {.line}
[]{#l00551}[
[551](classtensorflow_1_1serving_1_1BasicManager.html#a31716665d8df8451d379363309dac826){.line}]{.lineno} [BasicManager::GetManagedServableStateSnapshots](classtensorflow_1_1serving_1_1BasicManager.html#a31716665d8df8451d379363309dac826){.code}(
:::

::: {.line}
[]{#l00552}[ 552]{.lineno}  [const]{.keyword} [string]{.keywordtype}&
servable\_name)[ const ]{.keyword}{
:::

::: {.line}
[]{#l00553}[ 553]{.lineno}  mutex\_lock l(mu\_);
:::

::: {.line}
[]{#l00554}[ 554]{.lineno} 
:::

::: {.line}
[]{#l00555}[ 555]{.lineno}  [const]{.keyword} [auto]{.keyword} range =
managed\_map\_.equal\_range(servable\_name);
:::

::: {.line}
[]{#l00556}[ 556]{.lineno}  std::vector\<ServableStateSnapshot\<T\>\>
state\_snapshots;
:::

::: {.line}
[]{#l00557}[ 557]{.lineno} 
state\_snapshots.reserve(std::distance(range.first, range.second));
:::

::: {.line}
[]{#l00558}[ 558]{.lineno}  [for]{.keywordflow} ([auto]{.keyword} it =
range.first; it != range.second; ++it) {
:::

::: {.line}
[]{#l00559}[ 559]{.lineno} 
state\_snapshots.push\_back(it-\>second-\>loader\_state\_snapshot\<T\>());
:::

::: {.line}
[]{#l00560}[ 560]{.lineno}  }
:::

::: {.line}
[]{#l00561}[ 561]{.lineno} 
:::

::: {.line}
[]{#l00562}[ 562]{.lineno}  [return]{.keywordflow} state\_snapshots;
:::

::: {.line}
[]{#l00563}[ 563]{.lineno} }
:::

::: {.line}
[]{#l00564}[ 564]{.lineno} 
:::

::: {.line}
[]{#l00565}[ 565]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00566}[ 566]{.lineno} absl::optional\<ServableStateSnapshot\<T\>\>
:::

::: {.line}
[]{#l00567}[
[567](classtensorflow_1_1serving_1_1BasicManager.html#af681f56bbef07ab201f25c0097f73e75){.line}]{.lineno} [BasicManager::GetManagedServableStateSnapshot](classtensorflow_1_1serving_1_1BasicManager.html#af681f56bbef07ab201f25c0097f73e75){.code}([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
[id]{.keywordtype}) {
:::

::: {.line}
[]{#l00568}[ 568]{.lineno}  mutex\_lock l(mu\_);
:::

::: {.line}
[]{#l00569}[ 569]{.lineno} 
:::

::: {.line}
[]{#l00570}[ 570]{.lineno}  [auto]{.keyword} iter =
FindHarnessInMap([id]{.keywordtype});
:::

::: {.line}
[]{#l00571}[ 571]{.lineno}  [if]{.keywordflow} (iter ==
managed\_map\_.end()) {
:::

::: {.line}
[]{#l00572}[ 572]{.lineno}  [return]{.keywordflow} absl::nullopt;
:::

::: {.line}
[]{#l00573}[ 573]{.lineno}  }
:::

::: {.line}
[]{#l00574}[ 574]{.lineno}  [return]{.keywordflow}
iter-\>second-\>loader\_state\_snapshot\<T\>();
:::

::: {.line}
[]{#l00575}[ 575]{.lineno} }
:::

::: {.line}
[]{#l00576}[ 576]{.lineno} 
:::

::: {.line}
[]{#l00577}[ 577]{.lineno} [template]{.keyword} \<[typename]{.keyword}
T\>
:::

::: {.line}
[]{#l00578}[
[578](classtensorflow_1_1serving_1_1BasicManager.html#a99dbea960f6d47461dbfca5bfa149335){.line}]{.lineno} T\*
[BasicManager::GetAdditionalServableState](classtensorflow_1_1serving_1_1BasicManager.html#a99dbea960f6d47461dbfca5bfa149335){.code}([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
[id]{.keywordtype}) {
:::

::: {.line}
[]{#l00579}[ 579]{.lineno}  mutex\_lock l(mu\_);
:::

::: {.line}
[]{#l00580}[ 580]{.lineno} 
:::

::: {.line}
[]{#l00581}[ 581]{.lineno}  [auto]{.keyword} iter =
FindHarnessInMap([id]{.keywordtype});
:::

::: {.line}
[]{#l00582}[ 582]{.lineno}  [if]{.keywordflow} (iter ==
managed\_map\_.end()) {
:::

::: {.line}
[]{#l00583}[ 583]{.lineno}  DCHECK([false]{.keyword}) \<\< [\"This
servable is not being managed by the mananger: \"]{.stringliteral}
:::

::: {.line}
[]{#l00584}[ 584]{.lineno}  \<\< [id]{.keywordtype}.DebugString();
:::

::: {.line}
[]{#l00585}[ 585]{.lineno}  [return]{.keywordflow} [nullptr]{.keyword};
:::

::: {.line}
[]{#l00586}[ 586]{.lineno}  }
:::

::: {.line}
[]{#l00587}[ 587]{.lineno}  [return]{.keywordflow}
iter-\>second-\>additional\_state\<T\>();
:::

::: {.line}
[]{#l00588}[ 588]{.lineno} }
:::

::: {.line}
[]{#l00589}[ 589]{.lineno} 
:::

::: {.line}
[]{#l00590}[ 590]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00591}[ 591]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00592}[ 592]{.lineno} 
:::

::: {.line}
[]{#l00593}[ 593]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_BASIC\_MANAGER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1AspiredVersionsManager_html .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html)
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager.h:86
:::
:::

::: {#aclasstensorflow_1_1serving_1_1BasicManager_html .ttc}
::: {.ttname}
[tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html)
:::

::: {.ttdef}
**Definition:** basic\_manager.h:106
:::
:::

::: {#aclasstensorflow_1_1serving_1_1BasicManager_html_a09e87e3b0bc3410a78db3439ff0fb9bb .ttc}
::: {.ttname}
[tensorflow::serving::BasicManager::LoadServable](classtensorflow_1_1serving_1_1BasicManager.html#a09e87e3b0bc3410a78db3439ff0fb9bb)
:::

::: {.ttdeci}
void LoadServable(const ServableId &id, DoneCallback done\_callback)
:::

::: {.ttdef}
**Definition:** basic\_manager.cc:523
:::
:::

::: {#aclasstensorflow_1_1serving_1_1BasicManager_html_a31716665d8df8451d379363309dac826 .ttc}
::: {.ttname}
[tensorflow::serving::BasicManager::GetManagedServableStateSnapshots](classtensorflow_1_1serving_1_1BasicManager.html#a31716665d8df8451d379363309dac826)
:::

::: {.ttdeci}
std::vector\< ServableStateSnapshot\< T \> \>
GetManagedServableStateSnapshots(const string &servable\_name) const
:::

::: {.ttdef}
**Definition:** basic\_manager.h:551
:::
:::

::: {#aclasstensorflow_1_1serving_1_1BasicManager_html_a3209cd82cbb5eac79bc3238b3c6bec43 .ttc}
::: {.ttname}
[tensorflow::serving::BasicManager::StopManagingServable](classtensorflow_1_1serving_1_1BasicManager.html#a3209cd82cbb5eac79bc3238b3c6bec43)
:::

::: {.ttdeci}
Status StopManagingServable(const ServableId &id)
:::

::: {.ttdef}
**Definition:** basic\_manager.cc:390
:::
:::

::: {#aclasstensorflow_1_1serving_1_1BasicManager_html_a3c004d32952596c1f5759b1cfcc3c639 .ttc}
::: {.ttname}
[tensorflow::serving::BasicManager::ListAvailableServableIds](classtensorflow_1_1serving_1_1BasicManager.html#a3c004d32952596c1f5759b1cfcc3c639)
:::

::: {.ttdeci}
std::vector\< ServableId \> ListAvailableServableIds() const override
:::

::: {.ttdef}
**Definition:** basic\_manager.cc:311
:::
:::

::: {#aclasstensorflow_1_1serving_1_1BasicManager_html_a492123b8bb97709184ddb57772e3ccf3 .ttc}
::: {.ttname}
[tensorflow::serving::BasicManager::\~BasicManager](classtensorflow_1_1serving_1_1BasicManager.html#a492123b8bb97709184ddb57772e3ccf3)
:::

::: {.ttdeci}
\~BasicManager() override
:::

::: {.ttdef}
**Definition:** basic\_manager.cc:270
:::
:::

::: {#aclasstensorflow_1_1serving_1_1BasicManager_html_a72406e3aedfa0084e24f2bd8ec7efdcc .ttc}
::: {.ttname}
[tensorflow::serving::BasicManager::ManageServableWithAdditionalState](classtensorflow_1_1serving_1_1BasicManager.html#a72406e3aedfa0084e24f2bd8ec7efdcc)
:::

::: {.ttdeci}
Status ManageServableWithAdditionalState(ServableData\<
std::unique\_ptr\< Loader \>\> servable, std::unique\_ptr\< T \>
additional\_state)
:::

::: {.ttdef}
**Definition:** basic\_manager.h:536
:::
:::

::: {#aclasstensorflow_1_1serving_1_1BasicManager_html_a84dca5ec1ecc28421d5ab020beac2ee3 .ttc}
::: {.ttname}
[tensorflow::serving::BasicManager::CancelLoadServableRetry](classtensorflow_1_1serving_1_1BasicManager.html#a84dca5ec1ecc28421d5ab020beac2ee3)
:::

::: {.ttdeci}
void CancelLoadServableRetry(const ServableId &id)
:::

::: {.ttdef}
**Definition:** basic\_manager.cc:532
:::
:::

::: {#aclasstensorflow_1_1serving_1_1BasicManager_html_a8ee7a19d059b362c0702686d981bf5fc .ttc}
::: {.ttname}
[tensorflow::serving::BasicManager::DoneCallback](classtensorflow_1_1serving_1_1BasicManager.html#a8ee7a19d059b362c0702686d981bf5fc)
:::

::: {.ttdeci}
std::function\< void(const Status &status)\> DoneCallback
:::

::: {.ttdef}
**Definition:** basic\_manager.h:232
:::
:::

::: {#aclasstensorflow_1_1serving_1_1BasicManager_html_a97af7156e38c29225534bacdeefe9408 .ttc}
::: {.ttname}
[tensorflow::serving::BasicManager::UnloadServable](classtensorflow_1_1serving_1_1BasicManager.html#a97af7156e38c29225534bacdeefe9408)
:::

::: {.ttdeci}
void UnloadServable(const ServableId &id, DoneCallback done\_callback)
:::

::: {.ttdef}
**Definition:** basic\_manager.cc:563
:::
:::

::: {#aclasstensorflow_1_1serving_1_1BasicManager_html_a99dbea960f6d47461dbfca5bfa149335 .ttc}
::: {.ttname}
[tensorflow::serving::BasicManager::GetAdditionalServableState](classtensorflow_1_1serving_1_1BasicManager.html#a99dbea960f6d47461dbfca5bfa149335)
:::

::: {.ttdeci}
T \* GetAdditionalServableState(const ServableId &id)
:::

::: {.ttdef}
**Definition:** basic\_manager.h:578
:::
:::

::: {#aclasstensorflow_1_1serving_1_1BasicManager_html_ac2759caea67d3d37b9dba31589f9ef1d .ttc}
::: {.ttname}
[tensorflow::serving::BasicManager::ManageServable](classtensorflow_1_1serving_1_1BasicManager.html#ac2759caea67d3d37b9dba31589f9ef1d)
:::

::: {.ttdeci}
Status ManageServable(ServableData\< std::unique\_ptr\< Loader \>\>
servable)
:::

::: {.ttdef}
**Definition:** basic\_manager.cc:380
:::
:::

::: {#aclasstensorflow_1_1serving_1_1BasicManager_html_af681f56bbef07ab201f25c0097f73e75 .ttc}
::: {.ttname}
[tensorflow::serving::BasicManager::GetManagedServableStateSnapshot](classtensorflow_1_1serving_1_1BasicManager.html#af681f56bbef07ab201f25c0097f73e75)
:::

::: {.ttdeci}
absl::optional\< ServableStateSnapshot\< T \> \>
GetManagedServableStateSnapshot(const ServableId &id)
:::

::: {.ttdef}
**Definition:** basic\_manager.h:567
:::
:::

::: {#aclasstensorflow_1_1serving_1_1BasicManager_html_afbdc3d0ed83559c7d8b3b0092194ead6 .ttc}
::: {.ttname}
[tensorflow::serving::BasicManager::GetManagedServableNames](classtensorflow_1_1serving_1_1BasicManager.html#afbdc3d0ed83559c7d8b3b0092194ead6)
:::

::: {.ttdeci}
std::vector\< string \> GetManagedServableNames() const
:::

::: {.ttdef}
**Definition:** basic\_manager.cc:477
:::
:::

::: {#aclasstensorflow_1_1serving_1_1EventBus_html .ttc}
::: {.ttname}
[tensorflow::serving::EventBus](classtensorflow_1_1serving_1_1EventBus.html)
:::

::: {.ttdef}
**Definition:** event\_bus.h:63
:::
:::

::: {#aclasstensorflow_1_1serving_1_1LoaderHarness_html .ttc}
::: {.ttname}
[tensorflow::serving::LoaderHarness](classtensorflow_1_1serving_1_1LoaderHarness.html)
:::

::: {.ttdef}
**Definition:** loader\_harness.h:49
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

::: {#aclasstensorflow_1_1serving_1_1ServableData_html .ttc}
::: {.ttname}
[tensorflow::serving::ServableData](classtensorflow_1_1serving_1_1ServableData.html)
:::

::: {.ttdef}
**Definition:** servable\_data.h:32
:::
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1BasicManagerTestAccess_html .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::BasicManagerTestAccess](classtensorflow_1_1serving_1_1test__util_1_1BasicManagerTestAccess.html)
:::

::: {.ttdef}
**Definition:** manager\_test\_util.h:55
:::
:::

::: {#astructtensorflow_1_1serving_1_1BasicManager_1_1Options_html .ttc}
::: {.ttname}
[tensorflow::serving::BasicManager::Options](structtensorflow_1_1serving_1_1BasicManager_1_1Options.html)
:::

::: {.ttdef}
**Definition:** basic\_manager.h:113
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

::: {#astructtensorflow_1_1serving_1_1ServableRequest_html .ttc}
::: {.ttname}
[tensorflow::serving::ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html)
:::

::: {.ttdef}
**Definition:** manager.h:39
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

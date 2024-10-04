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
aspired\_versions\_manager.h
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
TENSORFLOW\_SERVING\_CORE\_ASPIRED\_VERSIONS\_MANAGER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_ASPIRED\_VERSIONS\_MANAGER\_H\_]{.preprocessor}
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
[]{#l00021}[ 21]{.lineno} [\#include \<unordered\_map\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} 
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"absl/types/optional.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/kernels/batching\_util/periodic\_function.h\"]{.preprocessor}
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
\"tensorflow\_serving/core/aspired\_version\_policy.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [\#include
\"tensorflow\_serving/core/basic\_manager.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [\#include
\"tensorflow\_serving/core/loader.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [\#include
\"tensorflow\_serving/core/manager.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_data.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_handle.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_id.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_state.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [\#include
\"tensorflow\_serving/core/target.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [\#include
\"tensorflow\_serving/util/event\_bus.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [\#include
\"tensorflow\_serving/util/observer.h\"]{.preprocessor}
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
[]{#l00048}[ 48]{.lineno} [class ]{.keyword}AspiredVersionsManager;
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} 
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [namespace ]{.keyword}internal {
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [class
]{.keyword}AspiredVersionsManagerTargetImpl;
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} 
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} uint32
GetManagerNumLoadThreads(AspiredVersionsManager\* manager);
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} 
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} [// Returns the Notifier function of the
manager\'s Observer, which forwards]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} [// SetNumLoadThreads(). This indirection is
to prevent callers from using]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} [// SetNumLoadThreads() on a deleted
manager.]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} std::function\<void(uint32)\>
SetManagerNumLoadThreadsNotifier(
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  AspiredVersionsManager\* manager);
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} 
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} } [// namespace internal]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} 
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} [namespace ]{.keyword}test\_util {
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} [class
]{.keyword}AspiredVersionsManagerTestAccess;
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} } [// namespace test\_util]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
:::

::: {.line}
[]{#l00085}[
[85](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.line}]{.lineno} [class
]{.keyword}[AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.code}
: [public]{.keyword}
[Manager](classtensorflow_1_1serving_1_1Manager.html){.code},
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  [public]{.keyword}
[Target](classtensorflow_1_1serving_1_1Target.html){.code}\<std::unique\_ptr\<Loader\>\>
{
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  [using]{.keyword} PreLoadHook =
BasicManager::PreLoadHook;
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} 
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  [using]{.keyword} CustomSortActionsFn =
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  std::function\<bool([const]{.keyword}
[AspiredVersionPolicy::ServableAction](structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction.html){.code}&,
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [const]{.keyword}
[AspiredVersionPolicy::ServableAction](structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction.html){.code}&)\>;
:::

::: {.line}
[]{#l00093}[ 93]{.lineno} 
:::

::: {.line}
[]{#l00096}[
[96](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html){.line}]{.lineno} 
[struct
]{.keyword}[Options](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html){.code}
{
:::

::: {.line}
[]{#l00099}[
[99](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a68571485293a22013658ecaff027b0a1){.line}]{.lineno} 
std::unique\_ptr\<ResourceTracker\>
[resource\_tracker](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a68571485293a22013658ecaff027b0a1){.code};
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} 
:::

::: {.line}
[]{#l00104}[
[104](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a60e52c6ea540f1a1bfad9a8987699684){.line}]{.lineno} 
int64\_t
[manage\_state\_interval\_micros](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a60e52c6ea540f1a1bfad9a8987699684){.code}
= 100 \* 1000;
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} 
:::

::: {.line}
[]{#l00108}[
[108](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#ac021adf80573b8c2e0c61688b43f6130){.line}]{.lineno} 
[EventBus\<ServableState\>](classtensorflow_1_1serving_1_1EventBus.html){.code}\*
[servable\_event\_bus](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#ac021adf80573b8c2e0c61688b43f6130){.code}
= [nullptr]{.keyword};
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} 
:::

::: {.line}
[]{#l00111}[
[111](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a921d700e38f7e4f6add9288beb0506e5){.line}]{.lineno} 
std::unique\_ptr\<AspiredVersionPolicy\>
[aspired\_version\_policy](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a921d700e38f7e4f6add9288beb0506e5){.code};
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} 
:::

::: {.line}
[]{#l00117}[
[117](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a68dce64ddf3bec5995ad7161c03efdb9){.line}]{.lineno} 
CustomSortActionsFn
[custom\_sort\_actions](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a68dce64ddf3bec5995ad7161c03efdb9){.code};
:::

::: {.line}
[]{#l00118}[ 118]{.lineno} 
:::

::: {.line}
[]{#l00123}[
[123](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#aae4c93fdb83f2538e44df55f3669d38e){.line}]{.lineno} 
uint32
[num\_load\_threads](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#aae4c93fdb83f2538e44df55f3669d38e){.code}
= 0;
:::

::: {.line}
[]{#l00124}[ 124]{.lineno} 
:::

::: {.line}
[]{#l00129}[
[129](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a6c54dcb0499ef952eca4fdb364aa4859){.line}]{.lineno} 
uint32
[num\_unload\_threads](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a6c54dcb0499ef952eca4fdb364aa4859){.code}
= 0;
:::

::: {.line}
[]{#l00130}[ 130]{.lineno} 
:::

::: {.line}
[]{#l00133}[
[133](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a2d3ca06a39d39b03efd513250ce1cf89){.line}]{.lineno} 
uint32
[max\_num\_load\_retries](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a2d3ca06a39d39b03efd513250ce1cf89){.code}
= 5;
:::

::: {.line}
[]{#l00134}[ 134]{.lineno} 
:::

::: {.line}
[]{#l00138}[
[138](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#ad44f1e8c79d9b60cc87bd616b2f02169){.line}]{.lineno} 
int64\_t
[load\_retry\_interval\_micros](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#ad44f1e8c79d9b60cc87bd616b2f02169){.code}
= 1LL \* 60 \* 1000 \* 1000;
:::

::: {.line}
[]{#l00139}[ 139]{.lineno} 
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  [// Defines how we want to retry when model
loading fails.]{.comment}
:::

::: {.line}
[]{#l00141}[ 141]{.lineno}  std::function\<bool(absl::Status)\>
should\_retry\_model\_load;
:::

::: {.line}
[]{#l00142}[ 142]{.lineno} 
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  [// If true, and there are not multiple load
threads, filesystem caches will]{.comment}
:::

::: {.line}
[]{#l00144}[ 144]{.lineno}  [// be flushed after each servable is
loaded. (Cache flush is skipped when]{.comment}
:::

::: {.line}
[]{#l00145}[ 145]{.lineno}  [// multiple load threads are active, in
order to avoid setting back a]{.comment}
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  [// concurrent load on another
thread.)]{.comment}
:::

::: {.line}
[]{#l00147}[ 147]{.lineno}  [bool]{.keywordtype}
flush\_filesystem\_caches = [false]{.keyword};
:::

::: {.line}
[]{#l00148}[ 148]{.lineno} 
:::

::: {.line}
[]{#l00151}[
[151](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a8f08cac3875a829ae408727f852269e7){.line}]{.lineno} 
Env\*
[env](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a8f08cac3875a829ae408727f852269e7){.code}
= Env::Default();
:::

::: {.line}
[]{#l00152}[ 152]{.lineno} 
:::

::: {.line}
[]{#l00155}[
[155](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#ac16d5d89359873e7004b4a64c2c54a4f){.line}]{.lineno} 
PreLoadHook
[pre\_load\_hook](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#ac16d5d89359873e7004b4a64c2c54a4f){.code};
:::

::: {.line}
[]{#l00156}[ 156]{.lineno} 
:::

::: {.line}
[]{#l00157}[ 157]{.lineno}  [// For servables which end with
LoaderHarness::State::kError, enable]{.comment}
:::

::: {.line}
[]{#l00158}[ 158]{.lineno}  [// future attempts at reload to
progress.]{.comment}
:::

::: {.line}
[]{#l00159}[ 159]{.lineno}  [bool]{.keywordtype}
enable\_reload\_servables\_with\_error = [false]{.keyword};
:::

::: {.line}
[]{#l00160}[ 160]{.lineno} 
:::

::: {.line}
[]{#l00161}[ 161]{.lineno}  [// If true, the AspiredVersionsManager will
propagate its current context to]{.comment}
:::

::: {.line}
[]{#l00162}[ 162]{.lineno}  [// the newly created periodic
functions.]{.comment}
:::

::: {.line}
[]{#l00163}[ 163]{.lineno}  [bool]{.keywordtype} with\_current\_context
= [false]{.keyword};
:::

::: {.line}
[]{#l00164}[ 164]{.lineno}  };
:::

::: {.line}
[]{#l00165}[ 165]{.lineno}  [static]{.keyword} Status
Create([Options](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html){.code}
options,
:::

::: {.line}
[]{#l00166}[ 166]{.lineno}  std::unique\_ptr\<AspiredVersionsManager\>\*
manager);
:::

::: {.line}
[]{#l00167}[ 167]{.lineno} 
\~[AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00168}[ 168]{.lineno} 
:::

::: {.line}
[]{#l00169}[ 169]{.lineno}  std::vector\<ServableId\>
[ListAvailableServableIds](classtensorflow_1_1serving_1_1AspiredVersionsManager.html#a058a76ee71c52d4a6319f14cd9b2ad69){.code}()
[const override]{.keyword};
:::

::: {.line}
[]{#l00170}[ 170]{.lineno} 
:::

::: {.line}
[]{#l00173}[ 173]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00174}[ 174]{.lineno}  [// AspiredVersionsManager\'s semantics with
respect to this callback are as]{.comment}
:::

::: {.line}
[]{#l00175}[ 175]{.lineno}  [// follows:]{.comment}
:::

::: {.line}
[]{#l00176}[ 176]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00177}[ 177]{.lineno}  [// 1. OMITTING A VERSION INSTRUCTS THE
MANAGER TO UNLOAD IT]{.comment}
:::

::: {.line}
[]{#l00178}[ 178]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00179}[ 179]{.lineno}  [// An invocation of the callback for
servable stream S specifies all the]{.comment}
:::

::: {.line}
[]{#l00180}[ 180]{.lineno}  [// versions of S (if any) the manager
should aim to have loaded. Each callback]{.comment}
:::

::: {.line}
[]{#l00181}[ 181]{.lineno}  [// invocation for S supercedes any prior
invocations for S. Versions of S]{.comment}
:::

::: {.line}
[]{#l00182}[ 182]{.lineno}  [// supplied in previous invocations that
are omitted from the latest]{.comment}
:::

::: {.line}
[]{#l00183}[ 183]{.lineno}  [// invocation will be unloaded. An
invocation for S supplying an empty version]{.comment}
:::

::: {.line}
[]{#l00184}[ 184]{.lineno}  [// list causes the manager to unload all
versions of S.]{.comment}
:::

::: {.line}
[]{#l00185}[ 185]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00186}[ 186]{.lineno}  [// First example call sequence:]{.comment}
:::

::: {.line}
[]{#l00187}[ 187]{.lineno}  [// callback(A, {A1}) // Aspire to load
version 1 of servable A.]{.comment}
:::

::: {.line}
[]{#l00188}[ 188]{.lineno}  [// callback(B, {B1, B2}) // Aspire to load
versions 1 and 2 of servable B.]{.comment}
:::

::: {.line}
[]{#l00189}[ 189]{.lineno}  [// callback(A, {A2}) // Aspire to unload A1
and load A2.]{.comment}
:::

::: {.line}
[]{#l00190}[ 190]{.lineno}  [// callback(B, {}) // Aspire to unload all
versions of servable B.]{.comment}
:::

::: {.line}
[]{#l00191}[ 191]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00192}[ 192]{.lineno}  [// Second example call sequence:]{.comment}
:::

::: {.line}
[]{#l00193}[ 193]{.lineno}  [// callback(A, {A1}) // Aspire to load
version 1 of servable A.]{.comment}
:::

::: {.line}
[]{#l00194}[ 194]{.lineno}  [// callback(A, {A1, A2}) // Aspire to load
versions 1 and 2 of servable A.]{.comment}
:::

::: {.line}
[]{#l00195}[ 195]{.lineno}  [// callback(A, {A2}) // Aspire to unload
A1.]{.comment}
:::

::: {.line}
[]{#l00196}[ 196]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00197}[ 197]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00198}[ 198]{.lineno}  [// 2. Load()/Unload() CALLS GO TO A SINGLE
LOADER OBJECT]{.comment}
:::

::: {.line}
[]{#l00199}[ 199]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00200}[ 200]{.lineno}  [// In general, multiple callback calls may
supply a loader object for a given]{.comment}
:::

::: {.line}
[]{#l00201}[ 201]{.lineno}  [// servable id. Once the manager calls
Load() on one of those loaders, its]{.comment}
:::

::: {.line}
[]{#l00202}[ 202]{.lineno}  [// next call for that id will be to the
same loader\'s Unload() method. (In]{.comment}
:::

::: {.line}
[]{#l00203}[ 203]{.lineno}  [// other words, bracketed Load() and
Unload() calls will be to the same loader]{.comment}
:::

::: {.line}
[]{#l00204}[ 204]{.lineno}  [// object.)]{.comment}
:::

::: {.line}
[]{#l00205}[ 205]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00206}[ 206]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00207}[ 207]{.lineno}  [// 3. NO SPONTANEOUS UNLOADING]{.comment}
:::

::: {.line}
[]{#l00208}[ 208]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00209}[ 209]{.lineno}  [// The manager aims to evolve the
loadedness states of the servable objects it]{.comment}
:::

::: {.line}
[]{#l00210}[ 210]{.lineno}  [// manages to match the aspired list, but
at a given point in time the two may]{.comment}
:::

::: {.line}
[]{#l00211}[ 211]{.lineno}  [// not coincide. That is because (a)
loading/unloading are not instantaneous]{.comment}
:::

::: {.line}
[]{#l00212}[ 212]{.lineno}  [// operations, (b) loading can fail, and
(c) the manager reserves the right to]{.comment}
:::

::: {.line}
[]{#l00213}[ 213]{.lineno}  [// refuse to load a servable version in the
aspired list e.g. due to resource]{.comment}
:::

::: {.line}
[]{#l00214}[ 214]{.lineno}  [// limitations.]{.comment}
:::

::: {.line}
[]{#l00215}[ 215]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00216}[ 216]{.lineno}  [// However, the manager does obey the
following constraint: Once it has loaded]{.comment}
:::

::: {.line}
[]{#l00217}[ 217]{.lineno}  [// a given servable version V, as long as V
is present in the latest aspired]{.comment}
:::

::: {.line}
[]{#l00218}[ 218]{.lineno}  [// list it cannot unload V. One purpose of
this guarantee is to facilitate]{.comment}
:::

::: {.line}
[]{#l00219}[ 219]{.lineno}  [// incremental loading, in which version
V\'s Load() implementation arranges to]{.comment}
:::

::: {.line}
[]{#l00220}[ 220]{.lineno}  [// copy state from (or share state with)
and already-loaded version V-1 (or]{.comment}
:::

::: {.line}
[]{#l00221}[ 221]{.lineno}  [// any prior version(s) that are loaded,
for that matter). As long as V-1 is]{.comment}
:::

::: {.line}
[]{#l00222}[ 222]{.lineno}  [// currently loaded, and remains part of
the aspired list, V can rely on V-1]{.comment}
:::

::: {.line}
[]{#l00223}[ 223]{.lineno}  [// remaining loaded.]{.comment}
:::

::: {.line}
[]{#l00224}[ 224]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00225}[ 225]{.lineno} 
[Source\<std::unique\_ptr\<Loader\>](classtensorflow_1_1serving_1_1Source.html){.code}\>::AspiredVersionsCallback
:::

::: {.line}
[]{#l00226}[ 226]{.lineno} 
[GetAspiredVersionsCallback](classtensorflow_1_1serving_1_1AspiredVersionsManager.html#a4fcdded2573a67abe77f238857e57f35){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00227}[ 227]{.lineno} 
:::

::: {.line}
[]{#l00228}[ 228]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00229}[ 229]{.lineno}  [friend]{.keyword} [class
]{.keyword}[internal::AspiredVersionsManagerTargetImpl](classtensorflow_1_1serving_1_1internal_1_1AspiredVersionsManagerTargetImpl.html){.code};
:::

::: {.line}
[]{#l00230}[ 230]{.lineno}  [friend]{.keyword} [class
]{.keyword}[test\_util::AspiredVersionsManagerTestAccess](classtensorflow_1_1serving_1_1test__util_1_1AspiredVersionsManagerTestAccess.html){.code};
:::

::: {.line}
[]{#l00231}[ 231]{.lineno}  [friend]{.keyword} [class
]{.keyword}[ServerCore](classtensorflow_1_1serving_1_1ServerCore.html){.code};
:::

::: {.line}
[]{#l00232}[ 232]{.lineno}  [friend]{.keyword} uint32
internal::GetManagerNumLoadThreads(
:::

::: {.line}
[]{#l00233}[ 233]{.lineno} 
[AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.code}\*
manager);
:::

::: {.line}
[]{#l00234}[ 234]{.lineno}  [friend]{.keyword}
std::function\<void(uint32)\>
internal::SetManagerNumLoadThreadsNotifier(
:::

::: {.line}
[]{#l00235}[ 235]{.lineno} 
[AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.code}\*
manager);
:::

::: {.line}
[]{#l00236}[ 236]{.lineno} 
:::

::: {.line}
[]{#l00237}[ 237]{.lineno} 
[AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.code}(
:::

::: {.line}
[]{#l00238}[ 238]{.lineno}  int64\_t manage\_state\_interval\_micros,
Env\* env,
:::

::: {.line}
[]{#l00239}[ 239]{.lineno}  std::unique\_ptr\<AspiredVersionPolicy\>
aspired\_version\_policy,
:::

::: {.line}
[]{#l00240}[ 240]{.lineno}  CustomSortActionsFn custom\_sort\_actions,
:::

::: {.line}
[]{#l00241}[ 241]{.lineno}  std::unique\_ptr\<BasicManager\>
basic\_manager, [bool]{.keywordtype} with\_current\_context);
:::

::: {.line}
[]{#l00242}[ 242]{.lineno} 
:::

::: {.line}
[]{#l00243}[ 243]{.lineno}  Status GetUntypedServableHandle(
:::

::: {.line}
[]{#l00244}[ 244]{.lineno}  [const]{.keyword}
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.code}&
request,
:::

::: {.line}
[]{#l00245}[ 245]{.lineno}  std::unique\_ptr\<UntypedServableHandle\>\*
untyped\_handle) [override]{.keyword};
:::

::: {.line}
[]{#l00246}[ 246]{.lineno} 
:::

::: {.line}
[]{#l00247}[ 247]{.lineno}  std::map\<ServableId,
std::unique\_ptr\<UntypedServableHandle\>\>
:::

::: {.line}
[]{#l00248}[ 248]{.lineno}  GetAvailableUntypedServableHandles() [const
override]{.keyword};
:::

::: {.line}
[]{#l00249}[ 249]{.lineno} 
:::

::: {.line}
[]{#l00250}[ 250]{.lineno}  [// Enqueues an incoming aspired-versions
request to be processed later,]{.comment}
:::

::: {.line}
[]{#l00251}[ 251]{.lineno}  [// asynchronously.]{.comment}
:::

::: {.line}
[]{#l00252}[ 252]{.lineno}  [void]{.keywordtype}
EnqueueAspiredVersionsRequest(
:::

::: {.line}
[]{#l00253}[ 253]{.lineno}  [const]{.keyword} StringPiece
servable\_name,
:::

::: {.line}
[]{#l00254}[ 254]{.lineno} 
std::vector\<[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.code}\<std::unique\_ptr\<Loader\>\>\>
versions)
:::

::: {.line}
[]{#l00255}[ 255]{.lineno} 
TF\_LOCKS\_EXCLUDED(pending\_aspired\_versions\_requests\_mu\_);
:::

::: {.line}
[]{#l00256}[ 256]{.lineno} 
:::

::: {.line}
[]{#l00257}[ 257]{.lineno}  [// Processes an aspired-versions request.
It assumes the request doesn\'t]{.comment}
:::

::: {.line}
[]{#l00258}[ 258]{.lineno}  [// re-aspire any servables currently marked
as not aspired in]{.comment}
:::

::: {.line}
[]{#l00259}[ 259]{.lineno}  [// \'basic\_manager\_\'.]{.comment}
:::

::: {.line}
[]{#l00260}[ 260]{.lineno}  [void]{.keywordtype}
ProcessAspiredVersionsRequest(
:::

::: {.line}
[]{#l00261}[ 261]{.lineno}  [const]{.keyword} StringPiece
servable\_name,
:::

::: {.line}
[]{#l00262}[ 262]{.lineno} 
std::vector\<[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.code}\<std::unique\_ptr\<Loader\>\>\>
versions)
:::

::: {.line}
[]{#l00263}[ 263]{.lineno} 
TF\_EXCLUSIVE\_LOCKS\_REQUIRED(basic\_manager\_read\_modify\_write\_mu\_);
:::

::: {.line}
[]{#l00264}[ 264]{.lineno} 
:::

::: {.line}
[]{#l00265}[ 265]{.lineno}  [// Determines whether an aspired-versions
request contains any versions that]{.comment}
:::

::: {.line}
[]{#l00266}[ 266]{.lineno}  [// are currently being managed in
\'basic\_manager\_\' with is\_aspired==false.]{.comment}
:::

::: {.line}
[]{#l00267}[ 267]{.lineno}  [bool]{.keywordtype}
ContainsAnyReaspiredVersions(
:::

::: {.line}
[]{#l00268}[ 268]{.lineno}  [const]{.keyword} StringPiece
servable\_name,
:::

::: {.line}
[]{#l00269}[ 269]{.lineno}  [const]{.keyword}
std::vector\<[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.code}\<std::unique\_ptr\<Loader\>\>\>&
versions) [const]{.keyword}
:::

::: {.line}
[]{#l00270}[ 270]{.lineno} 
TF\_SHARED\_LOCKS\_REQUIRED(basic\_manager\_read\_modify\_write\_mu\_);
:::

::: {.line}
[]{#l00271}[ 271]{.lineno} 
:::

::: {.line}
[]{#l00272}[ 272]{.lineno}  [// Performs the action on the
harness.]{.comment}
:::

::: {.line}
[]{#l00273}[ 273]{.lineno}  [void]{.keywordtype}
PerformAction([const]{.keyword}
[AspiredVersionPolicy::ServableAction](structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction.html){.code}
action)
:::

::: {.line}
[]{#l00274}[ 274]{.lineno} 
TF\_EXCLUSIVE\_LOCKS\_REQUIRED(basic\_manager\_read\_modify\_write\_mu\_);
:::

::: {.line}
[]{#l00275}[ 275]{.lineno} 
:::

::: {.line}
[]{#l00276}[ 276]{.lineno}  [// Goes through the harness map and calls
the configured servable\_policy with]{.comment}
:::

::: {.line}
[]{#l00277}[ 277]{.lineno}  [// the state snapshots to get a list of
suggested actions. The actions are]{.comment}
:::

::: {.line}
[]{#l00278}[ 278]{.lineno}  [// then ordered and finally the topmost one
is performed.]{.comment}
:::

::: {.line}
[]{#l00279}[ 279]{.lineno} 
absl::optional\<AspiredVersionPolicy::ServableAction\> GetNextAction()
:::

::: {.line}
[]{#l00280}[ 280]{.lineno} 
TF\_EXCLUSIVE\_LOCKS\_REQUIRED(basic\_manager\_read\_modify\_write\_mu\_);
:::

::: {.line}
[]{#l00281}[ 281]{.lineno} 
:::

::: {.line}
[]{#l00282}[ 282]{.lineno}  [// Checks for servables that are not
aspired and at some final state and tells]{.comment}
:::

::: {.line}
[]{#l00283}[ 283]{.lineno}  [// \'basic\_manager\_\' to forget about
them. This method is intended to be]{.comment}
:::

::: {.line}
[]{#l00284}[ 284]{.lineno}  [// invoked periodically, interleaved with
InvokePolicyAndExecuteAction() and]{.comment}
:::

::: {.line}
[]{#l00285}[ 285]{.lineno}  [//
HandlePendingAspiredVersionsRequests().]{.comment}
:::

::: {.line}
[]{#l00286}[ 286]{.lineno}  [void]{.keywordtype} FlushServables()
TF\_LOCKS\_EXCLUDED(basic\_manager\_read\_modify\_write\_mu\_);
:::

::: {.line}
[]{#l00287}[ 287]{.lineno} 
:::

::: {.line}
[]{#l00288}[ 288]{.lineno}  [// Handles enqueued aspired-versions
requests. This method is intended to be]{.comment}
:::

::: {.line}
[]{#l00289}[ 289]{.lineno}  [// invoked periodically, interleaved with
InvokePolicyAndExecuteAction().]{.comment}
:::

::: {.line}
[]{#l00290}[ 290]{.lineno}  [void]{.keywordtype}
HandlePendingAspiredVersionsRequests()
:::

::: {.line}
[]{#l00291}[ 291]{.lineno} 
TF\_LOCKS\_EXCLUDED(basic\_manager\_read\_modify\_write\_mu\_,
:::

::: {.line}
[]{#l00292}[ 292]{.lineno}  pending\_aspired\_versions\_requests\_mu\_);
:::

::: {.line}
[]{#l00293}[ 293]{.lineno} 
:::

::: {.line}
[]{#l00294}[ 294]{.lineno}  [// Invokes the aspired-version policy and
executes any returned policy action.]{.comment}
:::

::: {.line}
[]{#l00295}[ 295]{.lineno}  [// This method is intended to be invoked
periodically.]{.comment}
:::

::: {.line}
[]{#l00296}[ 296]{.lineno}  [void]{.keywordtype}
InvokePolicyAndExecuteAction()
:::

::: {.line}
[]{#l00297}[ 297]{.lineno} 
TF\_LOCKS\_EXCLUDED(basic\_manager\_read\_modify\_write\_mu\_);
:::

::: {.line}
[]{#l00298}[ 298]{.lineno} 
:::

::: {.line}
[]{#l00299}[ 299]{.lineno}  [// Sets the number of load
threads.]{.comment}
:::

::: {.line}
[]{#l00300}[ 300]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00301}[ 301]{.lineno}  [// This may block all new load requests, or
temporarily allow more threads to]{.comment}
:::

::: {.line}
[]{#l00302}[ 302]{.lineno}  [// start, before it returns. See
BasicManager::SetNumLoadThreads for details]{.comment}
:::

::: {.line}
[]{#l00303}[ 303]{.lineno}  [void]{.keywordtype}
SetNumLoadThreads(uint32 num\_load\_threads);
:::

::: {.line}
[]{#l00304}[ 304]{.lineno}  uint32 num\_load\_threads() const;
:::

::: {.line}
[]{#l00305}[ 305]{.lineno} 
:::

::: {.line}
[]{#l00306}[ 306]{.lineno} 
std::unique\_ptr\<[AspiredVersionPolicy](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html){.code}\>
aspired\_version\_policy\_;
:::

::: {.line}
[]{#l00307}[ 307]{.lineno}  CustomSortActionsFn custom\_sort\_actions\_;
:::

::: {.line}
[]{#l00308}[ 308]{.lineno} 
:::

::: {.line}
[]{#l00309}[ 309]{.lineno}  [// Aspired-versions requests pending to be
processed, keyed by servable name.]{.comment}
:::

::: {.line}
[]{#l00310}[ 310]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00311}[ 311]{.lineno}  [// We stage incoming aspired-versions
requests here and process them]{.comment}
:::

::: {.line}
[]{#l00312}[ 312]{.lineno}  [// asynchronously from the
SetAspiredVersions() call, to avoid blocking in]{.comment}
:::

::: {.line}
[]{#l00313}[ 313]{.lineno}  [// SetAspiredVersions() to handle
re-aspiring versions.]{.comment}
:::

::: {.line}
[]{#l00314}[ 314]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00315}[ 315]{.lineno}  [// For a given servable name we to need
store at most pending request, since]{.comment}
:::

::: {.line}
[]{#l00316}[ 316]{.lineno}  [// each new request we receive supercedes
the prior one.]{.comment}
:::

::: {.line}
[]{#l00317}[ 317]{.lineno}  using AspiredVersionsMap =
:::

::: {.line}
[]{#l00318}[ 318]{.lineno}  std::map\<[string]{.keywordtype},
std::vector\<[ServableData](classtensorflow_1_1serving_1_1ServableData.html){.code}\<std::unique\_ptr\<[Loader](classtensorflow_1_1serving_1_1Loader.html){.code}\>\>\>\>;
:::

::: {.line}
[]{#l00319}[ 319]{.lineno}  AspiredVersionsMap
pending\_aspired\_versions\_requests\_
:::

::: {.line}
[]{#l00320}[ 320]{.lineno} 
TF\_GUARDED\_BY(pending\_aspired\_versions\_requests\_mu\_);
:::

::: {.line}
[]{#l00321}[ 321]{.lineno}  mutable mutex
pending\_aspired\_versions\_requests\_mu\_;
:::

::: {.line}
[]{#l00322}[ 322]{.lineno} 
:::

::: {.line}
[]{#l00323}[ 323]{.lineno}  [// To lock basic\_manager\_ to perform
atomic read/modify/write operations on]{.comment}
:::

::: {.line}
[]{#l00324}[ 324]{.lineno}  [// the set of managed servables and their
state (in particular, aspiredness).]{.comment}
:::

::: {.line}
[]{#l00325}[ 325]{.lineno}  mutable mutex
basic\_manager\_read\_modify\_write\_mu\_;
:::

::: {.line}
[]{#l00326}[ 326]{.lineno} 
:::

::: {.line}
[]{#l00327}[ 327]{.lineno}  [// Periodically runs
HandlePendingAspiredVersionsRequests() and]{.comment}
:::

::: {.line}
[]{#l00328}[ 328]{.lineno}  [// InvokePolicyAndExecuteAction() in a
background thread.]{.comment}
:::

::: {.line}
[]{#l00329}[ 329]{.lineno}  std::unique\_ptr\<PeriodicFunction\>
manage\_state\_thread\_;
:::

::: {.line}
[]{#l00330}[ 330]{.lineno} 
:::

::: {.line}
[]{#l00331}[ 331]{.lineno}  [// The object that implements the Target
API on behalf of this manager.]{.comment}
:::

::: {.line}
[]{#l00332}[ 332]{.lineno} 
std::unique\_ptr\<[TargetBase](classtensorflow_1_1serving_1_1TargetBase.html){.code}\<std::unique\_ptr\<[Loader](classtensorflow_1_1serving_1_1Loader.html){.code}\>\>\>
target\_impl\_;
:::

::: {.line}
[]{#l00333}[ 333]{.lineno} 
:::

::: {.line}
[]{#l00334}[ 334]{.lineno}  [// This is where the servables \"live\"
while they are being managed.]{.comment}
:::

::: {.line}
[]{#l00335}[ 335]{.lineno} 
std::unique\_ptr\<[BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.code}\>
basic\_manager\_;
:::

::: {.line}
[]{#l00336}[ 336]{.lineno} 
:::

::: {.line}
[]{#l00337}[ 337]{.lineno}  [// An observer object that forwards to
SetNumLoadThreads(), if not detached.]{.comment}
:::

::: {.line}
[]{#l00338}[ 338]{.lineno}  [// This is declared last here so that it is
deleted before basic\_manager\_.]{.comment}
:::

::: {.line}
[]{#l00339}[ 339]{.lineno} 
std::unique\_ptr\<[Observer](classtensorflow_1_1serving_1_1Observer.html){.code}\<const
uint32\>\> set\_num\_load\_threads\_observer\_;
:::

::: {.line}
[]{#l00340}[ 340]{.lineno} 
:::

::: {.line}
[]{#l00341}[ 341]{.lineno}  [// For servables which end with
LoaderHarness::State::kError, enable]{.comment}
:::

::: {.line}
[]{#l00342}[ 342]{.lineno}  [// future attempts at reload to
progress.]{.comment}
:::

::: {.line}
[]{#l00343}[ 343]{.lineno}  [bool]{.keywordtype}
enable\_reload\_servables\_with\_error\_ = false;
:::

::: {.line}
[]{#l00344}[ 344]{.lineno} 
:::

::: {.line}
[]{#l00345}[ 345]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html){.code});
:::

::: {.line}
[]{#l00346}[ 346]{.lineno} };
:::

::: {.line}
[]{#l00347}[ 347]{.lineno} 
:::

::: {.line}
[]{#l00348}[ 348]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00349}[ 349]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00350}[ 350]{.lineno} 
:::

::: {.line}
[]{#l00351}[ 351]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_ASPIRED\_VERSIONS\_MANAGER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1AspiredVersionPolicy_html .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionPolicy](classtensorflow_1_1serving_1_1AspiredVersionPolicy.html)
:::

::: {.ttdef}
**Definition:** aspired\_version\_policy.h:48
:::
:::

::: {#aclasstensorflow_1_1serving_1_1AspiredVersionsManager_html .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManager](classtensorflow_1_1serving_1_1AspiredVersionsManager.html)
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager.h:86
:::
:::

::: {#aclasstensorflow_1_1serving_1_1AspiredVersionsManager_html_a058a76ee71c52d4a6319f14cd9b2ad69 .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManager::ListAvailableServableIds](classtensorflow_1_1serving_1_1AspiredVersionsManager.html#a058a76ee71c52d4a6319f14cd9b2ad69)
:::

::: {.ttdeci}
std::vector\< ServableId \> ListAvailableServableIds() const override
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager.cc:243
:::
:::

::: {#aclasstensorflow_1_1serving_1_1AspiredVersionsManager_html_a4fcdded2573a67abe77f238857e57f35 .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManager::GetAspiredVersionsCallback](classtensorflow_1_1serving_1_1AspiredVersionsManager.html#a4fcdded2573a67abe77f238857e57f35)
:::

::: {.ttdeci}
Source\< std::unique\_ptr\< Loader \> \>::AspiredVersionsCallback
GetAspiredVersionsCallback() override
:::

::: {.ttdoc}
Returns a callback to set the list of aspired versions for a particular
servable stream,\...
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager.cc:260
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

::: {#aclasstensorflow_1_1serving_1_1EventBus_html .ttc}
::: {.ttname}
[tensorflow::serving::EventBus](classtensorflow_1_1serving_1_1EventBus.html)
:::

::: {.ttdef}
**Definition:** event\_bus.h:63
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Loader_html .ttc}
::: {.ttname}
[tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html)
:::

::: {.ttdef}
**Definition:** loader.h:56
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

::: {#aclasstensorflow_1_1serving_1_1Observer_html .ttc}
::: {.ttname}
[tensorflow::serving::Observer](classtensorflow_1_1serving_1_1Observer.html)
:::

::: {.ttdef}
**Definition:** observer.h:60
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

::: {#aclasstensorflow_1_1serving_1_1ServerCore_html .ttc}
::: {.ttname}
[tensorflow::serving::ServerCore](classtensorflow_1_1serving_1_1ServerCore.html)
:::

::: {.ttdef}
**Definition:** server\_core.h:74
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Source_html .ttc}
::: {.ttname}
[tensorflow::serving::Source](classtensorflow_1_1serving_1_1Source.html)
:::

::: {.ttdef}
**Definition:** source.h:65
:::
:::

::: {#aclasstensorflow_1_1serving_1_1TargetBase_html .ttc}
::: {.ttname}
[tensorflow::serving::TargetBase](classtensorflow_1_1serving_1_1TargetBase.html)
:::

::: {.ttdef}
**Definition:** target.h:61
:::
:::

::: {#aclasstensorflow_1_1serving_1_1Target_html .ttc}
::: {.ttname}
[tensorflow::serving::Target](classtensorflow_1_1serving_1_1Target.html)
:::

::: {.ttdef}
**Definition:** target.h:37
:::
:::

::: {#aclasstensorflow_1_1serving_1_1internal_1_1AspiredVersionsManagerTargetImpl_html .ttc}
::: {.ttname}
[tensorflow::serving::internal::AspiredVersionsManagerTargetImpl](classtensorflow_1_1serving_1_1internal_1_1AspiredVersionsManagerTargetImpl.html)
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager.cc:135
:::
:::

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1AspiredVersionsManagerTestAccess_html .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::AspiredVersionsManagerTestAccess](classtensorflow_1_1serving_1_1test__util_1_1AspiredVersionsManagerTestAccess.html)
:::

::: {.ttdef}
**Definition:** manager\_test\_util.h:28
:::
:::

::: {#astructtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction_html .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionPolicy::ServableAction](structtensorflow_1_1serving_1_1AspiredVersionPolicy_1_1ServableAction.html)
:::

::: {.ttdoc}
Action and the id of the servable associated with it.
:::

::: {.ttdef}
**Definition:** aspired\_version\_policy.h:61
:::
:::

::: {#astructtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_html .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManager::Options](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html)
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager.h:96
:::
:::

::: {#astructtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_html_a2d3ca06a39d39b03efd513250ce1cf89 .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManager::Options::max\_num\_load\_retries](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a2d3ca06a39d39b03efd513250ce1cf89)
:::

::: {.ttdeci}
uint32 max\_num\_load\_retries
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager.h:133
:::
:::

::: {#astructtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_html_a60e52c6ea540f1a1bfad9a8987699684 .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManager::Options::manage\_state\_interval\_micros](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a60e52c6ea540f1a1bfad9a8987699684)
:::

::: {.ttdeci}
int64\_t manage\_state\_interval\_micros
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager.h:104
:::
:::

::: {#astructtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_html_a68571485293a22013658ecaff027b0a1 .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManager::Options::resource\_tracker](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a68571485293a22013658ecaff027b0a1)
:::

::: {.ttdeci}
std::unique\_ptr\< ResourceTracker \> resource\_tracker
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager.h:99
:::
:::

::: {#astructtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_html_a68dce64ddf3bec5995ad7161c03efdb9 .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManager::Options::custom\_sort\_actions](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a68dce64ddf3bec5995ad7161c03efdb9)
:::

::: {.ttdeci}
CustomSortActionsFn custom\_sort\_actions
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager.h:117
:::
:::

::: {#astructtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_html_a6c54dcb0499ef952eca4fdb364aa4859 .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManager::Options::num\_unload\_threads](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a6c54dcb0499ef952eca4fdb364aa4859)
:::

::: {.ttdeci}
uint32 num\_unload\_threads
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager.h:129
:::
:::

::: {#astructtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_html_a8f08cac3875a829ae408727f852269e7 .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManager::Options::env](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a8f08cac3875a829ae408727f852269e7)
:::

::: {.ttdeci}
Env \* env
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager.h:151
:::
:::

::: {#astructtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_html_a921d700e38f7e4f6add9288beb0506e5 .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManager::Options::aspired\_version\_policy](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#a921d700e38f7e4f6add9288beb0506e5)
:::

::: {.ttdeci}
std::unique\_ptr\< AspiredVersionPolicy \> aspired\_version\_policy
:::

::: {.ttdoc}
The AspiredVersionPolicy to use for the manager. Must be non-null.
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager.h:111
:::
:::

::: {#astructtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_html_aae4c93fdb83f2538e44df55f3669d38e .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManager::Options::num\_load\_threads](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#aae4c93fdb83f2538e44df55f3669d38e)
:::

::: {.ttdeci}
uint32 num\_load\_threads
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager.h:123
:::
:::

::: {#astructtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_html_ac021adf80573b8c2e0c61688b43f6130 .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManager::Options::servable\_event\_bus](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#ac021adf80573b8c2e0c61688b43f6130)
:::

::: {.ttdeci}
EventBus\< ServableState \> \* servable\_event\_bus
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager.h:108
:::
:::

::: {#astructtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_html_ac16d5d89359873e7004b4a64c2c54a4f .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManager::Options::pre\_load\_hook](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#ac16d5d89359873e7004b4a64c2c54a4f)
:::

::: {.ttdeci}
PreLoadHook pre\_load\_hook
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager.h:155
:::
:::

::: {#astructtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options_html_ad44f1e8c79d9b60cc87bd616b2f02169 .ttc}
::: {.ttname}
[tensorflow::serving::AspiredVersionsManager::Options::load\_retry\_interval\_micros](structtensorflow_1_1serving_1_1AspiredVersionsManager_1_1Options.html#ad44f1e8c79d9b60cc87bd616b2f02169)
:::

::: {.ttdeci}
int64\_t load\_retry\_interval\_micros
:::

::: {.ttdef}
**Definition:** aspired\_versions\_manager.h:138
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

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
servable\_state\_monitor.h
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
TENSORFLOW\_SERVING\_CORE\_SERVABLE\_STATE\_MONITOR\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_SERVABLE\_STATE\_MONITOR\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<deque\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<functional\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<map\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} 
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"absl/time/time.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"absl/types/optional.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/platform/env.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow/core/platform/mutex.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow/core/platform/thread\_annotations.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow\_serving/core/manager.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_id.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include
\"tensorflow\_serving/core/servable\_state.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [\#include
\"tensorflow\_serving/util/event\_bus.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} 
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} 
:::

::: {.line}
[]{#l00046}[
[46](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.line}]{.lineno} [class
]{.keyword}[ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.code}
{
:::

::: {.line}
[]{#l00047}[ 47]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00048}[ 48]{.lineno}  [// START\_SKIP\_DOXYGEN]{.comment}
:::

::: {.line}
[]{#l00049}[
[49](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime.html){.line}]{.lineno} 
[struct
]{.keyword}[ServableStateAndTime](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime.html){.code}
{
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} 
[ServableStateAndTime](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} 
[ServableStateAndTime](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime.html){.code}([ServableState](structtensorflow_1_1serving_1_1ServableState.html){.code}
servable\_state,
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [const]{.keyword} uint64\_t event\_time)
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  :
[state](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime.html#a80581c8a1a09ea03377c3988a25c274d){.code}(std::move(servable\_state)),
[event\_time\_micros](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime.html#ab32413dcaaebc9df926c4ed28fa1fb4d){.code}(event\_time)
{}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} 
:::

::: {.line}
[]{#l00056}[
[56](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime.html#a80581c8a1a09ea03377c3988a25c274d){.line}]{.lineno} 
[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.code}
[state](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime.html#a80581c8a1a09ea03377c3988a25c274d){.code};
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} 
:::

::: {.line}
[]{#l00059}[
[59](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime.html#ab32413dcaaebc9df926c4ed28fa1fb4d){.line}]{.lineno} 
uint64\_t
[event\_time\_micros](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime.html#ab32413dcaaebc9df926c4ed28fa1fb4d){.code};
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  [string]{.keywordtype}
[DebugString](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime.html#a7730a4eb7f73739112fa5f51d1879387){.code}()
[const]{.keyword};
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  };
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} 
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [using]{.keyword} ServableName = string;
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  [using]{.keyword} Version = int64;
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [using]{.keyword} VersionMap =
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  std::map\<Version, ServableStateAndTime,
std::greater\<Version\>\>;
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  [using]{.keyword} ServableMap =
std::map\<ServableName, VersionMap\>;
:::

::: {.line}
[]{#l00071}[ 71]{.lineno}  [using]{.keyword} ServableSet =
std::set\<ServableName\>;
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} 
:::

::: {.line}
[]{#l00073}[
[73](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1Options.html){.line}]{.lineno} 
[struct
]{.keyword}[Options](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1Options.html){.code}
{
:::

::: {.line}
[]{#l00074}[ 74]{.lineno} 
[Options](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1Options.html){.code}()
{}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} 
:::

::: {.line}
[]{#l00078}[
[78](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1Options.html#a65eadcb3e4a38f2b206df7dbedd9ed9b){.line}]{.lineno} 
uint64\_t
[max\_count\_log\_events](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1Options.html#a65eadcb3e4a38f2b206df7dbedd9ed9b){.code}
= 0;
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  };
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [// END\_SKIP\_DOXYGEN]{.comment}
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} 
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  [using]{.keyword} BoundedLog =
std::deque\<ServableStateAndTime\>;
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} 
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [explicit]{.keyword}
[ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.code}([EventBus\<ServableState\>](classtensorflow_1_1serving_1_1EventBus.html){.code}\*
bus,
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  [const]{.keyword}
[Options](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1Options.html){.code}&
options =
[Options](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1Options.html){.code}());
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  [virtual]{.keyword}
\~[ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.code}();
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} 
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  absl::optional\<ServableState\>
[GetState](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a8fa6dd1536bbb85a55b3e41c1d2577d1){.code}([const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
servable\_id) [const]{.keyword}
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} 
:::

::: {.line}
[]{#l00095}[ 95]{.lineno}  absl::optional\<ServableStateAndTime\>
[GetStateAndTime](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a8ff54ab2471885168dba0b1a05be7bea){.code}(
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  [const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
servable\_id) [const]{.keyword} TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} 
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  VersionMap
[GetVersionStates](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a501ef561e30709fe17f10c913d34bb1e){.code}([const]{.keyword}
[string]{.keywordtype}& servable\_name) [const]{.keyword}
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00102}[ 102]{.lineno} 
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  ServableMap
[GetAllServableStates](classtensorflow_1_1serving_1_1ServableStateMonitor.html#abc3c1c27b6b7c0e8ef9a42039ede74cc){.code}()
const TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} 
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  ServableMap
[GetLiveServableStates](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a522166e0255c93e87a6d63c3d17e3f38){.code}()
const TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} 
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  [void]{.keywordtype}
[ForgetUnloadedServableStates](classtensorflow_1_1serving_1_1ServableStateMonitor.html#ae3ad2a50b7fa7b695885fe913b70b029){.code}()
TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} 
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [// Returns all servables that are in
state]{.comment}
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  [//
ServableState::ManagerState::kAvailable.]{.comment}
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  [// Note that as opposed to
GetAllServableStates() and GetLiveServableStates(),]{.comment}
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  [// this method loops over all the tracked
servables.]{.comment}
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  ServableSet GetAvailableServableStates()
const TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00119}[ 119]{.lineno} 
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  BoundedLog
[GetBoundedLog](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a2afc57f0eb671a3c3342c7dd71a9d6a7){.code}()
const TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} 
:::

::: {.line}
[]{#l00147}[
[147](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a6b64d18d981941012439766e57bd8d66){.line}]{.lineno} 
using
[ServableStateNotifierFn](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a6b64d18d981941012439766e57bd8d66){.code}
= std::function\<[void]{.keywordtype}(
:::

::: {.line}
[]{#l00148}[ 148]{.lineno}  [bool]{.keywordtype} reached\_goal\_state,
:::

::: {.line}
[]{#l00149}[ 149]{.lineno}  const
std::map\<[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code},
[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.code}::ManagerState\>&
states\_reached)\>;
:::

::: {.line}
[]{#l00150}[ 150]{.lineno}  [void]{.keywordtype}
NotifyWhenServablesReachState(
:::

::: {.line}
[]{#l00151}[ 151]{.lineno}  const
std::vector\<[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.code}\>&
servables,
:::

::: {.line}
[]{#l00152}[ 152]{.lineno} 
[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.code}::ManagerState
goal\_state,
:::

::: {.line}
[]{#l00153}[ 153]{.lineno}  const
[ServableStateNotifierFn](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a6b64d18d981941012439766e57bd8d66){.code}&
notifier\_fn) TF\_LOCKS\_EXCLUDED(mu\_);
:::

::: {.line}
[]{#l00154}[ 154]{.lineno} 
:::

::: {.line}
[]{#l00163}[ 163]{.lineno}  [bool]{.keywordtype}
[WaitUntilServablesReachStateWithTimeout](classtensorflow_1_1serving_1_1ServableStateMonitor.html#aa9579ee04bf76fa627d65d9cbbb7ccb7){.code}(
:::

::: {.line}
[]{#l00164}[ 164]{.lineno}  const
std::vector\<[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.code}\>&
servables,
:::

::: {.line}
[]{#l00165}[ 165]{.lineno} 
[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.code}::ManagerState
goal\_state, absl::Duration timeout,
:::

::: {.line}
[]{#l00166}[ 166]{.lineno} 
std::map\<[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code},
[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.code}::ManagerState\>\*
states\_reached =
:::

::: {.line}
[]{#l00167}[ 167]{.lineno}  [nullptr]{.keywordtype})
TF\_LOCKS\_EXCLUDED(mu\_) TF\_MUST\_USE\_RESULT;
:::

::: {.line}
[]{#l00168}[ 168]{.lineno}  [bool]{.keywordtype}
WaitUntilServablesReachState(
:::

::: {.line}
[]{#l00169}[ 169]{.lineno}  const
std::vector\<[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.code}\>&
servables,
:::

::: {.line}
[]{#l00170}[ 170]{.lineno} 
[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.code}::ManagerState
goal\_state,
:::

::: {.line}
[]{#l00171}[ 171]{.lineno} 
std::map\<[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code},
[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.code}::ManagerState\>\*
states\_reached =
:::

::: {.line}
[]{#l00172}[ 172]{.lineno}  [nullptr]{.keywordtype})
TF\_MUST\_USE\_RESULT;
:::

::: {.line}
[]{#l00173}[ 173]{.lineno} 
:::

::: {.line}
[]{#l00174}[ 174]{.lineno}  [// Subscribes to all servable state changes
hitting this monitor. This is]{.comment}
:::

::: {.line}
[]{#l00175}[ 175]{.lineno}  [// called after the monitor updates its own
state based on the event.]{.comment}
:::

::: {.line}
[]{#l00176}[ 176]{.lineno}  using NotifyFn =
std::function\<[void]{.keywordtype}(const
[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.code}&)\>;
:::

::: {.line}
[]{#l00177}[ 177]{.lineno}  [void]{.keywordtype} Notify(const NotifyFn&
notify\_fn) TF\_LOCKS\_EXCLUDED(notify\_mu\_);
:::

::: {.line}
[]{#l00178}[ 178]{.lineno} 
:::

::: {.line}
[]{#l00179}[ 179]{.lineno}  private:
:::

::: {.line}
[]{#l00180}[ 180]{.lineno} 
absl::optional\<[ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.code}::[ServableStateAndTime](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime.html){.code}\>
:::

::: {.line}
[]{#l00181}[ 181]{.lineno}  GetStateAndTimeInternal(const
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
servable\_id) const
:::

::: {.line}
[]{#l00182}[ 182]{.lineno}  TF\_EXCLUSIVE\_LOCKS\_REQUIRED(mu\_);
:::

::: {.line}
[]{#l00183}[ 183]{.lineno} 
:::

::: {.line}
[]{#l00184}[ 184]{.lineno}  [// Request to send notification, setup
using]{.comment}
:::

::: {.line}
[]{#l00185}[ 185]{.lineno}  [//
NotifyWhenServablesReachState(\...).]{.comment}
:::

::: {.line}
[]{#l00186}[ 186]{.lineno}  struct ServableStateNotificationRequest {
:::

::: {.line}
[]{#l00187}[ 187]{.lineno}  std::vector\<ServableRequest\> servables;
:::

::: {.line}
[]{#l00188}[ 188]{.lineno}  ServableState::ManagerState goal\_state;
:::

::: {.line}
[]{#l00189}[ 189]{.lineno} 
[ServableStateNotifierFn](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a6b64d18d981941012439766e57bd8d66){.code}
notifier\_fn;
:::

::: {.line}
[]{#l00190}[ 190]{.lineno}  };
:::

::: {.line}
[]{#l00191}[ 191]{.lineno} 
:::

::: {.line}
[]{#l00192}[ 192]{.lineno}  [// Checks whether the notification request
is satisfied and we cand send it.]{.comment}
:::

::: {.line}
[]{#l00193}[ 193]{.lineno}  [// If so, returns the
\'reached\_goal\_state\' bool and the \'states\_reached\' by]{.comment}
:::

::: {.line}
[]{#l00194}[ 194]{.lineno}  [// each servable. Oterwise returns
nullopt.]{.comment}
:::

::: {.line}
[]{#l00195}[ 195]{.lineno}  absl::optional\<
:::

::: {.line}
[]{#l00196}[ 196]{.lineno}  std::pair\<bool, std::map\<ServableId,
ServableState::ManagerState\>\>\>
:::

::: {.line}
[]{#l00197}[ 197]{.lineno}  ShouldSendStateReachedNotification(
:::

::: {.line}
[]{#l00198}[ 198]{.lineno}  [const]{.keyword}
ServableStateNotificationRequest& notification\_request)
:::

::: {.line}
[]{#l00199}[ 199]{.lineno}  TF\_EXCLUSIVE\_LOCKS\_REQUIRED(mu\_);
:::

::: {.line}
[]{#l00200}[ 200]{.lineno} 
:::

::: {.line}
[]{#l00201}[ 201]{.lineno}  [// Goes through the notification requests
and tries to see if any of them can]{.comment}
:::

::: {.line}
[]{#l00202}[ 202]{.lineno}  [// be sent. If a notification is sent, the
corresponding request is removed.]{.comment}
:::

::: {.line}
[]{#l00203}[ 203]{.lineno}  [void]{.keywordtype}
MaybeSendStateReachedNotifications()
TF\_EXCLUSIVE\_LOCKS\_REQUIRED(mu\_);
:::

::: {.line}
[]{#l00204}[ 204]{.lineno} 
:::

::: {.line}
[]{#l00205}[ 205]{.lineno}  [// Goes through the notify\_fns list and
calls each one with the currently]{.comment}
:::

::: {.line}
[]{#l00206}[ 206]{.lineno}  [// received ServableState.]{.comment}
:::

::: {.line}
[]{#l00207}[ 207]{.lineno}  [void]{.keywordtype} SendNotifications(const
[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.code}&
servable\_state)
:::

::: {.line}
[]{#l00208}[ 208]{.lineno}  TF\_LOCKS\_EXCLUDED(notify\_mu\_);
:::

::: {.line}
[]{#l00209}[ 209]{.lineno} 
:::

::: {.line}
[]{#l00210}[ 210]{.lineno}  [// This method is called when an event
comes in, but before we update our]{.comment}
:::

::: {.line}
[]{#l00211}[ 211]{.lineno}  [// state with the contents of the event.
Subclasses may override this method]{.comment}
:::

::: {.line}
[]{#l00212}[ 212]{.lineno}  [// to do custom prepreocessing based on the
event and the previous state of]{.comment}
:::

::: {.line}
[]{#l00213}[ 213]{.lineno}  [// the monitor, like calculate load-time,
etc.]{.comment}
:::

::: {.line}
[]{#l00214}[ 214]{.lineno}  virtual [void]{.keywordtype} PreHandleEvent(
:::

::: {.line}
[]{#l00215}[ 215]{.lineno}  const
[EventBus](classtensorflow_1_1serving_1_1EventBus.html){.code}\<[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.code}\>::EventAndTime&
state\_and\_time);
:::

::: {.line}
[]{#l00216}[ 216]{.lineno} 
:::

::: {.line}
[]{#l00217}[ 217]{.lineno}  [// Handles a bus event.]{.comment}
:::

::: {.line}
[]{#l00218}[ 218]{.lineno}  [void]{.keywordtype} HandleEvent(const
[EventBus](classtensorflow_1_1serving_1_1EventBus.html){.code}\<[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.code}\>::EventAndTime&
event\_and\_time)
:::

::: {.line}
[]{#l00219}[ 219]{.lineno}  TF\_LOCKS\_EXCLUDED(mu\_, notify\_mu\_);
:::

::: {.line}
[]{#l00220}[ 220]{.lineno} 
:::

::: {.line}
[]{#l00221}[ 221]{.lineno}  const Options options\_;
:::

::: {.line}
[]{#l00222}[ 222]{.lineno} 
:::

::: {.line}
[]{#l00223}[ 223]{.lineno} 
std::unique\_ptr\<[EventBus](classtensorflow_1_1serving_1_1EventBus.html){.code}\<[ServableState](structtensorflow_1_1serving_1_1ServableState.html){.code}\>::Subscription\>
bus\_subscription\_;
:::

::: {.line}
[]{#l00224}[ 224]{.lineno} 
:::

::: {.line}
[]{#l00225}[ 225]{.lineno}  mutable mutex mu\_;
:::

::: {.line}
[]{#l00226}[ 226]{.lineno} 
:::

::: {.line}
[]{#l00227}[ 227]{.lineno}  [// The current state of each servable
version that has appeared on the bus.]{.comment}
:::

::: {.line}
[]{#l00228}[ 228]{.lineno}  [// (Entries are never removed, even when
they enter state kEnd.)]{.comment}
:::

::: {.line}
[]{#l00229}[ 229]{.lineno}  ServableMap states\_ TF\_GUARDED\_BY(mu\_);
:::

::: {.line}
[]{#l00230}[ 230]{.lineno} 
:::

::: {.line}
[]{#l00231}[ 231]{.lineno}  [// The current state of each servable
version that has not transitioned to]{.comment}
:::

::: {.line}
[]{#l00232}[ 232]{.lineno}  [// state
ServableState::ManagerState::kEnd.]{.comment}
:::

::: {.line}
[]{#l00233}[ 233]{.lineno}  ServableMap live\_states\_
TF\_GUARDED\_BY(mu\_);
:::

::: {.line}
[]{#l00234}[ 234]{.lineno} 
:::

::: {.line}
[]{#l00235}[ 235]{.lineno}  [// Deque of pairs of timestamp and
ServableState, corresponding to the most]{.comment}
:::

::: {.line}
[]{#l00236}[ 236]{.lineno}  [// recent servable state events handled by
the monitor. The size of this deque]{.comment}
:::

::: {.line}
[]{#l00237}[ 237]{.lineno}  [// is upper bounded by
max\_count\_log\_events in Options.]{.comment}
:::

::: {.line}
[]{#l00238}[ 238]{.lineno}  BoundedLog log\_ TF\_GUARDED\_BY(mu\_);
:::

::: {.line}
[]{#l00239}[ 239]{.lineno} 
:::

::: {.line}
[]{#l00240}[ 240]{.lineno} 
std::vector\<ServableStateNotificationRequest\>
:::

::: {.line}
[]{#l00241}[ 241]{.lineno}  servable\_state\_notification\_requests\_
TF\_GUARDED\_BY(mu\_);
:::

::: {.line}
[]{#l00242}[ 242]{.lineno} 
:::

::: {.line}
[]{#l00243}[ 243]{.lineno}  [// Separate mutex to protect the
notify\_fns\_ so that they can be updated]{.comment}
:::

::: {.line}
[]{#l00244}[ 244]{.lineno}  [// independently. This also allows these
notify\_fns\_ to call other methods]{.comment}
:::

::: {.line}
[]{#l00245}[ 245]{.lineno}  [// in ServableStateMonitor which don\'t
depend on this mutex without being]{.comment}
:::

::: {.line}
[]{#l00246}[ 246]{.lineno}  [// deadlocked.]{.comment}
:::

::: {.line}
[]{#l00247}[ 247]{.lineno}  mutable mutex notify\_mu\_;
:::

::: {.line}
[]{#l00248}[ 248]{.lineno}  std::vector\<NotifyFn\> notify\_fns\_
TF\_GUARDED\_BY(notify\_mu\_);
:::

::: {.line}
[]{#l00249}[ 249]{.lineno} 
:::

::: {.line}
[]{#l00250}[ 250]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.code});
:::

::: {.line}
[]{#l00251}[ 251]{.lineno} };
:::

::: {.line}
[]{#l00252}[ 252]{.lineno} 
:::

::: {.line}
[]{#l00253}[ 253]{.lineno} inline [bool]{.keywordtype} operator==(const
[ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.code}::ServableStateAndTime&
a,
:::

::: {.line}
[]{#l00254}[ 254]{.lineno}  const
[ServableStateMonitor](classtensorflow_1_1serving_1_1ServableStateMonitor.html){.code}::ServableStateAndTime&
b) {
:::

::: {.line}
[]{#l00255}[ 255]{.lineno}  [return]{.keywordflow} a.event\_time\_micros
== b.event\_time\_micros && a.state == b.state;
:::

::: {.line}
[]{#l00256}[ 256]{.lineno} }
:::

::: {.line}
[]{#l00257}[ 257]{.lineno} 
:::

::: {.line}
[]{#l00258}[ 258]{.lineno} [inline]{.keyword} [bool]{.keywordtype}
operator!=([const]{.keyword} ServableStateMonitor::ServableStateAndTime&
a,
:::

::: {.line}
[]{#l00259}[ 259]{.lineno}  [const]{.keyword}
ServableStateMonitor::ServableStateAndTime& b) {
:::

::: {.line}
[]{#l00260}[ 260]{.lineno}  [return]{.keywordflow} !(a == b);
:::

::: {.line}
[]{#l00261}[ 261]{.lineno} }
:::

::: {.line}
[]{#l00262}[ 262]{.lineno} 
:::

::: {.line}
[]{#l00263}[ 263]{.lineno} [inline]{.keyword} std::ostream&
operator\<\<(
:::

::: {.line}
[]{#l00264}[ 264]{.lineno}  std::ostream& os,
:::

::: {.line}
[]{#l00265}[ 265]{.lineno}  [const]{.keyword}
ServableStateMonitor::ServableStateAndTime& state\_and\_time) {
:::

::: {.line}
[]{#l00266}[ 266]{.lineno}  [return]{.keywordflow} os \<\<
state\_and\_time.DebugString();
:::

::: {.line}
[]{#l00267}[ 267]{.lineno} }
:::

::: {.line}
[]{#l00268}[ 268]{.lineno} 
:::

::: {.line}
[]{#l00269}[ 269]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00270}[ 270]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00271}[ 271]{.lineno} 
:::

::: {.line}
[]{#l00272}[ 272]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_SERVABLE\_STATE\_MONITOR\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1EventBus_html .ttc}
::: {.ttname}
[tensorflow::serving::EventBus](classtensorflow_1_1serving_1_1EventBus.html)
:::

::: {.ttdef}
**Definition:** event\_bus.h:63
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

::: {#aclasstensorflow_1_1serving_1_1ServableStateMonitor_html_a2afc57f0eb671a3c3342c7dd71a9d6a7 .ttc}
::: {.ttname}
[tensorflow::serving::ServableStateMonitor::GetBoundedLog](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a2afc57f0eb671a3c3342c7dd71a9d6a7)
:::

::: {.ttdeci}
BoundedLog GetBoundedLog() const TF\_LOCKS\_EXCLUDED(mu\_)
:::

::: {.ttdoc}
Returns the current bounded log of handled servable state events.
:::

::: {.ttdef}
**Definition:** servable\_state\_monitor.cc:218
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServableStateMonitor_html_a501ef561e30709fe17f10c913d34bb1e .ttc}
::: {.ttname}
[tensorflow::serving::ServableStateMonitor::GetVersionStates](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a501ef561e30709fe17f10c913d34bb1e)
:::

::: {.ttdeci}
VersionMap GetVersionStates(const string &servable\_name) const
TF\_LOCKS\_EXCLUDED(mu\_)
:::

::: {.ttdef}
**Definition:** servable\_state\_monitor.cc:160
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServableStateMonitor_html_a522166e0255c93e87a6d63c3d17e3f38 .ttc}
::: {.ttname}
[tensorflow::serving::ServableStateMonitor::GetLiveServableStates](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a522166e0255c93e87a6d63c3d17e3f38)
:::

::: {.ttdeci}
ServableMap GetLiveServableStates() const TF\_LOCKS\_EXCLUDED(mu\_)
:::

::: {.ttdef}
**Definition:** servable\_state\_monitor.cc:176
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServableStateMonitor_html_a6b64d18d981941012439766e57bd8d66 .ttc}
::: {.ttname}
[tensorflow::serving::ServableStateMonitor::ServableStateNotifierFn](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a6b64d18d981941012439766e57bd8d66)
:::

::: {.ttdeci}
std::function\< void(bool reached\_goal\_state, const std::map\<
ServableId, ServableState::ManagerState \> &states\_reached)\>
ServableStateNotifierFn
:::

::: {.ttdef}
**Definition:** servable\_state\_monitor.h:149
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServableStateMonitor_html_a8fa6dd1536bbb85a55b3e41c1d2577d1 .ttc}
::: {.ttname}
[tensorflow::serving::ServableStateMonitor::GetState](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a8fa6dd1536bbb85a55b3e41c1d2577d1)
:::

::: {.ttdeci}
absl::optional\< ServableState \> GetState(const ServableId
&servable\_id) const TF\_LOCKS\_EXCLUDED(mu\_)
:::

::: {.ttdef}
**Definition:** servable\_state\_monitor.cc:150
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServableStateMonitor_html_a8ff54ab2471885168dba0b1a05be7bea .ttc}
::: {.ttname}
[tensorflow::serving::ServableStateMonitor::GetStateAndTime](classtensorflow_1_1serving_1_1ServableStateMonitor.html#a8ff54ab2471885168dba0b1a05be7bea)
:::

::: {.ttdeci}
absl::optional\< ServableStateAndTime \> GetStateAndTime(const
ServableId &servable\_id) const TF\_LOCKS\_EXCLUDED(mu\_)
:::

::: {.ttdef}
**Definition:** servable\_state\_monitor.cc:145
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServableStateMonitor_html_aa9579ee04bf76fa627d65d9cbbb7ccb7 .ttc}
::: {.ttname}
[tensorflow::serving::ServableStateMonitor::WaitUntilServablesReachStateWithTimeout](classtensorflow_1_1serving_1_1ServableStateMonitor.html#aa9579ee04bf76fa627d65d9cbbb7ccb7)
:::

::: {.ttdeci}
bool WaitUntilServablesReachStateWithTimeout(const std::vector\<
ServableRequest \> &servables, ServableState::ManagerState goal\_state,
absl::Duration timeout, std::map\< ServableId,
ServableState::ManagerState \> \*states\_reached=nullptr)
TF\_LOCKS\_EXCLUDED(mu\_) TF\_MUST\_USE\_RESULT
:::

::: {.ttdef}
**Definition:** servable\_state\_monitor.cc:238
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServableStateMonitor_html_abc3c1c27b6b7c0e8ef9a42039ede74cc .ttc}
::: {.ttname}
[tensorflow::serving::ServableStateMonitor::GetAllServableStates](classtensorflow_1_1serving_1_1ServableStateMonitor.html#abc3c1c27b6b7c0e8ef9a42039ede74cc)
:::

::: {.ttdeci}
ServableMap GetAllServableStates() const TF\_LOCKS\_EXCLUDED(mu\_)
:::

::: {.ttdoc}
Returns the current states of all tracked versions of all servables.
:::

::: {.ttdef}
**Definition:** servable\_state\_monitor.cc:170
:::
:::

::: {#aclasstensorflow_1_1serving_1_1ServableStateMonitor_html_ae3ad2a50b7fa7b695885fe913b70b029 .ttc}
::: {.ttname}
[tensorflow::serving::ServableStateMonitor::ForgetUnloadedServableStates](classtensorflow_1_1serving_1_1ServableStateMonitor.html#ae3ad2a50b7fa7b695885fe913b70b029)
:::

::: {.ttdeci}
void ForgetUnloadedServableStates() TF\_LOCKS\_EXCLUDED(mu\_)
:::

::: {.ttdef}
**Definition:** servable\_state\_monitor.cc:182
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

::: {#astructtensorflow_1_1serving_1_1ServableStateMonitor_1_1Options_html .ttc}
::: {.ttname}
[tensorflow::serving::ServableStateMonitor::Options](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1Options.html)
:::

::: {.ttdef}
**Definition:** servable\_state\_monitor.h:73
:::
:::

::: {#astructtensorflow_1_1serving_1_1ServableStateMonitor_1_1Options_html_a65eadcb3e4a38f2b206df7dbedd9ed9b .ttc}
::: {.ttname}
[tensorflow::serving::ServableStateMonitor::Options::max\_count\_log\_events](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1Options.html#a65eadcb3e4a38f2b206df7dbedd9ed9b)
:::

::: {.ttdeci}
uint64\_t max\_count\_log\_events
:::

::: {.ttdef}
**Definition:** servable\_state\_monitor.h:78
:::
:::

::: {#astructtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime_html .ttc}
::: {.ttname}
[tensorflow::serving::ServableStateMonitor::ServableStateAndTime](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime.html)
:::

::: {.ttdef}
**Definition:** servable\_state\_monitor.h:49
:::
:::

::: {#astructtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime_html_a7730a4eb7f73739112fa5f51d1879387 .ttc}
::: {.ttname}
[tensorflow::serving::ServableStateMonitor::ServableStateAndTime::DebugString](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime.html#a7730a4eb7f73739112fa5f51d1879387)
:::

::: {.ttdeci}
string DebugString() const
:::

::: {.ttdef}
**Definition:** servable\_state\_monitor.cc:106
:::
:::

::: {#astructtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime_html_a80581c8a1a09ea03377c3988a25c274d .ttc}
::: {.ttname}
[tensorflow::serving::ServableStateMonitor::ServableStateAndTime::state](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime.html#a80581c8a1a09ea03377c3988a25c274d)
:::

::: {.ttdeci}
ServableState state
:::

::: {.ttdoc}
State of the servable.
:::

::: {.ttdef}
**Definition:** servable\_state\_monitor.h:56
:::
:::

::: {#astructtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime_html_ab32413dcaaebc9df926c4ed28fa1fb4d .ttc}
::: {.ttname}
[tensorflow::serving::ServableStateMonitor::ServableStateAndTime::event\_time\_micros](structtensorflow_1_1serving_1_1ServableStateMonitor_1_1ServableStateAndTime.html#ab32413dcaaebc9df926c4ed28fa1fb4d)
:::

::: {.ttdeci}
uint64\_t event\_time\_micros
:::

::: {.ttdoc}
Time at which servable state event was published.
:::

::: {.ttdef}
**Definition:** servable\_state\_monitor.h:59
:::
:::

::: {#astructtensorflow_1_1serving_1_1ServableState_html .ttc}
::: {.ttname}
[tensorflow::serving::ServableState](structtensorflow_1_1serving_1_1ServableState.html)
:::

::: {.ttdef}
**Definition:** servable\_state.h:34
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

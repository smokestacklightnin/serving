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
:::
:::

::: {.header}
::: {.headertitle}
::: {.title}
event\_bus.h
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
[]{#l00016}[ 16]{.lineno} [// TODO(b/25725560): Consider having a thread
pool for invoking callbacks.]{.comment}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} 
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} [\#ifndef
TENSORFLOW\_SERVING\_UTIL\_EVENT\_BUS\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#define
TENSORFLOW\_SERVING\_UTIL\_EVENT\_BUS\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} 
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<algorithm\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<functional\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include \<type\_traits\>]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} 
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow/core/platform/env.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow/core/platform/mutex.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow/core/platform/thread\_annotations.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include
\"tensorflow/core/platform/types.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} 
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} 
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} [template]{.keyword} \<[typename]{.keyword}
E\>
:::

::: {.line}
[]{#l00063}[
[63](classtensorflow_1_1serving_1_1EventBus.html){.line}]{.lineno} [class
]{.keyword}[EventBus](classtensorflow_1_1serving_1_1EventBus.html){.code}
: [public]{.keyword} std::enable\_shared\_from\_this\<EventBus\<E\>\> {
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} 
static\_assert(std::is\_move\_assignable\<E\>::value, [\"E must be
moveable\"]{.stringliteral});
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} 
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00074}[
[74](classtensorflow_1_1serving_1_1EventBus_1_1Subscription.html){.line}]{.lineno} 
[class
]{.keyword}[Subscription](classtensorflow_1_1serving_1_1EventBus_1_1Subscription.html){.code}
{
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00077}[
[77](classtensorflow_1_1serving_1_1EventBus_1_1Subscription.html#a81795ea8fef03dd4240a753ccd532f7c){.line}]{.lineno} 
[\~Subscription](classtensorflow_1_1serving_1_1EventBus_1_1Subscription.html#a81795ea8fef03dd4240a753ccd532f7c){.code}();
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} 
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [friend]{.keyword} [class
]{.keyword}[EventBus](classtensorflow_1_1serving_1_1EventBus.html){.code};
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} 
:::

::: {.line}
[]{#l00082}[ 82]{.lineno}  [explicit]{.keyword}
Subscription(std::weak\_ptr\<[EventBus\<E\>](classtensorflow_1_1serving_1_1EventBus.html){.code}\>
bus);
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} 
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [// Weak pointer to the EventBus that
originated this Subscription.]{.comment}
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  std::weak\_ptr\<EventBus\<E\>\> bus\_;
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} 
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN(Subscription);
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  };
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} 
:::

::: {.line}
[]{#l00090}[
[90](structtensorflow_1_1serving_1_1EventBus_1_1Options.html){.line}]{.lineno} 
[struct
]{.keyword}[Options](structtensorflow_1_1serving_1_1EventBus_1_1Options.html){.code}
{
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  [// The environment to use for
time.]{.comment}
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  Env\* env = Env::Default();
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  };
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} 
:::

::: {.line}
[]{#l00098}[
[98](classtensorflow_1_1serving_1_1EventBus.html#abdf7f12c47dab911dfa5adbc8c3031c5){.line}]{.lineno} 
[static]{.keyword} std::shared\_ptr\<EventBus\>
[CreateEventBus](classtensorflow_1_1serving_1_1EventBus.html#abdf7f12c47dab911dfa5adbc8c3031c5){.code}([const]{.keyword}
Options& options = {});
:::

::: {.line}
[]{#l00099}[ 99]{.lineno} 
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} 
\~[EventBus](classtensorflow_1_1serving_1_1EventBus.html){.code}() =
[default]{.keywordflow};
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} 
:::

::: {.line}
[]{#l00103}[
[103](structtensorflow_1_1serving_1_1EventBus_1_1EventAndTime.html){.line}]{.lineno} 
[struct
]{.keyword}[EventAndTime](structtensorflow_1_1serving_1_1EventBus_1_1EventAndTime.html){.code}
{
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  [const]{.keyword} E& event;
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  uint64\_t event\_time\_micros;
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  };
:::

::: {.line}
[]{#l00107}[ 107]{.lineno} 
:::

::: {.line}
[]{#l00115}[
[115](classtensorflow_1_1serving_1_1EventBus.html#a5d602ec2a5a845d27799970475af24b9){.line}]{.lineno} 
[using]{.keyword}
[Callback](classtensorflow_1_1serving_1_1EventBus.html#a5d602ec2a5a845d27799970475af24b9){.code}
= std::function\<void([const]{.keyword}
[EventAndTime](structtensorflow_1_1serving_1_1EventBus_1_1EventAndTime.html){.code}&)\>;
:::

::: {.line}
[]{#l00116}[ 116]{.lineno} 
:::

::: {.line}
[]{#l00130}[
[130](classtensorflow_1_1serving_1_1EventBus.html#a39fe8c3ad82da890bdc4455dc05a43fb){.line}]{.lineno} 
std::unique\_ptr\<Subscription\>
[Subscribe](classtensorflow_1_1serving_1_1EventBus.html#a39fe8c3ad82da890bdc4455dc05a43fb){.code}([const]{.keyword}
[Callback](classtensorflow_1_1serving_1_1EventBus.html#a5d602ec2a5a845d27799970475af24b9){.code}&
callback)
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  TF\_LOCKS\_EXCLUDED(mutex\_)
TF\_MUST\_USE\_RESULT;
:::

::: {.line}
[]{#l00132}[ 132]{.lineno} 
:::

::: {.line}
[]{#l00134}[
[134](classtensorflow_1_1serving_1_1EventBus.html#a29a951f5d7d4e6f7a85bf8d3b4c463f8){.line}]{.lineno} 
[void]{.keywordtype}
[Publish](classtensorflow_1_1serving_1_1EventBus.html#a29a951f5d7d4e6f7a85bf8d3b4c463f8){.code}([const]{.keyword}
E& event) TF\_LOCKS\_EXCLUDED(mutex\_);
:::

::: {.line}
[]{#l00135}[ 135]{.lineno} 
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  [explicit]{.keyword}
[EventBus](classtensorflow_1_1serving_1_1EventBus.html){.code}([const]{.keyword}
Options& options);
:::

::: {.line}
[]{#l00138}[ 138]{.lineno} 
:::

::: {.line}
[]{#l00139}[ 139]{.lineno}  [// Unsubscribes the specified subscriber.
Called only by Subscription.]{.comment}
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  [void]{.keywordtype}
Unsubscribe([const]{.keyword} Subscription\* subscription)
TF\_LOCKS\_EXCLUDED(mutex\_);
:::

::: {.line}
[]{#l00141}[ 141]{.lineno} 
:::

::: {.line}
[]{#l00142}[ 142]{.lineno}  [// All of the information needed for a
single subscription, both for]{.comment}
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  [// publishing events and
unsubscribing.]{.comment}
:::

::: {.line}
[]{#l00144}[ 144]{.lineno}  [struct ]{.keyword}SubscriptionTuple {
:::

::: {.line}
[]{#l00145}[ 145]{.lineno}  [// Uniquely identifies the
Subscription.]{.comment}
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  Subscription\* subscription;
:::

::: {.line}
[]{#l00147}[ 147]{.lineno} 
[Callback](classtensorflow_1_1serving_1_1EventBus.html#a5d602ec2a5a845d27799970475af24b9){.code}
callback;
:::

::: {.line}
[]{#l00148}[ 148]{.lineno}  };
:::

::: {.line}
[]{#l00149}[ 149]{.lineno} 
:::

::: {.line}
[]{#l00150}[ 150]{.lineno}  [// Mutex held for all operations on an
EventBus including all publishing and]{.comment}
:::

::: {.line}
[]{#l00151}[ 151]{.lineno}  [// subscription operations.]{.comment}
:::

::: {.line}
[]{#l00152}[ 152]{.lineno}  [mutable]{.keyword} mutex mutex\_;
:::

::: {.line}
[]{#l00153}[ 153]{.lineno} 
:::

::: {.line}
[]{#l00154}[ 154]{.lineno}  [// All subscriptions that the EventBus is
aware of. Note that this is not]{.comment}
:::

::: {.line}
[]{#l00155}[ 155]{.lineno}  [// optimized for high scale in the number
of subscribers.]{.comment}
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  std::vector\<SubscriptionTuple\>
subscriptions\_ TF\_GUARDED\_BY(mutex\_);
:::

::: {.line}
[]{#l00157}[ 157]{.lineno} 
:::

::: {.line}
[]{#l00158}[ 158]{.lineno}  [const]{.keyword} Options options\_;
:::

::: {.line}
[]{#l00159}[ 159]{.lineno} 
:::

::: {.line}
[]{#l00160}[ 160]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([EventBus](classtensorflow_1_1serving_1_1EventBus.html){.code});
:::

::: {.line}
[]{#l00161}[ 161]{.lineno} };
:::

::: {.line}
[]{#l00162}[ 162]{.lineno} 
:::

::: {.line}
[]{#l00163}[ 163]{.lineno} [// \-\-- Implementation details below
\-\--]{.comment}
:::

::: {.line}
[]{#l00164}[ 164]{.lineno} 
:::

::: {.line}
[]{#l00165}[ 165]{.lineno} [template]{.keyword} \<[typename]{.keyword}
E\>
:::

::: {.line}
[]{#l00166}[
166]{.lineno} EventBus\<E\>::Subscription::Subscription(std::weak\_ptr\<EventBus\<E\>\>
bus)
:::

::: {.line}
[]{#l00167}[ 167]{.lineno}  : bus\_(std::move(bus)) {}
:::

::: {.line}
[]{#l00168}[ 168]{.lineno} 
:::

::: {.line}
[]{#l00169}[ 169]{.lineno} [template]{.keyword} \<[typename]{.keyword}
E\>
:::

::: {.line}
[]{#l00170}[
[170](classtensorflow_1_1serving_1_1EventBus_1_1Subscription.html#a81795ea8fef03dd4240a753ccd532f7c){.line}]{.lineno} [EventBus\<E\>::Subscription::\~Subscription](classtensorflow_1_1serving_1_1EventBus.html){.code}()
{
:::

::: {.line}
[]{#l00171}[ 171]{.lineno}  std::shared\_ptr\<EventBus\<E\>\>
temp\_shared\_ptr = bus\_.lock();
:::

::: {.line}
[]{#l00172}[ 172]{.lineno}  [if]{.keywordflow} (temp\_shared\_ptr !=
[nullptr]{.keyword}) {
:::

::: {.line}
[]{#l00173}[ 173]{.lineno} 
temp\_shared\_ptr-\>Unsubscribe([this]{.keyword});
:::

::: {.line}
[]{#l00174}[ 174]{.lineno}  }
:::

::: {.line}
[]{#l00175}[ 175]{.lineno} }
:::

::: {.line}
[]{#l00176}[ 176]{.lineno} 
:::

::: {.line}
[]{#l00177}[ 177]{.lineno} [template]{.keyword} \<[typename]{.keyword}
E\>
:::

::: {.line}
[]{#l00178}[
[178](classtensorflow_1_1serving_1_1EventBus.html#a39fe8c3ad82da890bdc4455dc05a43fb){.line}]{.lineno} std::unique\_ptr\<typename
EventBus\<E\>::Subscription\>
[EventBus\<E\>::Subscribe](classtensorflow_1_1serving_1_1EventBus.html){.code}(
:::

::: {.line}
[]{#l00179}[ 179]{.lineno}  [const]{.keyword}
[Callback](classtensorflow_1_1serving_1_1EventBus.html#a5d602ec2a5a845d27799970475af24b9){.code}&
callback) {
:::

::: {.line}
[]{#l00180}[ 180]{.lineno}  mutex\_lock lock(mutex\_);
:::

::: {.line}
[]{#l00181}[ 181]{.lineno}  std::unique\_ptr\<Subscription\>
subscription(
:::

::: {.line}
[]{#l00182}[ 182]{.lineno}  [new]{.keyword}
[Subscription](classtensorflow_1_1serving_1_1EventBus_1_1Subscription.html){.code}(this-\>shared\_from\_this()));
:::

::: {.line}
[]{#l00183}[ 183]{.lineno} 
subscriptions\_.push\_back({subscription.get(), callback});
:::

::: {.line}
[]{#l00184}[ 184]{.lineno}  [return]{.keywordflow} subscription;
:::

::: {.line}
[]{#l00185}[ 185]{.lineno} }
:::

::: {.line}
[]{#l00186}[ 186]{.lineno} 
:::

::: {.line}
[]{#l00187}[ 187]{.lineno} [template]{.keyword} \<[typename]{.keyword}
E\>
:::

::: {.line}
[]{#l00188}[
188]{.lineno} [EventBus\<E\>::EventBus](classtensorflow_1_1serving_1_1EventBus.html){.code}([const]{.keyword}
Options& options) : options\_(options) {}
:::

::: {.line}
[]{#l00189}[ 189]{.lineno} 
:::

::: {.line}
[]{#l00190}[ 190]{.lineno} [template]{.keyword} \<[typename]{.keyword}
E\>
:::

::: {.line}
[]{#l00191}[
[191](classtensorflow_1_1serving_1_1EventBus.html#abdf7f12c47dab911dfa5adbc8c3031c5){.line}]{.lineno} std::shared\_ptr\<EventBus\<E\>\>
[EventBus\<E\>::CreateEventBus](classtensorflow_1_1serving_1_1EventBus.html#abdf7f12c47dab911dfa5adbc8c3031c5){.code}(
:::

::: {.line}
[]{#l00192}[ 192]{.lineno}  [const]{.keyword}
[Options](structtensorflow_1_1serving_1_1EventBus_1_1Options.html){.code}&
options) {
:::

::: {.line}
[]{#l00193}[ 193]{.lineno}  [return]{.keywordflow}
std::shared\_ptr\<EventBus\<E\>\>([new]{.keyword}
[EventBus\<E\>](classtensorflow_1_1serving_1_1EventBus.html){.code}(options));
:::

::: {.line}
[]{#l00194}[ 194]{.lineno} }
:::

::: {.line}
[]{#l00195}[ 195]{.lineno} 
:::

::: {.line}
[]{#l00196}[ 196]{.lineno} [template]{.keyword} \<[typename]{.keyword}
E\>
:::

::: {.line}
[]{#l00197}[ 197]{.lineno} [void]{.keywordtype}
[EventBus\<E\>::Unsubscribe](classtensorflow_1_1serving_1_1EventBus.html){.code}(
:::

::: {.line}
[]{#l00198}[ 198]{.lineno}  [const]{.keyword} [typename]{.keyword}
[EventBus\<E\>::Subscription](classtensorflow_1_1serving_1_1EventBus_1_1Subscription.html){.code}\*
subscription) {
:::

::: {.line}
[]{#l00199}[ 199]{.lineno}  mutex\_lock lock(mutex\_);
:::

::: {.line}
[]{#l00200}[ 200]{.lineno}  subscriptions\_.erase(
:::

::: {.line}
[]{#l00201}[ 201]{.lineno}  std::remove\_if(subscriptions\_.begin(),
subscriptions\_.end(),
:::

::: {.line}
[]{#l00202}[ 202]{.lineno}  \[subscription\](SubscriptionTuple s) {
:::

::: {.line}
[]{#l00203}[ 203]{.lineno}  return s.subscription == subscription;
:::

::: {.line}
[]{#l00204}[ 204]{.lineno}  }),
:::

::: {.line}
[]{#l00205}[ 205]{.lineno}  subscriptions\_.end());
:::

::: {.line}
[]{#l00206}[ 206]{.lineno} }
:::

::: {.line}
[]{#l00207}[ 207]{.lineno} 
:::

::: {.line}
[]{#l00208}[ 208]{.lineno} [template]{.keyword} \<[typename]{.keyword}
E\>
:::

::: {.line}
[]{#l00209}[
[209](classtensorflow_1_1serving_1_1EventBus.html#a29a951f5d7d4e6f7a85bf8d3b4c463f8){.line}]{.lineno} [void]{.keywordtype}
[EventBus\<E\>::Publish](classtensorflow_1_1serving_1_1EventBus.html#a29a951f5d7d4e6f7a85bf8d3b4c463f8){.code}([const]{.keyword}
E& event) {
:::

::: {.line}
[]{#l00210}[ 210]{.lineno}  mutex\_lock lock(mutex\_);
:::

::: {.line}
[]{#l00211}[ 211]{.lineno}  [const]{.keyword} uint64\_t event\_time =
options\_.env-\>NowMicros();
:::

::: {.line}
[]{#l00212}[ 212]{.lineno}  [const]{.keyword}
[EventAndTime](structtensorflow_1_1serving_1_1EventBus_1_1EventAndTime.html){.code}
event\_and\_time = {event, event\_time};
:::

::: {.line}
[]{#l00213}[ 213]{.lineno}  [for]{.keywordflow} ([const]{.keyword}
SubscriptionTuple& subscription : subscriptions\_) {
:::

::: {.line}
[]{#l00214}[ 214]{.lineno}  subscription.callback(event\_and\_time);
:::

::: {.line}
[]{#l00215}[ 215]{.lineno}  }
:::

::: {.line}
[]{#l00216}[ 216]{.lineno} }
:::

::: {.line}
[]{#l00217}[ 217]{.lineno} 
:::

::: {.line}
[]{#l00218}[ 218]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00219}[ 219]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00220}[ 220]{.lineno} 
:::

::: {.line}
[]{#l00221}[ 221]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_UTIL\_EVENT\_BUS\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1EventBus_1_1Subscription_html .ttc}
::: {.ttname}
[tensorflow::serving::EventBus::Subscription](classtensorflow_1_1serving_1_1EventBus_1_1Subscription.html)
:::

::: {.ttdef}
**Definition:** event\_bus.h:74
:::
:::

::: {#aclasstensorflow_1_1serving_1_1EventBus_1_1Subscription_html_a81795ea8fef03dd4240a753ccd532f7c .ttc}
::: {.ttname}
[tensorflow::serving::EventBus::Subscription::\~Subscription](classtensorflow_1_1serving_1_1EventBus_1_1Subscription.html#a81795ea8fef03dd4240a753ccd532f7c)
:::

::: {.ttdeci}
\~Subscription()
:::

::: {.ttdoc}
Unsubscribes the subscriber.
:::

::: {.ttdef}
**Definition:** event\_bus.h:170
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

::: {#aclasstensorflow_1_1serving_1_1EventBus_html_a29a951f5d7d4e6f7a85bf8d3b4c463f8 .ttc}
::: {.ttname}
[tensorflow::serving::EventBus::Publish](classtensorflow_1_1serving_1_1EventBus.html#a29a951f5d7d4e6f7a85bf8d3b4c463f8)
:::

::: {.ttdeci}
void Publish(const E &event) TF\_LOCKS\_EXCLUDED(mutex\_)
:::

::: {.ttdoc}
Publishes an event to all subscribers.
:::

::: {.ttdef}
**Definition:** event\_bus.h:209
:::
:::

::: {#aclasstensorflow_1_1serving_1_1EventBus_html_a39fe8c3ad82da890bdc4455dc05a43fb .ttc}
::: {.ttname}
[tensorflow::serving::EventBus::Subscribe](classtensorflow_1_1serving_1_1EventBus.html#a39fe8c3ad82da890bdc4455dc05a43fb)
:::

::: {.ttdeci}
std::unique\_ptr\< Subscription \> Subscribe(const Callback &callback)
TF\_LOCKS\_EXCLUDED(mutex\_) TF\_MUST\_USE\_RESULT
:::

::: {.ttdef}
**Definition:** event\_bus.h:178
:::
:::

::: {#aclasstensorflow_1_1serving_1_1EventBus_html_a5d602ec2a5a845d27799970475af24b9 .ttc}
::: {.ttname}
[tensorflow::serving::EventBus::Callback](classtensorflow_1_1serving_1_1EventBus.html#a5d602ec2a5a845d27799970475af24b9)
:::

::: {.ttdeci}
std::function\< void(const EventAndTime &)\> Callback
:::

::: {.ttdef}
**Definition:** event\_bus.h:115
:::
:::

::: {#aclasstensorflow_1_1serving_1_1EventBus_html_abdf7f12c47dab911dfa5adbc8c3031c5 .ttc}
::: {.ttname}
[tensorflow::serving::EventBus::CreateEventBus](classtensorflow_1_1serving_1_1EventBus.html#abdf7f12c47dab911dfa5adbc8c3031c5)
:::

::: {.ttdeci}
static std::shared\_ptr\< EventBus \> CreateEventBus(const Options
&options={})
:::

::: {.ttdef}
**Definition:** event\_bus.h:191
:::
:::

::: {#astructtensorflow_1_1serving_1_1EventBus_1_1EventAndTime_html .ttc}
::: {.ttname}
[tensorflow::serving::EventBus::EventAndTime](structtensorflow_1_1serving_1_1EventBus_1_1EventAndTime.html)
:::

::: {.ttdoc}
Event and the publish time associated with it.
:::

::: {.ttdef}
**Definition:** event\_bus.h:103
:::
:::

::: {#astructtensorflow_1_1serving_1_1EventBus_1_1Options_html .ttc}
::: {.ttname}
[tensorflow::serving::EventBus::Options](structtensorflow_1_1serving_1_1EventBus_1_1Options.html)
:::

::: {.ttdef}
**Definition:** event\_bus.h:90
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

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
caching\_manager.h
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
TENSORFLOW\_SERVING\_CORE\_CACHING\_MANAGER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_CACHING\_MANAGER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include \<map\>]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include \<memory\>]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include \<string\>]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include \<vector\>]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} 
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow\_serving/core/basic\_manager.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow\_serving/core/manager.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/core/source\_adapter.h\"]{.preprocessor}
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
[]{#l00031}[ 31]{.lineno} [namespace ]{.keyword}test\_util {
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [class ]{.keyword}CachingManagerTestAccess;
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} } [// namespace test\_util]{.comment}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} 
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [// TODO(b/25449742): Add support for
evictions of loaded servables from the]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [// caching-manager.]{.comment}
:::

::: {.line}
[]{#l00045}[
[45](classtensorflow_1_1serving_1_1CachingManager.html){.line}]{.lineno} [class
]{.keyword}[CachingManager](classtensorflow_1_1serving_1_1CachingManager.html){.code}
: [public]{.keyword}
[Manager](classtensorflow_1_1serving_1_1Manager.html){.code} {
:::

::: {.line}
[]{#l00046}[ 46]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00049}[
[49](structtensorflow_1_1serving_1_1CachingManager_1_1Options.html){.line}]{.lineno} 
[struct
]{.keyword}[Options](structtensorflow_1_1serving_1_1CachingManager_1_1Options.html){.code}
{
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [// The resource tracker to use while
managing servable resources. Optional.]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [// If left as nullptr, we do not validate
servable resource usage.]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  std::unique\_ptr\<ResourceTracker\>
resource\_tracker;
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} 
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  [// The number of threads in the thread-pool
used to load servables.]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  [// If set as 0, we don\'t use a thread-pool,
and LoadServable() blocks.]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  uint32 num\_load\_threads = 0;
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} 
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [// The number of threads in the thread-pool
used to unload servables.]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [// If set as 0, we don\'t use a
thread-pool.]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  uint32 num\_unload\_threads = 0;
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} 
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  [// EventBus to publish servable state
changes. This is optional, if unset,]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [// we don\'t publish.]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} 
[EventBus\<ServableState\>](classtensorflow_1_1serving_1_1EventBus.html){.code}\*
servable\_event\_bus = [nullptr]{.keyword};
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [// Maximum number of times we retry loading
a servable, after the first]{.comment}
:::

::: {.line}
[]{#l00069}[ 69]{.lineno}  [// failure, before we give up. If set to 0,
a load is attempted only once.]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno}  uint32 max\_num\_load\_retries = 5;
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} 
:::

::: {.line}
[]{#l00072}[ 72]{.lineno}  [// The interval, in microseconds, between
each servable load retry. If set]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [// negative, we don\'t wait.]{.comment}
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  [// Default: 1 minute.]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  int64\_t load\_retry\_interval\_micros = 1LL
\* 60 \* 1000 \* 1000;
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} 
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  [// The environment to use for starting
threads in the thread-pool.]{.comment}
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  Env\* env = Env::Default();
:::

::: {.line}
[]{#l00079}[ 79]{.lineno}  };
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} 
:::

::: {.line}
[]{#l00083}[
[83](classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory.html){.line}]{.lineno} 
[class
]{.keyword}[LoaderFactory](classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory.html){.code}
{
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  [virtual]{.keyword}
\~[LoaderFactory](classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory.html){.code}()
= [default]{.keywordflow};
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} 
:::

::: {.line}
[]{#l00090}[
[90](classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory.html#ab95a61ff7c67b25e96594631207045a2){.line}]{.lineno} 
[virtual]{.keyword}
[ServableData\<std::unique\_ptr\<Loader\>](classtensorflow_1_1serving_1_1ServableData.html){.code}\>
[CreateLoader](classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory.html#ab95a61ff7c67b25e96594631207045a2){.code}(
:::

::: {.line}
[]{#l00091}[ 91]{.lineno}  [const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
servable\_id) = 0;
:::

::: {.line}
[]{#l00092}[ 92]{.lineno} 
:::

::: {.line}
[]{#l00095}[
[95](classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory.html#ae3b86ce052eeee59a53ef0ab58080729){.line}]{.lineno} 
[virtual]{.keyword} int64\_t
[GetServableVersion](classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory.html#ae3b86ce052eeee59a53ef0ab58080729){.code}(
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  [const]{.keyword} [string]{.keywordtype}&
servable\_name,
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  ServableRequest::AutoVersionPolicy policy)
[const]{.keyword} = 0;
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  };
:::

::: {.line}
[]{#l00099}[ 99]{.lineno} 
:::

::: {.line}
[]{#l00100}[ 100]{.lineno}  [static]{.keyword} Status
Create([Options](structtensorflow_1_1serving_1_1CachingManager_1_1Options.html){.code}
options,
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  std::unique\_ptr\<LoaderFactory\>
loader\_factory,
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  std::unique\_ptr\<CachingManager\>\*
caching\_manager);
:::

::: {.line}
[]{#l00103}[ 103]{.lineno} 
:::

::: {.line}
[]{#l00104}[ 104]{.lineno} 
\~[CachingManager](classtensorflow_1_1serving_1_1CachingManager.html){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00105}[ 105]{.lineno} 
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  std::map\<ServableId,
std::unique\_ptr\<UntypedServableHandle\>\>
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  GetAvailableUntypedServableHandles() [const
override]{.keyword};
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} 
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  std::vector\<ServableId\>
[ListAvailableServableIds](classtensorflow_1_1serving_1_1CachingManager.html#af7ec61e19bcd1ac85a4c97c32e977ffe){.code}()
[const override]{.keyword};
:::

::: {.line}
[]{#l00110}[ 110]{.lineno} 
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  [friend]{.keyword} [class
]{.keyword}[test\_util::CachingManagerTestAccess](classtensorflow_1_1serving_1_1test__util_1_1CachingManagerTestAccess.html){.code};
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} 
:::

::: {.line}
[]{#l00114}[ 114]{.lineno} 
[CachingManager](classtensorflow_1_1serving_1_1CachingManager.html){.code}(std::unique\_ptr\<LoaderFactory\>
loader\_factory,
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  std::unique\_ptr\<BasicManager\>
basic\_manager);
:::

::: {.line}
[]{#l00116}[ 116]{.lineno} 
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  [// Returns the untyped handle for the
servable request.]{.comment}
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  [// Semantics related to a ServableRequest
for \"latest\":]{.comment}
:::

::: {.line}
[]{#l00120}[ 120]{.lineno}  [// The manager forwards the \"latest\"
request to the loader-factory, which]{.comment}
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  [// emits its notion of the \"latest\"
version. This is then managed and loaded]{.comment}
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  [// by the manager, if not already
available, and a handle to it is returned.]{.comment}
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  Status GetUntypedServableHandle(
:::

::: {.line}
[]{#l00124}[ 124]{.lineno}  [const]{.keyword}
[ServableRequest](structtensorflow_1_1serving_1_1ServableRequest.html){.code}&
request,
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  std::unique\_ptr\<UntypedServableHandle\>\*
handle) [override]{.keyword};
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} 
:::

::: {.line}
[]{#l00127}[ 127]{.lineno}  [// Returns the untyped handle for a
servable-id.]{.comment}
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  Status GetUntypedServableHandleForId(
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  [const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
servable\_id,
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  std::unique\_ptr\<UntypedServableHandle\>\*
handle);
:::

::: {.line}
[]{#l00131}[ 131]{.lineno} 
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  [// Transfer the given servable to
\'basic\_manager\_\', and ask it to load it. For]{.comment}
:::

::: {.line}
[]{#l00133}[ 133]{.lineno}  [// multiple concurrent requests for the
same servable-id, enforces that]{.comment}
:::

::: {.line}
[]{#l00134}[ 134]{.lineno}  [// exactly one thread performs the load
operation using the wrapped]{.comment}
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  [// basic-manager. All other requests block
until the load completes and then]{.comment}
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  [// trivially succeed.]{.comment}
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  Status
LoadServable([ServableData](classtensorflow_1_1serving_1_1ServableData.html){.code}\<std::unique\_ptr\<Loader\>\>
loader\_data)
:::

::: {.line}
[]{#l00138}[ 138]{.lineno}  TF\_LOCKS\_EXCLUDED(load\_mutex\_map\_mu\_);
:::

::: {.line}
[]{#l00139}[ 139]{.lineno} 
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  [// Returns the size of the
load\_mutex\_map\_.]{.comment}
:::

::: {.line}
[]{#l00141}[ 141]{.lineno}  int64\_t GetLoadMutexMapSize() const
TF\_LOCKS\_EXCLUDED(load\_mutex\_map\_mu\_);
:::

::: {.line}
[]{#l00142}[ 142]{.lineno} 
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  [// Erases the entry from the map
corresponding to the servable-id if there is]{.comment}
:::

::: {.line}
[]{#l00144}[ 144]{.lineno}  [// only one remaining reference to the
mutex.]{.comment}
:::

::: {.line}
[]{#l00145}[ 145]{.lineno}  [void]{.keywordtype}
MaybeEraseLoadMutexMapEntry(const
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
servable\_id);
:::

::: {.line}
[]{#l00146}[ 146]{.lineno} 
:::

::: {.line}
[]{#l00147}[ 147]{.lineno} 
std::unique\_ptr\<[LoaderFactory](classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory.html){.code}\>
loader\_factory\_;
:::

::: {.line}
[]{#l00148}[ 148]{.lineno} 
:::

::: {.line}
[]{#l00149}[ 149]{.lineno} 
std::unique\_ptr\<[BasicManager](classtensorflow_1_1serving_1_1BasicManager.html){.code}\>
basic\_manager\_;
:::

::: {.line}
[]{#l00150}[ 150]{.lineno} 
:::

::: {.line}
[]{#l00151}[ 151]{.lineno}  [// Used to protect access to the
load\_mutex\_map\_.]{.comment}
:::

::: {.line}
[]{#l00152}[ 152]{.lineno}  mutable mutex load\_mutex\_map\_mu\_;
:::

::: {.line}
[]{#l00153}[ 153]{.lineno} 
:::

::: {.line}
[]{#l00154}[ 154]{.lineno}  [// Map of servable-id to a mutex, which is
required to synchronize calls to]{.comment}
:::

::: {.line}
[]{#l00155}[ 155]{.lineno}  [// load the servable using the wrapped
basic-manager. The value in the map is]{.comment}
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  [// a shared\_ptr to allow for reference
counting and consequent garbage]{.comment}
:::

::: {.line}
[]{#l00157}[ 157]{.lineno}  [// collection.]{.comment}
:::

::: {.line}
[]{#l00158}[ 158]{.lineno} 
std::map\<[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code},
std::shared\_ptr\<mutex\>\> load\_mutex\_map\_
:::

::: {.line}
[]{#l00159}[ 159]{.lineno}  TF\_GUARDED\_BY(load\_mutex\_map\_mu\_);
:::

::: {.line}
[]{#l00160}[ 160]{.lineno} 
:::

::: {.line}
[]{#l00161}[ 161]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([CachingManager](classtensorflow_1_1serving_1_1CachingManager.html){.code});
:::

::: {.line}
[]{#l00162}[ 162]{.lineno} };
:::

::: {.line}
[]{#l00163}[ 163]{.lineno} 
:::

::: {.line}
[]{#l00167}[
[167](classtensorflow_1_1serving_1_1PathPrefixLoaderFactory.html){.line}]{.lineno} class
[PathPrefixLoaderFactory](classtensorflow_1_1serving_1_1PathPrefixLoaderFactory.html){.code}
: public
[CachingManager](classtensorflow_1_1serving_1_1CachingManager.html){.code}::LoaderFactory
{
:::

::: {.line}
[]{#l00168}[ 168]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00169}[ 169]{.lineno} 
[PathPrefixLoaderFactory](classtensorflow_1_1serving_1_1PathPrefixLoaderFactory.html){.code}([const]{.keyword}
[string]{.keywordtype}& path\_prefix,
:::

::: {.line}
[]{#l00170}[ 170]{.lineno}  std::unique\_ptr\<StoragePathSourceAdapter\>
adapter);
:::

::: {.line}
[]{#l00171}[ 171]{.lineno} 
\~[PathPrefixLoaderFactory](classtensorflow_1_1serving_1_1PathPrefixLoaderFactory.html){.code}()
[override]{.keyword} = [default]{.keywordflow};
:::

::: {.line}
[]{#l00172}[ 172]{.lineno} 
:::

::: {.line}
[]{#l00173}[ 173]{.lineno} 
[ServableData\<std::unique\_ptr\<Loader\>](classtensorflow_1_1serving_1_1ServableData.html){.code}\>
CreateLoader(
:::

::: {.line}
[]{#l00174}[ 174]{.lineno}  [const]{.keyword}
[ServableId](structtensorflow_1_1serving_1_1ServableId.html){.code}&
[id]{.keywordtype}) [override]{.keyword};
:::

::: {.line}
[]{#l00175}[ 175]{.lineno} 
:::

::: {.line}
[]{#l00176}[ 176]{.lineno}  int64\_t GetServableVersion(
:::

::: {.line}
[]{#l00177}[ 177]{.lineno}  [const]{.keyword} [string]{.keywordtype}&
servable\_name,
:::

::: {.line}
[]{#l00178}[ 178]{.lineno}  ServableRequest::AutoVersionPolicy policy)
[const override]{.keyword};
:::

::: {.line}
[]{#l00179}[ 179]{.lineno} 
:::

::: {.line}
[]{#l00180}[ 180]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00181}[ 181]{.lineno}  [// The prefix of the path to the
servables.]{.comment}
:::

::: {.line}
[]{#l00182}[ 182]{.lineno}  [const]{.keyword} [string]{.keywordtype}
path\_prefix\_;
:::

::: {.line}
[]{#l00183}[ 183]{.lineno} 
:::

::: {.line}
[]{#l00184}[ 184]{.lineno}  [// An adapter for creating a loader from a
given path.]{.comment}
:::

::: {.line}
[]{#l00185}[ 185]{.lineno}  [const]{.keyword}
std::unique\_ptr\<StoragePathSourceAdapter\> adapter\_;
:::

::: {.line}
[]{#l00186}[ 186]{.lineno} 
:::

::: {.line}
[]{#l00187}[ 187]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([PathPrefixLoaderFactory](classtensorflow_1_1serving_1_1PathPrefixLoaderFactory.html){.code});
:::

::: {.line}
[]{#l00188}[ 188]{.lineno} };
:::

::: {.line}
[]{#l00189}[ 189]{.lineno} 
:::

::: {.line}
[]{#l00190}[ 190]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00191}[ 191]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00192}[ 192]{.lineno} 
:::

::: {.line}
[]{#l00193}[ 193]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_CACHING\_MANAGER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1BasicManager_html .ttc}
::: {.ttname}
[tensorflow::serving::BasicManager](classtensorflow_1_1serving_1_1BasicManager.html)
:::

::: {.ttdef}
**Definition:** basic\_manager.h:106
:::
:::

::: {#aclasstensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory_html .ttc}
::: {.ttname}
[tensorflow::serving::CachingManager::LoaderFactory](classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory.html)
:::

::: {.ttdef}
**Definition:** caching\_manager.h:83
:::
:::

::: {#aclasstensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory_html_ab95a61ff7c67b25e96594631207045a2 .ttc}
::: {.ttname}
[tensorflow::serving::CachingManager::LoaderFactory::CreateLoader](classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory.html#ab95a61ff7c67b25e96594631207045a2)
:::

::: {.ttdeci}
virtual ServableData\< std::unique\_ptr\< Loader \> \>
CreateLoader(const ServableId &servable\_id)=0
:::
:::

::: {#aclasstensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory_html_ae3b86ce052eeee59a53ef0ab58080729 .ttc}
::: {.ttname}
[tensorflow::serving::CachingManager::LoaderFactory::GetServableVersion](classtensorflow_1_1serving_1_1CachingManager_1_1LoaderFactory.html#ae3b86ce052eeee59a53ef0ab58080729)
:::

::: {.ttdeci}
virtual int64\_t GetServableVersion(const string &servable\_name,
ServableRequest::AutoVersionPolicy policy) const =0
:::
:::

::: {#aclasstensorflow_1_1serving_1_1CachingManager_html .ttc}
::: {.ttname}
[tensorflow::serving::CachingManager](classtensorflow_1_1serving_1_1CachingManager.html)
:::

::: {.ttdef}
**Definition:** caching\_manager.h:45
:::
:::

::: {#aclasstensorflow_1_1serving_1_1CachingManager_html_af7ec61e19bcd1ac85a4c97c32e977ffe .ttc}
::: {.ttname}
[tensorflow::serving::CachingManager::ListAvailableServableIds](classtensorflow_1_1serving_1_1CachingManager.html#af7ec61e19bcd1ac85a4c97c32e977ffe)
:::

::: {.ttdeci}
std::vector\< ServableId \> ListAvailableServableIds() const override
:::

::: {.ttdef}
**Definition:** caching\_manager.cc:199
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

::: {#aclasstensorflow_1_1serving_1_1Manager_html .ttc}
::: {.ttname}
[tensorflow::serving::Manager](classtensorflow_1_1serving_1_1Manager.html)
:::

::: {.ttdef}
**Definition:** manager.h:77
:::
:::

::: {#aclasstensorflow_1_1serving_1_1PathPrefixLoaderFactory_html .ttc}
::: {.ttname}
[tensorflow::serving::PathPrefixLoaderFactory](classtensorflow_1_1serving_1_1PathPrefixLoaderFactory.html)
:::

::: {.ttdef}
**Definition:** caching\_manager.h:167
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

::: {#aclasstensorflow_1_1serving_1_1test__util_1_1CachingManagerTestAccess_html .ttc}
::: {.ttname}
[tensorflow::serving::test\_util::CachingManagerTestAccess](classtensorflow_1_1serving_1_1test__util_1_1CachingManagerTestAccess.html)
:::

::: {.ttdef}
**Definition:** manager\_test\_util.h:70
:::
:::

::: {#astructtensorflow_1_1serving_1_1CachingManager_1_1Options_html .ttc}
::: {.ttname}
[tensorflow::serving::CachingManager::Options](structtensorflow_1_1serving_1_1CachingManager_1_1Options.html)
:::

::: {.ttdef}
**Definition:** caching\_manager.h:49
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

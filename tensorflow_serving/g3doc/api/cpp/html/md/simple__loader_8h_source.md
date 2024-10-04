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
simple\_loader.h
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
TENSORFLOW\_SERVING\_CORE\_SIMPLE\_LOADER\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_CORE\_SIMPLE\_LOADER\_H\_]{.preprocessor}
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
[]{#l00021}[ 21]{.lineno} 
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"absl/types/optional.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"absl/types/variant.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow/core/lib/core/errors.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow/core/platform/mem.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow/core/platform/mutex.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow/core/platform/types.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow\_serving/core/loader.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include
\"tensorflow\_serving/core/source\_adapter.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [\#include
\"tensorflow\_serving/resources/resource\_util.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [\#include
\"tensorflow\_serving/resources/resource\_values.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [\#include
\"tensorflow\_serving/util/any\_ptr.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} 
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [// SimpleLoader is a wrapper that simplifies
Loader creation for common, simple]{.comment}
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [// use-cases that conform to the following
restrictions:]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [// - The servable\'s estimated resource
footprint is static.]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [// - The servable can be loaded by invoking a
no-argument closure.]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} [// - The servable can be unloaded by invoking
its destructor.]{.comment}
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [// When constructing a SimpleLoader users
provide a Creator callback. This]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [// callback is used in the Load() method to
construct a servable of type]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [// ServableType and populate the servable.
The servable object is destroyed when]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [// Unload() is called.]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [// SimpleLoader uses a second supplied
callback to estimate the servable\'s]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} [// resource usage. It memoizes that
callback\'s result, for efficiency. If main-]{.comment}
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} [// memory resources are specified, Unload()
releases that amount of memory to]{.comment}
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} [// the OS after deleting the
servable.]{.comment}
:::

::: {.line}
[]{#l00054}[ 54]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} [// Example use: create a toy Loader for a
servable of type time\_t. Here the]{.comment}
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} [// time servable is instantiated with the
current time when Load() is called.]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} [// auto servable\_creator =
\[\](std::unique\_ptr\<time\_t\>\* servable) {]{.comment}
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} [// servable-\>reset(new time\_t);]{.comment}
:::

::: {.line}
[]{#l00059}[ 59]{.lineno} [// \*servable = time(nullptr);]{.comment}
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} [// return Status();]{.comment}
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} [// };]{.comment}
:::

::: {.line}
[]{#l00062}[ 62]{.lineno} [// auto resource\_estimator =
\[\](ResourceAllocation\* estimate) {]{.comment}
:::

::: {.line}
[]{#l00063}[ 63]{.lineno} [//
estimate-\>mutable\_\...(\...)-\>set\_\...(\...);]{.comment}
:::

::: {.line}
[]{#l00064}[ 64]{.lineno} [// return Status();]{.comment}
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} [// };]{.comment}
:::

::: {.line}
[]{#l00066}[ 66]{.lineno} [// std::unique\_ptr\<Loader\> loader(new
SimpleLoader\<time\_t\>(]{.comment}
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} [// servable\_creator,
resource\_estimator));]{.comment}
:::

::: {.line}
[]{#l00068}[ 68]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} [// This class is not thread-safe.
Synchronization is assumed to be done by the]{.comment}
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} [// caller.]{.comment}
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} [template]{.keyword} \<[typename]{.keyword}
ServableType\>
:::

::: {.line}
[]{#l00072}[
[72](classtensorflow_1_1serving_1_1SimpleLoader.html){.line}]{.lineno} [class
]{.keyword}[SimpleLoader](classtensorflow_1_1serving_1_1SimpleLoader.html){.code}
: [public]{.keyword}
[Loader](classtensorflow_1_1serving_1_1Loader.html){.code} {
:::

::: {.line}
[]{#l00073}[ 73]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  [// Creator is called in Load and used to
create the servable.]{.comment}
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  [using]{.keyword} Creator =
std::function\<Status(std::unique\_ptr\<ServableType\>\*)\>;
:::

::: {.line}
[]{#l00076}[ 76]{.lineno}  [using]{.keyword} CreatorWithMetadata =
:::

::: {.line}
[]{#l00077}[ 77]{.lineno}  std::function\<Status([const]{.keyword}
[Metadata](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html){.code}&,
std::unique\_ptr\<ServableType\>\*)\>;
:::

::: {.line}
[]{#l00078}[ 78]{.lineno}  [using]{.keyword} CreatorVariant =
absl::variant\<Creator, CreatorWithMetadata\>;
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} 
:::

::: {.line}
[]{#l00080}[ 80]{.lineno}  [// A callback for estimating a servable\'s
resource usage.]{.comment}
:::

::: {.line}
[]{#l00081}[ 81]{.lineno}  [using]{.keyword} ResourceEstimator =
std::function\<Status(ResourceAllocation\*)\>;
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} 
:::

::: {.line}
[]{#l00083}[ 83]{.lineno}  [// Returns a dummy resource-estimation
callback that estimates the servable\'s]{.comment}
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [// resource footprint at zero. Useful in
best-effort or test environments that]{.comment}
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  [// do not track resource usage.]{.comment}
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  [// IMPORTANT: Use of EstimateNoResources()
abdicates resource safety, i.e. a]{.comment}
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  [// loader using that option does not declare
its servable\'s resource usage,]{.comment}
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  [// and hence the serving system cannot
enforce resource safety.]{.comment}
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  [static]{.keyword} ResourceEstimator
EstimateNoResources();
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} 
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [// Constructor that takes a single resource
estimator, to use for estimating]{.comment}
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  [// the resources needed during load as well
as post-load.]{.comment}
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} 
[SimpleLoader](classtensorflow_1_1serving_1_1SimpleLoader.html){.code}(Creator
creator, ResourceEstimator resource\_estimator);
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} 
:::

::: {.line}
[]{#l00096}[ 96]{.lineno}  [// Similar to the above constructor, but
accepts a CreatorWithMetadata]{.comment}
:::

::: {.line}
[]{#l00097}[ 97]{.lineno}  [// function.]{.comment}
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} 
[SimpleLoader](classtensorflow_1_1serving_1_1SimpleLoader.html){.code}(CreatorWithMetadata
creator\_with\_metadata,
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  ResourceEstimator resource\_estimator);
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} 
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  [// Constructor that takes two resource
estimators: one to use for estimating]{.comment}
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  [// the resources needed during load, as
well as a second one that gives a]{.comment}
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  [// different estimate after loading has
finished. See the documentation on]{.comment}
:::

::: {.line}
[]{#l00104}[ 104]{.lineno}  [// Loader::EstimateResources() for (a)
potential reasons the estimate might]{.comment}
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  [// decrease, and (b) correctness
constraints on how the estimate is allowed to]{.comment}
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  [// change over time.]{.comment}
:::

::: {.line}
[]{#l00107}[ 107]{.lineno} 
[SimpleLoader](classtensorflow_1_1serving_1_1SimpleLoader.html){.code}(Creator
creator, ResourceEstimator resource\_estimator,
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  ResourceEstimator
post\_load\_resource\_estimator);
:::

::: {.line}
[]{#l00109}[ 109]{.lineno} 
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  [// Similar to the above constructor, but
accepts a CreatorWithMetadata]{.comment}
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  [// function.]{.comment}
:::

::: {.line}
[]{#l00112}[ 112]{.lineno} 
[SimpleLoader](classtensorflow_1_1serving_1_1SimpleLoader.html){.code}(CreatorWithMetadata
creator\_with\_metadata,
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  ResourceEstimator resource\_estimator,
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  ResourceEstimator
post\_load\_resource\_estimator);
:::

::: {.line}
[]{#l00115}[ 115]{.lineno} 
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  [// Constructor which accepts all variations
of the params.]{.comment}
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} 
[SimpleLoader](classtensorflow_1_1serving_1_1SimpleLoader.html){.code}(CreatorVariant
creator\_variant,
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  ResourceEstimator resource\_estimator,
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  absl::optional\<ResourceEstimator\>
post\_load\_resource\_estimator);
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} 
:::

::: {.line}
[]{#l00121}[ 121]{.lineno} 
\~[SimpleLoader](classtensorflow_1_1serving_1_1SimpleLoader.html){.code}()
[override]{.keyword} = [default]{.keywordflow};
:::

::: {.line}
[]{#l00122}[ 122]{.lineno} 
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  Status
[EstimateResources](classtensorflow_1_1serving_1_1SimpleLoader.html#a05ede6c604d05037f59fe13472b48935){.code}(ResourceAllocation\*
estimate) [const override]{.keyword};
:::

::: {.line}
[]{#l00124}[ 124]{.lineno} 
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  [// REQUIRES: That the ctor with Creator be
used, otherwise returns an error]{.comment}
:::

::: {.line}
[]{#l00126}[ 126]{.lineno}  [// status.]{.comment}
:::

::: {.line}
[]{#l00127}[ 127]{.lineno}  Status
[Load](classtensorflow_1_1serving_1_1SimpleLoader.html#ada69d680b17f2e054faef889f135cb74){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00128}[ 128]{.lineno} 
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  Status
[LoadWithMetadata](classtensorflow_1_1serving_1_1SimpleLoader.html#a4c9a2f88fd1cab8a68ffa69bb9900e24){.code}([const]{.keyword}
[Metadata](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html){.code}&
metadata) [override]{.keyword};
:::

::: {.line}
[]{#l00130}[ 130]{.lineno} 
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  [void]{.keywordtype}
[Unload](classtensorflow_1_1serving_1_1SimpleLoader.html#ae24b904b3155f039fadd88b1c23e2f82){.code}()
[override]{.keyword};
:::

::: {.line}
[]{#l00132}[ 132]{.lineno} 
:::

::: {.line}
[]{#l00133}[
[133](classtensorflow_1_1serving_1_1SimpleLoader.html#a914a9107be7cfeb587998934be9d9fee){.line}]{.lineno} 
[AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html){.code}
[servable](classtensorflow_1_1serving_1_1SimpleLoader.html#a914a9107be7cfeb587998934be9d9fee){.code}()[
override ]{.keyword}{ [return]{.keywordflow}
[AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html){.code}{servable\_.get()};
}
:::

::: {.line}
[]{#l00134}[ 134]{.lineno} 
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  Status EstimateResourcesPostLoad();
:::

::: {.line}
[]{#l00137}[ 137]{.lineno} 
:::

::: {.line}
[]{#l00138}[ 138]{.lineno}  CreatorVariant creator\_variant\_;
:::

::: {.line}
[]{#l00139}[ 139]{.lineno} 
:::

::: {.line}
[]{#l00140}[ 140]{.lineno}  [// A function that estimates the resources
needed to load the servable.]{.comment}
:::

::: {.line}
[]{#l00141}[ 141]{.lineno}  ResourceEstimator resource\_estimator\_;
:::

::: {.line}
[]{#l00142}[ 142]{.lineno} 
:::

::: {.line}
[]{#l00143}[ 143]{.lineno}  [// An optional function that estimates the
resources needed for the servable]{.comment}
:::

::: {.line}
[]{#l00144}[ 144]{.lineno}  [// after it has been loaded. (If omitted,
\'resource\_estimator\_\' should be used]{.comment}
:::

::: {.line}
[]{#l00145}[ 145]{.lineno}  [// for all estimates, i.e. before, during
and after load.)]{.comment}
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  absl::optional\<ResourceEstimator\>
post\_load\_resource\_estimator\_;
:::

::: {.line}
[]{#l00147}[ 147]{.lineno} 
:::

::: {.line}
[]{#l00148}[ 148]{.lineno}  [// The memoized estimated resource
requirement of the servable.]{.comment}
:::

::: {.line}
[]{#l00149}[ 149]{.lineno}  [mutable]{.keyword}
absl::optional\<ResourceAllocation\> memoized\_resource\_estimate\_
:::

::: {.line}
[]{#l00150}[ 150]{.lineno} 
TF\_GUARDED\_BY(memoized\_resource\_estimate\_mu\_);
:::

::: {.line}
[]{#l00151}[ 151]{.lineno}  [mutable]{.keyword} mutex
memoized\_resource\_estimate\_mu\_;
:::

::: {.line}
[]{#l00152}[ 152]{.lineno} 
:::

::: {.line}
[]{#l00153}[ 153]{.lineno}  std::unique\_ptr\<ResourceUtil\>
resource\_util\_;
:::

::: {.line}
[]{#l00154}[ 154]{.lineno}  Resource ram\_resource\_;
:::

::: {.line}
[]{#l00155}[ 155]{.lineno} 
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  std::unique\_ptr\<ServableType\> servable\_;
:::

::: {.line}
[]{#l00157}[ 157]{.lineno} 
:::

::: {.line}
[]{#l00158}[ 158]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([SimpleLoader](classtensorflow_1_1serving_1_1SimpleLoader.html){.code});
:::

::: {.line}
[]{#l00159}[ 159]{.lineno} };
:::

::: {.line}
[]{#l00160}[ 160]{.lineno} 
:::

::: {.line}
[]{#l00161}[ 161]{.lineno} [// SimpleLoaderSourceAdapter is used to
create a simple SourceAdapter that]{.comment}
:::

::: {.line}
[]{#l00162}[ 162]{.lineno} [// creates Loaders for servables of type
ServableType (e.g. std::map), from]{.comment}
:::

::: {.line}
[]{#l00163}[ 163]{.lineno} [// objects of type DataType (e.g. storage
paths of serialized hashmaps).]{.comment}
:::

::: {.line}
[]{#l00164}[ 164]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00165}[ 165]{.lineno} [// It bundles together the SourceAdapter and
Loader concepts, in a way that]{.comment}
:::

::: {.line}
[]{#l00166}[ 166]{.lineno} [// suffices for simple use cases. In
particular, its limitations are:]{.comment}
:::

::: {.line}
[]{#l00167}[ 167]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00168}[ 168]{.lineno} [// - Like UnarySourceAdapter (see
source\_adapter.h), it translates aspired-]{.comment}
:::

::: {.line}
[]{#l00169}[ 169]{.lineno} [// version items one at a time, giving a
simpler interface but less flexibility.]{.comment}
:::

::: {.line}
[]{#l00170}[ 170]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00171}[ 171]{.lineno} [// - Like SimpleLoader, the servable\'s
estimated resource footprint is static,]{.comment}
:::

::: {.line}
[]{#l00172}[ 172]{.lineno} [// and the emitted loaders\' Unload()
implementation calls ServableType\'s]{.comment}
:::

::: {.line}
[]{#l00173}[ 173]{.lineno} [// destructor and releases the memory to the
OS.]{.comment}
:::

::: {.line}
[]{#l00174}[ 174]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00175}[ 175]{.lineno} [// For more complex behaviors,
SimpleLoaderSourceAdapter is inapplicable. You]{.comment}
:::

::: {.line}
[]{#l00176}[ 176]{.lineno} [// must instead create a SourceAdapter and
Loader. That said, you may still be]{.comment}
:::

::: {.line}
[]{#l00177}[ 177]{.lineno} [// able to use one of UnarySourceAdapter or
SimpleLoader.]{.comment}
:::

::: {.line}
[]{#l00178}[ 178]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00179}[ 179]{.lineno} [// IMPORTANT: Every leaf derived class must
call Detach() at the top of its]{.comment}
:::

::: {.line}
[]{#l00180}[ 180]{.lineno} [// destructor. (See documentation on
TargetBase::Detach() in target.h.) Doing so]{.comment}
:::

::: {.line}
[]{#l00181}[ 181]{.lineno} [// ensures that no virtual method calls are
in flight during destruction of]{.comment}
:::

::: {.line}
[]{#l00182}[ 182]{.lineno} [// member variables.]{.comment}
:::

::: {.line}
[]{#l00183}[ 183]{.lineno} [template]{.keyword} \<[typename]{.keyword}
DataType, [typename]{.keyword} ServableType\>
:::

::: {.line}
[]{#l00184}[
[184](classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter.html){.line}]{.lineno} [class
]{.keyword}[SimpleLoaderSourceAdapter](classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter.html){.code}
:::

::: {.line}
[]{#l00185}[ 185]{.lineno}  : [public]{.keyword}
[UnarySourceAdapter](classtensorflow_1_1serving_1_1UnarySourceAdapter.html){.code}\<DataType,
std::unique\_ptr\<Loader\>\> {
:::

::: {.line}
[]{#l00186}[ 186]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00187}[ 187]{.lineno} 
\~[SimpleLoaderSourceAdapter](classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter.html){.code}()
[override]{.keyword} = 0;
:::

::: {.line}
[]{#l00188}[ 188]{.lineno} 
:::

::: {.line}
[]{#l00189}[ 189]{.lineno}  [// Creator is called by the produced
Loaders\' Load() method, and used to]{.comment}
:::

::: {.line}
[]{#l00190}[ 190]{.lineno}  [// create objects of type ServableType. It
takes a DataType object as input.]{.comment}
:::

::: {.line}
[]{#l00191}[ 191]{.lineno}  [using]{.keyword} Creator =
:::

::: {.line}
[]{#l00192}[ 192]{.lineno}  std::function\<Status([const]{.keyword}
DataType&, std::unique\_ptr\<ServableType\>\*)\>;
:::

::: {.line}
[]{#l00193}[ 193]{.lineno} 
:::

::: {.line}
[]{#l00194}[ 194]{.lineno}  [// A callback for estimating a servable\'s
resource usage. It takes a DataType]{.comment}
:::

::: {.line}
[]{#l00195}[ 195]{.lineno}  [// object as input.]{.comment}
:::

::: {.line}
[]{#l00196}[ 196]{.lineno}  [using]{.keyword} ResourceEstimator =
:::

::: {.line}
[]{#l00197}[ 197]{.lineno}  std::function\<Status([const]{.keyword}
DataType&, ResourceAllocation\*)\>;
:::

::: {.line}
[]{#l00198}[ 198]{.lineno} 
:::

::: {.line}
[]{#l00199}[ 199]{.lineno}  [// Returns a dummy resource-estimation
callback that estimates the servable\'s]{.comment}
:::

::: {.line}
[]{#l00200}[ 200]{.lineno}  [// resource footprint at zero. Useful in
best-effort or test environments that]{.comment}
:::

::: {.line}
[]{#l00201}[ 201]{.lineno}  [// do not track resource usage.]{.comment}
:::

::: {.line}
[]{#l00202}[ 202]{.lineno}  [//]{.comment}
:::

::: {.line}
[]{#l00203}[ 203]{.lineno}  [// IMPORTANT: Use of EstimateNoResources()
abdicates resource safety, i.e. a]{.comment}
:::

::: {.line}
[]{#l00204}[ 204]{.lineno}  [// loader using that option does not
declare its servable\'s resource usage,]{.comment}
:::

::: {.line}
[]{#l00205}[ 205]{.lineno}  [// and hence the serving system cannot
enforce resource safety.]{.comment}
:::

::: {.line}
[]{#l00206}[ 206]{.lineno}  [static]{.keyword} ResourceEstimator
EstimateNoResources();
:::

::: {.line}
[]{#l00207}[ 207]{.lineno} 
:::

::: {.line}
[]{#l00208}[ 208]{.lineno}  [protected]{.keyword}:
:::

::: {.line}
[]{#l00209}[ 209]{.lineno}  [// This is an abstract class.]{.comment}
:::

::: {.line}
[]{#l00210}[ 210]{.lineno} 
[SimpleLoaderSourceAdapter](classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter.html){.code}(Creator
creator,
:::

::: {.line}
[]{#l00211}[ 211]{.lineno}  ResourceEstimator resource\_estimator);
:::

::: {.line}
[]{#l00212}[ 212]{.lineno} 
:::

::: {.line}
[]{#l00213}[ 213]{.lineno}  Status Convert([const]{.keyword} DataType&
data, std::unique\_ptr\<Loader\>\* loader) [final]{.keyword};
:::

::: {.line}
[]{#l00214}[ 214]{.lineno} 
:::

::: {.line}
[]{#l00215}[ 215]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00216}[ 216]{.lineno}  Creator creator\_;
:::

::: {.line}
[]{#l00217}[ 217]{.lineno}  ResourceEstimator resource\_estimator\_;
:::

::: {.line}
[]{#l00218}[ 218]{.lineno} 
:::

::: {.line}
[]{#l00219}[ 219]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN([SimpleLoaderSourceAdapter](classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter.html){.code});
:::

::: {.line}
[]{#l00220}[ 220]{.lineno} };
:::

::: {.line}
[]{#l00221}[ 221]{.lineno} 
:::

::: {.line}
[]{#l00223}[ 223]{.lineno} [// Implementation details follow. API users
need not read.]{.comment}
:::

::: {.line}
[]{#l00224}[ 224]{.lineno} 
:::

::: {.line}
[]{#l00225}[ 225]{.lineno} [template]{.keyword} \<[typename]{.keyword}
ServableType\>
:::

::: {.line}
[]{#l00226}[ 226]{.lineno} [typename]{.keyword}
SimpleLoader\<ServableType\>::ResourceEstimator
:::

::: {.line}
[]{#l00227}[
227]{.lineno} [SimpleLoader\<ServableType\>::EstimateNoResources](classtensorflow_1_1serving_1_1SimpleLoader.html){.code}()
{
:::

::: {.line}
[]{#l00228}[ 228]{.lineno}  [return]{.keywordflow}
\[\](ResourceAllocation\* estimate) {
:::

::: {.line}
[]{#l00229}[ 229]{.lineno}  estimate-\>Clear();
:::

::: {.line}
[]{#l00230}[ 230]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00231}[ 231]{.lineno}  };
:::

::: {.line}
[]{#l00232}[ 232]{.lineno} }
:::

::: {.line}
[]{#l00233}[ 233]{.lineno} 
:::

::: {.line}
[]{#l00234}[ 234]{.lineno} [template]{.keyword} \<[typename]{.keyword}
ServableType\>
:::

::: {.line}
[]{#l00235}[
235]{.lineno} SimpleLoader\<ServableType\>::SimpleLoader(Creator
creator,
:::

::: {.line}
[]{#l00236}[ 236]{.lineno}  ResourceEstimator resource\_estimator)
:::

::: {.line}
[]{#l00237}[ 237]{.lineno}  : SimpleLoader(CreatorVariant(creator),
resource\_estimator, absl::nullopt) {
:::

::: {.line}
[]{#l00238}[ 238]{.lineno} }
:::

::: {.line}
[]{#l00239}[ 239]{.lineno} 
:::

::: {.line}
[]{#l00240}[ 240]{.lineno} [template]{.keyword} \<[typename]{.keyword}
ServableType\>
:::

::: {.line}
[]{#l00241}[ 241]{.lineno} SimpleLoader\<ServableType\>::SimpleLoader(
:::

::: {.line}
[]{#l00242}[ 242]{.lineno}  CreatorWithMetadata creator\_with\_metadata,
:::

::: {.line}
[]{#l00243}[ 243]{.lineno}  ResourceEstimator resource\_estimator)
:::

::: {.line}
[]{#l00244}[ 244]{.lineno}  :
SimpleLoader(CreatorVariant(creator\_with\_metadata),
resource\_estimator,
:::

::: {.line}
[]{#l00245}[ 245]{.lineno}  absl::nullopt) {}
:::

::: {.line}
[]{#l00246}[ 246]{.lineno} 
:::

::: {.line}
[]{#l00247}[ 247]{.lineno} [template]{.keyword} \<[typename]{.keyword}
ServableType\>
:::

::: {.line}
[]{#l00248}[ 248]{.lineno} SimpleLoader\<ServableType\>::SimpleLoader(
:::

::: {.line}
[]{#l00249}[ 249]{.lineno}  Creator creator, ResourceEstimator
resource\_estimator,
:::

::: {.line}
[]{#l00250}[ 250]{.lineno}  ResourceEstimator
post\_load\_resource\_estimator)
:::

::: {.line}
[]{#l00251}[ 251]{.lineno}  : SimpleLoader(CreatorVariant(creator),
resource\_estimator,
:::

::: {.line}
[]{#l00252}[ 252]{.lineno}  {post\_load\_resource\_estimator}) {}
:::

::: {.line}
[]{#l00253}[ 253]{.lineno} 
:::

::: {.line}
[]{#l00254}[ 254]{.lineno} [template]{.keyword} \<[typename]{.keyword}
ServableType\>
:::

::: {.line}
[]{#l00255}[ 255]{.lineno} SimpleLoader\<ServableType\>::SimpleLoader(
:::

::: {.line}
[]{#l00256}[ 256]{.lineno}  CreatorWithMetadata creator\_with\_metadata,
:::

::: {.line}
[]{#l00257}[ 257]{.lineno}  ResourceEstimator resource\_estimator,
:::

::: {.line}
[]{#l00258}[ 258]{.lineno}  ResourceEstimator
post\_load\_resource\_estimator)
:::

::: {.line}
[]{#l00259}[ 259]{.lineno}  :
SimpleLoader(CreatorVariant(creator\_with\_metadata),
resource\_estimator,
:::

::: {.line}
[]{#l00260}[ 260]{.lineno}  {post\_load\_resource\_estimator}) {}
:::

::: {.line}
[]{#l00261}[ 261]{.lineno} 
:::

::: {.line}
[]{#l00262}[ 262]{.lineno} [template]{.keyword} \<[typename]{.keyword}
ServableType\>
:::

::: {.line}
[]{#l00263}[ 263]{.lineno} SimpleLoader\<ServableType\>::SimpleLoader(
:::

::: {.line}
[]{#l00264}[ 264]{.lineno}  CreatorVariant creator\_variant,
ResourceEstimator resource\_estimator,
:::

::: {.line}
[]{#l00265}[ 265]{.lineno}  absl::optional\<ResourceEstimator\>
post\_load\_resource\_estimator)
:::

::: {.line}
[]{#l00266}[ 266]{.lineno}  : creator\_variant\_(creator\_variant),
:::

::: {.line}
[]{#l00267}[ 267]{.lineno}  resource\_estimator\_(resource\_estimator),
:::

::: {.line}
[]{#l00268}[ 268]{.lineno} 
post\_load\_resource\_estimator\_(post\_load\_resource\_estimator) {
:::

::: {.line}
[]{#l00269}[ 269]{.lineno}  ResourceUtil::Options
resource\_util\_options;
:::

::: {.line}
[]{#l00270}[ 270]{.lineno}  resource\_util\_options.devices =
{{device\_types::kMain, 1}};
:::

::: {.line}
[]{#l00271}[ 271]{.lineno}  resource\_util\_ =
:::

::: {.line}
[]{#l00272}[ 272]{.lineno} 
std::unique\_ptr\<ResourceUtil\>([new]{.keyword}
ResourceUtil(resource\_util\_options));
:::

::: {.line}
[]{#l00273}[ 273]{.lineno} 
:::

::: {.line}
[]{#l00274}[ 274]{.lineno}  ram\_resource\_ =
resource\_util\_-\>CreateBoundResource(
:::

::: {.line}
[]{#l00275}[ 275]{.lineno}  device\_types::kMain,
resource\_kinds::kRamBytes);
:::

::: {.line}
[]{#l00276}[ 276]{.lineno} }
:::

::: {.line}
[]{#l00277}[ 277]{.lineno} 
:::

::: {.line}
[]{#l00278}[ 278]{.lineno} [template]{.keyword} \<[typename]{.keyword}
ServableType\>
:::

::: {.line}
[]{#l00279}[
[279](classtensorflow_1_1serving_1_1SimpleLoader.html#a05ede6c604d05037f59fe13472b48935){.line}]{.lineno} Status
[SimpleLoader\<ServableType\>::EstimateResources](classtensorflow_1_1serving_1_1SimpleLoader.html#a05ede6c604d05037f59fe13472b48935){.code}(
:::

::: {.line}
[]{#l00280}[ 280]{.lineno}  ResourceAllocation\* estimate)[ const
]{.keyword}{
:::

::: {.line}
[]{#l00281}[ 281]{.lineno}  mutex\_lock
l(memoized\_resource\_estimate\_mu\_);
:::

::: {.line}
[]{#l00282}[ 282]{.lineno}  [if]{.keywordflow}
(memoized\_resource\_estimate\_) {
:::

::: {.line}
[]{#l00283}[ 283]{.lineno}  \*estimate =
\*memoized\_resource\_estimate\_;
:::

::: {.line}
[]{#l00284}[ 284]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00285}[ 285]{.lineno}  }
:::

::: {.line}
[]{#l00286}[ 286]{.lineno} 
:::

::: {.line}
[]{#l00287}[ 287]{.lineno}  [// Compute and memoize the resource
estimate.]{.comment}
:::

::: {.line}
[]{#l00288}[ 288]{.lineno} 
TF\_RETURN\_IF\_ERROR(resource\_estimator\_(estimate));
:::

::: {.line}
[]{#l00289}[ 289]{.lineno}  memoized\_resource\_estimate\_ = \*estimate;
:::

::: {.line}
[]{#l00290}[ 290]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00291}[ 291]{.lineno} }
:::

::: {.line}
[]{#l00292}[ 292]{.lineno} 
:::

::: {.line}
[]{#l00293}[ 293]{.lineno} [template]{.keyword} \<[typename]{.keyword}
ServableType\>
:::

::: {.line}
[]{#l00294}[
[294](classtensorflow_1_1serving_1_1SimpleLoader.html#ada69d680b17f2e054faef889f135cb74){.line}]{.lineno} Status
[SimpleLoader\<ServableType\>::Load](classtensorflow_1_1serving_1_1SimpleLoader.html#ada69d680b17f2e054faef889f135cb74){.code}()
{
:::

::: {.line}
[]{#l00295}[ 295]{.lineno}  [if]{.keywordflow}
(absl::holds\_alternative\<CreatorWithMetadata\>(creator\_variant\_)) {
:::

::: {.line}
[]{#l00296}[ 296]{.lineno}  [return]{.keywordflow}
errors::FailedPrecondition(
:::

::: {.line}
[]{#l00297}[ 297]{.lineno}  [\"SimpleLoader::Load() called even though
\"]{.stringliteral}
:::

::: {.line}
[]{#l00298}[ 298]{.lineno}  [\"SimpleLoader::CreatorWithMetadata was
setup. Please use \"]{.stringliteral}
:::

::: {.line}
[]{#l00299}[ 299]{.lineno}  [\"SimpleLoader::LoadWithMetadata()
instead.\"]{.stringliteral});
:::

::: {.line}
[]{#l00300}[ 300]{.lineno}  }
:::

::: {.line}
[]{#l00301}[ 301]{.lineno} 
TF\_RETURN\_IF\_ERROR(absl::get\<Creator\>(creator\_variant\_)(&servable\_));
:::

::: {.line}
[]{#l00302}[ 302]{.lineno}  [return]{.keywordflow}
EstimateResourcesPostLoad();
:::

::: {.line}
[]{#l00303}[ 303]{.lineno} }
:::

::: {.line}
[]{#l00304}[ 304]{.lineno} 
:::

::: {.line}
[]{#l00305}[ 305]{.lineno} [template]{.keyword} \<[typename]{.keyword}
ServableType\>
:::

::: {.line}
[]{#l00306}[
[306](classtensorflow_1_1serving_1_1SimpleLoader.html#a4c9a2f88fd1cab8a68ffa69bb9900e24){.line}]{.lineno} Status
[SimpleLoader\<ServableType\>::LoadWithMetadata](classtensorflow_1_1serving_1_1SimpleLoader.html#a4c9a2f88fd1cab8a68ffa69bb9900e24){.code}([const]{.keyword}
[Metadata](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html){.code}&
metadata) {
:::

::: {.line}
[]{#l00307}[ 307]{.lineno}  [if]{.keywordflow}
(absl::holds\_alternative\<CreatorWithMetadata\>(creator\_variant\_)) {
:::

::: {.line}
[]{#l00308}[ 308]{.lineno}  TF\_RETURN\_IF\_ERROR(
:::

::: {.line}
[]{#l00309}[ 309]{.lineno} 
absl::get\<CreatorWithMetadata\>(creator\_variant\_)(metadata,
&servable\_));
:::

::: {.line}
[]{#l00310}[ 310]{.lineno}  } [else]{.keywordflow} {
:::

::: {.line}
[]{#l00311}[ 311]{.lineno} 
TF\_RETURN\_IF\_ERROR(absl::get\<Creator\>(creator\_variant\_)(&servable\_));
:::

::: {.line}
[]{#l00312}[ 312]{.lineno}  }
:::

::: {.line}
[]{#l00313}[ 313]{.lineno}  [return]{.keywordflow}
EstimateResourcesPostLoad();
:::

::: {.line}
[]{#l00314}[ 314]{.lineno} }
:::

::: {.line}
[]{#l00315}[ 315]{.lineno} 
:::

::: {.line}
[]{#l00316}[ 316]{.lineno} [template]{.keyword} \<[typename]{.keyword}
ServableType\>
:::

::: {.line}
[]{#l00317}[ 317]{.lineno} Status
[SimpleLoader\<ServableType\>::EstimateResourcesPostLoad](classtensorflow_1_1serving_1_1SimpleLoader.html){.code}()
{
:::

::: {.line}
[]{#l00318}[ 318]{.lineno}  [if]{.keywordflow}
(post\_load\_resource\_estimator\_) {
:::

::: {.line}
[]{#l00319}[ 319]{.lineno}  [// Save the during-load estimate (may be
able to use the memoized value).]{.comment}
:::

::: {.line}
[]{#l00320}[ 320]{.lineno}  ResourceAllocation
during\_load\_resource\_estimate;
:::

::: {.line}
[]{#l00321}[ 321]{.lineno} 
TF\_RETURN\_IF\_ERROR(EstimateResources(&during\_load\_resource\_estimate));
:::

::: {.line}
[]{#l00322}[ 322]{.lineno} 
:::

::: {.line}
[]{#l00323}[ 323]{.lineno}  [// Obtain the post-load estimate, and store
it as the memoized value.]{.comment}
:::

::: {.line}
[]{#l00324}[ 324]{.lineno}  ResourceAllocation
post\_load\_resource\_estimate;
:::

::: {.line}
[]{#l00325}[ 325]{.lineno}  TF\_RETURN\_IF\_ERROR(
:::

::: {.line}
[]{#l00326}[ 326]{.lineno} 
(\*post\_load\_resource\_estimator\_)(&post\_load\_resource\_estimate));
:::

::: {.line}
[]{#l00327}[ 327]{.lineno}  {
:::

::: {.line}
[]{#l00328}[ 328]{.lineno}  mutex\_lock
l(memoized\_resource\_estimate\_mu\_);
:::

::: {.line}
[]{#l00329}[ 329]{.lineno}  memoized\_resource\_estimate\_ =
post\_load\_resource\_estimate;
:::

::: {.line}
[]{#l00330}[ 330]{.lineno}  }
:::

::: {.line}
[]{#l00331}[ 331]{.lineno} 
:::

::: {.line}
[]{#l00332}[ 332]{.lineno}  [// Release any transient memory used only
during load to the OS.]{.comment}
:::

::: {.line}
[]{#l00333}[ 333]{.lineno}  [const]{.keyword} uint64\_t
during\_load\_ram\_estimate = resource\_util\_-\>GetQuantity(
:::

::: {.line}
[]{#l00334}[ 334]{.lineno}  ram\_resource\_,
during\_load\_resource\_estimate);
:::

::: {.line}
[]{#l00335}[ 335]{.lineno}  [const]{.keyword} uint64\_t
post\_load\_ram\_estimate =
:::

::: {.line}
[]{#l00336}[ 336]{.lineno} 
resource\_util\_-\>GetQuantity(ram\_resource\_,
post\_load\_resource\_estimate);
:::

::: {.line}
[]{#l00337}[ 337]{.lineno}  [if]{.keywordflow}
(post\_load\_ram\_estimate \< during\_load\_ram\_estimate) {
:::

::: {.line}
[]{#l00338}[ 338]{.lineno}  [const]{.keyword} uint64\_t
transient\_ram\_estimate =
:::

::: {.line}
[]{#l00339}[ 339]{.lineno}  during\_load\_ram\_estimate -
post\_load\_ram\_estimate;
:::

::: {.line}
[]{#l00340}[ 340]{.lineno}  LOG(INFO) \<\< [\"Calling
MallocExtension\_ReleaseToSystem() after servable \"]{.stringliteral}
:::

::: {.line}
[]{#l00341}[ 341]{.lineno}  [\"load with \"]{.stringliteral}
:::

::: {.line}
[]{#l00342}[ 342]{.lineno}  \<\< transient\_ram\_estimate;
:::

::: {.line}
[]{#l00343}[ 343]{.lineno} 
::tensorflow::port::MallocExtension\_ReleaseToSystem(
:::

::: {.line}
[]{#l00344}[ 344]{.lineno}  transient\_ram\_estimate);
:::

::: {.line}
[]{#l00345}[ 345]{.lineno}  }
:::

::: {.line}
[]{#l00346}[ 346]{.lineno}  }
:::

::: {.line}
[]{#l00347}[ 347]{.lineno} 
:::

::: {.line}
[]{#l00348}[ 348]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00349}[ 349]{.lineno} }
:::

::: {.line}
[]{#l00350}[ 350]{.lineno} 
:::

::: {.line}
[]{#l00351}[ 351]{.lineno} [template]{.keyword} \<[typename]{.keyword}
ServableType\>
:::

::: {.line}
[]{#l00352}[
[352](classtensorflow_1_1serving_1_1SimpleLoader.html#ae24b904b3155f039fadd88b1c23e2f82){.line}]{.lineno} [void]{.keywordtype}
[SimpleLoader\<ServableType\>::Unload](classtensorflow_1_1serving_1_1SimpleLoader.html#ae24b904b3155f039fadd88b1c23e2f82){.code}()
{
:::

::: {.line}
[]{#l00353}[ 353]{.lineno}  [// Before destroying the servable, run the
resource estimator (in case the]{.comment}
:::

::: {.line}
[]{#l00354}[ 354]{.lineno}  [// estimation routine calls into the
servable behind the scenes.)]{.comment}
:::

::: {.line}
[]{#l00355}[ 355]{.lineno}  ResourceAllocation resource\_estimate;
:::

::: {.line}
[]{#l00356}[ 356]{.lineno}  Status resource\_status =
EstimateResources(&resource\_estimate);
:::

::: {.line}
[]{#l00357}[ 357]{.lineno} 
:::

::: {.line}
[]{#l00358}[ 358]{.lineno}  [// Delete the servable no matter what (even
if the resource estimator had some]{.comment}
:::

::: {.line}
[]{#l00359}[ 359]{.lineno}  [// error).]{.comment}
:::

::: {.line}
[]{#l00360}[ 360]{.lineno}  servable\_.reset();
:::

::: {.line}
[]{#l00361}[ 361]{.lineno} 
:::

::: {.line}
[]{#l00362}[ 362]{.lineno}  [if]{.keywordflow} (!resource\_status.ok())
{
:::

::: {.line}
[]{#l00363}[ 363]{.lineno}  [return]{.keywordflow};
:::

::: {.line}
[]{#l00364}[ 364]{.lineno}  }
:::

::: {.line}
[]{#l00365}[ 365]{.lineno} 
:::

::: {.line}
[]{#l00366}[ 366]{.lineno}  [// If we have a main-memory footprint
estimate, release that amount of memory]{.comment}
:::

::: {.line}
[]{#l00367}[ 367]{.lineno}  [// to the OS.]{.comment}
:::

::: {.line}
[]{#l00368}[ 368]{.lineno}  [const]{.keyword} uint64\_t memory\_estimate
=
:::

::: {.line}
[]{#l00369}[ 369]{.lineno} 
resource\_util\_-\>GetQuantity(ram\_resource\_, resource\_estimate);
:::

::: {.line}
[]{#l00370}[ 370]{.lineno}  [if]{.keywordflow} (memory\_estimate \> 0) {
:::

::: {.line}
[]{#l00371}[ 371]{.lineno}  LOG(INFO) \<\< [\"Calling
MallocExtension\_ReleaseToSystem() after servable \"]{.stringliteral}
:::

::: {.line}
[]{#l00372}[ 372]{.lineno}  [\"unload with \"]{.stringliteral}
:::

::: {.line}
[]{#l00373}[ 373]{.lineno}  \<\< memory\_estimate;
:::

::: {.line}
[]{#l00374}[ 374]{.lineno} 
::tensorflow::port::MallocExtension\_ReleaseToSystem(memory\_estimate);
:::

::: {.line}
[]{#l00375}[ 375]{.lineno}  }
:::

::: {.line}
[]{#l00376}[ 376]{.lineno} }
:::

::: {.line}
[]{#l00377}[ 377]{.lineno} 
:::

::: {.line}
[]{#l00378}[ 378]{.lineno} [template]{.keyword} \<[typename]{.keyword}
DataType, [typename]{.keyword} ServableType\>
:::

::: {.line}
[]{#l00379}[
379]{.lineno} [SimpleLoaderSourceAdapter](classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter.html){.code}\<DataType,
:::

::: {.line}
[]{#l00380}[ 380]{.lineno} 
ServableType\>::\~SimpleLoaderSourceAdapter() {}
:::

::: {.line}
[]{#l00381}[ 381]{.lineno} 
:::

::: {.line}
[]{#l00382}[ 382]{.lineno} [template]{.keyword} \<[typename]{.keyword}
DataType, [typename]{.keyword} ServableType\>
:::

::: {.line}
[]{#l00383}[ 383]{.lineno} [typename]{.keyword}
SimpleLoaderSourceAdapter\<DataType, ServableType\>::ResourceEstimator
:::

::: {.line}
[]{#l00384}[ 384]{.lineno} SimpleLoaderSourceAdapter\<DataType,
ServableType\>::EstimateNoResources() {
:::

::: {.line}
[]{#l00385}[ 385]{.lineno}  [return]{.keywordflow}
\[\]([const]{.keyword} DataType& data, ResourceAllocation\* estimate) {
:::

::: {.line}
[]{#l00386}[ 386]{.lineno}  estimate-\>Clear();
:::

::: {.line}
[]{#l00387}[ 387]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00388}[ 388]{.lineno}  };
:::

::: {.line}
[]{#l00389}[ 389]{.lineno} }
:::

::: {.line}
[]{#l00390}[ 390]{.lineno} 
:::

::: {.line}
[]{#l00391}[ 391]{.lineno} [template]{.keyword} \<[typename]{.keyword}
DataType, [typename]{.keyword} ServableType\>
:::

::: {.line}
[]{#l00392}[ 392]{.lineno} SimpleLoaderSourceAdapter\<DataType,
ServableType\>::SimpleLoaderSourceAdapter(
:::

::: {.line}
[]{#l00393}[ 393]{.lineno}  Creator creator, ResourceEstimator
resource\_estimator)
:::

::: {.line}
[]{#l00394}[ 394]{.lineno}  : creator\_(creator),
resource\_estimator\_(resource\_estimator) {}
:::

::: {.line}
[]{#l00395}[ 395]{.lineno} 
:::

::: {.line}
[]{#l00396}[ 396]{.lineno} [template]{.keyword} \<[typename]{.keyword}
DataType, [typename]{.keyword} ServableType\>
:::

::: {.line}
[]{#l00397}[ 397]{.lineno} Status SimpleLoaderSourceAdapter\<DataType,
ServableType\>::Convert(
:::

::: {.line}
[]{#l00398}[ 398]{.lineno}  [const]{.keyword} DataType& data,
std::unique\_ptr\<Loader\>\* loader) {
:::

::: {.line}
[]{#l00399}[ 399]{.lineno}  [// We copy \'creator\_\' and
\'resource\_estimator\_\', rather than passing via]{.comment}
:::

::: {.line}
[]{#l00400}[ 400]{.lineno}  [// reference, so that the loader we emit is
not tied to the adapter, in case]{.comment}
:::

::: {.line}
[]{#l00401}[ 401]{.lineno}  [// the adapter is deleted before the
loader.]{.comment}
:::

::: {.line}
[]{#l00402}[ 402]{.lineno}  [const]{.keyword} [auto]{.keyword} creator =
creator\_;
:::

::: {.line}
[]{#l00403}[ 403]{.lineno}  [const]{.keyword} [auto]{.keyword}
resource\_estimator = resource\_estimator\_;
:::

::: {.line}
[]{#l00404}[ 404]{.lineno}  loader-\>reset([new]{.keyword}
SimpleLoader\<ServableType\>(
:::

::: {.line}
[]{#l00405}[ 405]{.lineno}  \[creator,
data\](std::unique\_ptr\<ServableType\>\* servable) {
:::

::: {.line}
[]{#l00406}[ 406]{.lineno}  [return]{.keywordflow} creator(data,
servable);
:::

::: {.line}
[]{#l00407}[ 407]{.lineno}  },
:::

::: {.line}
[]{#l00408}[ 408]{.lineno}  \[resource\_estimator,
data\](ResourceAllocation\* estimate) {
:::

::: {.line}
[]{#l00409}[ 409]{.lineno}  [return]{.keywordflow}
resource\_estimator(data, estimate);
:::

::: {.line}
[]{#l00410}[ 410]{.lineno}  }));
:::

::: {.line}
[]{#l00411}[ 411]{.lineno}  [return]{.keywordflow} Status();
:::

::: {.line}
[]{#l00412}[ 412]{.lineno} }
:::

::: {.line}
[]{#l00413}[ 413]{.lineno} 
:::

::: {.line}
[]{#l00414}[ 414]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00415}[ 415]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00416}[ 416]{.lineno} 
:::

::: {.line}
[]{#l00417}[ 417]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_CORE\_SIMPLE\_LOADER\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1AnyPtr_html .ttc}
::: {.ttname}
[tensorflow::serving::AnyPtr](classtensorflow_1_1serving_1_1AnyPtr.html)
:::

::: {.ttdef}
**Definition:** any\_ptr.h:65
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

::: {#aclasstensorflow_1_1serving_1_1SimpleLoaderSourceAdapter_html .ttc}
::: {.ttname}
[tensorflow::serving::SimpleLoaderSourceAdapter](classtensorflow_1_1serving_1_1SimpleLoaderSourceAdapter.html)
:::

::: {.ttdef}
**Definition:** simple\_loader.h:185
:::
:::

::: {#aclasstensorflow_1_1serving_1_1SimpleLoader_html .ttc}
::: {.ttname}
[tensorflow::serving::SimpleLoader](classtensorflow_1_1serving_1_1SimpleLoader.html)
:::

::: {.ttdef}
**Definition:** simple\_loader.h:72
:::
:::

::: {#aclasstensorflow_1_1serving_1_1SimpleLoader_html_a05ede6c604d05037f59fe13472b48935 .ttc}
::: {.ttname}
[tensorflow::serving::SimpleLoader::EstimateResources](classtensorflow_1_1serving_1_1SimpleLoader.html#a05ede6c604d05037f59fe13472b48935)
:::

::: {.ttdeci}
Status EstimateResources(ResourceAllocation \*estimate) const override
:::

::: {.ttdef}
**Definition:** simple\_loader.h:279
:::
:::

::: {#aclasstensorflow_1_1serving_1_1SimpleLoader_html_a4c9a2f88fd1cab8a68ffa69bb9900e24 .ttc}
::: {.ttname}
[tensorflow::serving::SimpleLoader::LoadWithMetadata](classtensorflow_1_1serving_1_1SimpleLoader.html#a4c9a2f88fd1cab8a68ffa69bb9900e24)
:::

::: {.ttdeci}
Status LoadWithMetadata(const Metadata &metadata) override
:::

::: {.ttdef}
**Definition:** simple\_loader.h:306
:::
:::

::: {#aclasstensorflow_1_1serving_1_1SimpleLoader_html_a914a9107be7cfeb587998934be9d9fee .ttc}
::: {.ttname}
[tensorflow::serving::SimpleLoader::servable](classtensorflow_1_1serving_1_1SimpleLoader.html#a914a9107be7cfeb587998934be9d9fee)
:::

::: {.ttdeci}
AnyPtr servable() override
:::

::: {.ttdef}
**Definition:** simple\_loader.h:133
:::
:::

::: {#aclasstensorflow_1_1serving_1_1SimpleLoader_html_ada69d680b17f2e054faef889f135cb74 .ttc}
::: {.ttname}
[tensorflow::serving::SimpleLoader::Load](classtensorflow_1_1serving_1_1SimpleLoader.html#ada69d680b17f2e054faef889f135cb74)
:::

::: {.ttdeci}
Status Load() override
:::

::: {.ttdef}
**Definition:** simple\_loader.h:294
:::
:::

::: {#aclasstensorflow_1_1serving_1_1SimpleLoader_html_ae24b904b3155f039fadd88b1c23e2f82 .ttc}
::: {.ttname}
[tensorflow::serving::SimpleLoader::Unload](classtensorflow_1_1serving_1_1SimpleLoader.html#ae24b904b3155f039fadd88b1c23e2f82)
:::

::: {.ttdeci}
void Unload() override
:::

::: {.ttdef}
**Definition:** simple\_loader.h:352
:::
:::

::: {#aclasstensorflow_1_1serving_1_1UnarySourceAdapter_html .ttc}
::: {.ttname}
[tensorflow::serving::UnarySourceAdapter](classtensorflow_1_1serving_1_1UnarySourceAdapter.html)
:::

::: {.ttdef}
**Definition:** source\_adapter.h:120
:::
:::

::: {#astructtensorflow_1_1serving_1_1Loader_1_1Metadata_html .ttc}
::: {.ttname}
[tensorflow::serving::Loader::Metadata](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html)
:::

::: {.ttdoc}
The metadata consists of the ServableId.
:::

::: {.ttdef}
**Definition:** loader.h:94
:::
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}

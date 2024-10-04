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
tfrt\_saved\_model\_factory.h
:::
:::
:::

::: {.contents}
::: {.fragment}
::: {.line}
[]{#l00001}[ 1]{.lineno} [/\* Copyright 2020 Google Inc. All Rights
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
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_TFRT\_SAVED\_MODEL\_FACTORY\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_TFRT\_SAVED\_MODEL\_FACTORY\_H\_]{.preprocessor}
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
\"absl/status/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"absl/synchronization/mutex.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"absl/types/optional.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow/core/kernels/batching\_util/shared\_batch\_scheduler.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow/core/platform/macros.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow/core/tfrt/runtime/runtime.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow/core/tfrt/saved\_model/saved\_model.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} [\#include
\"tensorflow\_serving/batching/tfrt\_saved\_model\_with\_batching.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [\#include
\"tensorflow\_serving/core/loader.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [\#include
\"tensorflow\_serving/resources/resources.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/session\_bundle\_config.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/tfrt\_saved\_model\_source\_adapter.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/tfrt\_servable.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/thread\_pool\_factory.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} 
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} 
:::

::: {.line}
[]{#l00049}[
[49](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.line}]{.lineno} [class
]{.keyword}[TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.code}
{
:::

::: {.line}
[]{#l00050}[ 50]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00051}[ 51]{.lineno}  [using]{.keyword} Batcher =
SharedBatchScheduler\<SavedModelBatchingTask\>;
:::

::: {.line}
[]{#l00052}[ 52]{.lineno} 
:::

::: {.line}
[]{#l00053}[ 53]{.lineno} 
[TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.code}([const]{.keyword}
TfrtSavedModelConfig& config,
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  std::shared\_ptr\<Batcher\> batch\_scheduler,
:::

::: {.line}
[]{#l00055}[ 55]{.lineno}  std::unique\_ptr\<ThreadPoolFactory\>
thread\_pool\_factory)
:::

::: {.line}
[]{#l00056}[ 56]{.lineno}  :
[TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.code}(config,
std::move(batch\_scheduler),
:::

::: {.line}
[]{#l00057}[ 57]{.lineno}  std::move(thread\_pool\_factory),
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} 
\[\]([TfrtSavedModelServable](classtensorflow_1_1serving_1_1TfrtSavedModelServable.html){.code}&)
{ [return]{.keywordflow} [nullptr]{.keyword}; }) {
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  }
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
:::

::: {.line}
[]{#l00061}[ 61]{.lineno} 
[TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.code}(
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [const]{.keyword} TfrtSavedModelConfig&
config,
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  std::shared\_ptr\<Batcher\> batch\_scheduler,
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  std::unique\_ptr\<ThreadPoolFactory\>
thread\_pool\_factory,
:::

::: {.line}
[]{#l00065}[ 65]{.lineno} 
std::function\<std::unique\_ptr\<RequestRecorder\>([TfrtSavedModelServable](classtensorflow_1_1serving_1_1TfrtSavedModelServable.html){.code}&)\>
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  recorder\_creator);
:::

::: {.line}
[]{#l00067}[ 67]{.lineno} 
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [virtual]{.keyword}
\~[TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html){.code}();
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} 
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  [static]{.keyword} absl::Status
[Create](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html#ad168a4902febebaa51745428a5da5f17){.code}([const]{.keyword}
TfrtSavedModelConfig& config,
:::

::: {.line}
[]{#l00075}[ 75]{.lineno}  std::unique\_ptr\<TfrtSavedModelFactory\>\*
factory);
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} 
:::

::: {.line}
[]{#l00083}[
[83](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html#affd90c58362c83fb9949bc9892201386){.line}]{.lineno} 
[virtual]{.keyword} absl::Status
[CreateTfrtSavedModelWithMetadata](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html#affd90c58362c83fb9949bc9892201386){.code}(
:::

::: {.line}
[]{#l00084}[ 84]{.lineno}  [const]{.keyword}
[Loader::Metadata](structtensorflow_1_1serving_1_1Loader_1_1Metadata.html){.code}&
metadata, [const]{.keyword} [string]{.keywordtype}& path,
:::

::: {.line}
[]{#l00085}[ 85]{.lineno}  std::unique\_ptr\<Servable\>\* servable);
:::

::: {.line}
[]{#l00086}[ 86]{.lineno} 
:::

::: {.line}
[]{#l00087}[ 87]{.lineno}  ABSL\_DEPRECATED([\"Use the overload that
creates Servable instead\"]{.stringliteral})
:::

::: {.line}
[]{#l00088}[ 88]{.lineno}  absl::Status
[CreateTfrtSavedModelWithMetadata](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html#affd90c58362c83fb9949bc9892201386){.code}(
:::

::: {.line}
[]{#l00089}[ 89]{.lineno}  const
[Loader](classtensorflow_1_1serving_1_1Loader.html){.code}::Metadata&
metadata, const [string]{.keywordtype}& path,
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  std::unique\_ptr\<tfrt\_stub::SavedModel\>\*
saved\_model);
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} 
:::

::: {.line}
[]{#l00098}[ 98]{.lineno}  absl::Status
[EstimateResourceRequirement](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html#aa1451f446252c259f225722b9cd07aaf){.code}(const
[string]{.keywordtype}& path,
:::

::: {.line}
[]{#l00099}[ 99]{.lineno}  ResourceAllocation\* estimate) const;
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} 
:::

::: {.line}
[]{#l00101}[ 101]{.lineno}  const TfrtSavedModelConfig& config()[ const
]{.keyword}{ [return]{.keywordflow} config\_; }
:::

::: {.line}
[]{#l00102}[ 102]{.lineno}  TfrtSavedModelConfig& mutable\_config() {
[return]{.keywordflow} config\_; }
:::

::: {.line}
[]{#l00103}[ 103]{.lineno}  absl::string\_view GetServingResourceType()
[const]{.keyword};
:::

::: {.line}
[]{#l00104}[ 104]{.lineno} 
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00106}[ 106]{.lineno}  [// The subclass can override this method to
return a custom servable]{.comment}
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [// instead of creating one using
CreateTfrtSavedModelWithMetadata(). If it]{.comment}
:::

::: {.line}
[]{#l00108}[ 108]{.lineno}  [// returns nullptr,
CreateTfrtSavedModelWithMetadata() will be used normally.]{.comment}
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  [virtual]{.keyword}
absl::StatusOr\<std::unique\_ptr\<Servable\>\> OverrideServable(
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  [const]{.keyword} Loader::Metadata&
metadata, [const]{.keyword} std::string& path) {
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  [return]{.keywordflow} [nullptr]{.keyword};
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  }
:::

::: {.line}
[]{#l00113}[ 113]{.lineno} 
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  [// The subclass can override this method to
register the custom backend into]{.comment}
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  [// TFRT savedmodel.]{.comment}
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  [virtual]{.keyword} absl::Status
RegisterCustomBackend(
:::

::: {.line}
[]{#l00117}[ 117]{.lineno}  tfrt\_stub::GraphExecutionOptions& options)
{
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  [return]{.keywordflow} absl::OkStatus();
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  }
:::

::: {.line}
[]{#l00120}[ 120]{.lineno} 
:::

::: {.line}
[]{#l00121}[ 121]{.lineno}  [virtual]{.keyword} absl::Status
Freeze(tfrt\_stub::SavedModel& saved\_model) {
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  [return]{.keywordflow} absl::OkStatus();
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  }
:::

::: {.line}
[]{#l00124}[ 124]{.lineno} 
:::

::: {.line}
[]{#l00125}[ 125]{.lineno}  TfrtSavedModelConfig config\_;
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} 
:::

::: {.line}
[]{#l00127}[ 127]{.lineno}  [// A shared batch scheduler. One queue is
used for each saved model this]{.comment}
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  [// factory emits. If batching is not
configured, this remains null.]{.comment}
:::

::: {.line}
[]{#l00129}[ 129]{.lineno}  std::shared\_ptr\<Batcher\>
batch\_scheduler\_;
:::

::: {.line}
[]{#l00130}[ 130]{.lineno} 
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  [// \`thread\_pool\_factory\_\` is used to
create inter-op ThreadPools. It can be a]{.comment}
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  [// nullptr and then the default Tensorflow
threadpools should be used.]{.comment}
:::

::: {.line}
[]{#l00133}[ 133]{.lineno}  std::unique\_ptr\<ThreadPoolFactory\>
thread\_pool\_factory\_;
:::

::: {.line}
[]{#l00134}[ 134]{.lineno} 
:::

::: {.line}
[]{#l00135}[ 135]{.lineno} 
std::function\<std::unique\_ptr\<RequestRecorder\>(TfrtSavedModelServable&)\>
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  recorder\_creator\_ =
\[\](TfrtSavedModelServable&) { [return]{.keywordflow}
[nullptr]{.keyword}; };
:::

::: {.line}
[]{#l00137}[ 137]{.lineno} 
:::

::: {.line}
[]{#l00138}[ 138]{.lineno} 
TF\_DISALLOW\_COPY\_AND\_ASSIGN(TfrtSavedModelFactory);
:::

::: {.line}
[]{#l00139}[ 139]{.lineno} };
:::

::: {.line}
[]{#l00140}[ 140]{.lineno} 
:::

::: {.line}
[]{#l00141}[ 141]{.lineno} [// The registry for creating the
TfrtSavedModelFactory. By default the CreateFn]{.comment}
:::

::: {.line}
[]{#l00142}[ 142]{.lineno} [// creates an instance of
TfrtSavedModelFactory. Custom implementations can use]{.comment}
:::

::: {.line}
[]{#l00143}[ 143]{.lineno} [// this registry to override the CreateFn so
that it creates an instance of the]{.comment}
:::

::: {.line}
[]{#l00144}[ 144]{.lineno} [// subclass of
TfrtSavedModelFactory.]{.comment}
:::

::: {.line}
[]{#l00145}[
[145](classtensorflow_1_1serving_1_1TfrtSavedModelFactoryRegistry.html){.line}]{.lineno} [class
]{.keyword}[TfrtSavedModelFactoryRegistry](classtensorflow_1_1serving_1_1TfrtSavedModelFactoryRegistry.html){.code}
{
:::

::: {.line}
[]{#l00146}[ 146]{.lineno}  [public]{.keyword}:
:::

::: {.line}
[]{#l00147}[ 147]{.lineno}  [using]{.keyword} CreateFn =
:::

::: {.line}
[]{#l00148}[ 148]{.lineno} 
std::function\<absl::StatusOr\<std::unique\_ptr\<TfrtSavedModelFactory\>\>(
:::

::: {.line}
[]{#l00149}[ 149]{.lineno}  [const]{.keyword} TfrtSavedModelConfig&
config)\>;
:::

::: {.line}
[]{#l00150}[ 150]{.lineno} 
:::

::: {.line}
[]{#l00151}[ 151]{.lineno} 
[TfrtSavedModelFactoryRegistry](classtensorflow_1_1serving_1_1TfrtSavedModelFactoryRegistry.html){.code}();
:::

::: {.line}
[]{#l00152}[ 152]{.lineno} 
:::

::: {.line}
[]{#l00153}[ 153]{.lineno}  [void]{.keywordtype} Register(CreateFn fn) {
:::

::: {.line}
[]{#l00154}[ 154]{.lineno}  absl::MutexLock lock(&mu\_);
:::

::: {.line}
[]{#l00155}[ 155]{.lineno}  [if]{.keywordflow} (factory\_create\_fn\_) {
:::

::: {.line}
[]{#l00156}[ 156]{.lineno}  LOG(INFO) \<\< [\"Overriding
TfrtSavedModelFactory\'s create function.\"]{.stringliteral};
:::

::: {.line}
[]{#l00157}[ 157]{.lineno}  }
:::

::: {.line}
[]{#l00158}[ 158]{.lineno}  factory\_create\_fn\_ = std::move(fn);
:::

::: {.line}
[]{#l00159}[ 159]{.lineno}  }
:::

::: {.line}
[]{#l00160}[ 160]{.lineno} 
:::

::: {.line}
[]{#l00161}[ 161]{.lineno}  CreateFn Get()[ const ]{.keyword}{
:::

::: {.line}
[]{#l00162}[ 162]{.lineno}  absl::MutexLock lock(&mu\_);
:::

::: {.line}
[]{#l00163}[ 163]{.lineno}  [return]{.keywordflow}
factory\_create\_fn\_;
:::

::: {.line}
[]{#l00164}[ 164]{.lineno}  }
:::

::: {.line}
[]{#l00165}[ 165]{.lineno} 
:::

::: {.line}
[]{#l00166}[ 166]{.lineno}  [private]{.keyword}:
:::

::: {.line}
[]{#l00167}[ 167]{.lineno}  [mutable]{.keyword} absl::Mutex mu\_;
:::

::: {.line}
[]{#l00168}[ 168]{.lineno}  CreateFn factory\_create\_fn\_
ABSL\_GUARDED\_BY(mu\_);
:::

::: {.line}
[]{#l00169}[ 169]{.lineno} };
:::

::: {.line}
[]{#l00170}[ 170]{.lineno} 
:::

::: {.line}
[]{#l00171}[ 171]{.lineno} [// Creates a batch scheduler based on
\`config\`. The result can be a nullptr if]{.comment}
:::

::: {.line}
[]{#l00172}[ 172]{.lineno} [// \`config\` does not specify batch
parameters.]{.comment}
:::

::: {.line}
[]{#l00173}[
173]{.lineno} absl::StatusOr\<std::shared\_ptr\<TfrtSavedModelFactory::Batcher\>\>
:::

::: {.line}
[]{#l00174}[
174]{.lineno} CreateBatchSchedulerFromConfig([const]{.keyword}
TfrtSavedModelConfig& config);
:::

::: {.line}
[]{#l00175}[ 175]{.lineno} 
:::

::: {.line}
[]{#l00176}[ 176]{.lineno} [// Creates a thread pool factory based on
\`config\`. The result can be a nullptr]{.comment}
:::

::: {.line}
[]{#l00177}[ 177]{.lineno} [// if \`config\` does not specify thread
pool factory config.]{.comment}
:::

::: {.line}
[]{#l00178}[
178]{.lineno} absl::StatusOr\<std::unique\_ptr\<ThreadPoolFactory\>\>
:::

::: {.line}
[]{#l00179}[
179]{.lineno} CreateThreadPoolFactoryFromConfig([const]{.keyword}
TfrtSavedModelConfig& config);
:::

::: {.line}
[]{#l00180}[ 180]{.lineno} 
:::

::: {.line}
[]{#l00181}[
181]{.lineno} [TfrtSavedModelFactoryRegistry](classtensorflow_1_1serving_1_1TfrtSavedModelFactoryRegistry.html){.code}&
GetGlobalTfrtSavedModelFactoryRegistry();
:::

::: {.line}
[]{#l00182}[ 182]{.lineno} 
:::

::: {.line}
[]{#l00183}[ 183]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00184}[ 184]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00185}[ 185]{.lineno} 
:::

::: {.line}
[]{#l00186}[ 186]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_TFRT\_SAVED\_MODEL\_FACTORY\_H\_]{.comment}
:::

::: {#aclasstensorflow_1_1serving_1_1Loader_html .ttc}
::: {.ttname}
[tensorflow::serving::Loader](classtensorflow_1_1serving_1_1Loader.html)
:::

::: {.ttdef}
**Definition:** loader.h:56
:::
:::

::: {#aclasstensorflow_1_1serving_1_1TfrtSavedModelFactoryRegistry_html .ttc}
::: {.ttname}
[tensorflow::serving::TfrtSavedModelFactoryRegistry](classtensorflow_1_1serving_1_1TfrtSavedModelFactoryRegistry.html)
:::

::: {.ttdef}
**Definition:** tfrt\_saved\_model\_factory.h:145
:::
:::

::: {#aclasstensorflow_1_1serving_1_1TfrtSavedModelFactory_html .ttc}
::: {.ttname}
[tensorflow::serving::TfrtSavedModelFactory](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html)
:::

::: {.ttdef}
**Definition:** tfrt\_saved\_model\_factory.h:49
:::
:::

::: {#aclasstensorflow_1_1serving_1_1TfrtSavedModelFactory_html_aa1451f446252c259f225722b9cd07aaf .ttc}
::: {.ttname}
[tensorflow::serving::TfrtSavedModelFactory::EstimateResourceRequirement](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html#aa1451f446252c259f225722b9cd07aaf)
:::

::: {.ttdeci}
absl::Status EstimateResourceRequirement(const string &path,
ResourceAllocation \*estimate) const
:::

::: {.ttdef}
**Definition:** tfrt\_saved\_model\_factory.cc:164
:::
:::

::: {#aclasstensorflow_1_1serving_1_1TfrtSavedModelFactory_html_ad168a4902febebaa51745428a5da5f17 .ttc}
::: {.ttname}
[tensorflow::serving::TfrtSavedModelFactory::Create](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html#ad168a4902febebaa51745428a5da5f17)
:::

::: {.ttdeci}
static absl::Status Create(const TfrtSavedModelConfig &config,
std::unique\_ptr\< TfrtSavedModelFactory \> \*factory)
:::

::: {.ttdef}
**Definition:** tfrt\_saved\_model\_factory.cc:152
:::
:::

::: {#aclasstensorflow_1_1serving_1_1TfrtSavedModelFactory_html_affd90c58362c83fb9949bc9892201386 .ttc}
::: {.ttname}
[tensorflow::serving::TfrtSavedModelFactory::CreateTfrtSavedModelWithMetadata](classtensorflow_1_1serving_1_1TfrtSavedModelFactory.html#affd90c58362c83fb9949bc9892201386)
:::

::: {.ttdeci}
virtual absl::Status CreateTfrtSavedModelWithMetadata(const
Loader::Metadata &metadata, const string &path, std::unique\_ptr\<
Servable \> \*servable)
:::
:::

::: {#aclasstensorflow_1_1serving_1_1TfrtSavedModelServable_html .ttc}
::: {.ttname}
[tensorflow::serving::TfrtSavedModelServable](classtensorflow_1_1serving_1_1TfrtSavedModelServable.html)
:::

::: {.ttdef}
**Definition:** tfrt\_servable.h:56
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

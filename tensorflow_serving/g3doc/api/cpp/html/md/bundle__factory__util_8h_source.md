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
bundle\_factory\_util.h
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
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_BUNDLE\_FACTORY\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00017}[ 17]{.lineno} [\#define
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_BUNDLE\_FACTORY\_UTIL\_H\_]{.preprocessor}
:::

::: {.line}
[]{#l00018}[ 18]{.lineno} 
:::

::: {.line}
[]{#l00019}[ 19]{.lineno} [\#include
\"google/protobuf/wrappers.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00020}[ 20]{.lineno} [\#include
\"absl/types/optional.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00021}[ 21]{.lineno} [\#include
\"tensorflow/core/kernels/batching\_util/shared\_batch\_scheduler.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00022}[ 22]{.lineno} [\#include
\"tensorflow/core/lib/core/status.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00023}[ 23]{.lineno} [\#include
\"tensorflow/core/protobuf/config.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00024}[ 24]{.lineno} [\#include
\"tensorflow/core/public/session.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00025}[ 25]{.lineno} [\#include
\"tensorflow/core/public/session\_options.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00026}[ 26]{.lineno} [\#include
\"tensorflow\_serving/batching/batching\_session.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00027}[ 27]{.lineno} [\#include
\"tensorflow\_serving/resources/resources.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00028}[ 28]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/resource\_estimator.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00029}[ 29]{.lineno} [\#include
\"tensorflow\_serving/servables/tensorflow/session\_bundle\_config.pb.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00030}[ 30]{.lineno} [\#include
\"tensorflow\_serving/util/file\_probing\_env.h\"]{.preprocessor}
:::

::: {.line}
[]{#l00031}[ 31]{.lineno} 
:::

::: {.line}
[]{#l00032}[ 32]{.lineno} [namespace ]{.keyword}tensorflow {
:::

::: {.line}
[]{#l00033}[ 33]{.lineno} [namespace ]{.keyword}serving {
:::

::: {.line}
[]{#l00034}[ 34]{.lineno} 
:::

::: {.line}
[]{#l00035}[ 35]{.lineno} [// Returns SessionOptions based on the
SessionBundleConfig.]{.comment}
:::

::: {.line}
[]{#l00036}[ 36]{.lineno} [// TODO(b/32248363): add
SavedModelBundleConfig after we switch Model Server to]{.comment}
:::

::: {.line}
[]{#l00037}[ 37]{.lineno} [// Saved Model.]{.comment}
:::

::: {.line}
[]{#l00038}[ 38]{.lineno} SessionOptions
GetSessionOptions([const]{.keyword} SessionBundleConfig& config);
:::

::: {.line}
[]{#l00039}[ 39]{.lineno} 
:::

::: {.line}
[]{#l00040}[ 40]{.lineno} [// Returns RunOptions based on
SessionBundleConfig.]{.comment}
:::

::: {.line}
[]{#l00041}[ 41]{.lineno} [// TODO(b/32248363): add
SavedModelBundleConfig after we switch Model Server to]{.comment}
:::

::: {.line}
[]{#l00042}[ 42]{.lineno} [// Saved Model.]{.comment}
:::

::: {.line}
[]{#l00043}[ 43]{.lineno} RunOptions GetRunOptions([const]{.keyword}
SessionBundleConfig& config);
:::

::: {.line}
[]{#l00044}[ 44]{.lineno} 
:::

::: {.line}
[]{#l00045}[ 45]{.lineno} [// Get per-model batching parameters if they
are present.]{.comment}
:::

::: {.line}
[]{#l00046}[ 46]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00047}[ 47]{.lineno} [// When \`per\_model\_configured\` is true we
return model specific batching]{.comment}
:::

::: {.line}
[]{#l00048}[ 48]{.lineno} [// parameters from \`batching\_params.pbtxt\`
file in SavedModel dir under \`path\`]{.comment}
:::

::: {.line}
[]{#l00049}[ 49]{.lineno} [// if one exists. If
\`per\_model\_configured\` is false we return
\`common\_params\`.]{.comment}
:::

::: {.line}
[]{#l00050}[ 50]{.lineno} [// Failure to parse model specific params
will return error.]{.comment}
:::

::: {.line}
[]{#l00051}[ 51]{.lineno} Status
GetPerModelBatchingParams([const]{.keyword} [string]{.keywordtype}&
path,
:::

::: {.line}
[]{#l00052}[ 52]{.lineno}  [const]{.keyword} BatchingParameters&
common\_params,
:::

::: {.line}
[]{#l00053}[ 53]{.lineno}  [bool]{.keywordtype} per\_model\_configured,
:::

::: {.line}
[]{#l00054}[ 54]{.lineno}  absl::optional\<BatchingParameters\>\*
params);
:::

::: {.line}
[]{#l00055}[ 55]{.lineno} 
:::

::: {.line}
[]{#l00056}[ 56]{.lineno} [// Creates a BatchScheduler based on the
batching configuration.]{.comment}
:::

::: {.line}
[]{#l00057}[ 57]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00058}[ 58]{.lineno} Status CreateBatchScheduler(
:::

::: {.line}
[]{#l00059}[ 59]{.lineno}  [const]{.keyword} BatchingParameters&
batching\_config,
:::

::: {.line}
[]{#l00060}[ 60]{.lineno} 
std::shared\_ptr\<SharedBatchScheduler\<TaskType\>\>\* batch\_scheduler)
{
:::

::: {.line}
[]{#l00061}[ 61]{.lineno}  [typename]{.keyword}
SharedBatchScheduler\<TaskType\>::Options options;
:::

::: {.line}
[]{#l00062}[ 62]{.lineno}  [if]{.keywordflow}
(batching\_config.has\_num\_batch\_threads()) {
:::

::: {.line}
[]{#l00063}[ 63]{.lineno}  options.num\_batch\_threads =
batching\_config.num\_batch\_threads().value();
:::

::: {.line}
[]{#l00064}[ 64]{.lineno}  }
:::

::: {.line}
[]{#l00065}[ 65]{.lineno}  [if]{.keywordflow}
(batching\_config.has\_thread\_pool\_name()) {
:::

::: {.line}
[]{#l00066}[ 66]{.lineno}  options.thread\_pool\_name =
batching\_config.thread\_pool\_name().value();
:::

::: {.line}
[]{#l00067}[ 67]{.lineno}  }
:::

::: {.line}
[]{#l00068}[ 68]{.lineno}  [return]{.keywordflow}
SharedBatchScheduler\<TaskType\>::Create(options, batch\_scheduler);
:::

::: {.line}
[]{#l00069}[ 69]{.lineno} }
:::

::: {.line}
[]{#l00070}[ 70]{.lineno} 
:::

::: {.line}
[]{#l00071}[ 71]{.lineno} [// Estimates the resources a session bundle
or saved model bundle will use once]{.comment}
:::

::: {.line}
[]{#l00072}[ 72]{.lineno} [// loaded, from infra validation.]{.comment}
:::

::: {.line}
[]{#l00073}[ 73]{.lineno} Status
EstimateResourceFromValidationResult([const]{.keyword}
[string]{.keywordtype}& path,
:::

::: {.line}
[]{#l00074}[ 74]{.lineno}  ResourceAllocation\* estimate);
:::

::: {.line}
[]{#l00075}[ 75]{.lineno} 
:::

::: {.line}
[]{#l00076}[ 76]{.lineno} [// Estimates the resources a session bundle
or saved model bundle will use once]{.comment}
:::

::: {.line}
[]{#l00077}[ 77]{.lineno} [// loaded, from its export or saved model
path. tensorflow::Env::Default() will]{.comment}
:::

::: {.line}
[]{#l00078}[ 78]{.lineno} [// be used to access the file
system.]{.comment}
:::

::: {.line}
[]{#l00079}[ 79]{.lineno} [//]{.comment}
:::

::: {.line}
[]{#l00080}[ 80]{.lineno} [// If use\_validation\_result = true, tries
to use the result from infra validtion]{.comment}
:::

::: {.line}
[]{#l00081}[ 81]{.lineno} [// first. Otherwise, uses the following crude
heuristic: estimated main-memory]{.comment}
:::

::: {.line}
[]{#l00082}[ 82]{.lineno} [// RAM = (combined size of all exported
file(s)) \*]{.comment}
:::

::: {.line}
[]{#l00083}[ 83]{.lineno} [// kResourceEstimateRAMMultiplier +
kResourceEstimateRAMPadBytes.]{.comment}
:::

::: {.line}
[]{#l00084}[ 84]{.lineno} [// TODO(b/27694447): Improve the heuristic.
At a minimum, account for GPU RAM.]{.comment}
:::

::: {.line}
[]{#l00085}[ 85]{.lineno} Status
EstimateResourceFromPath([const]{.keyword} [string]{.keywordtype}& path,
[bool]{.keywordtype} use\_validation\_result,
:::

::: {.line}
[]{#l00086}[ 86]{.lineno}  ResourceAllocation\* estimate);
:::

::: {.line}
[]{#l00087}[ 87]{.lineno} 
:::

::: {.line}
[]{#l00088}[ 88]{.lineno} [// Wraps a session in a new session that
automatically batches Run() calls.]{.comment}
:::

::: {.line}
[]{#l00089}[ 89]{.lineno} Status WrapSessionForBatching(
:::

::: {.line}
[]{#l00090}[ 90]{.lineno}  [const]{.keyword} BatchingParameters&
batching\_config,
:::

::: {.line}
[]{#l00091}[ 91]{.lineno} 
std::shared\_ptr\<SharedBatchScheduler\<BatchingSessionTask\>\>
batch\_scheduler,
:::

::: {.line}
[]{#l00092}[ 92]{.lineno}  [const]{.keyword}
std::vector\<SignatureDef\>& signatures,
:::

::: {.line}
[]{#l00093}[ 93]{.lineno}  std::unique\_ptr\<Session\>\* session);
:::

::: {.line}
[]{#l00094}[ 94]{.lineno} 
:::

::: {.line}
[]{#l00095}[ 95]{.lineno} [// Wraps a session in a new session that only
supports Run() without batching.]{.comment}
:::

::: {.line}
[]{#l00096}[ 96]{.lineno} Status
WrapSession(std::unique\_ptr\<Session\>\* session);
:::

::: {.line}
[]{#l00097}[ 97]{.lineno} 
:::

::: {.line}
[]{#l00098}[ 98]{.lineno} [// Wraps a session in a new session that only
supports Run() without threading]{.comment}
:::

::: {.line}
[]{#l00099}[ 99]{.lineno} [// parameters.]{.comment}
:::

::: {.line}
[]{#l00100}[ 100]{.lineno} Status
WrapSessionIgnoreThreadPoolOptions(std::unique\_ptr\<Session\>\*
session);
:::

::: {.line}
[]{#l00101}[ 101]{.lineno} 
:::

::: {.line}
[]{#l00102}[ 102]{.lineno} [// Construct Queue Options from
BatchingParameters.]{.comment}
:::

::: {.line}
[]{#l00103}[ 103]{.lineno} [template]{.keyword} \<[typename]{.keyword}
TaskType\>
:::

::: {.line}
[]{#l00104}[ 104]{.lineno} [typename]{.keyword}
SharedBatchScheduler\<TaskType\>::QueueOptions GetQueueOptions(
:::

::: {.line}
[]{#l00105}[ 105]{.lineno}  [const]{.keyword} BatchingParameters&
batching\_config,
:::

::: {.line}
[]{#l00106}[ 106]{.lineno} 
std::function\<Status(std::unique\_ptr\<TaskType\>\* input\_task,
:::

::: {.line}
[]{#l00107}[ 107]{.lineno}  [int]{.keywordtype}
first\_output\_task\_size, [int]{.keywordtype}
input\_batch\_size\_limit,
:::

::: {.line}
[]{#l00108}[ 108]{.lineno} 
std::vector\<std::unique\_ptr\<TaskType\>\>\* output\_tasks)\>
:::

::: {.line}
[]{#l00109}[ 109]{.lineno}  split\_input\_task\_func) {
:::

::: {.line}
[]{#l00110}[ 110]{.lineno}  [typename]{.keyword}
SharedBatchScheduler\<TaskType\>::QueueOptions queue\_options;
:::

::: {.line}
[]{#l00111}[ 111]{.lineno}  [if]{.keywordflow}
(batching\_config.has\_max\_batch\_size()) {
:::

::: {.line}
[]{#l00112}[ 112]{.lineno}  queue\_options.input\_batch\_size\_limit =
:::

::: {.line}
[]{#l00113}[ 113]{.lineno}  batching\_config.max\_batch\_size().value();
:::

::: {.line}
[]{#l00114}[ 114]{.lineno}  }
:::

::: {.line}
[]{#l00115}[ 115]{.lineno}  [if]{.keywordflow}
(batching\_config.has\_batch\_timeout\_micros()) {
:::

::: {.line}
[]{#l00116}[ 116]{.lineno}  queue\_options.batch\_timeout\_micros =
:::

::: {.line}
[]{#l00117}[ 117]{.lineno} 
batching\_config.batch\_timeout\_micros().value();
:::

::: {.line}
[]{#l00118}[ 118]{.lineno}  }
:::

::: {.line}
[]{#l00119}[ 119]{.lineno}  [if]{.keywordflow}
(batching\_config.has\_max\_enqueued\_batches()) {
:::

::: {.line}
[]{#l00120}[ 120]{.lineno}  queue\_options.max\_enqueued\_batches =
:::

::: {.line}
[]{#l00121}[ 121]{.lineno} 
batching\_config.max\_enqueued\_batches().value();
:::

::: {.line}
[]{#l00122}[ 122]{.lineno}  }
:::

::: {.line}
[]{#l00123}[ 123]{.lineno}  [if]{.keywordflow}
(batching\_config.has\_enable\_large\_batch\_splitting() &&
:::

::: {.line}
[]{#l00124}[ 124]{.lineno} 
batching\_config.enable\_large\_batch\_splitting().value()) {
:::

::: {.line}
[]{#l00125}[ 125]{.lineno} 
queue\_options.enable\_large\_batch\_splitting = [true]{.keyword};
:::

::: {.line}
[]{#l00126}[ 126]{.lineno} 
:::

::: {.line}
[]{#l00127}[ 127]{.lineno}  [if]{.keywordflow}
(batching\_config.has\_max\_execution\_batch\_size()) {
:::

::: {.line}
[]{#l00128}[ 128]{.lineno}  queue\_options.max\_execution\_batch\_size =
:::

::: {.line}
[]{#l00129}[ 129]{.lineno} 
batching\_config.max\_execution\_batch\_size().value();
:::

::: {.line}
[]{#l00130}[ 130]{.lineno}  } [else]{.keywordflow} {
:::

::: {.line}
[]{#l00131}[ 131]{.lineno}  queue\_options.max\_execution\_batch\_size =
:::

::: {.line}
[]{#l00132}[ 132]{.lineno}  batching\_config.max\_batch\_size().value();
:::

::: {.line}
[]{#l00133}[ 133]{.lineno}  }
:::

::: {.line}
[]{#l00134}[ 134]{.lineno} 
:::

::: {.line}
[]{#l00135}[ 135]{.lineno}  queue\_options.split\_input\_task\_func =
split\_input\_task\_func;
:::

::: {.line}
[]{#l00136}[ 136]{.lineno}  }
:::

::: {.line}
[]{#l00137}[ 137]{.lineno}  [return]{.keywordflow} queue\_options;
:::

::: {.line}
[]{#l00138}[ 138]{.lineno} }
:::

::: {.line}
[]{#l00139}[ 139]{.lineno} 
:::

::: {.line}
[]{#l00140}[ 140]{.lineno} } [// namespace serving]{.comment}
:::

::: {.line}
[]{#l00141}[ 141]{.lineno} } [// namespace tensorflow]{.comment}
:::

::: {.line}
[]{#l00142}[ 142]{.lineno} 
:::

::: {.line}
[]{#l00143}[ 143]{.lineno} [\#endif ]{.preprocessor}[//
TENSORFLOW\_SERVING\_SERVABLES\_TENSORFLOW\_BUNDLE\_FACTORY\_UTIL\_H\_]{.comment}
:::
:::
:::

------------------------------------------------------------------------

[Generated by [![doxygen](doxygen.svg){.footer width="104"
height="31"}](https://www.doxygen.org/index.html) 1.9.1]{.small}
